# CLI Examples
apploications.security.amber.cli is the command line interface tool used by tenants to access Amber services. 

## Supported OS
Ubuntu LTS 20.01 is the only supported operating system.

## Commands
The following sections list the commands included in apploications.security.amber.cli.

## Build
1. git clone https://github.com/intel-innersource/applications.security.amber.cli.git cli
2. cd cli and run "make installer"
3. copy the binary installer tenantctl-{version}.bin to the system where it needs to be deployed
4. create an env file tac.env and add the following mandatory contents:
5. a. AMBER_BASE_URL=< URL of API Gateway >
6. b. TENANT_ID="< Id of the Tenant >" (The Tenant Id can be overridden from CLI)
7. run "./tenantctl-{version}.bin". This will install the CLI to your system.
8. use the CLI: tenantctl < command > < resource >

**Note:** If behind a proxy, add the Amber FQDN to NO_PROXY environment variable.
## Uninstall
Use the following command to uninstall the tenant CLI. 
- run "tenantctl uninstall"

## Setup configuration
- tenantctl config -v < env file path >

## Bash completion
- tenantctl version

## Command usage examples 
- **Create User** tenantctl create user -a < api key > -e < email Id> -r < Role (Tenant Admin/User) >
- **Get Users** tenantctl list user -a < api key >
- **Get User by id** tenantctl list user -a < api key > -u < user id >
- **Update User** tenantctl update user -a < api key > -u < user id >
- **Update User Role** tenantctl update user role -a < api key > -u < user id > -r "Tenant Admin,User"
- **Delte User** tenantctl delete user -a < api key > -u < user id >
- **Get Service Offers** tenantctl list serviceOffer -a < api key >
- **Get Products** tenantctl list product -a < api key > -r < service offer id >
- **Create Service** tenantctl create service -a < api key > -r < service offer id > -n < service name >
- **Get Services** tenantctl list service -a < api key >
- **Delte Service** tenantctl delete service -a < api key > -s < service id >
- **Update Service** tenantctl update service -a < api key > -s < service id > -n < service name >
- **Create Subscription** tenantctl create subscription -a < api key > -r < service offer id > -p < product id > -d < subscription name > -i "comma separated policy Ids" -v "tag-id1:tag-name1,tag-id2:tag-name2"
- **Updatea Subscription** tenantctl update subscription -a < api key > -r < service offer id > -p < product id > -u < subscription id > -d < subscription name > -i "comma separated policy Ids" -v "tag-id1:tag-name1,tag-id2:tag-name2" -s < active/inactive >
- **Get Subscription** tenantctl list subscription -a < api key > -r < service offer id >
- **Get Subscriptions** tenantctl list subscription -a < api key > -r < service offer id > -d < subscription id >
- **Delete a Subsciption** tenantctl delete subscription -a < api key > -r < service offer id > -d < subscription id >
- **Create Tag** tenantctl create tag -a < api key > -n < tag name > -t < tenant Id >
- **List Tags** tenantctl list tag -a < api key >
- **List Subscription Policies** tenantctl list subscription policy -a < api key > -r < service offer id > -s < subscription id >
- **List Subscibtion Tags** tenantctl list subscription tag -a < api key > -r < service offer id > -s < subscription id >
- **Create Policy** tenantctl create policy -a < api key > -f < policy file path ><br>
Sample policy for policy create command:<br>

```
{
    "policy": "default matches_sgx_policy = false \n\n matches_sgx_policy = true { \n input.amber_sgx_is_debuggable == false \n input.amber_sgx_isvsvn == 0 \n input.amber_sgx_isvprodid == 0 \n input.amber_sgx_mrsigner ==  \"d412a4f07ef83892a5915fb2ab584be31e186e5a4f95ab5f6950fd4eb8694d7b\" \n  \n input.amber_sgx_mrenclave == \"bab91f200038076ac25f87de0ca67472443c2ebe17ed9ba95314e609038f51ab\" \n }",</br>
   "user_id": "f04971b7-fb41-4a9e-a06e-4bf6e71f98b3",
   "policy_name": "Sample_Policy_SGX",
   "policy_type": "Appraisal policy",
   "service_offer_name": "SGX Attestation",
   "service_offer_id": "b04971b7-fb41-4a9e-a06e-4bf6e71f98bd"
}
```
- **Get Policies** tenantctl list policies -a < api key >
- **Get policy id** tenantctl list policies -a < api key > -p < policy id >
- **Update policy** tenantctl delete policy -a < api key > -p < policy id >
    - Sample policy for policy update command
```
{
"policy_id": "e48dabc5-9608-4ff3-aaed-f25909ab9de1",
"policy": "default matches_sgx_policy = false \n\n matches_sgx_policy = true { \n  input.amber_sgx_is_debuggable == false \n input.amber_sgx_isvsvn == 0 \n input. amber_sgx_isvprodid == 0 \n input.amber_sgx_mrsigner ==   \"d412a4f07ef83892a5915fb2ab584be31e186e5a4f95ab5f6950fd4eb8694d7b\" \n  \n input. amber_sgx_mrenclave ==  \"bab91f200038076ac25f87de0ca67472443c2ebe17ed9ba95314e609038f51ab\" \n }",
"user_id": "f04971b7-fb41-4a9e-a06e-4bf6e71f98b3",
"policy_name": "Sample_Policy_SGX",
"policy_type": "Appraisal policy",
"service_offer_name": "SGX Attestation",
"service_offer_id": "b04971b7-fb41-4a9e-a06e-4bf6e71f98bd"
}
```