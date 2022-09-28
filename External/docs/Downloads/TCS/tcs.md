# TEE Cache System (TCS)
 The Trust Execution Environment Cache System (TCS) stores information from your Process Control Solution (PSC) locally so it can be processed at a later date. This allows you system Administartor to schedule when certain systems or networks are available to the internet without having to process the information at the same time. This allows administrator to have greater control over the processes on their system.
 
Amber provides a secure environment to process informaiton. When combined with Amber, TCS becomes a very secure environment to process data. Follow these instructions to set up TCS binaries for Amber.

## Prerequisites
Complete these tasks before building the TCS.
- Install version 1.18.6 of Go (https://go.dev/dl/) on the build machine.

- Install versaion 11 of [Postgres db] (https://www.postgresql.org/download/). Create a username and a set a password.

## Build Binaries for TCS
Follow these instructions to build TCS binaries.
1. Clone the repository for which you want to create the TCS https://github.com/intel-innersource/applications.security.amber.core-services.git -b release/v0.3.0.
2. Change the working directory to the TCS folder of the cloned repository:<br>
`cd tee-caching-service/`<br>
`make bin`
3. Export the following variables before installation: <br>
   `export TCS_DB_USER=<tcs-db-user-name from pre-req> `<br>
   `export TCS_DB_NAME=<tcs-db-password> `<br>
   `export TCS_DB_PASSWORD=<tcs-db-password> `<br>
   `export TCS_ENABLE_TLS=true  #accept true/false `<br>
   `export TCS_DB_PORT=5432 `<br>
   `export TCS_DB_HOST=<tcs-db-hosts> `<br>
   `export SGX_PROV_CERT_SERVER_API_KEY=<PCCS_SERVER_KEY> `<br>
   `export SGX_PROV_CERT_SERVER_URL=<PCCS URL> `

 **Note:** Sample PCCS example: https://api.trustedservices.intel.com/sgx/certification/v3 

 4. Step 2 generates the binary of the TCS. Use the follow commad to run the TCS installer in the background. <br>
 `./tcs&`

 5. Check the TCS logs by running the following command: <br>
 `journalctl -u -f tcs`

 6. Kill the TCS instance by running the following command: <br>
 `ps -ef | grep "tcs"` <br>
 `kill -9 <pid>`