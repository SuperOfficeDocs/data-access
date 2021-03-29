---
uid: services83-erpsync-getconnection
title: Services83.ErpSyncAgent.GetConnection SOAP
Generated: true
---

# Services83 ErpSync GetConnection SOAP

SOAP request and response examples **Remote/Services83/ErpSync.svc**
Implemented by the <see cref="M:SuperOffice.Services83.IErpSyncAgent.GetConnection">SuperOffice.Services83.IErpSyncAgent.GetConnection</see> method.

## GetConnection

Returns the specified connection.

* **erpConnectionId:** Primary key of the connection

**Returns:** The connection


[WSDL file for Services83/ErpSync](../Services83-ErpSync.md)

Obtain a ticket from the [Services83/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## GetConnection Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices832="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices831="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:ErpSync="http://www.superoffice.net/ws/crm/NetServer/Services83">
  <ErpSync:ApplicationToken>1234567-1234-9876</ErpSync:ApplicationToken>
  <ErpSync:Credentials>
    <ErpSync:Ticket>7T:1234abcxyzExample==</ErpSync:Ticket>
  </ErpSync:Credentials>
 <SOAP-ENV:Body>
   <ErpSync:GetConnection>
    <ErpSync:ErpConnectionId xsi:type="xsd:int">0</ErpSync:ErpConnectionId>
   </ErpSync:GetConnection>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## GetConnection Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices832="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices831="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:ErpSync="http://www.superoffice.net/ws/crm/NetServer/Services83">
 <SOAP-ENV:Body>
  <ErpSync:GetConnectionResponse>
   <ErpSync:Response xsi:type="ErpSync:ErpConnection">
    <ErpSync:ErpConnectionId xsi:type="xsd:int">0</ErpSync:ErpConnectionId>
    <ErpSync:ErpConnectorId xsi:type="xsd:int">0</ErpSync:ErpConnectorId>
    <ErpSync:DisplayName xsi:type="xsd:string"></ErpSync:DisplayName>
    <ErpSync:DisplayDescription xsi:type="xsd:string"></ErpSync:DisplayDescription>
    <ErpSync:Active xsi:type="xsd:boolean">false</ErpSync:Active>
    <ErpSync:ConnectionId xsi:type="xsd:string"></ErpSync:ConnectionId>
    <ErpSync:MostRecentTimestamp xsi:type="xsd:string"></ErpSync:MostRecentTimestamp>
    <ErpSync:ConfigFields xsi:type="ErpSync:StringDictionary">
     <ErpSync:StringKeyValuePair>
      <ErpSync:Key xsi:type="xsd:string"></ErpSync:Key>
      <ErpSync:Value xsi:type="xsd:string"></ErpSync:Value>
     </ErpSync:StringKeyValuePair>
    </ErpSync:ConfigFields>
    <ErpSync:Deleted xsi:type="xsd:boolean">false</ErpSync:Deleted>
    <ErpSync:AllAccess xsi:type="xsd:boolean">false</ErpSync:AllAccess>
    <ErpSync:UserGroupAccessIds xsi:type="NetServerServices832:ArrayOfint">
     <NetServerServices832:int xsi:type="xsd:int">0</NetServerServices832:int>
    </ErpSync:UserGroupAccessIds>
    <ErpSync:AssociateAccessIds xsi:type="NetServerServices832:ArrayOfint">
     <NetServerServices832:int xsi:type="xsd:int">0</NetServerServices832:int>
    </ErpSync:AssociateAccessIds>
   </ErpSync:Response>
  </ErpSync:GetConnectionResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
