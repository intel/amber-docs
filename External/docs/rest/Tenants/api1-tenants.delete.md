# Delete User from Tenant

**DELETE /ps/v1/policies**

## Description

Deletes the user from the tenant. Unless the user is part of the tenant, the user record will also be deleted.

## Headers

tenant_id (**REQUIRED**)
Available values : tenant_id 

user_id (**REQUIRED**)
Available values : user_id

## Responses: 
| Code         | Description                                           |
| :----------- | :-----------                                          |
| 200          | Successfully deleted the user from the tenant.        |
| 404          | No user with the provided user ID found.              |
| 500          | Internal server error.                                |

