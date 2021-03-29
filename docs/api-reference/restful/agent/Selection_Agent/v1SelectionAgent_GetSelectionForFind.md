---
title: POST Agents/Selection/GetSelectionForFind
id: v1SelectionAgent_GetSelectionForFind
---

# POST Agents/Selection/GetSelectionForFind

```http
POST /api/v1/Agents/Selection/GetSelectionForFind
```

Obtain a selection for the given entity, for the current user, of type WorkingSetForFind.

Optionally populate criteria from the TypicalSearches system





## Query String Parameters

| Parameter Name | Type |  Description |
|----------------|------|--------------|
| $select | string |  Optional comma separated list of properties to include in the result. Other fields are then nulled out to reduce payload size: "Name,department,category". Default = show all fields. |

```http
POST /api/v1/Agents/Selection/GetSelectionForFind?$select=name,department,category/id
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

EntityName, TypicalSearchId 

| Property Name | Type |  Description |
|----------------|------|--------------|
| EntityName | string |  |
| TypicalSearchId | int32 |  |


## Response: object

Provider name and selection id for a Find temporary selection



Carrier object for SelectionForFind.
Services for the SelectionForFind Carrier is available from the <see cref="T:SuperOffice.CRM.Services.ISelectionAgent">Selection Agent</see>.

| Response | Description |
|----------------|-------------|
| 200 | OK |

Response body: object

| Property Name | Type |  Description |
|----------------|------|--------------|
| ProviderName | string | The name of the Archive Provider to use when working with this selection; this is the main entity provider, never Shadow, Combined or anything else fancy |
| SelectionId | int32 | Primary key |
| CanSaveAsSelection | bool | Most Find entities support saving the search as a Dynamic Selection: this bool indicates if that is the case |
| MainHeading | string | 'Sale', intended for the main headings in the Find front page; this string will contain resource references |
| FilterScreenHeading | string | 'Find sale', or whatever is appropriate for the Find &lt;entity&gt; filter page; this string will contain resource references |
| SelectionEntityHeading | string | 'Companies', or whatever else is appropriate - the plural form of the entity name, intended for the Selection.Details tab before it is saved (!!); this string will contain resource references |
| TableRight |  |  |
| FieldProperties | object |  |

## Sample Request

```http!
POST /api/v1/Agents/Selection/GetSelectionForFind
Authorization: Basic dGplMDpUamUw
Accept: application/json; charset=utf-8
Accept-Language: sv
Content-Type: application/json; charset=utf-8

{
  "EntityName": "Kihn, Schuster and Ward",
  "TypicalSearchId": 304
}
```

```http_
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "ProviderName": "Reinger Inc and Sons",
  "SelectionId": 56,
  "CanSaveAsSelection": false,
  "MainHeading": "ut",
  "FilterScreenHeading": "est",
  "SelectionEntityHeading": "id",
  "TableRight": {
    "Mask": "Delete",
    "Reason": "recontextualize back-end paradigms"
  },
  "FieldProperties": {
    "fieldName": {
      "FieldRight": {
        "Mask": "FULL",
        "Reason": ""
      },
      "FieldType": "System.Int32",
      "FieldLength": 446
    }
  }
}
```