---
title: POST Agents/Person/SaveConsentPerson
id: v1PersonAgent_SaveConsentPerson
---

# POST Agents/Person/SaveConsentPerson

```http
POST /api/v1/Agents/Person/SaveConsentPerson
```

Updates the existing ConsentPerson or creates a new ConsentPerson if the id parameter is empty








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

## Request Body: entity  

The ConsentPerson to be saved. 

| Property Name | Type |  Description |
|----------------|------|--------------|
| ConsentPersonId | int32 | ConsentPerson ID |
| ConsentSource |  | The consent source |
| LegalBase |  | The legal base |
| PersonId | int32 | Person ID |
| ConsentPurpose |  | The consent purpose |
| Comment | string | Comment regarding this specific consent |


## Response: object

Carrier object for ConsentPerson.
Services for the ConsentPerson Carrier is available from the <see cref="T:SuperOffice.CRM.Services.IPersonAgent">Person Agent</see>.

| Response | Description |
|----------------|-------------|
| 200 | OK |

Response body: object

| Property Name | Type |  Description |
|----------------|------|--------------|
| ConsentPersonId | int32 | ConsentPerson ID |
| ConsentSource |  | The consent source |
| LegalBase |  | The legal base |
| PersonId | int32 | Person ID |
| ConsentPurpose |  | The consent purpose |
| Comment | string | Comment regarding this specific consent |
| TableRight |  |  |
| FieldProperties | object |  |

## Sample Request

```http!
POST /api/v1/Agents/Person/SaveConsentPerson
Authorization: Basic dGplMDpUamUw
Accept: application/json; charset=utf-8
Accept-Language: en
Content-Type: application/json; charset=utf-8

{
  "ConsentPersonId": 286,
  "ConsentSource": {
    "ConsentSourceId": 378,
    "Name": "Schmidt-Lehner",
    "Tooltip": "dignissimos",
    "Rank": 164,
    "Key": "odio",
    "MailTemplateId": 178,
    "Deleted": false
  },
  "LegalBase": {
    "LegalBaseId": 913,
    "Name": "Tremblay Group",
    "Tooltip": "et",
    "Rank": 770,
    "Key": "ea",
    "Deleted": false
  },
  "PersonId": 4,
  "ConsentPurpose": {
    "ConsentPurposeId": 450,
    "Name": "Windler-Emmerich",
    "ConsentText": "amet",
    "FormText": "fugiat",
    "Key": "aut",
    "Tooltip": "sed",
    "Active": 36,
    "UpdatedDate": "2011-04-05T16:48:30.0359252+02:00",
    "UpdatedBy": {},
    "Deleted": true,
    "Rank": 890,
    "PrivacyStatementDesc": "beatae",
    "PrivacyStatementUrl": "http://www.example.com/"
  },
  "Comment": "labore"
}
```

```http_
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "ConsentPersonId": 745,
  "ConsentSource": {
    "ConsentSourceId": 591,
    "Name": "Weber-Batz",
    "Tooltip": "sed",
    "Rank": 828,
    "Key": "quae",
    "MailTemplateId": 154,
    "Deleted": true,
    "TableRight": {},
    "FieldProperties": {
      "fieldName": {
        "FieldRight": {
          "Mask": "FULL",
          "Reason": "benchmark dynamic infomediaries"
        },
        "FieldType": "System.String",
        "FieldLength": 23
      }
    }
  },
  "LegalBase": {
    "LegalBaseId": 268,
    "Name": "Jast Inc and Sons",
    "Tooltip": "quia",
    "Rank": 475,
    "Key": "molestiae",
    "Deleted": false,
    "TableRight": {},
    "FieldProperties": {
      "fieldName": {
        "FieldRight": {
          "Mask": "FULL",
          "Reason": ""
        },
        "FieldType": "System.String",
        "FieldLength": 431
      }
    }
  },
  "PersonId": 127,
  "ConsentPurpose": {
    "ConsentPurposeId": 134,
    "Name": "Morissette-Torphy",
    "ConsentText": "aliquam",
    "FormText": "fugiat",
    "Key": "aperiam",
    "Tooltip": "ipsum",
    "Active": 202,
    "UpdatedDate": "1996-11-12T16:48:30.0369272+01:00",
    "UpdatedBy": {},
    "Deleted": false,
    "Rank": 475,
    "PrivacyStatementDesc": "fuga",
    "PrivacyStatementUrl": "http://www.example.com/",
    "TableRight": {},
    "FieldProperties": {
      "fieldName": {
        "FieldRight": {
          "Mask": "FULL",
          "Reason": ""
        },
        "FieldType": "System.Int32",
        "FieldLength": 335
      }
    }
  },
  "Comment": "delectus",
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
      "FieldLength": 649
    }
  }
}
```