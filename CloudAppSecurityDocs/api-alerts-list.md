---
title: List - Alerts API
description: This article describes the list request in the Defender for Cloud Apps Alerts API.
ms.date: 01/29/2023
ms.topic: reference
---
# List - Alerts API

[!INCLUDE [Banner for top of topics](includes/banner.md)]

Run the GET or POST request to fetch a list of alerts matching the specified filters.

## HTTP request

```rest
GET /api/v1/alerts/
```

```rest
POST /api/v1/alerts/
```

## Request BODY parameters

| Parameter | Description |
| --- | --- |
| filters | Filter objects with all the search filters for the request, see [alert filters](api-alerts.md#filters) for more details |
| sortDirection | The sorting direction. Possible values are: `asc` and `desc` |
| sortField | Fields used to sort alerts. Possible values are:<br />- **date**: The date when then the alert was created<br />- **severity**: The severity of the alert |
| skip | Skips the specified number of records |
| limit | Maximum number of records returned by the request |

## Example

### Request

Here is an example of the request.

```rest
curl -XPOST -H "Authorization:Token <your_token_key>" -H "Content-Type: application/json" "https://<tenant_id>.<tenant_region>.contoso.com/api/v1/alerts/" -d '{
  "filters": {
    // some filters
  },
  "skip": 5,
  "limit": 10
  ...
}'
```

### Response

Returns a list of alerts in JSON format. For detailed information on each property, refer to the [alert properties specifications](api-alerts.md#properties).

```json
{
  "data": [
    {
      "_id": "603f704aaf7417985bbf3b22",
      "contextId": "206e2965-6533-48a6-ba9e-794364a84bf9",
      "description": "Contoso user performed 11 suspicious activities MITRE Technique used Account Discovery (T1087) and subtechnique used Domain Account (T1087.002)",
      "entities": [
        {
          "entityRole": "Source",
          "entityType": 2,
          "id": "6204bdaf-ad46-4e99-a25d-374a0532c666",
          "inst": 0,
          "label": "user1",
          "pa": "user1@contoso.com",
          "type": "account"
        },
        {
          "entityRole": "Related",
          "id": "55017817-27af-49a7-93d6-8af6c5030fdb",
          "label": "DC3",
          "type": "device"
        },
        {
          "id": 20940,
          "label": "Active Directory",
          "type": "service"
        },
        {
          "entityRole": "Related",
          "id": "95c59b48-98c1-40ff-a444-d9040f1f68f2",
          "label": "DC4",
          "type": "device"
        },
        {
          "id": "5bfd18bfab73c36ba10d38ca",
          "label": "Honeytoken activity",
          "policyType": "ANOMALY_DETECTION",
          "type": "policyRule"
        },
        {
          "entityRole": "Source",
          "id": "34f3ecc9-6903-4df7-af79-14fe2d0d4553",
          "label": "Client1",
          "type": "device"
        },
        {
          "entityRole": "Related",
          "id": "d68772fe-1171-4124-9f73-0f410340bd54",
          "label": "DC1",
          "type": "device"
        },
        {
          "type": "groupTag",
          "id": "5f759b4d106abbe4a504ea5d",
          "label": "All Users"
        }
      ],
      "idValue": 15795464,
      "isSystemAlert": false,
      "resolutionStatusValue": 0,
      "severityValue": 1,
      "statusValue": 1,
      "stories": [
        0
      ],
      "threatScore": 34,
      "timestamp": 1621941916475,
      "title": "Honeytoken activity",
      "comment": "",
      "handledByUser": "administrator@contoso.com",
      "resolveTime": "2021-05-13T14:02:34.904Z",
      "URL": "https://contoso.portal.cloudappsecurity.com/#/alerts/603f704aaf7417985bbf3b22"
    }
  ],
  "hasNext": false,
  "max": 1,
  "total": 1,
  "moreThanTotal": false
}

```

[!INCLUDE [Open support ticket](includes/support.md)]
