---
title: POST Agents/CustomerService/CreateDefaultCustomerCenterConfig
id: v1CustomerServiceAgent_CreateDefaultCustomerCenterConfig
---

# POST Agents/CustomerService/CreateDefaultCustomerCenterConfig

```http
POST /api/v1/Agents/CustomerService/CreateDefaultCustomerCenterConfig
```

Set default values into a new CustomerCenterConfig.

NetServer calculates default values on the entity, which is required when creating/storing a new instance






## Request Headers

| Parameter Name | Description |
|----------------|-------------|
| Authorization  | Supports 'Basic', 'SoTicket' and 'Bearer' schemes, depending on installation type. |
| X-XSRF-TOKEN   | If not using Authorization header, you must provide XSRF value from cookie or hidden input field |
| Accept         | Content-type(s) you would like the response in: `application/json`, `text/json`, `application/xml`, `text/xml`, `application/json-patch+json`, `application/merge-patch+json` |
| Accept-Language | Convert string references and multi-language values into a specified language (iso2) code. |
| SO-Language | Convert string references and multi-language values into a specified language (iso2) code. Overrides Accept-Language value. |
| SO-Culture | Number, date formatting in a specified culture (iso2 language) code. Partially overrides SO-Language/Accept-Language value. Ignored if no Language set. |
| SO-TimeZone | Specify the timezone code that you would like date/time responses converted to. |
| SO-AppToken | The application token that identifies the partner app. Used when calling Online WebAPI from a server. |


## Response: object

Contains configuration when displaying the Customer Center



Carrier object for CustomerCenterConfig.
Services for the CustomerCenterConfig Carrier is available from the <see cref="T:SuperOffice.CRM.Services.ICustomerServiceAgent">CustomerService Agent</see>.

| Response | Description |
|----------------|-------------|
| 200 | OK |

Response body: object

| Property Name | Type |  Description |
|----------------|------|--------------|
| CustConfigId | int32 | Primary key |
| Type | string | What kind of data is in this row |
| Config | string | A JSON-formatted config |
| CustLangId | int32 | The customer language which this config belongs to. 0 indicates that the config is global |
| Registered | date-time | Registered when  in UTC. |
| RegisteredAssociateId | int32 | Registered by whom |
| Updated | date-time | Last updated when  in UTC. |
| UpdatedAssociateId | int32 | Last updated by whom |
| TableRight |  |  |
| FieldProperties | object |  |

## Sample Request

```http!
POST /api/v1/Agents/CustomerService/CreateDefaultCustomerCenterConfig
Authorization: Basic dGplMDpUamUw
Accept: application/json; charset=utf-8
Accept-Language: fr,de,ru,zh
```

```http_
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "CustConfigId": 374,
  "Type": "Options",
  "Config": "quia",
  "CustLangId": 978,
  "Registered": "2007-07-09T16:48:29.2198943+02:00",
  "RegisteredAssociateId": 102,
  "Updated": "2019-04-22T16:48:29.2198943+02:00",
  "UpdatedAssociateId": 229,
  "TableRight": {
    "Mask": "Delete",
    "Reason": ""
  },
  "FieldProperties": {
    "fieldName": {
      "FieldRight": {
        "Mask": "FULL",
        "Reason": ""
      },
      "FieldType": "System.Int32",
      "FieldLength": 524
    }
  }
}
```