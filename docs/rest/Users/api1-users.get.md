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

[
{
  "active": true,
  "created_at": "2022-09-12T21:48:43.317Z",
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
```

## Responses

| Code         | Description                                        |
| :----------- | :-----------                                       |
| 200          | Successfully retrieved list of users.              |
| 404          | No tenant with the provided tenant ID found.       |
| 415          | Invalid Accept Header in Request.                  |
| 500          | Internal server error.                             |


