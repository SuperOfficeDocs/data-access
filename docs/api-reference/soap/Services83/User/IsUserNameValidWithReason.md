---
uid: services83-user-isusernamevalidwithreason
title: Services83.UserAgent.IsUserNameValidWithReason SOAP
Generated: true
---

# Services83 User IsUserNameValidWithReason SOAP

SOAP request and response examples **Remote/Services83/User.svc**
Implemented by the <see cref="M:SuperOffice.Services83.IUserAgent.IsUserNameValidWithReason">SuperOffice.Services83.IUserAgent.IsUserNameValidWithReason</see> method.

## IsUserNameValidWithReason



* **associateId:** 
* **type:** 
* **personId:** 
* **userName:** 



[WSDL file for Services83/User](../Services83-User.md)

Obtain a ticket from the [Services83/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## IsUserNameValidWithReason Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices832="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices831="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:User="http://www.superoffice.net/ws/crm/NetServer/Services83">
  <User:ApplicationToken>1234567-1234-9876</User:ApplicationToken>
  <User:Credentials>
    <User:Ticket>7T:1234abcxyzExample==</User:Ticket>
  </User:Credentials>
 <SOAP-ENV:Body>
   <User:IsUserNameValidWithReason>
    <User:AssociateId xsi:type="xsd:int">0</User:AssociateId>
    <User:Type xsi:type="User:UserType">Unknown</User:Type>
    <User:PersonId xsi:type="xsd:int">0</User:PersonId>
    <User:UserName xsi:type="xsd:string"></User:UserName>
   </User:IsUserNameValidWithReason>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## IsUserNameValidWithReason Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices832="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices831="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:User="http://www.superoffice.net/ws/crm/NetServer/Services83">
 <SOAP-ENV:Body>
  <User:IsUserNameValidWithReasonResponse>
   <User:Response xsi:type="User:UserValidationResult">
    <User:Reason xsi:type="xsd:string"></User:Reason>
    <User:Result xsi:type="xsd:boolean">false</User:Result>
   </User:Response>
  </User:IsUserNameValidWithReasonResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
