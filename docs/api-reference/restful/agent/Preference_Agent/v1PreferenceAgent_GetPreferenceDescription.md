---
title: POST Agents/Preference/GetPreferenceDescription
id: v1PreferenceAgent_GetPreferenceDescription
---

# POST Agents/Preference/GetPreferenceDescription

```http
POST /api/v1/Agents/Preference/GetPreferenceDescription
```

Gets a PreferenceDescription object.







## Query String Parameters

| Parameter Name | Type |  Description |
|----------------|------|--------------|
| preferenceDescriptionId | int32 | **Required** The primary key. |
| $select | string |  Optional comma separated list of properties to include in the result. Other fields are then nulled out to reduce payload size: "Name,department,category". Default = show all fields. |

```http
POST /api/v1/Agents/Preference/GetPreferenceDescription?preferenceDescriptionId=555
POST /api/v1/Agents/Preference/GetPreferenceDescription?$select=name,department,category/id
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

Preference description, drives the Preference GUI. Maintenance client - controls all preferences in SuperOffice.



Carrier object for PreferenceDescription.
Services for the PreferenceDescription Carrier is available from the <see cref="T:SuperOffice.CRM.Services.IPreferenceAgent">Preference Agent</see>.

| Response | Description |
|----------------|-------------|
| 200 | OK |

Response body: object

| Property Name | Type |  Description |
|----------------|------|--------------|
| PrefDescId | int32 | Primary key |
| Section | string | Preference section name |
| Key | string | Preference key name |
| Name | string | Multi-language name |
| ValueType | string | 1=number, 2=text, 3=bool, 4=list of values; 5=list table ref; 6=contact ID, 7=Person ID, 8=Project ID, 9=Selection ID |
| MaxLevel | string | Lowest allowed setting level, set by user, but not lower than sysMaxLevel |
| SysMaxLevel | string | Lowest allowed setting level, set by SuperOffice |
| AccessFlags | string | 1=wizard mode, 2=level 0, 4=admin gui, 8=crm gui |
| Description | string | Description of preference, multi-language parsed |
| IsBuiltin | bool | 1 = This row populated and maintained by SuperOffice |
| TableName | string | If valueType = 5, then TableName contains the table referenced by the preference |
| UserDefinedListId | int32 | Read-only field, If valueType = 5, and TableName is UDList, then UserdefinedLIstId contains the id of the list referenced by the preference |
| Rank | int32 | Rank field for ordering sections, and keys within sections |
| SubGroup | string | Keys that share a value (including NULL) in this field are shown together; a visual spacer is shown between groups |
| MinLevel | int32 | The minimum (furthest away from User) level this preference can be set for |
| MaxValue | int32 | Max value (if type 1); list table ID (if type 5) |
| MinValue | int32 | Min value (if type 1); list extra id (if type 5) |
| RequiredLicense | string | Licenses the user/installation must have if this reference is to be shown. Comma-separated list of owner.module pairs |
| TableRight |  |  |
| FieldProperties | object |  |

## Sample Request

```http!
POST /api/v1/Agents/Preference/GetPreferenceDescription
Authorization: Basic dGplMDpUamUw
Accept: application/json; charset=utf-8
Accept-Language: sv
```

```http_
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "PrefDescId": 865,
  "Section": "est",
  "Key": "consequatur",
  "Name": "Conn Inc and Sons",
  "ValueType": "Bool",
  "MaxLevel": "Database",
  "SysMaxLevel": "Database",
  "AccessFlags": "adminGUI",
  "Description": "Up-sized 24/7 hierarchy",
  "IsBuiltin": true,
  "TableName": "Boehm Group",
  "UserDefinedListId": 961,
  "Rank": 450,
  "SubGroup": "praesentium",
  "MinLevel": 642,
  "MaxValue": 114,
  "MinValue": 254,
  "RequiredLicense": "id",
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
      "FieldLength": 938
    }
  }
}
```