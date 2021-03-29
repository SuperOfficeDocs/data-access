---
uid: services75-audience-getconfigparametervalue
title: Services75.AudienceAgent.GetConfigParameterValue SOAP
Generated: true
---

# Services75 Audience GetConfigParameterValue SOAP

SOAP request and response examples **Remote/Services75/Audience.svc**
Implemented by the <see cref="M:SuperOffice.Services75.IAudienceAgent.GetConfigParameterValue">SuperOffice.Services75.IAudienceAgent.GetConfigParameterValue</see> method.

## GetConfigParameterValue

Gets the string value of an Audience configuration parameter belonging to a given Audience layout with the specified configuration parameter name

* **layoutName:** Name of the Audience layout instance
* **parameterName:** The name of the Audience configuration parameter

**Returns:** The string value of the Audience configuration parameter.


[WSDL file for Services75/Audience](../Services75-Audience.md)

Obtain a ticket from the [Services75/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## GetConfigParameterValue Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices751="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Audience="http://www.superoffice.net/ws/crm/NetServer/Services75">
  <Audience:ApplicationToken>1234567-1234-9876</Audience:ApplicationToken>
  <Audience:Credentials>
    <Audience:Ticket>7T:1234abcxyzExample==</Audience:Ticket>
  </Audience:Credentials>
 <SOAP-ENV:Body>
   <Audience:GetConfigParameterValue>
    <Audience:LayoutName xsi:type="xsd:string"></Audience:LayoutName>
    <Audience:ParameterName xsi:type="xsd:string"></Audience:ParameterName>
   </Audience:GetConfigParameterValue>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## GetConfigParameterValue Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices751="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Audience="http://www.superoffice.net/ws/crm/NetServer/Services75">
 <SOAP-ENV:Body>
  <Audience:GetConfigParameterValueResponse>
   <Audience:Response xsi:type="xsd:string"></Audience:Response>
  </Audience:GetConfigParameterValueResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
