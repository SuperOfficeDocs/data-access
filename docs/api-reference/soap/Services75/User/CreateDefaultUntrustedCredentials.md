---
uid: services75-user-createdefaultuntrustedcredentials
title: Services75.UserAgent.CreateDefaultUntrustedCredentials SOAP
Generated: true
---

# Services75 User CreateDefaultUntrustedCredentials SOAP

SOAP request and response examples **Remote/Services75/User.svc**
Implemented by the <see cref="M:SuperOffice.Services75.IUserAgent.CreateDefaultUntrustedCredentials">SuperOffice.Services75.IUserAgent.CreateDefaultUntrustedCredentials</see> method.

## CreateDefaultUntrustedCredentials

Loading default values into a new UntrustedCredentials.
NetServer calculates default values (e.g. Country) on the entity, which is required when creating/storing a new instance


**Returns:** New UntrustedCredentials with default values


[WSDL file for Services75/User](../Services75-User.md)

Obtain a ticket from the [Services75/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## CreateDefaultUntrustedCredentials Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices752="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices751="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:User="http://www.superoffice.net/ws/crm/NetServer/Services75">
  <User:ApplicationToken>1234567-1234-9876</User:ApplicationToken>
  <User:Credentials>
    <User:Ticket>7T:1234abcxyzExample==</User:Ticket>
  </User:Credentials>
 <SOAP-ENV:Body>
   <User:CreateDefaultUntrustedCredentials>
   </User:CreateDefaultUntrustedCredentials>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## CreateDefaultUntrustedCredentials Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices752="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices751="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:User="http://www.superoffice.net/ws/crm/NetServer/Services75">
 <SOAP-ENV:Body>
  <User:CreateDefaultUntrustedCredentialsResponse>
   <User:Response xsi:type="User:UntrustedCredentials">
    <User:ValidFrom xsi:type="xsd:dateTime">2021-03-25T21:34:02Z</User:ValidFrom>
    <User:ValidTo xsi:type="xsd:dateTime">2021-03-25T21:34:02Z</User:ValidTo>
    <User:Comment xsi:type="xsd:string"></User:Comment>
    <User:SecretValue xsi:type="xsd:string"></User:SecretValue>
    <User:PublicValue xsi:type="xsd:string"></User:PublicValue>
    <User:IsActive xsi:type="xsd:boolean">false</User:IsActive>
   </User:Response>
  </User:CreateDefaultUntrustedCredentialsResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
