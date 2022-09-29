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

**DELETE /ps/v1/policies/{policy_id}**

## Description

Deletes a policy.

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


# Delete Subscription

**DELETE /tms/v1/tenants/{tenant_id}/services/{service_id}/subscriptions/{subscription_id}**

## Description

Deletes a subscription.

## Headers

tenant_id (**REQUIRED**)
Available values : tenant_id

service_id (**REQUIRED**)
Available values : service_id

subscription_id (**REQUIRED**)
Available values : subscription_id

## Responses: 

| Code         | Description                                              |
| :----------- | :-----------                                             |
| 200          | Successfully deleted the subscription.                   |
| 404          | No subscription with the provided subscription ID found. |
| 500          | Internal server error.                                   |

# Delete User from Tenant

**DELETE /tms/v1/tenants/{tenant_id}/users/{user_id}**

## Description

Deletes the user from the tenant. Unless the user is part of the tenant, the user record will also be deleted.

## Headers

tenant_id (**REQUIRED**)
Available values : tenant_id

user_id (**REQUIRED**)
Available values : user_id

## Responses: 

| Code         | Description                                              |
| :----------- | :-----------                                             |
| 200          | Successfully deleted the user from the tenant.           |
| 404          | No user with the provided user ID found.                 |
| 500          | Internal server error.                                   |

