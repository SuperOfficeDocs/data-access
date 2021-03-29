---
uid: services83-list-getfromlistdefinition
title: Services83.ListAgent.GetFromListDefinition SOAP
Generated: true
---

# Services83 List GetFromListDefinition SOAP

SOAP request and response examples **Remote/Services83/List.svc**
Implemented by the <see cref="M:SuperOffice.Services83.IListAgent.GetFromListDefinition">SuperOffice.Services83.IListAgent.GetFromListDefinition</see> method.

## GetFromListDefinition

Get a list item for the specified list defintion

* **id:** The identity of the list item to load
* **udListDefinitionId:** The id of the list definition, indicating which list to get the item from. Negative numbers indicate TableNumber value instead of UDListDefId. e.g. -64 = category.

**Returns:** The loaded list item


[WSDL file for Services83/List](../Services83-List.md)

Obtain a ticket from the [Services83/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## GetFromListDefinition Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices832="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices831="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:List="http://www.superoffice.net/ws/crm/NetServer/Services83">
  <List:ApplicationToken>1234567-1234-9876</List:ApplicationToken>
  <List:Credentials>
    <List:Ticket>7T:1234abcxyzExample==</List:Ticket>
  </List:Credentials>
 <SOAP-ENV:Body>
   <List:GetFromListDefinition>
    <List:Id xsi:type="xsd:int">0</List:Id>
    <List:UdListDefinitionId xsi:type="xsd:int">0</List:UdListDefinitionId>
   </List:GetFromListDefinition>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## GetFromListDefinition Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices832="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices831="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:List="http://www.superoffice.net/ws/crm/NetServer/Services83">
 <SOAP-ENV:Body>
  <List:GetFromListDefinitionResponse>
   <List:Response xsi:type="List:ListItemEntity">
    <List:Id xsi:type="xsd:int">0</List:Id>
    <List:Name xsi:type="xsd:string"></List:Name>
    <List:Tooltip xsi:type="xsd:string"></List:Tooltip>
    <List:Deleted xsi:type="xsd:boolean">false</List:Deleted>
    <List:UdListDefinitionId xsi:type="xsd:int">0</List:UdListDefinitionId>
    <List:Rank xsi:type="xsd:int">0</List:Rank>
   </List:Response>
  </List:GetFromListDefinitionResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
