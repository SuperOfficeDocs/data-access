---
title: POST Agents/EMail/RelayMessage
id: v1EMailAgent_RelayMessage
---

# POST Agents/EMail/RelayMessage

```http
POST /api/v1/Agents/EMail/RelayMessage
```

<para />

## Online Restricted: ## The EMail agent is not available in Online by default. Access must be requested specifically when app is registered.





## Query String Parameters

| Parameter Name | Type |  Description |
|----------------|------|--------------|
| $select | string |  Optional comma separated list of properties to include in the result. Other fields are then nulled out to reduce payload size: "Name,department,category". Default = show all fields. |

```http
POST /api/v1/Agents/EMail/RelayMessage?$select=name,department,category/id
```


## Request Headers

| Parameter Name | Description |
|----------------|-------------|
| Authorization  | Supports 'Basic', 'SoTicket' and 'Bearer' schemes, depending on installation type. |
| X-XSRF-TOKEN   | If not using Authorization header, you must provide XSRF value from cookie or hidden input field |
| Content-Type | Content-type of the request body: `application/json`, `text/json`, `application/xml`, `text/xml`, `application/x-www-form-urlencoded`, `application/json-patch+json`, `application/merge-patch+json` |
| SO-AppToken | The application token that identifies the partner app. Used when calling Online WebAPI from a server. |

## Request Body: request  

ConnectionInfoExtended, Rfc822, From, Recipients 

| Property Name | Type |  Description |
|----------------|------|--------------|
| ConnectionInfoExtended |  | Carrier object for EMailConnectionInfoExtended. Services for the EMailConnectionInfoExtended Carrier is available from the <see cref="T:SuperOffice.CRM.Services.IEMailAgent">EMail Agent</see>. |
| Rfc822 | string |  |
| From | string |  |
| Recipients | array |  |


## Response


| Response | Description |
|----------------|-------------|
| 204 | No Content |