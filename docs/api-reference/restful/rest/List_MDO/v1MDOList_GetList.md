---
title: GET MDOList/{listname}
id: v1MDOList_GetList
---

# GET MDOList/{listname}

```http
GET /api/v1/MDOList/{listname}
```

Get the list items in a named list.






| Path Part | Type | Description |
|-----------|------|-------------|
| listname | string | "category", "business" etc **Required** |


## Query String Parameters

| Parameter Name | Type |  Description |
|----------------|------|--------------|
| flat | bool |  Flatten the list? Default false. |
| additional | string |  Extra context for the provider. Depends on listname. |
| query | string |  Search terms (implies flat=true) |

```http
GET /api/v1/MDOList/{listname}?flat=False
GET /api/v1/MDOList/{listname}?additional=accusamus
GET /api/v1/MDOList/{listname}?query=officia
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


## Response: array



| Response | Description |
|----------------|-------------|
| 200 | OK |

Response body: array

| Property Name | Type |  Description |
|----------------|------|--------------|
| Id | int32 | The Id of the ListItem |
| Name | string | The name of the ListItem |
| ToolTip | string | The tooltip of the ListItem |
| Deleted | bool | The deleted status of the ListItem |
| Rank | int32 | The rank of the ListItem |
| Type | string | The type of the ListItem. Custom field. |
| ChildItems | array | The child items of the MDOListItem |
| IconHint | string | The Icon hint of the ListItem. Custom field. |
| ColorBlock | int32 | The color indicator of the ListItem color block |
| ExtraInfo | string | Extra information added to the ListItem. Could be information such as sort order etc or other meta data. Custom field. |
| StyleHint | string | Style hint indicating, information such as background color etc. Custom field. |
| FullName | string | The name of the ListItem in its context |
| TableRight |  |  |
| FieldProperties | object |  |

## Sample Request

```http!
GET /api/v1/MDOList/{listname}
Authorization: Basic dGplMDpUamUw
Accept: application/json; charset=utf-8
Accept-Language: en
```

```http_
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

[
  {
    "Id": 559,
    "Name": "Grady Group",
    "ToolTip": "Distinctio nemo iusto vel.",
    "Deleted": false,
    "Rank": 425,
    "Type": "quod",
    "ChildItems": [
      {
        "Id": 989,
        "Name": "Goodwin Inc and Sons",
        "ToolTip": "Occaecati aut minima commodi rerum.",
        "Deleted": true,
        "Rank": 681,
        "Type": "vel",
        "ChildItems": [
          {},
          {}
        ],
        "IconHint": "at",
        "ColorBlock": 933,
        "ExtraInfo": "aut",
        "StyleHint": "quas",
        "FullName": "Jerome Wehner II",
        "TableRight": {},
        "FieldProperties": {
          "fieldName": {
            "FieldRight": {
              "Mask": "FULL",
              "Reason": ""
            },
            "FieldType": "System.Int32",
            "FieldLength": 233
          }
        }
      }
    ],
    "IconHint": "alias",
    "ColorBlock": 21,
    "ExtraInfo": "at",
    "StyleHint": "eaque",
    "FullName": "Mr. Bud Sauer",
    "TableRight": {
      "Mask": "Delete",
      "Reason": ""
    },
    "FieldProperties": {
      "fieldName": {
        "FieldRight": {
          "Mask": "FULL",
          "Reason": "orchestrate rich web-readiness"
        },
        "FieldType": "System.Int32",
        "FieldLength": 392
      }
    }
  }
]
```