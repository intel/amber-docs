# Gramine Integration

Follow these instructions to prepare your software stack to retrieve an attestation token from project Amber servcies through patched Gramine-SGX. 


1. Deploy system components on SGX2 enabled platform. <br>
[System Requirements for Customer PoCs] (https://wiki.ith.intel.com/display/DCGSecurity/System+Requirements+for+Customer+PoCs)<br>

   **Note:** In case of Azure VM, please install az-dcap-client  package as well 

2. Register on Intel PCS if your the platform owner (not for CSP tenant) <br>
https://api.portal.trustedservices.intel.com/ <br>
and configure PCCS with provisioned API key 
3. Install all required packages for Gramine-SGX build and run <br>
   - For GSC - https://gramine.readthedocs.io/projects/gsc/en/latest/index.html?highlight=gsc 
   - For non-GSC - https://gramine.readthedocs.io/en/stable/devel/building.html  
4. Build Amber-Gramine-SGX <br>
   - PR URL: https://github.com/gramineproject/gramine/pull/828 (on v1.2) 
   - Patch source branch: https://github.com/bigdata-memory/gramine/tree/amber_pr (on v1.2) 
   - https://gramine.readthedocs.io/projects/gsc/en/latest/index.html?highlight=gsc#gsc-build-gramine-build-gramine-only-docker-image (for GSC) 
   - The Repository  option needs to point to the patch source URL with no Branch  specified 
   - https://gramine.readthedocs.io/en/stable/devel/building.html#id2 (for non-GSC) 
Clone the patched codebase instead of the upstream one and build.
5. General configuration of Gramine-SGX WLs 
   - https://gramine.readthedocs.io/projects/gsc/en/latest/index.html?highlight=gsc#configuration (for GSC) 
   - https://gramine.readthedocs.io/en/stable/manifest-syntax.html (for non-GSC) 
6. Special configuration for Amber integration <br>
   - https://github.com/bigdata-memory/gramine/tree/amber_pr/CI-Examples/amber 
7. Provide the static IP address to project Amber team for configuration 
   ```
   $ curl ipinfo.io/ip 
   ```
8. Once get approved, Amber-Gramine-SGX WLs is able to retrieve the Amber token for its running SGX enclave by reading a file
<br> `/dev/amber/token` <br>
https://github.com/bigdata-memory/gramine/blob/220eccbb31a29c1d8f9b18d8890868b197635a00/CI-Examples/amber/src/app.c#L75 

