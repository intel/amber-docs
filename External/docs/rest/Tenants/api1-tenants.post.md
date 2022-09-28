# Create New Service

**POST /tms/v1/tenants/{tenant_id}/services**

## Description

Creates new service in database.

## Sample request body

```json
{
  "description": "string",
  "service_offer_id": [
    0
  ]
}
```
## Headers

request-body (**REQUIRED**)
Available values : application/json

tenant_id (**REQUIRED**)
Available values : tenant_id

Content-type (**REQUIRED**)
Available values : application/json

Created-by (**REQUIRED**)
Available values : Created-by

Accept (**REQUIRED**)
Available values : application/json

## Sample Call

```json
{
  "created_at": "2022-09-12T18:10:08.136Z",
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

| Code         | Description                                               |
| :----------- | :-----------                                              |
| 201          | Successfully created the service.                         |
| 400          | Invalid request body provided.                            |
| 415          | Invalid Accept Header in Request.                         |
| 500          | Internal server error.                                    |

