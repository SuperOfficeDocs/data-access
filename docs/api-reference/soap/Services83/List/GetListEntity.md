---
uid: services83-list-getlistentity
title: Services83.ListAgent.GetListEntity SOAP
Generated: true
---

# Services83 List GetListEntity SOAP

SOAP request and response examples **Remote/Services83/List.svc**
Implemented by the <see cref="M:SuperOffice.Services83.IListAgent.GetListEntity">SuperOffice.Services83.IListAgent.GetListEntity</see> method.

## GetListEntity

Gets a ListEntity object.

* **listEntityId:** The identifier of the ListEntity object

**Returns:** ListEntity


[WSDL file for Services83/List](../Services83-List.md)

Obtain a ticket from the [Services83/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## GetListEntity Request

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
   <List:GetListEntity>
    <List:ListEntityId xsi:type="xsd:int">0</List:ListEntityId>
   </List:GetListEntity>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## GetListEntity Response

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
  <List:GetListEntityResponse>
   <List:Response xsi:type="List:ListEntity">
    <List:Id xsi:type="xsd:int">0</List:Id>
    <List:Name xsi:type="xsd:string"></List:Name>
    <List:Tooltip xsi:type="xsd:string"></List:Tooltip>
    <List:Deleted xsi:type="xsd:boolean">false</List:Deleted>
    <List:Rank xsi:type="xsd:int">0</List:Rank>
    <List:IsCustomList xsi:type="xsd:boolean">false</List:IsCustomList>
    <List:IsMDOList xsi:type="xsd:boolean">false</List:IsMDOList>
    <List:UseGroupsAndHeadings xsi:type="xsd:boolean">false</List:UseGroupsAndHeadings>
    <List:ListType xsi:type="xsd:string"></List:ListType>
    <List:InUseByUserDefinedFields xsi:type="xsd:boolean">false</List:InUseByUserDefinedFields>
   </List:Response>
  </List:GetListEntityResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
