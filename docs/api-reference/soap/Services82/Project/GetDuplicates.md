---
uid: services82-project-getduplicates
title: Services82.ProjectAgent.GetDuplicates SOAP
Generated: true
---

# Services82 Project GetDuplicates SOAP

SOAP request and response examples **Remote/Services82/Project.svc**
Implemented by the <see cref="M:SuperOffice.Services82.IProjectAgent.GetDuplicates">SuperOffice.Services82.IProjectAgent.GetDuplicates</see> method.

## GetDuplicates

Get duplicates(exact or similar in the database) based on the name

* **name:** Name used for lookup

**Returns:** Any records matching the specified name


[WSDL file for Services82/Project](../Services82-Project.md)

Obtain a ticket from the [Services82/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## GetDuplicates Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices822="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices821="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Project="http://www.superoffice.net/ws/crm/NetServer/Services82">
  <Project:ApplicationToken>1234567-1234-9876</Project:ApplicationToken>
  <Project:Credentials>
    <Project:Ticket>7T:1234abcxyzExample==</Project:Ticket>
  </Project:Credentials>
 <SOAP-ENV:Body>
   <Project:GetDuplicates>
    <Project:Name xsi:type="xsd:string"></Project:Name>
   </Project:GetDuplicates>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## GetDuplicates Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices822="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices821="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Project="http://www.superoffice.net/ws/crm/NetServer/Services82">
 <SOAP-ENV:Body>
  <Project:GetDuplicatesResponse>
   <Project:Response xsi:type="Project:ArrayOfDuplicateEntry">
    <Project:DuplicateEntry xsi:type="Project:DuplicateEntry">
     <Project:RuleName xsi:type="xsd:string"></Project:RuleName>
     <Project:SoPrimaryKey xsi:type="xsd:int">0</Project:SoPrimaryKey>
     <Project:EntryName xsi:type="xsd:string"></Project:EntryName>
     <Project:EntryIdentifier xsi:type="xsd:string"></Project:EntryIdentifier>
     <Project:RuleDisplayName xsi:type="xsd:string"></Project:RuleDisplayName>
    </Project:DuplicateEntry>
   </Project:Response>
  </Project:GetDuplicatesResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
