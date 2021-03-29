---
title: POST Agents/Chat/DeleteChatTopicEntity
id: v1ChatAgent_DeleteChatTopicEntity
---

# POST Agents/Chat/DeleteChatTopicEntity

```http
POST /api/v1/Agents/Chat/DeleteChatTopicEntity
```

Deletes the ChatTopicEntity







## Query String Parameters

| Parameter Name | Type |  Description |
|----------------|------|--------------|
| ChatTopicEntityId | int32 | **Required** The id of the ChatTopicEntity to be deleted. |

```http
POST /api/v1/Agents/Chat/DeleteChatTopicEntity?ChatTopicEntityId=752
```


## Request Headers

| Parameter Name | Description |
|----------------|-------------|
| Authorization  | Supports 'Basic', 'SoTicket' and 'Bearer' schemes, depending on installation type. |
| X-XSRF-TOKEN   | If not using Authorization header, you must provide XSRF value from cookie or hidden input field |
| SO-AppToken | The application token that identifies the partner app. Used when calling Online WebAPI from a server. |


## Response


| Response | Description |
|----------------|-------------|
| 204 | No Content |