---
title: GET List/ProductFamily/MDOItems
id: v1ProductFamilyList_GetMDOList
---

# GET List/ProductFamily/MDOItems

```http
GET /api/v1/List/ProductFamily/MDOItems
```

Get the MDO list items for "ProductFamily" - with headings and filtering by user group.







## Query String Parameters

| Parameter Name | Type |  Description |
|----------------|------|--------------|
| flat | bool |  Flatten the list? Default false. |
| query | string |  Search terms (implies flat=true) |

```http
GET /api/v1/List/ProductFamily/MDOItems?flat=True
GET /api/v1/List/ProductFamily/MDOItems?query=ratione
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
GET /api/v1/List/ProductFamily/MDOItems
Authorization: Basic dGplMDpUamUw
Accept: application/json; charset=utf-8
Accept-Language: en
```

```http_
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

[
  {
    "Id": 170,
    "Name": "Effertz Group",
    "ToolTip": "Iusto ipsum accusamus laudantium ut rem ut.",
    "Deleted": true,
    "Rank": 670,
    "Type": "dignissimos",
    "ChildItems": [
      {
        "Id": 734,
        "Name": "Mann, Morar and Wolf",
        "ToolTip": "Sunt dolore repudiandae.",
        "Deleted": false,
        "Rank": 246,
        "Type": "aut",
        "ChildItems": [
          {},
          {}
        ],
        "IconHint": "non",
        "ColorBlock": 507,
        "ExtraInfo": "est",
        "StyleHint": "voluptatem",
        "FullName": "Miss Vincent Brown",
        "TableRight": {},
        "FieldProperties": {
          "fieldName": {
            "FieldRight": {
              "Mask": "FULL",
              "Reason": "incentivize killer communities"
            },
            "FieldType": "System.String",
            "FieldLength": 334
          }
        }
      }
    ],
    "IconHint": "porro",
    "ColorBlock": 515,
    "ExtraInfo": "et",
    "StyleHint": "ullam",
    "FullName": "Sabina Blick",
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
        "FieldType": "System.String",
        "FieldLength": 896
      }
    }
  }
]
```