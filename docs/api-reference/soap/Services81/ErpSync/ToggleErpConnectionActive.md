---
uid: services81-erpsync-toggleerpconnectionactive
title: Services81.ErpSyncAgent.ToggleErpConnectionActive SOAP
Generated: true
---

# Services81 ErpSync ToggleErpConnectionActive SOAP

SOAP request and response examples **Remote/Services81/ErpSync.svc**
Implemented by the <see cref="M:SuperOffice.Services81.IErpSyncAgent.ToggleErpConnectionActive">SuperOffice.Services81.IErpSyncAgent.ToggleErpConnectionActive</see> method.

## ToggleErpConnectionActive

Toggles the Active state of the connection

* **erpConnectionId:** Primary key of the erp connection

**Returns:** Contains the reason for why the toggle failed. Empty if operation was successful


[WSDL file for Services81/ErpSync](../Services81-ErpSync.md)

Obtain a ticket from the [Services81/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## ToggleErpConnectionActive Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices812="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices811="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:ErpSync="http://www.superoffice.net/ws/crm/NetServer/Services81">
  <ErpSync:ApplicationToken>1234567-1234-9876</ErpSync:ApplicationToken>
  <ErpSync:Credentials>
    <ErpSync:Ticket>7T:1234abcxyzExample==</ErpSync:Ticket>
  </ErpSync:Credentials>
 <SOAP-ENV:Body>
   <ErpSync:ToggleErpConnectionActive>
    <ErpSync:ErpConnectionId xsi:type="xsd:int">0</ErpSync:ErpConnectionId>
   </ErpSync:ToggleErpConnectionActive>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## ToggleErpConnectionActive Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices812="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices811="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:ErpSync="http://www.superoffice.net/ws/crm/NetServer/Services81">
 <SOAP-ENV:Body>
  <ErpSync:ToggleErpConnectionActiveResponse>
   <ErpSync:Response xsi:type="NetServerServices812:ArrayOfstring">
    <NetServerServices812:string xsi:type="xsd:string"></NetServerServices812:string>
   </ErpSync:Response>
  </ErpSync:ToggleErpConnectionActiveResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
