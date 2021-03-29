---
title: POST Agents/Project/GetProjectEventEntityFromProjectId
id: v1ProjectAgent_GetProjectEventEntityFromProjectId
---

# POST Agents/Project/GetProjectEventEntityFromProjectId

```http
POST /api/v1/Agents/Project/GetProjectEventEntityFromProjectId
```

Get a ProjectEventEntity based on a projectId.







## Query String Parameters

| Parameter Name | Type |  Description |
|----------------|------|--------------|
| $select | string |  Optional comma separated list of properties to include in the result. Other fields are then nulled out to reduce payload size: "Name,department,category". Default = show all fields. |

```http
POST /api/v1/Agents/Project/GetProjectEventEntityFromProjectId?$select=name,department,category/id
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

ProjectId 

| Property Name | Type |  Description |
|----------------|------|--------------|
| ProjectId | int32 |  |


## Response: object

The ProjectEvent Service. The service implements all services working with the ProjectEvent object



Carrier object for ProjectEventEntity.
Services for the ProjectEventEntity Carrier is available from the <see cref="T:SuperOffice.CRM.Services.IProjectAgent">Project Agent</see>.

| Response | Description |
|----------------|-------------|
| 200 | OK |

Response body: object

| Property Name | Type |  Description |
|----------------|------|--------------|
| SignOffConfirmationText | string | Text shown as confirmation text before accepting sign off. |
| SignOffText | string | Default text for the activity created when signing off. |
| SignOnConfirmationText | string | Text shown as confirmation text before accepting sign on. |
| SignOnText | string | Default text for the activity created when signing on. |
| EventDate | date-time | Dateof the event; publishing/visibility dates are in Publish, and restrictions are in AudienceVisibility |
| Enabled | bool | Is the event enabled |
| CreatedDate | date-time | Registered when  in UTC. |
| SignOff | bool | Is Sign Off functionality enabled? |
| SignOffTaskEnable | bool | If not 0, a task should be created when the external user Signs Off an event |
| SignOffTaskId | int32 | If not 0, sign off should cause an Activity of this type to be registered |
| SignOffTriggersAssign | bool | If 1, the SignOff task should be created as an Assigned task, triggering the invitation dialog |
| SignOn | bool | Is Sign On functionality enabled |
| SignOnTaskEnable | bool | If not 0, a task should be created when the external user Signs On to an event |
| SignOnTaskId | int32 | If not 0, sign on should cause an Activity of this type to be registered |
| SignOnTriggersAssign | bool | If 1, the SignOn task should be created as an Assigned task, triggering the invitation dialog |
| UpdatedDate | date-time | Last updated when  in UTC. |
| CreatedBy |  | The person that created the projectevent |
| UpdatedBy |  | The person that last updated the projectevent |
| ProjectId | int32 | The projectId for the project this projectEvent belongs to |
| Id | int32 | Id of the external event |
| PublishFrom | date-time | Publication valid from (inclusive) |
| PublishType | string | Type of publishing action, 0 = Unknown, 1 = to external persons |
| PublishTo | date-time | Publication valid to (inclusive) |
| VisibleForCategories | array | Array of categories that the event is visible for. MDO Table "category". |
| VisibleForPersonInterests | array | Array of person interests (MDO table "persint") that this event is visible for. |
| IsPublished | bool | Publish to external users? When true, the event/project information is visible to external users through the Audience portal. You can control the publish duration using the PublishFrom/PublishTo properties. |
| IsVisibleForMembers | bool |  |
| IsVisibleForCategories | bool |  |
| IsVisibleForPersonInterests | bool |  |
| ProjectEventId | int32 | Primary key |
| TableRight |  |  |
| FieldProperties | object |  |

## Sample Request

```http!
POST /api/v1/Agents/Project/GetProjectEventEntityFromProjectId
Authorization: Basic dGplMDpUamUw
Accept: application/json; charset=utf-8
Accept-Language: en
Content-Type: application/json; charset=utf-8

{
  "ProjectId": 953
}
```

```http_
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "SignOffConfirmationText": "voluptas",
  "SignOffText": "adipisci",
  "SignOnConfirmationText": "accusantium",
  "SignOnText": "ut",
  "EventDate": "2009-10-12T16:48:30.363919+02:00",
  "Enabled": false,
  "CreatedDate": "2006-09-20T16:48:30.363919+02:00",
  "SignOff": true,
  "SignOffTaskEnable": false,
  "SignOffTaskId": 217,
  "SignOffTriggersAssign": true,
  "SignOn": false,
  "SignOnTaskEnable": true,
  "SignOnTaskId": 680,
  "SignOnTriggersAssign": false,
  "UpdatedDate": "2005-05-23T16:48:30.363919+02:00",
  "CreatedBy": {
    "AssociateId": 791,
    "Name": "Medhurst LLC",
    "PersonId": 888,
    "Rank": 948,
    "Tooltip": "qui",
    "Type": "AnonymousAssociate",
    "GroupIdx": 994,
    "FullName": "Frieda Zieme",
    "FormalName": "Armstrong, Nolan and Sporer",
    "Deleted": false,
    "EjUserId": 762,
    "UserName": "Larson-Abernathy",
    "TableRight": {},
    "FieldProperties": {
      "fieldName": {
        "FieldRight": {
          "Mask": "FULL",
          "Reason": ""
        },
        "FieldType": "System.Int32",
        "FieldLength": 88
      }
    }
  },
  "UpdatedBy": {
    "AssociateId": 820,
    "Name": "Leffler Group",
    "PersonId": 934,
    "Rank": 688,
    "Tooltip": "similique",
    "Type": "AnonymousAssociate",
    "GroupIdx": 882,
    "FullName": "Candida Hackett PhD",
    "FormalName": "Lindgren Group",
    "Deleted": true,
    "EjUserId": 951,
    "UserName": "Keebler Group",
    "TableRight": {},
    "FieldProperties": {
      "fieldName": {
        "FieldRight": {
          "Mask": "FULL",
          "Reason": ""
        },
        "FieldType": "System.String",
        "FieldLength": 360
      }
    }
  },
  "ProjectId": 920,
  "Id": 321,
  "PublishFrom": "2019-08-08T16:48:30.3649607+02:00",
  "PublishType": "External",
  "PublishTo": "2003-06-06T16:48:30.3649607+02:00",
  "VisibleForCategories": [
    {
      "Id": 318,
      "Name": "Schmidt Inc and Sons",
      "ToolTip": "Exercitationem rerum veritatis sunt et.",
      "Deleted": true,
      "Rank": 610,
      "Type": "qui",
      "ChildItems": [
        {},
        {}
      ],
      "IconHint": "reprehenderit",
      "ColorBlock": 925,
      "ExtraInfo": "aut",
      "StyleHint": "qui",
      "FullName": "Vince O'Keefe",
      "TableRight": {},
      "FieldProperties": {
        "fieldName": {
          "FieldRight": {
            "Mask": "FULL",
            "Reason": ""
          },
          "FieldType": "System.Int32",
          "FieldLength": 744
        }
      }
    }
  ],
  "VisibleForPersonInterests": [
    {
      "Id": 575,
      "Name": "Schoen, Labadie and Hilll",
      "ToolTip": "Recusandae at molestias.",
      "Deleted": false,
      "Rank": 591,
      "Type": "rerum",
      "ChildItems": [
        {},
        {}
      ],
      "IconHint": "vero",
      "ColorBlock": 919,
      "ExtraInfo": "quis",
      "StyleHint": "repellat",
      "FullName": "Virginie Ziemann",
      "TableRight": {},
      "FieldProperties": {
        "fieldName": {
          "FieldRight": {
            "Mask": "FULL",
            "Reason": "whiteboard sexy methodologies"
          },
          "FieldType": "System.Int32",
          "FieldLength": 146
        }
      }
    }
  ],
  "IsPublished": true,
  "IsVisibleForMembers": false,
  "IsVisibleForCategories": true,
  "IsVisibleForPersonInterests": true,
  "ProjectEventId": 488,
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
      "FieldLength": 465
    }
  }
}
```