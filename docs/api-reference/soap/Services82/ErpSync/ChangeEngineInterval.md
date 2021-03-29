---
uid: services82-erpsync-changeengineinterval
title: Services82.ErpSyncAgent.ChangeEngineInterval SOAP
Generated: true
---

# Services82 ErpSync ChangeEngineInterval SOAP

SOAP request and response examples **Remote/Services82/ErpSync.svc**
Implemented by the <see cref="M:SuperOffice.Services82.IErpSyncAgent.ChangeEngineInterval">SuperOffice.Services82.IErpSyncAgent.ChangeEngineInterval</see> method.

## ChangeEngineInterval

Change the interval for each run of the Sync Engine

* **interval:** The run interval for the engine



[WSDL file for Services82/ErpSync](../Services82-ErpSync.md)

Obtain a ticket from the [Services82/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## ChangeEngineInterval Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices822="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices821="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:ErpSync="http://www.superoffice.net/ws/crm/NetServer/Services82">
  <ErpSync:ApplicationToken>1234567-1234-9876</ErpSync:ApplicationToken>
  <ErpSync:Credentials>
    <ErpSync:Ticket>7T:1234abcxyzExample==</ErpSync:Ticket>
  </ErpSync:Credentials>
 <SOAP-ENV:Body>
   <ErpSync:ChangeEngineInterval>
    <ErpSync:Interval xsi:type="NetServerServices821:duration"></ErpSync:Interval>
   </ErpSync:ChangeEngineInterval>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## ChangeEngineInterval Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices822="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices821="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:ErpSync="http://www.superoffice.net/ws/crm/NetServer/Services82">
 <SOAP-ENV:Body>
  <ErpSync:ChangeEngineIntervalResponse>
  </ErpSync:ChangeEngineIntervalResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
