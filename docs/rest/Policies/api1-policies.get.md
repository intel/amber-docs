# Search Policy

**GET ps/v1/policies**

## Description

A policy is a set of measurements and metadata organized in a flexible format that allows for ease of further extension. The measurements included in the policy pertain to various hardware and feature categories, and their respective metadata sections provide descriptive information.

Searches for relevant policies and returns the signed policy collection consisting of all the associated policies.
Returns - The serialized Signed Policy Collection Go struct object that was retrieved.

## Headers

Content-Type (**REQUIRED**)
Available values : application/json

Accept (**REQUIRED**)
Available values : application/json

## Parameters

|Name                    | Type            | Available Values               | Description         |
| :-----------           | :-----------    | :--------------                | -----------         |
| policyName             | string($string) |                                | Policy Name         |
| serviceOfferName       | string          | TDX, SGX                       | Type of the service. offered.|
| policyType             | string          | Appraisal, Token Customization | Type of the policy. |
| TenantId               | string          | TenantId                       | Tenant Id for whom policy is being searched.|

## Sample Call

```json
[
{
  "created_time": "2022-09-13T21:44:29.947Z",
  "creator_id": [
    0
  ],
  "deleted": true,
  "modified_time": "2022-09-13T21:44:29.947Z",
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
]
```

## Responses

| Code         | Description                                                   |
| :----------- | :-----------                                                  |
| 200          | Successfully searched and returned a signed policy collection.|
| 400          | Invalid search criteria provided.                             |
| 415          | Invalid Accept Header in Request.                             |
| 500          | Internal server error.                                        |

# Retrieve Policy

**GET /ps/v1/policies/{policy_id}**

## Description

Retrieves a policy. Returns - The serialized Signed Policy Go struct object that was retrieved.

## Headers

policy_id (**REQUIRED**)
Available values : policy_id

Accept (**REQUIRED**)
Available values : application/json

TenantId (**REQUIRED**)
Available values : TenantId

## Sample Call

```json
{
  "created_time": "2022-09-09T17:04:37.768Z",
  "creator_id": [
    0
  ],
  "deleted": true,
  "modified_time": "2022-09-09T17:04:37.768Z",
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

| Code         | Description                           |
| :----------- | :-----------                          |
| 200          | Successfully retrieved the policy.    |
| 400          | Bad request.                          |
| 415          | Invalid Accept Header in Request.     |
| 500          | Internal server error.                |