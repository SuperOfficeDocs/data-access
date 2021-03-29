---
title: PATCH ShipmentMessage/{id}
id: v1ShipmentMessageEntity_PatchShipmentMessageEntity
---

# PATCH ShipmentMessage/{id}

```http
PATCH /api/v1/ShipmentMessage/{id}
```

Update a ShipmentMessageEntity with changes, as described in a JSON Patch or a JSON Merge Patch document.

See <a href="https://tools.ietf.org/html/rfc6902">RFC6902</a> and <a href="https://tools.ietf.org/html/rfc7386">RFC 7396</a>. Update the Department field to "foo" can be done either as a JSON PATCH:

```js

[ { "op": "replace", "path": "/Department", "value": "foo" } ]

```

or as a JSON MERGE PATCH, which describes the change directly:

```js

{ "Department": "foo" }

```



JSON PATCH supports operations 'add', 'replace', 'remove' and 'test'.
The path is case insensitive, and the leading slash is optional, so the paths "/department", "Department" and "department" are all equivalent.



Calls the {SuperOffice.CRM.Services.IMarketingAgent} service SaveShipmentMessageEntity.




| Path Part | Type | Description |
|-----------|------|-------------|
| id | int32 | The ShipmentMessageEntity  id to update. **Required** |


## Query String Parameters

| Parameter Name | Type |  Description |
|----------------|------|--------------|
| $select | string |  Optional comma separated list of properties to include in the result. Other fields are then nulled out to reduce payload size: "Name,department,category" Default = show all fields. |

```http
PATCH /api/v1/ShipmentMessage/{id}?$select=name,department,category/id
```


## Request Headers

| Parameter Name | Description |
|----------------|-------------|
| Authorization  | Supports 'Basic', 'SoTicket' and 'Bearer' schemes, depending on installation type. |
| X-XSRF-TOKEN   | If not using Authorization header, you must provide XSRF value from cookie or hidden input field |
| Content-Type | Content-type of the request body:  |
| Accept         | Content-type(s) you would like the response in: `application/json`, `text/json`, `application/xml`, `text/xml`, `application/json-patch+json`, `application/merge-patch+json` |
| Accept-Language | Convert string references and multi-language values into a specified language (iso2) code. |
| SO-Language | Convert string references and multi-language values into a specified language (iso2) code. Overrides Accept-Language value. |
| SO-Culture | Number, date formatting in a specified culture (iso2 language) code. Partially overrides SO-Language/Accept-Language value. Ignored if no Language set. |
| SO-TimeZone | Specify the timezone code that you would like date/time responses converted to. |
| SO-AppToken | The application token that identifies the partner app. Used when calling Online WebAPI from a server. |

## Request Body: changes string 

JSON-Patch array of operations+path+value, or a MERGE-PATCH object (which will be converted to a list of JSON-PATCH operations). 

| Property Name | Type |  Description |
|----------------|------|--------------|
| op | string | "add", "replace", "remove", "test" "move" and "copy" not supported |
| path | string | The property names to modify.  "/users/0/email", "/users/-", |
| value | object | New/Replaced value - string or object. |


## Response: object

A shipment message, that contains the actual message being sent out in a mailing



ShipmentMessageEntity entity with API _Links added.

| Response | Description |
|----------------|-------------|
| 200 | ShipmentMessageEntity  updated. |
| 404 | ShipmentMessageEntity with given id does not exist in the db. |
| 409 | Update blocked because a 'test' operation has detected a conflict with the entity value. |
| 412 | Update aborted because ShipmentMessageEntity has changed since the requested If-Unmodified-Since timestamp. |

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
| _Links | object |  |

## Sample Request

```http!
PATCH /api/v1/ShipmentMessage/{id}
Authorization: Basic dGplMDpUamUw
Accept: application/json; charset=utf-8
Accept-Language: *
Content-Type: application/json; charset=utf-8

[
  {
    "op": "add",
    "path": "accusamus",
    "value": {
      "value1": {
        "PrimaryKey": 6875,
        "EntityName": "person",
        "personId": 6875,
        "fullName": "Ms. Neil Jacobi"
      },
      "value2": {
        "PrimaryKey": 199,
        "EntityName": "person",
        "personId": 199,
        "fullName": "Uriel Pfeffer"
      }
    }
  },
  {
    "op": "add",
    "path": "accusamus",
    "value": {
      "value1": {
        "PrimaryKey": 6875,
        "EntityName": "person",
        "personId": 6875,
        "fullName": "Ms. Neil Jacobi"
      },
      "value2": {
        "PrimaryKey": 199,
        "EntityName": "person",
        "personId": 199,
        "fullName": "Uriel Pfeffer"
      }
    }
  }
]
```

```http_
HTTP/1.1 200 ShipmentMessageEntity  updated.
Content-Type: application/json; charset=utf-8

{
  "ShipmentMessageId": 74,
  "PlainMessage": "beatae",
  "HtmlMessage": "cumque",
  "SmsMessage": "ea",
  "Description": "Switchable regional monitoring",
  "Subject": "aliquid",
  "FolderId": 938,
  "HeaderField": "dolores",
  "Design": "reprehenderit",
  "Designtype": "SOEditor",
  "Flags": "Document",
  "RegisterViews": false,
  "InlineImages": false,
  "LongDescription": "Profound heuristic artificial intelligence",
  "AccessKey": "aut",
  "DocumentMessage": 901,
  "Registered": "1998-06-17T09:40:59.7590318+02:00",
  "RegisteredAssociateId": 894,
  "Updated": "1994-01-29T09:40:59.7590318+01:00",
  "UpdatedAssociateId": 1001,
  "UpdatedCount": 946,
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
      "FieldLength": 655
    }
  },
  "_Links": {
    "Self": "https://www.example.com/api/v1/contact/321",
    "Archive": "https://www.example.com/api/v1/contact"
  }
}
```