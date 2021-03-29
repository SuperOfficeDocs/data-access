---
title: GET User/{userName}
id: v1User_GetUserFromName
---

# GET User/{userName}

```http
GET /api/v1/User/{userName}
```

Get a user, with lookup based on user name.



## Online Restricted: ## The User agent is not available in Online by default. User management is not allowed for partner apps.




| Path Part | Type | Description |
|-----------|------|-------------|
| userName | string | User name of the user to get. **Required** |



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

SuperOffice User, with login credentials and an associated person.



Carrier object for User.
Services for the User Carrier is available from the <see cref="T:SuperOffice.CRM.Services.IUserAgent">User Agent</see>.

| Response | Description |
|----------------|-------------|
| 200 | OK |

Response body: object

| Property Name | Type |  Description |
|----------------|------|--------------|
| AssociateId | int32 | Primary key |
| Name | string | Initials, UserId - also used as login name for on-site installations. Identifies user in archives. |
| Rank | int32 | Rank order |
| Tooltip | string | Tooltip or other description |
| LicenseOwners | array | The restricted and unrestricted module licenses grouped by license owner. These module licenses are either assigned or unassigned to this user |
| Role |  | Users role for role-based security. Determines permissions and access rights for the user. |
| UserGroup |  | The main user group that this user belongs to.  <para>Use MDO List name "usergroup" to get list items.</para> |
| OtherGroups | array | The other groups this user is a member of, apart from the main user group.  <para>Use MDO List name "usergroup" to get list items.</para> |
| Person |  | The person associated with this user. Detailed information about the user  <para>Use MDO List name "person_new" to get list items.</para> |
| Deleted | bool | If true, the user is retired and should have no rights, not appear in lists, etc. |
| Lastlogin | date-time | Last login date |
| Lastlogout | date-time | Last logout date |
| EjUserId | int32 | ID of the ej user record corresponding to this associate; 0 for associates that are not ej users |
| RequestSignature | string | ej users request signature |
| Type | string | User type: 1=InternalAssociate, 2=ResourceAssociate, 3=ExternalAssociate, 4=AnonymousAssociate, 5=SystemAssociate |
| IsPersonRetired | bool | True if the user is retired and should have no rights, not appear in lists, etc. |
| IsOnTravel | bool | True if the user is on travel. |
| Credentials | array | List of credentials registered for this user. i.e. valid authentication methods. |
| UserName | string | User name, a.k.a. Login name. This might be an e-mail address. |
| TicketCategories | array | Request Ticket Categories assigned to the user.   <para>Use MDO List name "ejCategory" to get list items.</para> |
| NickName | string | The unique nick name for this user. Used in Service as an alias, similar to Name/Initials. |
| WaitingForApproval | bool | The user is waiting for an administrator to approve/grant her/him access. |
| ExtraFields | object | Deprecated: Use {SuperOffice.CRM.Services.User.CustomFields} instead. Extra fields added to the carrier. This could be data from Plug-ins, the foreign key system, external applications, etc. |
| CustomFields | object | Udef + Extra fields added to the carrier. Extra fields as defined by changes to database schema + user-defined fields as defined by admin. Custom fields combines user defined fields and extra fields into one bucket.  The individual {SuperOffice.CRM.Services.User.ExtraFields} and <see cref="!:UserDefinedFields">UserDefinedFields</see> properties are deprecated in favor of this combined collection. |
| PostSaveCommands | array | Post custom commands the client should execute after save has completed. |
| TableRight |  |  |
| FieldProperties | object |  |

## Sample Request

```http!
GET /api/v1/User/{userName}
Authorization: Basic dGplMDpUamUw
Accept: application/json; charset=utf-8
Accept-Language: *
```

```http_
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "AssociateId": 345,
  "Name": "Rutherford LLC",
  "Rank": 482,
  "Tooltip": "suscipit",
  "LicenseOwners": [
    {
      "Name": "Anderson-Kozey",
      "Description": "Grass-roots modular service-desk",
      "RestrictedModuleLicenses": [
        {},
        {}
      ],
      "UnrestrictedModuleLicenses": [
        {},
        {}
      ],
      "TableRight": {},
      "FieldProperties": {
        "fieldName": {
          "FieldRight": {
            "Mask": "FULL",
            "Reason": ""
          },
          "FieldType": "System.String",
          "FieldLength": 506
        }
      }
    },
    {
      "Name": "Anderson-Kozey",
      "Description": "Grass-roots modular service-desk",
      "RestrictedModuleLicenses": [
        {},
        {}
      ],
      "UnrestrictedModuleLicenses": [
        {},
        {}
      ],
      "TableRight": {},
      "FieldProperties": {
        "fieldName": {
          "FieldRight": {
            "Mask": "FULL",
            "Reason": ""
          },
          "FieldType": "System.String",
          "FieldLength": 506
        }
      }
    }
  ],
  "Role": {
    "Id": 296,
    "Value": "ea",
    "Tooltip": "nemo",
    "TableRight": {},
    "FieldProperties": {
      "fieldName": {
        "FieldRight": {
          "Mask": "FULL",
          "Reason": ""
        },
        "FieldType": "System.String",
        "FieldLength": 955
      }
    }
  },
  "UserGroup": {
    "Value": "quisquam",
    "Tooltip": "suscipit",
    "Id": 514,
    "Rank": 995,
    "Deleted": true,
    "TableRight": {},
    "FieldProperties": {
      "fieldName": {
        "FieldRight": {
          "Mask": "FULL",
          "Reason": ""
        },
        "FieldType": "System.String",
        "FieldLength": 137
      }
    }
  },
  "OtherGroups": [
    {
      "Value": "est",
      "Tooltip": "blanditiis",
      "Id": 366,
      "Rank": 250,
      "Deleted": true,
      "TableRight": {},
      "FieldProperties": {
        "fieldName": {
          "FieldRight": {
            "Mask": "FULL",
            "Reason": ""
          },
          "FieldType": "System.String",
          "FieldLength": 541
        }
      }
    }
  ],
  "Person": {
    "Position": "a",
    "PersonId": 823,
    "Mrmrs": "laudantium",
    "Firstname": "Hester",
    "Lastname": "Beatty",
    "MiddleName": "Cummerata Group",
    "Title": "non",
    "Description": "Future-proofed mission-critical conglomeration",
    "Email": "viola.mccullough@predovic.ca",
    "FullName": "Marques Smitham",
    "DirectPhone": "1-707-048-1734 x04567",
    "FormalName": "Heller-Deckow",
    "CountryId": 82,
    "ContactId": 681,
    "ContactName": "Corwin, Marks and Frami",
    "Retired": 624,
    "Rank": 761,
    "ActiveInterests": 952,
    "ContactDepartment": "",
    "ContactCountryId": 827,
    "ContactOrgNr": "415256",
    "FaxPhone": "1-541-836-8517 x7177",
    "MobilePhone": "285.155.1064 x43702",
    "ContactPhone": "043.805.7051 x44033",
    "AssociateName": "Schimmel-Schimmel",
    "AssociateId": 652,
    "UsePersonAddress": false,
    "ContactFax": "ipsum",
    "Kanafname": "dolores",
    "Kanalname": "totam",
    "Post1": "atque",
    "Post2": "reprehenderit",
    "Post3": "iste",
    "EmailName": "saige_pagac@walkerswaniawski.biz",
    "ContactFullName": "Miss Lupe Jaskolski",
    "ActiveErpLinks": 94,
    "TicketPriorityId": 674,
    "SupportLanguageId": 37,
    "SupportAssociateId": 353,
    "CategoryName": "VIP Customer",
    "TableRight": {},
    "FieldProperties": {
      "fieldName": {
        "FieldRight": {
          "Mask": "FULL",
          "Reason": ""
        },
        "FieldType": "System.String",
        "FieldLength": 998
      }
    }
  },
  "Deleted": true,
  "Lastlogin": "2011-04-11T09:41:00.0770589+02:00",
  "Lastlogout": "1999-04-26T09:41:00.0770589+02:00",
  "EjUserId": 876,
  "RequestSignature": "quia",
  "Type": "AnonymousAssociate",
  "IsPersonRetired": false,
  "IsOnTravel": true,
  "Credentials": [
    {
      "Type": {},
      "Value": "modi",
      "DisplayValue": "sit",
      "TableRight": {},
      "FieldProperties": {
        "fieldName": {
          "FieldRight": {
            "Mask": "FULL",
            "Reason": ""
          },
          "FieldType": "System.Int32",
          "FieldLength": 637
        }
      }
    },
    {
      "Type": {},
      "Value": "modi",
      "DisplayValue": "sit",
      "TableRight": {},
      "FieldProperties": {
        "fieldName": {
          "FieldRight": {
            "Mask": "FULL",
            "Reason": ""
          },
          "FieldType": "System.Int32",
          "FieldLength": 637
        }
      }
    }
  ],
  "UserName": "Simonis, Strosin and Waelchi",
  "TicketCategories": [
    {
      "Id": 919,
      "Name": "Lynch, Lebsack and Abshire",
      "ToolTip": "Autem et.",
      "Deleted": true,
      "Rank": 406,
      "Type": "et",
      "ChildItems": [
        {},
        {}
      ],
      "IconHint": "velit",
      "ColorBlock": 522,
      "ExtraInfo": "eos",
      "StyleHint": "voluptas",
      "FullName": "Della Morissette",
      "TableRight": {},
      "FieldProperties": {
        "fieldName": {
          "FieldRight": {
            "Mask": "FULL",
            "Reason": ""
          },
          "FieldType": "System.Int32",
          "FieldLength": 394
        }
      }
    }
  ],
  "NickName": "Bernier Group",
  "WaitingForApproval": false,
  "ExtraFields": {
    "ExtraFields1": "nisi",
    "ExtraFields2": "architecto"
  },
  "CustomFields": {
    "CustomFields1": "corrupti",
    "CustomFields2": "aliquid"
  },
  "PostSaveCommands": [
    {
      "Name": "Cruickshank LLC",
      "DisplayName": "Armstrong Group",
      "Description": "Optional exuding secured line",
      "ToolTip": "Vitae explicabo est quia et iure.",
      "Actions": "Implicit",
      "ActionData": "qui",
      "TableRight": {},
      "FieldProperties": {
        "fieldName": {
          "FieldRight": {
            "Mask": "FULL",
            "Reason": ""
          },
          "FieldType": "System.String",
          "FieldLength": 908
        }
      }
    }
  ],
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
      "FieldLength": 80
    }
  }
}
```