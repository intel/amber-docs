# Create New Policy

**POST /ps/v1/policies**

## Description

Creates a new policy.

TODO: add better description of what a "policy" is

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
## Headers

Content-Type (**REQUIRED**)
Available values : application/json

Accept (**REQUIRED**)
Available values : application/json

## Sample Call

```json
{
  "created_time": "2022-09-09T16:13:42.087Z",
  "creator_id": [
    0
  ],
  "deleted": true,
  "modified_time": "2022-09-09T16:13:42.087Z",
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

| Code         | Description                                             |
| :----------- | :-----------                                            |
| 201          | Successfully created the service.                       |
| 400          | Invalid search criteria provided.                       |
| 415          | Invalid Accept Header in Request.                       |
| 500          | Internal server error.                                  |

