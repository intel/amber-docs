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

```json
{
  "created_at": "2022-09-12T18:01:36.740Z",
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

| Code         | Description                                                   |
| :----------- | :-----------                                                  |
| 200          | Successfully retrieved the services that match criteria.
| 400          | Invalid search criteria provided.                             |
| 415          | Invalid Accept Header in Request.                             |
| 500          | Internal server error.                                        |

# Retrieve Services

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
  "created_at": "2022-09-12T18:17:03.844Z",
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

| Code         | Description                                                   |
| :----------- | :-----------                                                  |
| 200          | Successfully retrieved the service.
| 404          | No service with the provided service ID found.                |
| 415          | Invalid Accept Header in Request.                             |
| 500          | Internal server error.                                        |