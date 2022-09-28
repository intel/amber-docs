# Search ServiceOffers

**GET /tms/v1/serviceOffers**

## Description

Searches ServiceOffers. Returns - An array of serviceOffers that exist in the system.

## Headers

id (**REQUIRED**)
Available values : id

## Sample Call

```json
{
  "id": [
    0
  ],
  "name": "string"
}
```

## Responses

| Code         | Description                                                   |
| :----------- | :-----------                                                  |
| 200          | Successfully retrieved the serviceOffers that match criteria. |
| 404          | No serviceOffer with the provided serviceOffer ID found.      |
| 415          | Invalid Accept Header in Request.                             |
| 500          | Internal server error.                                        |

# Retrieve ServiceOffers

**GET /tms/v1/serviceOffers/{serviceOffer_id}**

## Description

Retrieves a serviceOffer. Returns - The serialized Signed ServiceOffer Go struct object that was retrieved.

## Headers

serviceOffer_id (**REQUIRED**)
Available values : serviceOffer_id

## Sample Call

```json
{
  "id": [
    0
  ],
  "name": "string"
}
```

## Responses

| Code         | Description                                                   |
| :----------- | :-----------                                                  |
| 200          | Successfully retrieved the serviceOffer.                      |
| 404          | No serviceOffer with the provided serviceOffer ID found.      |
| 415          | Invalid Accept Header in Request.                             |
| 500          | Internal server error.                                        |