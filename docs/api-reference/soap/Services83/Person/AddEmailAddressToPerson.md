---
uid: services83-person-addemailaddresstoperson
title: Services83.PersonAgent.AddEmailAddressToPerson SOAP
Generated: true
---

# Services83 Person AddEmailAddressToPerson SOAP

SOAP request and response examples **Remote/Services83/Person.svc**
Implemented by the <see cref="M:SuperOffice.Services83.IPersonAgent.AddEmailAddressToPerson">SuperOffice.Services83.IPersonAgent.AddEmailAddressToPerson</see> method.

## AddEmailAddressToPerson

Sets the primary email address on person, possibly re-ranking email addresses accordingly.

* **personId:** Person id of the person
* **emailAddress:** The email address to set as primary email address
* **setAsPrimaryEmail:** True if the address shall be primary email address (have rank == 1)



[WSDL file for Services83/Person](../Services83-Person.md)

Obtain a ticket from the [Services83/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## AddEmailAddressToPerson Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices832="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices831="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Person="http://www.superoffice.net/ws/crm/NetServer/Services83">
  <Person:ApplicationToken>1234567-1234-9876</Person:ApplicationToken>
  <Person:Credentials>
    <Person:Ticket>7T:1234abcxyzExample==</Person:Ticket>
  </Person:Credentials>
 <SOAP-ENV:Body>
   <Person:AddEmailAddressToPerson>
    <Person:PersonId xsi:type="xsd:int">0</Person:PersonId>
    <Person:EmailAddress xsi:type="xsd:string"></Person:EmailAddress>
    <Person:SetAsPrimaryEmail xsi:type="xsd:boolean">false</Person:SetAsPrimaryEmail>
   </Person:AddEmailAddressToPerson>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## AddEmailAddressToPerson Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices832="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices831="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Person="http://www.superoffice.net/ws/crm/NetServer/Services83">
 <SOAP-ENV:Body>
  <Person:AddEmailAddressToPersonResponse>
  </Person:AddEmailAddressToPersonResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
