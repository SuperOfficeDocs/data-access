---
uid: services86-audience-getconfigparameteronperson
title: Services86.AudienceAgent.GetConfigParameterOnPerson SOAP
Generated: true
---

# Services86 Audience GetConfigParameterOnPerson SOAP

SOAP request and response examples **Remote/Services86/Audience.svc**
Implemented by the <see cref="M:SuperOffice.Services86.IAudienceAgent.GetConfigParameterOnPerson">SuperOffice.Services86.IAudienceAgent.GetConfigParameterOnPerson</see> method.

## GetConfigParameterOnPerson

Gets an Audience configuration parameter with the specified configuration parameter name on the person specified

* **parameterName:** The name of the Audience configuration parameter
* **personId:** Id of the person the parameter belongs to

**Returns:** The Audience configuration parameter.


[WSDL file for Services86/Audience](../Services86-Audience.md)

Obtain a ticket from the [Services86/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## GetConfigParameterOnPerson Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices861="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Audience="http://www.superoffice.net/ws/crm/NetServer/Services86">
  <Audience:ApplicationToken>1234567-1234-9876</Audience:ApplicationToken>
  <Audience:Credentials>
    <Audience:Ticket>7T:1234abcxyzExample==</Audience:Ticket>
  </Audience:Credentials>
 <SOAP-ENV:Body>
   <Audience:GetConfigParameterOnPerson>
    <Audience:ParameterName xsi:type="xsd:string"></Audience:ParameterName>
    <Audience:PersonId xsi:type="xsd:int">0</Audience:PersonId>
   </Audience:GetConfigParameterOnPerson>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## GetConfigParameterOnPerson Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices861="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Audience="http://www.superoffice.net/ws/crm/NetServer/Services86">
 <SOAP-ENV:Body>
  <Audience:GetConfigParameterOnPersonResponse>
   <Audience:Response xsi:type="Audience:AudienceConfigParameter">
    <Audience:AudienceLayoutId xsi:type="xsd:int">0</Audience:AudienceLayoutId>
    <Audience:Name xsi:type="xsd:string"></Audience:Name>
    <Audience:Value xsi:type="xsd:string"></Audience:Value>
    <Audience:CreatedDate xsi:type="xsd:dateTime">2021-03-25T21:36:03Z</Audience:CreatedDate>
    <Audience:UpdatedDate xsi:type="xsd:dateTime">2021-03-25T21:36:03Z</Audience:UpdatedDate>
    <Audience:CreatedBy xsi:type="xsd:string"></Audience:CreatedBy>
    <Audience:UpdatedBy xsi:type="xsd:string"></Audience:UpdatedBy>
   </Audience:Response>
  </Audience:GetConfigParameterOnPersonResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
