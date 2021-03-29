---
uid: services82-erpsync-testconnectorurl
title: Services82.ErpSyncAgent.TestConnectorUrl SOAP
Generated: true
---

# Services82 ErpSync TestConnectorUrl SOAP

SOAP request and response examples **Remote/Services82/ErpSync.svc**
Implemented by the <see cref="M:SuperOffice.Services82.IErpSyncAgent.TestConnectorUrl">SuperOffice.Services82.IErpSyncAgent.TestConnectorUrl</see> method.

## TestConnectorUrl

Test if connector urls anwers

* **url:** The url to test connection on

**Returns:** Enum response says ok or what is wrong


[WSDL file for Services82/ErpSync](../Services82-ErpSync.md)

Obtain a ticket from the [Services82/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## TestConnectorUrl Request

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
   <ErpSync:TestConnectorUrl>
    <ErpSync:Url xsi:type="xsd:string"></ErpSync:Url>
   </ErpSync:TestConnectorUrl>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## TestConnectorUrl Response

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
  <ErpSync:TestConnectorUrlResponse>
   <ErpSync:Response xsi:type="ErpSync:ErpSyncResponseCode">NoError</ErpSync:Response>
  </ErpSync:TestConnectorUrlResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
