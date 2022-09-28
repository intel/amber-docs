# Delete a Service

**DELETE /tms/v1/tenants/{tenant_id}/services/{service_id}**

## Description

Deletes a service.

## Headers

tenant_id (**REQUIRED**)
Available values : tenant_id

service_id (**REQUIRED**)
Available values : service_id

## Responses: 
| Code         | Description                                   |
| :----------- | :-----------                                  |
| 200          | Successfully deleted the service.             |
| 404          | No service with the provided service ID found.|
| 500          | Internal server error.                        |

