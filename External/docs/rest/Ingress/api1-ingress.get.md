# Search Policy

**GET ps/v1/policies**

## Description

A policy is a set of measurements and metadata organized in a flexible format that allows for ease of further extension. The measurements included in the policy pertain to various hardware and feature categories, and their respective metadata sections provide descriptive information.

Searches for relevant policies and returns the signed policy collection consisting of all the associated policies.
Returns - The serialized Signed Policy Collection Go struct object that was retrieved.

## Headers

policyName (**REQUIRED**)
Available values : policyName

serviceOfferName (**REQUIRED**)
Available values : TDX, SGX

policyType (**REQUIRED**)
Available values : Appraisal, Token Customization

Accept (**REQUIRED**)
Available values : application/json

TenantId (**REQUIRED**)
Available values : TenantId

## Sample Call

```json
[
  {
  "created_time": "2022-09-09T17:39:32.815Z",
  "creator_id": [
    0
  ],
  "deleted": true,
  "modified_time": "2022-09-09T17:39:32.815Z",
  "policy": "string",
  "policy_hash": "string",
  "policy_id": [
    0
  ],
  "policy_name": "string",
  "policy_signature": "string",
  "policy_type": "string",
  "service_offer_id": [
    0
  ],
  "service_offer_name": "string",
  "updater_id": [
    0
  ]
}
]
```
## Responses

| Code         | Description                                                        |
| :----------- | :-----------                                                       |
| 200          | Successfully searched and returned a signed policy collection.     |
| 400          | Invalid search criteria provided.                                  |
| 415          | Invalid Accept Header in Request.                                  |
| 500          | Internal server error.                                             |

# Retrieve policy

**GET /ps/v1/policies/{policy_id}**

## Description

Retrieves a policy. Returns - The serialized Signed Policy Go struct object that was retrieved.

## Headers

policy_id (**REQUIRED**)
Available values : policy_id

Accept (**REQUIRED**)
Available values : application/json

TenantId (**REQUIRED**)
Available values : TenantId

## Sample Call

```json
{
  "created_time": "2022-09-09T17:39:32.824Z",
  "creator_id": [
    0
  ],
  "deleted": true,
  "modified_time": "2022-09-09T17:39:32.824Z",
  "policy": "string",
  "policy_hash": "string",
  "policy_id": [
    0
  ],
  "policy_name": "string",
  "policy_signature": "string",
  "policy_type": "string",
  "service_offer_id": [
    0
  ],
  "service_offer_name": "string",
  "updater_id": [
    0
  ]
  }
  ```

## Responses

| Code         | Description                            |
| :----------- | :-----------                           |
| 200          | Successfully retrieved the policy.     |
| 400          | Bad request.                           |
| 415          | Invalid Accept Header in Request.      |
| 500          | Internal server error.                 |

# Get Version

**GET /ps/v1/version**

## Description

GetVersion is used to get the version of the application. Returns - The version of the application.

## Responses

| Code         | Description                             |
| :----------- | :-----------                            |
| 200          | Successfully retrieved the version.     |

# Search Service Offers

**GET /tms/v1/serviceOffers**

## Description

Searches ServiceOffers. Returns - An array of serviceOffers that exist in the system.

## Headers

id (**REQUIRED**)
Available values : id

## Sample Call

```json
{
  "id": [
    0
  ],
  "name": "string"
  }
  ```

## Responses

| Code         | Description                                                      |
| :----------- | :-----------                                                     |
| 200          | Successfully retrieved the serviceOffers that match criteria.    |
| 404          | No serviceOffer with the provided serviceOffer ID found.         |
| 415          | Invalid Accept Header in Request.                                |
| 500          | Internal server error.                                           |

# Retreieves a serviceOffer

**GET /tms/v1/serviceOffers/{serviceOffer_id}**

## Description

Retrieves a serviceOffer. Returns - The serialized Signed ServiceOffer Go struct object that was retrieved.

## Headers

serviceOffer_id (**REQUIRED**)
Available values : serviceOffer_id

## Sample Call

```json
{
  "id": [
    0
  ],
  "name": "string"
  }
  ```


## Responses

| Code         | Description                                                      |
| :----------- | :-----------                                                     |
| 200          | Successfully retrieved the serviceOffer.                         |
| 404          | No serviceOffer with the provided serviceOffer ID found.         |
| 415          | Invalid Accept Header in Request.                                |
| 500          | Internal server error.                                           |

# Search Products

**GET /tms/v1/serviceOffers/{serviceOffer_id}/products**

## Description

Searches Products. Returns - An array of products that exist in the system.

## Headers

serviceOffer_id (**REQUIRED**)
Available values : serviceOffer_id

id (**REQUIRED**)
Available values : id

## Sample Call

```json
{
  "id": [
    0
  ],
  "name": "string",
  "policy": {
    "limit": 0,
    "limit_renewal_period": 0,
    "quota": 0,
    "quota_renewal_period": 0
  },
  "service_offer_id": [
    0
  ]
  }
  ```

## Responses


| Code         | Description                                              |
| :----------- | :-----------                                             |
| 200          | Successfully retrieved the products that match criteria. |
| 404          | No product with the provided product ID found.           |
| 415          | Invalid Accept Header in Request.                        |
| 500          | Internal server error.                                   |

# Retrieve Product

**GET /tms/v1/serviceOffers/{serviceOffer_id}/products/{product_id}**

## Description

Retrieves a product. Returns - The serialized Signed Product Go struct object that was retrieved.

## Headers

serviceOffer_id (**REQUIRED**)
Available values : serviceOffer_id

product_id (**REQUIRED**)
Available values : product_id

## Sample Call

```json
{
  "id": [
    0
  ],
  "name": "string",
  "policy": {
    "limit": 0,
    "limit_renewal_period": 0,
    "quota": 0,
    "quota_renewal_period": 0
  },
  "service_offer_id": [
    0
  ]
}
```

## Responses

| Code         | Description                                            |
| :----------- | :-----------                                           |
| 200          | Successfully retrieved the product.                    |
| 404          | No product with the provided product ID found.         |
| 415          | Invalid Accept Header in Request.                      |
| 500          | Internal server error.                                 |

# Retrieve Tenant

**GET /tms/v1/tenants/{tenant_id}**

## Description

Retrieves a tenant. Returns - The serialized Tenant Go struct object that was retrieved.

## Headers

tenant_id (**REQUIRED**)
Available values : tenant_id

Accept (**REQUIRED**)
Available values : application/json

## Sample Call

```json                                                 
{
  "address": "string",
  "company": "string",
  "email": "string",
  "id": [
    0
  ],
  "name": "string",
  "parent_id": [
    0
  ]
}
```
## Responses

| Code         | Description                                            |
| :----------- | :-----------                                           |
| 200          | Successfully retrieved the tenant.                     |
| 404          | No product with the provided product ID found.         |
| 415          | Invalid Accept Header in Request.                      |
| 500          | Internal server error.                                 |

# Search Services

**GET /tms/v1/tenants/{tenant_id}/services**

## Description

Searches Services. Returns - An array of services that exist in the system.

## Headers

tenant_id (**REQUIRED**)
Available values : tenant_id

id (**REQUIRED**)
Available values : id

## Sample Call

## Responses

```json
{
  "created_at": "2022-09-09T20:54:01.027Z",
  "description": "string",
  "id": [
    0
  ],
  "service_offer_id": [
    0
  ],
  "tenant_id": [
    0
  ]
}
```

| Code         | Description                                              |
| :----------- | :-----------                                             |
| 200          | Successfully retrieved the services that match criteria. |
| 404          | No product with the provided product ID found.           |
| 415          | Invalid Accept Header in Request.                        |
| 500          | Internal server error.                                   |

# Retrieve Service

**GET /tms/v1/tenants/{tenant_id}/services/{service_id}**

## Description

Retrieves a service. Returns - The serialized Signed Service Go struct object that was retrieved.

## Headers

tenant_id (**REQUIRED**)
Available values : tenant_id

service_id (**REQUIRED**)
Available values : service_id

## Sample Call

```json
{
  "created_at": "2022-09-09T21:07:50.332Z",
  "description": "string",
  "id": [
    0
  ],
  "service_offer_id": [
    0
  ],
  "tenant_id": [
    0
  ]
}
```

## Responses

| Code         | Description                                            |
| :----------- | :-----------                                           |
| 200          | Successfully retrieved the service.                    |
| 404          | No service with the provided service ID found.         |
| 415          | Invalid Accept Header in Request.                      |
| 500          | Internal server error.                                 |

# Search Subscriptions

**GET /tms/v1/tenants/{tenant_id}/services/{service_id}/subscriptions**

## Description

Searches Subscriptions. Returns - An array of subscriptions that exist in the system

## Headers

tenant_id (**REQUIRED**)
Available values : tenant_id

service_id (**REQUIRED**)
Available values : service_id

id (**REQUIRED**)
Available values : id

## Sample Call

```json                                                   
{
  "created_at": "2022-09-09T22:46:14.438Z",
  "description": "string",
  "expired_at": "2022-09-09T22:46:14.439Z",
  "id": [
    0
  ],
  "product_id": [
    0
  ],
  "product_name": "string",
  "service_id": [
    0
  ],
  "status": "string"
}
```

## Responses

| Code         | Description                                                  |
| :----------- | :-----------                                                 |
| 200          | Successfully retrieved the subscriptions that match criteria.|
| 404          | No subscription with the provided subscription ID found.     |
| 415          | Invalid Accept Header in Request.                            |
| 500          | Internal server error.                                       |

# Retrieve Subscriptions

**GET /tms/v1/tenants/{tenant_id}/services/{service_id}/subscriptions/{subscription_id}**

## Description

Retrieves a subscription. Returns - The serialized Signed Subscription Go struct object that was retrieved.

## Headers

tenant_id (**REQUIRED**)
Available values : tenant_id

service_id (**REQUIRED**)
Available values : service_id

subscription_id (**REQUIRED**)
Available values : subscription_id

## Sample Call

```json
{
  "created_at": "2022-09-09T22:54:34.433Z",
  "description": "string",
  "expired_at": "2022-09-09T22:54:34.433Z",
  "id": [
    0
  ],
  "product_id": [
    0
  ],
  "product_name": "string",
  "service_id": [
    0
  ],
  "status": "string"
  }
  ```

## Responses

| Code         | Description                                              |
| :----------- | :-----------                                             |
| 200          | Successfully retrieved the subscription.                 |
| 404          | No subscription with the provided subscription ID found. |
| 415          | Invalid Accept Header in Request.                        |
| 500          | Internal server error.                                   |

# Retrieve Associated Policy

**GET /tms/v1/tenants/{tenant_id}/services/{service_id}/subscriptions/{subscription_id}/policies**

## Description

Retrieves policies associated with a subscription. Returns - Array of policy Ids.

## Headers

tenant_id (**REQUIRED**)
Available values : tenant_id

service_id (**REQUIRED**)
Available values : service_id

subscription_id (**REQUIRED**)
Available values : subscription_id

## Sample Call

```json
 {
  "policy_ids": [
    [
      0
    ]
  ]
}
```

## Responses

| Code         | Description                                                         |
| :----------- | :-----------                                                        |
| 200          | Successfully retrieved the policies associated with subscription.   |
| 404          | No subscription with the provided subscription ID found.            |
| 415          | Invalid Accept Header in Request.                                   |
| 500          | Internal server error.                                              |

# Search Users in Tenant

**GET /tms/v1/tenants/{tenant_id}/users**

## Description

Searches for users that are in the tenant. Returns - The serialized array of Users Go struct object that was retrieved.

## Headers

Accept (**REQUIRED**)
Available values : application/json

tenant_id (**REQUIRED**)
Available values : tenant_id

email (**REQUIRED**)
Available values : email

## Sample Call

```json
{
  "active": true,
  "created_at": "2022-09-09T23:24:23.064Z",
  "email": "string",
  "id": [
    0
  ],
  "tenant_roles": [
    {
      "roles": [
        {
          "id": [
            0
          ],
          "name": "string"
        }
      ],
      "tenant_id": [
        0
      ]
    }
  ]
}
]

## Responses

| Code         | Description                                              |
| :----------- | :-----------                                             |
| 200          | Successfully retrieved list of users.                    |
| 404          | No user with the provided user ID found.                 |
| 415          | Invalid Accept Header in Request.                        |
| 500          | Internal server error.                                   |
