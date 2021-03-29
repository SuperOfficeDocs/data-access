---
uid: services83-diagnostics-logviewstate
title: Services83.DiagnosticsAgent.LogViewState SOAP
Generated: true
---

# Services83 Diagnostics LogViewState SOAP

SOAP request and response examples **Remote/Services83/Diagnostics.svc**
Implemented by the <see cref="M:SuperOffice.Services83.IDiagnosticsAgent.LogViewState">SuperOffice.Services83.IDiagnosticsAgent.LogViewState</see> method.

## LogViewState

Log a change in view state. The granularity of the logging depends on the current configuration. This call returns asynchronously, leaving the server to finish processing later on.

* **viewState:** Current view state to be logged



[WSDL file for Services83/Diagnostics](../Services83-Diagnostics.md)

Obtain a ticket from the [Services83/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## LogViewState Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices832="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices831="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Diagnostics="http://www.superoffice.net/ws/crm/NetServer/Services83">
  <Diagnostics:ApplicationToken>1234567-1234-9876</Diagnostics:ApplicationToken>
  <Diagnostics:Credentials>
    <Diagnostics:Ticket>7T:1234abcxyzExample==</Diagnostics:Ticket>
  </Diagnostics:Credentials>
 <SOAP-ENV:Body>
   <Diagnostics:LogViewState>
    <Diagnostics:ViewState xsi:type="xsd:string"></Diagnostics:ViewState>
   </Diagnostics:LogViewState>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## LogViewState Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices832="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices831="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Diagnostics="http://www.superoffice.net/ws/crm/NetServer/Services83">
 <SOAP-ENV:Body>
  <Diagnostics:LogViewStateResponse>
  </Diagnostics:LogViewStateResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
