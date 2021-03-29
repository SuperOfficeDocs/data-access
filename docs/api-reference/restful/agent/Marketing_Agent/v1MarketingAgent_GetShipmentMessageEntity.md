---
title: POST Agents/Marketing/GetShipmentMessageEntity
id: v1MarketingAgent_GetShipmentMessageEntity
---

# POST Agents/Marketing/GetShipmentMessageEntity

```http
POST /api/v1/Agents/Marketing/GetShipmentMessageEntity
```

Gets a ShipmentMessageEntity object.







## Query String Parameters

| Parameter Name | Type |  Description |
|----------------|------|--------------|
| shipmentMessageEntityId | int32 | **Required** The primary key. |
| $select | string |  Optional comma separated list of properties to include in the result. Other fields are then nulled out to reduce payload size: "Name,department,category". Default = show all fields. |

```http
POST /api/v1/Agents/Marketing/GetShipmentMessageEntity?shipmentMessageEntityId=172
POST /api/v1/Agents/Marketing/GetShipmentMessageEntity?$select=name,department,category/id
```


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

A shipment message, that contains the actual message being sent out in a mailing



Carrier object for ShipmentMessageEntity.
Services for the ShipmentMessageEntity Carrier is available from the <see cref="T:SuperOffice.CRM.Services.IMarketingAgent">Marketing Agent</see>.

| Response | Description |
|----------------|-------------|
| 200 | OK |

Response body: object

| Property Name | Type |  Description |
|----------------|------|--------------|
| ShipmentMessageId | int32 | Primary key |
| PlainMessage | string | Plain message text of this message |
| HtmlMessage | string | HTML formatted text of this message |
| SmsMessage | string | SMS version of this message |
| Description | string | Describes this message |
| Subject | string | The mail subject field of the message |
| FolderId | int32 | The folder which this message belongs to. -1 indicates that the message is on the root |
| HeaderField | string | Extra header fields added to mail. Must be formatted correctly |
| Design | string | Will contain the design part of a message. The format will vary based on the type of designer used to create the message |
| Designtype | string | Enum containing the type of the design |
| Flags | string | Identifies if HTML or plain message is included in message. |
| RegisterViews | bool | Register message views? |
| InlineImages | bool | Should images be included inline? |
| LongDescription | string | A field for a long description of this template |
| AccessKey | string | Key used for access verification |
| DocumentMessage | int32 | The SM document used as template for this mailing |
| Registered | date-time | Registered when  in UTC. |
| RegisteredAssociateId | int32 | Registered by whom |
| Updated | date-time | Last updated when  in UTC. |
| UpdatedAssociateId | int32 | Last updated by whom |
| UpdatedCount | int32 | Number of updates made to this record |
| TableRight |  |  |
| FieldProperties | object |  |

## Sample Request

```http!
POST /api/v1/Agents/Marketing/GetShipmentMessageEntity
Authorization: Basic dGplMDpUamUw
Accept: application/json; charset=utf-8
Accept-Language: sv
```

```http_
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "ShipmentMessageId": 597,
  "PlainMessage": "consequatur",
  "HtmlMessage": "praesentium",
  "SmsMessage": "qui",
  "Description": "Ergonomic human-resource flexibility",
  "Subject": "corrupti",
  "FolderId": 67,
  "HeaderField": "reiciendis",
  "Design": "voluptatem",
  "Designtype": "SOEditor",
  "Flags": "Document",
  "RegisterViews": false,
  "InlineImages": false,
  "LongDescription": "Optional system-worthy hierarchy",
  "AccessKey": "repellendus",
  "DocumentMessage": 730,
  "Registered": "2019-05-23T16:48:29.9589333+02:00",
  "RegisteredAssociateId": 665,
  "Updated": "1993-12-05T16:48:29.9589333+01:00",
  "UpdatedAssociateId": 867,
  "UpdatedCount": 663,
  "TableRight": {
    "Mask": "Delete",
    "Reason": ""
  },
  "FieldProperties": {
    "fieldName": {
      "FieldRight": {
        "Mask": "FULL",
        "Reason": "envisioneer global content"
      },
      "FieldType": "System.String",
      "FieldLength": 380
    }
  }
}
```