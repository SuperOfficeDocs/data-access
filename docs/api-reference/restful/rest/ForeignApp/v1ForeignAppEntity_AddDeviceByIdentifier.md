---
title: POST ForeignApp/{applicationName}/{deviceName}/{deviceIdentifier}
id: v1ForeignAppEntity_AddDeviceByIdentifier
---

# POST ForeignApp/{applicationName}/{deviceName}/{deviceIdentifier}

```http
POST /api/v1/ForeignApp/{applicationName}/{deviceName}/{deviceIdentifier}
```

Adds a new ForeignDevice with deviceName that belongs to the application with applicationName, with an optional device-specific identifier.






| Path Part | Type | Description |
|-----------|------|-------------|
| applicationName | string | The name of the foreign application. **Required** |
| deviceName | string | The name of the foreign device. **Required** |
| deviceIdentifier | string | Unique id of device (Palm pilot device ID, version number, etc) **Required** |



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

Saves a foreign device belonging to the ForeignDevice and application name specified.



Carrier object for ForeignDevice.
Services for the ForeignDevice Carrier is available from the <see cref="T:SuperOffice.CRM.Services.IForeignSystemAgent">ForeignSystem Agent</see>.

| Response | Description |
|----------------|-------------|
| 200 | OK |

Response body: object

| Property Name | Type |  Description |
|----------------|------|--------------|
| ForeignDeviceId | int32 | Primary key |
| Name | string | Name of device |
| CreatedDate | date-time | Registered when  in UTC. |
| UpdatedDate | date-time | Last updated when  in UTC. |
| AssociateFullName | string | The person owning the Foreign Device |
| CreatedBy | string | The person that created the device. |
| UpdatedBy | string | The person that last updated this device. |
| DeviceIdentifier | string | Optional unique id of device (Palm pilot device ID, etc) |
| ForeignAppId | int32 | Reference to foregin application (device type) |
| TableRight |  |  |
| FieldProperties | object |  |

## Sample Request

```http!
POST /api/v1/ForeignApp/{applicationName}/{deviceName}/{deviceIdentifier}
Authorization: Basic dGplMDpUamUw
Accept: application/json; charset=utf-8
Accept-Language: sv
```

```http_
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "ForeignDeviceId": 994,
  "Name": "Armstrong-Williamson",
  "CreatedDate": "2012-05-23T09:40:59.2226629+02:00",
  "UpdatedDate": "2013-02-13T09:40:59.2226629+01:00",
  "AssociateFullName": "Marjory Gibson",
  "CreatedBy": "consequatur",
  "UpdatedBy": "aliquam",
  "DeviceIdentifier": "assumenda",
  "ForeignAppId": 796,
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
      "FieldLength": 992
    }
  }
}
```