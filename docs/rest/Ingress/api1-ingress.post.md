# Create New Policy

**POST /ps/v1/policies**

## Description

Creates a new policy.

TODO: add better description of what a "policy" is.

## Sample request body

```json
{
  "policy": "string",
  "policy_id": [
    0
  ],
  "policy_name": "string",
  "policy_type": "string",
  "service_offer_id": [
    0
  ],
  "service_offer_name": "string",
  "user_id": [
    0
  ]
}
```

## Sample Call

```json                                                     
{
  "created_time": "2022-09-09T17:39:32.820Z",
  "creator_id": [
    0
  ],
  "deleted": true,
  "modified_time": "2022-09-09T17:39:32.820Z",
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

## Headers

request body (**REQUIRED**)
Available values : application/json

Content-Type (**REQUIRED**)
Available values : application/json

Accept (**REQUIRED**)
Available values : application/json

## Responses

| Code         | Description                                                   |
| :----------- | :-----------                                                  |
| 201          | Successfully created the policy.                              |
| 400          | Invalid search criteria provided.                             |
| 415          | Invalid Accept Header in Request.                             |
| 500          | Internal server error.                                        |

# Create New Service

**POST /tms/v1/tenants/{tenant_id}/services**

## Description

Creates a new service.

TODO: add better description of what a "policy" is.

## Sample request body

```json
{
  "description": "string",
  "service_offer_id": [
    0
  ]
}
```

## Sample Call

```json
{
  "created_at": "2022-09-09T21:01:28.818Z",
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

## Headers

request body (**REQUIRED**)
Available values : application/json

tenant_id (**REQUIRED**)
Available values : tenant_id

Content-Type (**REQUIRED**)
Available values : application/json

Created-by (**REQUIRED**)
Available values : Created-by

Accept (**REQUIRED**)
Available values : application/json

## Responses

| Code         | Description                                                |
| :----------- | :-----------                                               |
| 201          | Successfully created the service.                          |
| 400          | Invalid request body provided.                             |
| 415          | Invalid Content-Type/Accept Header in Request.             |
| 500          | Internal server error.                                     |

# Create New Subscription

**POST /tms/v1/tenants/{tenant_id}/services/{service_id}/subscriptions**

## Description

Creates new subscription in database.

## Sample request body

```json
{
  "description": "string",
  "expired_at": "2022-09-09T22:50:44.660Z",
  "policy_ids": [
    [
      0
    ]
  ],
  "product_id": [
    0
  ],
  "status": "string",
  "tagIds_values": [
    {
      "tagId": [
        0
      ],
      "value": "string"
    }
  ]
}
```

## Sample Call

```json
{
  "created_at": "2022-09-09T22:50:44.816Z",
  "description": "string",
  "expired_at": "2022-09-09T22:50:44.816Z",
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

## Headers

request body (**REQUIRED**)
Available values : application/json

tenant_id (**REQUIRED**)
Available values : tenant_id

service_id (**REQUIRED**)
Available values : service_id

Content-Type (**REQUIRED**)
Available values : application/json

Created-by (**REQUIRED**)
Available values : Created-by

Accept (**REQUIRED**)
Available values : application/json

## Responses

| Code         | Description                                                |
| :----------- | :-----------                                               |
| 200          | Successfully created the subscription.                     |
| 400          | Invalid request body provided                              |
| 415          | Invalid Content-Type/Accept Header in Request.             |
| 500          | Internal server error.                                     |

# Add Users to Tenant

**POST /tms/v1/tenants/{tenant_id}/users**

## Description

Add users to a tenant.

## Sample request body

```json
{
  "email": "string",
  "id": [
    0
  ],
  "role": "string"
}
```

## Sample Call

```json
{
  "active": true,
  "created_at": "2022-09-09T23:27:46.115Z",
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
```

## Headers

request body (**REQUIRED**)
Available values : application/json

Content-Type (**REQUIRED**)
Available values : application/json

Created-by (**REQUIRED**)
Available values : Created-by

Accept (**REQUIRED**)
Available values : application/json

tenant_id (**REQUIRED**)
Available values : tenant_id

## Responses

| Code         | Description                                                |
| :----------- | :-----------                                               |
| 201          | Successfully created the tenant user.                      |
| 400          | Invalid request body provided.                             |
| 415          | Invalid Content-Type/Accept Header in Request.             |
| 500          | Internal server error.                                     |