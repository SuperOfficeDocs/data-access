---
title: POST Agents/ErpSync/GetConnectionListMappings
id: v1ErpSyncAgent_GetConnectionListMappings
---

# POST Agents/ErpSync/GetConnectionListMappings

```http
POST /api/v1/Agents/ErpSync/GetConnectionListMappings
```

Returns the listmappings for the specified connection.



## Online Restricted: ## The ErpSync agent is not available in Online by default. Access must be requested specifically when app is registered. Intended for ERP integration apps.





## Query String Parameters

| Parameter Name | Type |  Description |
|----------------|------|--------------|
| $select | string |  Optional comma separated list of properties to include in the result. Other fields are then nulled out to reduce payload size: "Name,department,category". Default = show all fields. |

```http
POST /api/v1/Agents/ErpSync/GetConnectionListMappings?$select=name,department,category/id
```


## Request Headers

| Parameter Name | Description |
|----------------|-------------|
| Authorization  | Supports 'Basic', 'SoTicket' and 'Bearer' schemes, depending on installation type. |
| X-XSRF-TOKEN   | If not using Authorization header, you must provide XSRF value from cookie or hidden input field |
| Content-Type | Content-type of the request body: `application/json`, `text/json`, `application/xml`, `text/xml`, `application/x-www-form-urlencoded`, `application/json-patch+json`, `application/merge-patch+json` |
| Accept         | Content-type(s) you would like the response in: `application/json`, `text/json`, `application/xml`, `text/xml`, `application/json-patch+json`, `application/merge-patch+json` |
| Accept-Language | Convert string references and multi-language values into a specified language (iso2) code. |
| SO-Language | Convert string references and multi-language values into a specified language (iso2) code. Overrides Accept-Language value. |
| SO-Culture | Number, date formatting in a specified culture (iso2 language) code. Partially overrides SO-Language/Accept-Language value. Ignored if no Language set. |
| SO-TimeZone | Specify the timezone code that you would like date/time responses converted to. |
| SO-AppToken | The application token that identifies the partner app. Used when calling Online WebAPI from a server. |

## Request Body: request  

ErpConnectionId 

| Property Name | Type |  Description |
|----------------|------|--------------|
| ErpConnectionId | int32 |  |


## Response: object

Information about all list connections for a connection between CRM and the ERP system.



Carrier object for ErpConnectionListMappingContainer.
Services for the ErpConnectionListMappingContainer Carrier is available from the <see cref="T:SuperOffice.CRM.Services.IErpSyncAgent">ErpSync Agent</see>.

| Response | Description |
|----------------|-------------|
| 200 | OK |

Response body: object

| Property Name | Type |  Description |
|----------------|------|--------------|
| ErpListItemMappings | array | Array of ErpConnectionListMapping |
| ErpConnectionId | int32 | Primary key |
| ErpConnectionName | string | The name of the erp connection |
| TableRight |  |  |
| FieldProperties | object |  |

## Sample Request

```http!
POST /api/v1/Agents/ErpSync/GetConnectionListMappings
Authorization: Basic dGplMDpUamUw
Accept: application/json; charset=utf-8
Accept-Language: *
Content-Type: application/json; charset=utf-8

{
  "ErpConnectionId": 304
}
```

```http_
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "ErpListItemMappings": [
    {
      "CrmList": {},
      "ErpListName": "Hauck, Gusikowski and Tillman",
      "ErpCrmListItemMappings": [
        {},
        {}
      ],
      "ErpActorTypeName": "Cole LLC",
      "ErpFieldId": 195,
      "TableRight": {},
      "FieldProperties": {
        "fieldName": {
          "FieldRight": {
            "Mask": "FULL",
            "Reason": ""
          },
          "FieldType": "System.Int32",
          "FieldLength": 99
        }
      }
    }
  ],
  "ErpConnectionId": 909,
  "ErpConnectionName": "Smith Inc and Sons",
  "TableRight": {
    "Mask": "Delete",
    "Reason": "scale frictionless functionalities"
  },
  "FieldProperties": {
    "fieldName": {
      "FieldRight": {
        "Mask": "FULL",
        "Reason": "cultivate value-added metrics"
      },
      "FieldType": "System.Int32",
      "FieldLength": 296
    }
  }
}
```