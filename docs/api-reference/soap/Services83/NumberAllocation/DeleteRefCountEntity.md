---
uid: services83-numberallocation-deleterefcountentity
title: Services83.NumberAllocationAgent.DeleteRefCountEntity SOAP
Generated: true
---

# Services83 NumberAllocation DeleteRefCountEntity SOAP

SOAP request and response examples **Remote/Services83/NumberAllocation.svc**
Implemented by the <see cref="M:SuperOffice.Services83.INumberAllocationAgent.DeleteRefCountEntity">SuperOffice.Services83.INumberAllocationAgent.DeleteRefCountEntity</see> method.

## DeleteRefCountEntity

Deletes the RefCountEntity

* **refCountEntityId:** The identity of the RefCountEntity



[WSDL file for Services83/NumberAllocation](../Services83-NumberAllocation.md)

Obtain a ticket from the [Services83/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## DeleteRefCountEntity Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices831="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:NumberAllocation="http://www.superoffice.net/ws/crm/NetServer/Services83">
  <NumberAllocation:ApplicationToken>1234567-1234-9876</NumberAllocation:ApplicationToken>
  <NumberAllocation:Credentials>
    <NumberAllocation:Ticket>7T:1234abcxyzExample==</NumberAllocation:Ticket>
  </NumberAllocation:Credentials>
 <SOAP-ENV:Body>
   <NumberAllocation:DeleteRefCountEntity>
    <NumberAllocation:RefCountEntityId xsi:type="xsd:int">0</NumberAllocation:RefCountEntityId>
   </NumberAllocation:DeleteRefCountEntity>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## DeleteRefCountEntity Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices831="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:NumberAllocation="http://www.superoffice.net/ws/crm/NetServer/Services83">
 <SOAP-ENV:Body>
  <NumberAllocation:DeleteRefCountEntityResponse>
  </NumberAllocation:DeleteRefCountEntityResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
