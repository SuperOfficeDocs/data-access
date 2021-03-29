---
uid: services82-replication-getarea
title: Services82.ReplicationAgent.GetArea SOAP
Generated: true
---

# Services82 Replication GetArea SOAP

SOAP request and response examples **Remote/Services82/Replication.svc**
Implemented by the <see cref="M:SuperOffice.Services82.IReplicationAgent.GetArea">SuperOffice.Services82.IReplicationAgent.GetArea</see> method.

## GetArea

Gets a Area object.

* **areaId:** The identifier of the Area object

**Returns:** Area


[WSDL file for Services82/Replication](../Services82-Replication.md)

Obtain a ticket from the [Services82/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## GetArea Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices822="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices821="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Replication="http://www.superoffice.net/ws/crm/NetServer/Services82">
  <Replication:ApplicationToken>1234567-1234-9876</Replication:ApplicationToken>
  <Replication:Credentials>
    <Replication:Ticket>7T:1234abcxyzExample==</Replication:Ticket>
  </Replication:Credentials>
 <SOAP-ENV:Body>
   <Replication:GetArea>
    <Replication:AreaId xsi:type="xsd:int">0</Replication:AreaId>
   </Replication:GetArea>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## GetArea Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices822="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices821="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Replication="http://www.superoffice.net/ws/crm/NetServer/Services82">
 <SOAP-ENV:Body>
  <Replication:GetAreaResponse>
   <Replication:Response xsi:type="Replication:Area">
    <Replication:AreaId xsi:type="xsd:int">0</Replication:AreaId>
    <Replication:Name xsi:type="xsd:string"></Replication:Name>
    <Replication:MaxDataAge xsi:type="xsd:short">0</Replication:MaxDataAge>
    <Replication:NumberOfUsers xsi:type="xsd:int">0</Replication:NumberOfUsers>
    <Replication:NumberOfLogins xsi:type="xsd:int">0</Replication:NumberOfLogins>
    <Replication:FreetextEnabeled xsi:type="xsd:boolean">false</Replication:FreetextEnabeled>
   </Replication:Response>
  </Replication:GetAreaResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
