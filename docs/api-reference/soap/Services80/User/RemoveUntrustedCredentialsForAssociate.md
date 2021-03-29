---
uid: services80-user-removeuntrustedcredentialsforassociate
title: Services80.UserAgent.RemoveUntrustedCredentialsForAssociate SOAP
Generated: true
---

# Services80 User RemoveUntrustedCredentialsForAssociate SOAP

SOAP request and response examples **Remote/Services80/User.svc**
Implemented by the <see cref="M:SuperOffice.Services80.IUserAgent.RemoveUntrustedCredentialsForAssociate">SuperOffice.Services80.IUserAgent.RemoveUntrustedCredentialsForAssociate</see> method.

## RemoveUntrustedCredentialsForAssociate

Remove a credentials entry for a specified user.

* **associateId:** Id of user to remove credentials for.
* **type:** Type of credential(Ex: "imap", "smtp")
* **publicValue:** PublicValue field of credentials to remove.



[WSDL file for Services80/User](../Services80-User.md)

Obtain a ticket from the [Services80/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## RemoveUntrustedCredentialsForAssociate Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices802="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices801="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:User="http://www.superoffice.net/ws/crm/NetServer/Services80">
  <User:ApplicationToken>1234567-1234-9876</User:ApplicationToken>
  <User:Credentials>
    <User:Ticket>7T:1234abcxyzExample==</User:Ticket>
  </User:Credentials>
 <SOAP-ENV:Body>
   <User:RemoveUntrustedCredentialsForAssociate>
    <User:AssociateId xsi:type="xsd:int">0</User:AssociateId>
    <User:Type xsi:type="xsd:string"></User:Type>
    <User:PublicValue xsi:type="xsd:string"></User:PublicValue>
   </User:RemoveUntrustedCredentialsForAssociate>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## RemoveUntrustedCredentialsForAssociate Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices802="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices801="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:User="http://www.superoffice.net/ws/crm/NetServer/Services80">
 <SOAP-ENV:Body>
  <User:RemoveUntrustedCredentialsForAssociateResponse>
  </User:RemoveUntrustedCredentialsForAssociateResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
