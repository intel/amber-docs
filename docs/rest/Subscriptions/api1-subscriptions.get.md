# Search Subscriptions

**GET /tms/v1/tenants/{tenant_id}/services/{service_id}/subscriptions**

## Description

Searches Subscriptions. Returns - An array of subscriptions that exist in the system.

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
  "created_at": "2022-09-12T19:30:58.096Z",
  "description": "string",
  "expired_at": "2022-09-12T19:30:58.096Z",
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
| 200          | Successfully retrieved the subscriptions that match criteria. |
| 404          | No subscription with the provided subscription ID found.      |
| 415          | Invalid Accept Header in Request.                             |
| 500          | Internal server error.                                        |

# Retrieve Subscription

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
  "created_at": "2022-09-12T19:33:48.916Z",
  "description": "string",
  "expired_at": "2022-09-12T19:33:48.916Z",
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
| 200          | Successfully retrieved the subscription.                      |
| 404          | No subscription with the provided subscription ID found.      |
| 415          | Invalid Accept Header in Request.                             |
| 500          | Internal server error.                                        |

# Retrieve Policies for Subscriptions

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

| Code         | Description                                                       |
| :----------- | :-----------                                                      |
| 200          | Successfully retrieved the policies associated with subscription. |
| 404          | No subscription with the provided subscription ID found.          |
| 415          | Invalid Accept Header in Request.                                 |
| 500          | Internal server error.                                            |