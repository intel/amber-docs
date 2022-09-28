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

## Sample Call

```json
{
  "created_at": "2022-09-12T19:39:56.761Z",
  "description": "string",
  "expired_at": "2022-09-12T19:39:56.761Z",
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

| Code         | Description                                                |
| :----------- | :-----------                                               |
| 201          | Successfully created the subscription.                     |
| 400          | Invalid request body provided.                             |
| 415          | Invalid Accept Header in Request.                          |
| 500          | Internal server error.                                     |

