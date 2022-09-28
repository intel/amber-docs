# Key Broker Servcie - Amber
The Key Broker Service enables key distribution using TEE Attestation or Platform Attestation to authorize key transfers. By retaining decryption keys, unauthorized access can be prevented, even from within the Cloud Service Provider.

The Key Broker Service provides and retains encryption/decryption keys for virtual machine/container images/AI models. The entity launch intended to launch the encrypted workload or an AI model, will request for a key either using the Amber attestation token or the TEE(Trusted Execution Environment) quote which can be verified by the Amber Attestation Service. The released decryption keys will be wrapped with the secret wrapping key created by KBS, which is in turn wrapped with the user public key provided in the attestation token or with the TEE quote. 
The KBS in the backend can be plugged into a KMIP KMS i.e. The Key Broker Service connects to a backend 3rd Party KMIP-compliant key management service for key creation and vaulting services.

## KBS Use cases
The Key Broker Service (KBS) plays the role of relying party in TEE attestation. It provides following functionalities:
- manages the policies associated with a key
- provide the interface to support key request/transfer in two situations
    - Background check mode - Key request URL, without an attestation token.
    - Passport mode - A POST request to the Key request URL with attestation token in the request body.

![Key Broker Service](/docs/images/KBS.png)

## Background Verification Mode
The KBS in background mode sends a challenge/nonce to the requestor for TEE quote, based on the policy associated with the key identifier. If the key policy associated with the key specifies a particular TEE (SGX or TDX) attestation, KBS sends a request to the Amber Attestation Service to get the challenge/nonce. 
The challenge/nonce that the KBS sends to the requestor is retrieved from the Amber Attestation Service. Therefore, when KBS receives a request, it calls for the Amber API to initiate an attestation request, and receives the challenge/nonce, and response to the requestor with the same challenge/nonce.

## Passport Verification Mode
In this flow, an TEE agent or the KBS client can make an attestation request to the Amber Attestation Service directly and get an attestation token. Then, use the token to call the KBS key transfer API to request for the key.

KBS will verify the legitimacy of the attestation token and whether it complies with the key policy associated with the key id. If it complies, the requested key will be issued.

## Installation Guide
The Key Broker Service can be run as a VM or as a bare-metal server.
### Supported Operating Systems:
•	Ubuntu 20.04
•	RHEL8.3

### Steps to Setup KBS
1. Download the bin installer from <Download link to be inserted here>
2. Copy the KBS binary to /root/ directory
3. Create kbs.env file with all the configuration variables required to setup KBS

|Variable               |Description                              |
|-----------------------|-----------------------------------------|
| AS_BASE_URL           | Amber Attestation Service Base URL      |
| AS_API_KEY            | Amber Attestation Service API key       |
| LOG_LEVEL             | Log level                               |
| KEY_MANAGER           | Backend KMS                             |
| KMIP_SERVER_IP        | IP of KMIP server                       |
| KMIP_SERVER_PORT      | PORT of KMIP server                     |
| KMIP_HOSTNAME         | HOSTNAME of KMIP server                 |
| KMIP_VERSION          | VERSION of KMIP server                  |
| KMIP_USERNAME         | USERNAME of KMIP server                 |
| KMIP_PASSWORD         | PASSWORD of KMIP server                 |
| KMIP_CLIENT_CERT_PATH | KMIP Client certificate path            |
| KMIP_CLIENT_KEY_PATH  | KMIP Client key path                    |
| KMIP_ROOT_CERT_PATH   | KMIP Root Certificate path              |
| SERVICE_PORT          | The Port on which KBS Server Listens to |
| ADMIN_USERNAME        | KBS admin username                      |
| ADMIN_PASSWORD        | KBS admin password                      |
| SAN_LIST              | KBS host SAN list                       |

4. Run the installer (KBS must be installed by a privileged user)
5. Copy the token signing certificate from Amber to /etc/kbs/certs/trustedjwt/<br>
   The attestation token signing key is retrieved from the fv-controller.
6. Copy ats.cert from fv-controller collaterals to /etc/kbs/certs/trustedjwt/ats.pem
7. Copy the trusted CA Certificate from Amber to /etc/kbs/certs/trustedca/
8. Restart KBS for the copied certificates to be reflected in config using the following commands:
    - kbs stop
    - kbs start

