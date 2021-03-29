---
uid: services80-resource-deleteresourcesubstitution
title: Services80.ResourceAgent.DeleteResourceSubstitution SOAP
Generated: true
---

# Services80 Resource DeleteResourceSubstitution SOAP

SOAP request and response examples **Remote/Services80/Resource.svc**
Implemented by the <see cref="M:SuperOffice.Services80.IResourceAgent.DeleteResourceSubstitution">SuperOffice.Services80.IResourceAgent.DeleteResourceSubstitution</see> method.

## DeleteResourceSubstitution

Permanentely delete a resource substitution for one or more cultures

* **resourceName:** The name of the resource, without any brackets
* **culture:** The .NET culture string; if blank, then ALL substitutions for this resource will be dropped

**Returns:** This method has no return value


[WSDL file for Services80/Resource](../Services80-Resource.md)

Obtain a ticket from the [Services80/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## DeleteResourceSubstitution Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices802="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices801="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Resource="http://www.superoffice.net/ws/crm/NetServer/Services80">
  <Resource:ApplicationToken>1234567-1234-9876</Resource:ApplicationToken>
  <Resource:Credentials>
    <Resource:Ticket>7T:1234abcxyzExample==</Resource:Ticket>
  </Resource:Credentials>
 <SOAP-ENV:Body>
   <Resource:DeleteResourceSubstitution>
    <Resource:ResourceName xsi:type="xsd:string"></Resource:ResourceName>
    <Resource:Culture xsi:type="xsd:string"></Resource:Culture>
   </Resource:DeleteResourceSubstitution>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## DeleteResourceSubstitution Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices802="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices801="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Resource="http://www.superoffice.net/ws/crm/NetServer/Services80">
 <SOAP-ENV:Body>
  <Resource:DeleteResourceSubstitutionResponse>
  </Resource:DeleteResourceSubstitutionResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
