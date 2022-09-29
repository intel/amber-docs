# Search Products

**GET /tms/v1/serviceOffers/{serviceOffer_id}/products**

## Description

Searches Products. Returns - An array of products that exist in the system.

## Headers

serviceOffer_id (**REQUIRED**)
Available values : serviceOffer_id

id (**REQUIRED**)
Available values : id

## Sample Call

```json
{
  "id": [
    0
  ],
  "name": "string",
  "policy": {
    "limit": 0,
    "limit_renewal_period": 0,
    "quota": 0,
    "quota_renewal_period": 0
  },
  "service_offer_id": [
    0
  ]
}
```

## Responses

| Code         | Description                                                   |
| :----------- | :-----------                                                  |
| 200          | Successfully retrieved the products that match criteria.      |
| 404          | No serviceOffer with the provided serviceOffer ID found.      |
| 415          | Invalid Accept Header in Request.                             |
| 500          | Internal server error.                                        |

# Retrieves Products

**GET /tms/v1/serviceOffers/{serviceOffer_id}/products/{product_id}**

## Description

Retrieves a product. Returns - The serialized Signed Product Go struct object that was retrieved.

## Headers

serviceOffer_id (**REQUIRED**)
Available values : serviceOffer_id

product_id (**REQUIRED**)
Available values : product_id

## Sample Call

```json
{
  "id": [
    0
  ],
  "name": "string",
  "policy": {
    "limit": 0,
    "limit_renewal_period": 0,
    "quota": 0,
    "quota_renewal_period": 0
  },
  "service_offer_id": [
    0
  ]
}
```

## Responses

| Code         | Description                                                   |
| :----------- | :-----------                                                  |
| 200          | Successfully retrieved the product.                           |
| 404          | No serviceOffer with the provided serviceOffer ID found.      |
| 415          | Invalid Accept Header in Request.                             |
| 500          | Internal server error.                                        |