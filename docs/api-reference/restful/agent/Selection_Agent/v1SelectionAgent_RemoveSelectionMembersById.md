---
title: POST Agents/Selection/RemoveSelectionMembersById
id: v1SelectionAgent_RemoveSelectionMembersById
---

# POST Agents/Selection/RemoveSelectionMembersById

```http
POST /api/v1/Agents/Selection/RemoveSelectionMembersById
```

Removes members from the selection as specified in the collection of entity ids.

The ids can be a collection of sale ids, or other supported types.





## Query String Parameters

| Parameter Name | Type |  Description |
|----------------|------|--------------|
| $select | string |  Optional comma separated list of properties to include in the result. Other fields are then nulled out to reduce payload size: "Name,department,category". Default = show all fields. |

```http
POST /api/v1/Agents/Selection/RemoveSelectionMembersById?$select=name,department,category/id
```


## Request Headers

| Parameter Name | Description |
|----------------|-------------|
| Authorization  | Supports 'Basic', 'SoTicket' and 'Bearer' schemes, depending on installation type. |
| X-XSRF-TOKEN   | If not using Authorization header, you must provide XSRF value from cookie or hidden input field |
| Content-Type | Content-type of the request body: `application/json`, `text/json`, `application/xml`, `text/xml`, `application/x-www-form-urlencoded`, `application/json-patch+json`, `application/merge-patch+json` |
| SO-AppToken | The application token that identifies the partner app. Used when calling Online WebAPI from a server. |

## Request Body: request  

SelectionId, Ids 

| Property Name | Type |  Description |
|----------------|------|--------------|
| SelectionId | int32 |  |
| Ids | array |  |


## Response


| Response | Description |
|----------------|-------------|
| 204 | No Content |