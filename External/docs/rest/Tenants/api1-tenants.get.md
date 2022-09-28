# Retrieve Tenants

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

| Code         | Description                                        |
| :----------- | :-----------                                       |
| 200          | Successfully retrieved the tenant.                 |
| 404          | No tenant with the provided tenant ID found.       |
| 415          | Invalid Accept Header in Request.                  |
| 500          | Internal server error.                             |