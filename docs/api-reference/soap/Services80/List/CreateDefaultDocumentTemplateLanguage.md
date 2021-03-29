---
uid: services80-list-createdefaultdocumenttemplatelanguage
title: Services80.ListAgent.CreateDefaultDocumentTemplateLanguage SOAP
Generated: true
---

# Services80 List CreateDefaultDocumentTemplateLanguage SOAP

SOAP request and response examples **Remote/Services80/List.svc**
Implemented by the <see cref="M:SuperOffice.Services80.IListAgent.CreateDefaultDocumentTemplateLanguage">SuperOffice.Services80.IListAgent.CreateDefaultDocumentTemplateLanguage</see> method.

## CreateDefaultDocumentTemplateLanguage

Create a new document template language based on an existing template

* **documentTemplateId:** The id of the document template
* **languageCode:** The language code ('en-US, 'nb-NO', etc)

**Returns:** Returns nothing - throws on error


[WSDL file for Services80/List](../Services80-List.md)

Obtain a ticket from the [Services80/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## CreateDefaultDocumentTemplateLanguage Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices802="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices801="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:List="http://www.superoffice.net/ws/crm/NetServer/Services80">
  <List:ApplicationToken>1234567-1234-9876</List:ApplicationToken>
  <List:Credentials>
    <List:Ticket>7T:1234abcxyzExample==</List:Ticket>
  </List:Credentials>
 <SOAP-ENV:Body>
   <List:CreateDefaultDocumentTemplateLanguage>
    <List:DocumentTemplateId xsi:type="xsd:int">0</List:DocumentTemplateId>
    <List:LanguageCode xsi:type="xsd:string"></List:LanguageCode>
   </List:CreateDefaultDocumentTemplateLanguage>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## CreateDefaultDocumentTemplateLanguage Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices802="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices801="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:List="http://www.superoffice.net/ws/crm/NetServer/Services80">
 <SOAP-ENV:Body>
  <List:CreateDefaultDocumentTemplateLanguageResponse>
  </List:CreateDefaultDocumentTemplateLanguageResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
