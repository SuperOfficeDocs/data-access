---
title: POST Agents/Ticket/UploadAttachment
id: v1TicketAgent_UploadAttachment
---

# POST Agents/Ticket/UploadAttachment

```http
POST /api/v1/Agents/Ticket/UploadAttachment
```

Upload an attachment and return the attachment id







## Query String Parameters

| Parameter Name | Type |  Description |
|----------------|------|--------------|
| $select | string |  Optional comma separated list of properties to include in the result. Other fields are then nulled out to reduce payload size: "Name,department,category". Default = show all fields. |

```http
POST /api/v1/Agents/Ticket/UploadAttachment?$select=name,department,category/id
```


## Request Headers

| Parameter Name | Description |
|----------------|-------------|
| Authorization  | Supports 'Basic', 'SoTicket' and 'Bearer' schemes, depending on installation type. |
| X-XSRF-TOKEN   | If not using Authorization header, you must provide XSRF value from cookie or hidden input field |
| Content-Type | Content-type of the request body: `application/json`, `text/json`, `application/xml`, `text/xml`, `application/x-www-form-urlencoded`, `application/json-patch+json`, `application/merge-patch+json` |
| SO-AppToken | The application token that identifies the partner app. Used when calling Online WebAPI from a server. |

## Request Body: request  

AttachmentId, Content 

| Property Name | Type |  Description |
|----------------|------|--------------|
| AttachmentId | int32 |  |
| Content | byte |  |


## Response


| Response | Description |
|----------------|-------------|
| 204 | No Content |