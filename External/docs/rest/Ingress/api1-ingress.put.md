# Updates Subscription

**PUT /tms/v1/tenants/{tenant_id}/services/{service_id}/subscriptions/{subscription_id}**

## Description

Updates the subscription of the tenant.

## Sample request body

```json
{
  "expired_at": "2022-09-09T17:39:25.358Z",
  "name": "string",
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
  "created_at": "2022-09-09T22:54:34.438Z",
  "description": "string",
  "expired_at": "2022-09-09T22:54:34.439Z",
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

tenant_id (**REQUIRED**)
Available values : tenant_id

service_id (**REQUIRED**)
Available values : service_id

request body (**REQUIRED**)
Available values : application/json

## Responses

| Code         | Description                                                   |
| :----------- | :-----------                                                  |
| 200          | Successfully updated the subscription.                        |
| 400          | Invalid request body provided.                                |
| 415          | Invalid Accept Header in Request.                             |
| 500          | Internal server error.                                        |

# Update User Role in Tenant

**PUT /tms/v1/tenants/{tenant_id}/users/{user_id}**

## Description

Updates the roles of the user in the tenant.

## Sample request body

```json
{
  "roles": [
    "string"
  ]
}
```

## Sample Call

```json
{
  "active": true,
  "created_at": "2022-09-09T23:32:39.095Z",
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

Update-by (**REQUIRED**)
Available values : Update-by

Accept (**REQUIRED**)
Available values : Accept

tenant_id (**REQUIRED**)
Available values : tenant_id

user_id (**REQUIRED**)
Available values : user_id

## Responses

| Code         | Description                                 |
| :----------- | :-----------                                |
| 200          | Successfully updated the tenant user roles. |
| 400          | Invalid request body provided.              |
| 415          | Invalid Accept Header in Request.           |
| 500          | Internal server error.                      |