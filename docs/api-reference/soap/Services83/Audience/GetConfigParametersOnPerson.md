---
uid: services83-audience-getconfigparametersonperson
title: Services83.AudienceAgent.GetConfigParametersOnPerson SOAP
Generated: true
---

# Services83 Audience GetConfigParametersOnPerson SOAP

SOAP request and response examples **Remote/Services83/Audience.svc**
Implemented by the <see cref="M:SuperOffice.Services83.IAudienceAgent.GetConfigParametersOnPerson">SuperOffice.Services83.IAudienceAgent.GetConfigParametersOnPerson</see> method.

## GetConfigParametersOnPerson

Gets the Audience configuration parameters belonging to the person specified

* **personId:** Id of the person the parameter belongs to

**Returns:** Array of Audience configuration parameters.


[WSDL file for Services83/Audience](../Services83-Audience.md)

Obtain a ticket from the [Services83/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## GetConfigParametersOnPerson Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices831="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Audience="http://www.superoffice.net/ws/crm/NetServer/Services83">
  <Audience:ApplicationToken>1234567-1234-9876</Audience:ApplicationToken>
  <Audience:Credentials>
    <Audience:Ticket>7T:1234abcxyzExample==</Audience:Ticket>
  </Audience:Credentials>
 <SOAP-ENV:Body>
   <Audience:GetConfigParametersOnPerson>
    <Audience:PersonId xsi:type="xsd:int">0</Audience:PersonId>
   </Audience:GetConfigParametersOnPerson>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## GetConfigParametersOnPerson Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices831="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Audience="http://www.superoffice.net/ws/crm/NetServer/Services83">
 <SOAP-ENV:Body>
  <Audience:GetConfigParametersOnPersonResponse>
   <Audience:Response xsi:type="Audience:ArrayOfAudienceConfigParameter">
    <Audience:AudienceConfigParameter xsi:type="Audience:AudienceConfigParameter">
     <Audience:AudienceLayoutId xsi:type="xsd:int">0</Audience:AudienceLayoutId>
     <Audience:Name xsi:type="xsd:string"></Audience:Name>
     <Audience:Value xsi:type="xsd:string"></Audience:Value>
     <Audience:CreatedDate xsi:type="xsd:dateTime">2021-03-25T21:35:00Z</Audience:CreatedDate>
     <Audience:UpdatedDate xsi:type="xsd:dateTime">2021-03-25T21:35:00Z</Audience:UpdatedDate>
     <Audience:CreatedBy xsi:type="xsd:string"></Audience:CreatedBy>
     <Audience:UpdatedBy xsi:type="xsd:string"></Audience:UpdatedBy>
    </Audience:AudienceConfigParameter>
   </Audience:Response>
  </Audience:GetConfigParametersOnPersonResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
