---
uid: services83-erpsync-saveerpsyncconnectorentity
title: Services83.ErpSyncAgent.SaveErpSyncConnectorEntity SOAP
Generated: true
---

# Services83 ErpSync SaveErpSyncConnectorEntity SOAP

SOAP request and response examples **Remote/Services83/ErpSync.svc**
Implemented by the <see cref="M:SuperOffice.Services83.IErpSyncAgent.SaveErpSyncConnectorEntity">SuperOffice.Services83.IErpSyncAgent.SaveErpSyncConnectorEntity</see> method.

## SaveErpSyncConnectorEntity

Updates the existing ErpSyncConnectorEntity or creates a new ErpSyncConnectorEntity if the id parameter is 0.

* **erpSyncConnectorEntity:** The ErpSyncConnectorEntity that is saved.

**Returns:** New or updated ErpSyncConnectorEntity


[WSDL file for Services83/ErpSync](../Services83-ErpSync.md)

Obtain a ticket from the [Services83/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## SaveErpSyncConnectorEntity Request

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
   <ErpSync:SaveErpSyncConnectorEntity>
    <ErpSync:ErpSyncConnectorEntity xsi:type="ErpSync:ErpSyncConnectorEntity">
     <ErpSync:ErpConnectorId xsi:type="xsd:int">0</ErpSync:ErpConnectorId>
     <ErpSync:DisplayName xsi:type="xsd:string"></ErpSync:DisplayName>
     <ErpSync:URL xsi:type="xsd:string"></ErpSync:URL>
     <ErpSync:Deleted xsi:type="xsd:boolean">false</ErpSync:Deleted>
    </ErpSync:ErpSyncConnectorEntity>
   </ErpSync:SaveErpSyncConnectorEntity>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## SaveErpSyncConnectorEntity Response

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
  <ErpSync:SaveErpSyncConnectorEntityResponse>
   <ErpSync:Response xsi:type="ErpSync:ErpSyncConnectorEntity">
    <ErpSync:ErpConnectorId xsi:type="xsd:int">0</ErpSync:ErpConnectorId>
    <ErpSync:DisplayName xsi:type="xsd:string"></ErpSync:DisplayName>
    <ErpSync:URL xsi:type="xsd:string"></ErpSync:URL>
    <ErpSync:Deleted xsi:type="xsd:boolean">false</ErpSync:Deleted>
   </ErpSync:Response>
  </ErpSync:SaveErpSyncConnectorEntityResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
