---
uid: services80-project-getprojectmember
title: Services80.ProjectAgent.GetProjectMember SOAP
Generated: true
---

# Services80 Project GetProjectMember SOAP

SOAP request and response examples **Remote/Services80/Project.svc**
Implemented by the <see cref="M:SuperOffice.Services80.IProjectAgent.GetProjectMember">SuperOffice.Services80.IProjectAgent.GetProjectMember</see> method.

## GetProjectMember

Get single ProjectMember row.

* **projectMemberId:** The id of the ProjectMember row



[WSDL file for Services80/Project](../Services80-Project.md)

Obtain a ticket from the [Services80/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## GetProjectMember Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices802="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices801="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Project="http://www.superoffice.net/ws/crm/NetServer/Services80">
  <Project:ApplicationToken>1234567-1234-9876</Project:ApplicationToken>
  <Project:Credentials>
    <Project:Ticket>7T:1234abcxyzExample==</Project:Ticket>
  </Project:Credentials>
 <SOAP-ENV:Body>
   <Project:GetProjectMember>
    <Project:ProjectMemberId xsi:type="xsd:int">0</Project:ProjectMemberId>
   </Project:GetProjectMember>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## GetProjectMember Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices802="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices801="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Project="http://www.superoffice.net/ws/crm/NetServer/Services80">
 <SOAP-ENV:Body>
  <Project:GetProjectMemberResponse>
   <Project:Response xsi:type="Project:ProjectMember">
    <Project:ContactId xsi:type="xsd:int">0</Project:ContactId>
    <Project:ProjectId xsi:type="xsd:int">0</Project:ProjectId>
    <Project:ContactName xsi:type="xsd:string"></Project:ContactName>
    <Project:EmailId xsi:type="xsd:int">0</Project:EmailId>
    <Project:EmailAddress xsi:type="xsd:string"></Project:EmailAddress>
    <Project:CountryId xsi:type="xsd:int">0</Project:CountryId>
    <Project:Firstname xsi:type="xsd:string"></Project:Firstname>
    <Project:MiddleName xsi:type="xsd:string"></Project:MiddleName>
    <Project:Lastname xsi:type="xsd:string"></Project:Lastname>
    <Project:PersonId xsi:type="xsd:int">0</Project:PersonId>
    <Project:Mrmrs xsi:type="xsd:string"></Project:Mrmrs>
    <Project:ProjectMemberTypeName xsi:type="xsd:string"></Project:ProjectMemberTypeName>
    <Project:Phone xsi:type="xsd:string"></Project:Phone>
    <Project:PhoneId xsi:type="xsd:int">0</Project:PhoneId>
    <Project:ProjectMemberTypeId xsi:type="xsd:int">0</Project:ProjectMemberTypeId>
    <Project:EmailAddressName xsi:type="xsd:string"></Project:EmailAddressName>
    <Project:Comment xsi:type="xsd:string"></Project:Comment>
    <Project:ProjectmemberId xsi:type="xsd:int">0</Project:ProjectmemberId>
    <Project:FullName xsi:type="xsd:string"></Project:FullName>
   </Project:Response>
  </Project:GetProjectMemberResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
