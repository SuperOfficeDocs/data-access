---
uid: services75-list-getdocumenttemplateextension
title: Services75.ListAgent.GetDocumentTemplateExtension SOAP
Generated: true
---

# Services75 List GetDocumentTemplateExtension SOAP

SOAP request and response examples **Remote/Services75/List.svc**
Implemented by the <see cref="M:SuperOffice.Services75.IListAgent.GetDocumentTemplateExtension">SuperOffice.Services75.IListAgent.GetDocumentTemplateExtension</see> method.

## GetDocumentTemplateExtension

Get the file extension for the document template

* **documentTemplateId:** The primary key of the document template

**Returns:** Extension including '.'


[WSDL file for Services75/List](../Services75-List.md)

Obtain a ticket from the [Services75/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## GetDocumentTemplateExtension Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices752="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices751="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:List="http://www.superoffice.net/ws/crm/NetServer/Services75">
  <List:ApplicationToken>1234567-1234-9876</List:ApplicationToken>
  <List:Credentials>
    <List:Ticket>7T:1234abcxyzExample==</List:Ticket>
  </List:Credentials>
 <SOAP-ENV:Body>
   <List:GetDocumentTemplateExtension>
    <List:DocumentTemplateId xsi:type="xsd:int">0</List:DocumentTemplateId>
   </List:GetDocumentTemplateExtension>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## GetDocumentTemplateExtension Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices752="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices751="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:List="http://www.superoffice.net/ws/crm/NetServer/Services75">
 <SOAP-ENV:Body>
  <List:GetDocumentTemplateExtensionResponse>
   <List:Response xsi:type="xsd:string"></List:Response>
  </List:GetDocumentTemplateExtensionResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
