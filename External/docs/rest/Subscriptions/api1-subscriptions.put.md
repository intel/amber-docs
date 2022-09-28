# Update Subscription

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
## Headers

tenant_id (**REQUIRED**)
Available values : tenant_id

service_id (**REQUIRED**)
Available values : service_id

subscription_id (**REQUIRED**)
Available values : subscription_id

request body (**REQUIRED**)
Available values : application/json

## Sample Call

```json
{
  "created_at": "2022-09-12T19:49:19.236Z",
  "description": "string",
  "expired_at": "2022-09-12T19:49:19.236Z",
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

| Code         | Description                                                   |
| :----------- | :-----------                                                  |
| 200          | Successfully updated the subscription.                        |
| 400          | Invalid request body provided.                                |
| 415          | Invalid Accept Header in Request.                             |
| 500          | Internal server error.                                        |