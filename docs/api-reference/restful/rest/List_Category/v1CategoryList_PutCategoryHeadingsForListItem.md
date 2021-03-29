---
title: PUT List/Category/Items/{id}/Headings
id: v1CategoryList_PutCategoryHeadingsForListItem
---

# PUT List/Category/Items/{id}/Headings

```http
PUT /api/v1/List/Category/Items/{itemId}/Headings
```

Saves headings for the Category list's item.

Calls the List agent service SaveHeadingsForListItemFromListDefinition.




| Path Part | Type | Description |
|-----------|------|-------------|
| itemId | int32 | The ID of the headings to be saved. **Required** |



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

## Request Body: entities  

The headings to be saved. 

| Property Name | Type |  Description |
|----------------|------|--------------|
| Id | int32 | The Id of the ListItem |
| Name | string | The name of the ListItem |
| ToolTip | string | The tooltip of the ListItem |
| Deleted | bool | The deleted status of the ListItem |
| Rank | int32 | The rank of the ListItem |
| Type | string | The type of the ListItem. Custom field. |
| ColorBlock | int32 | The color indicator of the ListItem color block |
| IconHint | string | The Icon hint of the ListItem. Custom field. |
| Selected | bool | True if the ListItem is selected |
| LastChanged | date-time | Time of last change. |
| ChildItems | array | The child items of the SelectableMDOListItem |
| ExtraInfo | string | Extra information added to the ListItem. Could be information such as sort order etc or other meta data. Custom field. |
| StyleHint | string | Style hint indicating, information such as background color etc. Custom field. |
| Hidden | bool | True if the ListItem is hidden |
| FullName | string | The name of the ListItem in its context |


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
| ColorBlock | int32 | The color indicator of the ListItem color block |
| IconHint | string | The Icon hint of the ListItem. Custom field. |
| Selected | bool | True if the ListItem is selected |
| LastChanged | date-time | Time of last change. |
| ChildItems | array | The child items of the SelectableMDOListItem |
| ExtraInfo | string | Extra information added to the ListItem. Could be information such as sort order etc or other meta data. Custom field. |
| StyleHint | string | Style hint indicating, information such as background color etc. Custom field. |
| Hidden | bool | True if the ListItem is hidden |
| FullName | string | The name of the ListItem in its context |
| TableRight |  |  |
| FieldProperties | object |  |

## Sample Request

```http!
PUT /api/v1/List/Category/Items/{itemId}/Headings
Authorization: Basic dGplMDpUamUw
Accept: application/json; charset=utf-8
Accept-Language: en
Content-Type: application/json; charset=utf-8

[
  {
    "Id": 672,
    "Name": "Haley, Cole and Schaefer",
    "ToolTip": "Nostrum laudantium voluptatem magnam molestiae non nobis.",
    "Deleted": false,
    "Rank": 426,
    "Type": "perferendis",
    "ColorBlock": 645,
    "IconHint": "vero",
    "Selected": false,
    "LastChanged": "1997-05-28T09:41:00.1943337+02:00",
    "ChildItems": [
      {
        "Id": 680,
        "Name": "Macejkovic-Carroll",
        "ToolTip": "Molestiae incidunt qui accusantium laboriosam et.",
        "Deleted": true,
        "Rank": 157,
        "Type": "minus",
        "ColorBlock": 447,
        "IconHint": "dolores",
        "Selected": true,
        "LastChanged": "2002-09-27T09:41:00.1943337+02:00",
        "ChildItems": [
          {},
          {}
        ],
        "ExtraInfo": "ut",
        "StyleHint": "et",
        "Hidden": false,
        "FullName": "Elissa Turcotte"
      }
    ],
    "ExtraInfo": "ex",
    "StyleHint": "et",
    "Hidden": false,
    "FullName": "Armani Quitzon"
  }
]
```

```http_
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

[
  {
    "Id": 884,
    "Name": "Hackett-Hyatt",
    "ToolTip": "Consequatur in omnis aliquam doloribus dignissimos.",
    "Deleted": false,
    "Rank": 288,
    "Type": "necessitatibus",
    "ColorBlock": 426,
    "IconHint": "dignissimos",
    "Selected": false,
    "LastChanged": "2004-07-22T09:41:00.1963745+02:00",
    "ChildItems": [
      {
        "Id": 438,
        "Name": "Murphy, Heidenreich and Littel",
        "ToolTip": "Atque ut magnam quaerat quia ad quis.",
        "Deleted": false,
        "Rank": 548,
        "Type": "non",
        "ColorBlock": 707,
        "IconHint": "corporis",
        "Selected": false,
        "LastChanged": "2002-08-09T09:41:00.1963745+02:00",
        "ChildItems": [
          {},
          {}
        ],
        "ExtraInfo": "est",
        "StyleHint": "adipisci",
        "Hidden": false,
        "FullName": "Tito Pouros",
        "TableRight": {},
        "FieldProperties": {
          "fieldName": {
            "FieldRight": {
              "Mask": "FULL",
              "Reason": ""
            },
            "FieldType": "System.Int32",
            "FieldLength": 647
          }
        }
      }
    ],
    "ExtraInfo": "alias",
    "StyleHint": "sapiente",
    "Hidden": false,
    "FullName": "Sharon Osinski",
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
        "FieldLength": 683
      }
    }
  }
]
```