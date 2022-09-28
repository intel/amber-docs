# Delete a Subscription

**DELETE /tms/v1/tenants/{tenant_id}/services/{service_id}/subscriptions/{subscription_id}}**

## Description

Deletes a subscription.

## Headers

tenant_id (**REQUIRED**)
Available values : tenant_id

service_id (**REQUIRED**)
Available values : service_id

subscription_id (**REQUIRED**)
Available values : subscription_id

## Responses: 
| Code         | Description                                   |
| :----------- | :-----------                                  |
| 200          | Successfully deleted the subscription.        |
| 404          | No service with the provided service ID found.|
| 500          | Internal server error.                        |

