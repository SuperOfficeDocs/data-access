---
uid: services81-project-getprojectsfromcontact
title: Services81.ProjectAgent.GetProjectsFromContact SOAP
Generated: true
---

# Services81 Project GetProjectsFromContact SOAP

SOAP request and response examples **Remote/Services81/Project.svc**
Implemented by the <see cref="M:SuperOffice.Services81.IProjectAgent.GetProjectsFromContact">SuperOffice.Services81.IProjectAgent.GetProjectsFromContact</see> method.

## GetProjectsFromContact

Returns all projects where the given contact has projectmembers.

* **contactId:** The contact id

**Returns:** ProjectListEntity


[WSDL file for Services81/Project](../Services81-Project.md)

Obtain a ticket from the [Services81/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## GetProjectsFromContact Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices812="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices811="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Project="http://www.superoffice.net/ws/crm/NetServer/Services81">
  <Project:ApplicationToken>1234567-1234-9876</Project:ApplicationToken>
  <Project:Credentials>
    <Project:Ticket>7T:1234abcxyzExample==</Project:Ticket>
  </Project:Credentials>
 <SOAP-ENV:Body>
   <Project:GetProjectsFromContact>
    <Project:ContactId xsi:type="xsd:int">0</Project:ContactId>
   </Project:GetProjectsFromContact>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## GetProjectsFromContact Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices812="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices811="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Project="http://www.superoffice.net/ws/crm/NetServer/Services81">
 <SOAP-ENV:Body>
  <Project:GetProjectsFromContactResponse>
   <Project:Response xsi:type="Project:ArrayOfProject">
    <Project:Project xsi:type="Project:Project">
     <Project:ProjectId xsi:type="xsd:int">0</Project:ProjectId>
     <Project:Name xsi:type="xsd:string"></Project:Name>
     <Project:Description xsi:type="xsd:string"></Project:Description>
     <Project:URL xsi:type="xsd:string"></Project:URL>
     <Project:Type xsi:type="xsd:string"></Project:Type>
     <Project:AssociateId xsi:type="xsd:int">0</Project:AssociateId>
     <Project:AssociateFullName xsi:type="xsd:string"></Project:AssociateFullName>
     <Project:TypeId xsi:type="xsd:int">0</Project:TypeId>
     <Project:Updated xsi:type="xsd:dateTime">2021-03-25T21:34:34Z</Project:Updated>
     <Project:StatusId xsi:type="xsd:int">0</Project:StatusId>
     <Project:Status xsi:type="xsd:string"></Project:Status>
     <Project:TextId xsi:type="xsd:int">0</Project:TextId>
     <Project:PublishTo xsi:type="xsd:dateTime">2021-03-25T21:34:34Z</Project:PublishTo>
     <Project:PublishFrom xsi:type="xsd:dateTime">2021-03-25T21:34:34Z</Project:PublishFrom>
     <Project:IsPublished xsi:type="xsd:boolean">false</Project:IsPublished>
     <Project:URLName xsi:type="xsd:string"></Project:URLName>
     <Project:ProjectNumber xsi:type="xsd:string"></Project:ProjectNumber>
     <Project:ActiveErpLinks xsi:type="xsd:int">0</Project:ActiveErpLinks>
    </Project:Project>
   </Project:Response>
  </Project:GetProjectsFromContactResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
