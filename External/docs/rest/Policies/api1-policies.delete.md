# Delete Policy by Service

**DELETE /ps/v1/policies**

## Description

Deletes a policy by service offer type per tenant.

## Headers

TenantId (**REQUIRED**)
Available values : application/json

serviceOfferName (**REQUIRED**)
Available values : TDX, SGX

## Responses: 
| Code         | Description                             |
| :----------- | :-----------                            |
| 204          | Successfully deleted the policy.        |
| 400          | Bad request.                            |
| 500          | Internal server error.                  |

# Delete Policy

**DELETE/ps/v1/policies/{policy_id}**

# Description

Deletes a policy

## Headers

policy_id (**REQUIRED**)
Available values : policy_id

TenantId (**REQUIRED**)
Available values : TenantId

## Responses: 
| Code         | Description                             |
| :----------- | :-----------                            |
| 204          | Successfully deleted the policy.        |
| 400          | Bad request.                            |
| 500          | Internal server error.                  |
