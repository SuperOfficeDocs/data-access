---
uid: services81-document-gettemplatestreamfromid
title: Services81.DocumentAgent.GetTemplateStreamFromId SOAP
Generated: true
---

# Services81 Document GetTemplateStreamFromId SOAP

SOAP request and response examples **Remote/Services81/Document.svc**
Implemented by the <see cref="M:SuperOffice.Services81.IDocumentAgent.GetTemplateStreamFromId">SuperOffice.Services81.IDocumentAgent.GetTemplateStreamFromId</see> method.

## GetTemplateStreamFromId

Retrieve a stream to a document template based on its id

* **templateId:** Id of template to retrieve
* **uiCulture:** Language used in UI. ("en-US" or "nb-NO" etc). Used to select a template of the appropriate language. Can be overridden in SO ARC by user preference "PreferDocLang".

**Returns:** Open stream to the template


[WSDL file for Services81/Document](../Services81-Document.md)

Obtain a ticket from the [Services81/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## GetTemplateStreamFromId Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices812="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices811="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Document="http://www.superoffice.net/ws/crm/NetServer/Services81">
  <Document:ApplicationToken>1234567-1234-9876</Document:ApplicationToken>
  <Document:Credentials>
    <Document:Ticket>7T:1234abcxyzExample==</Document:Ticket>
  </Document:Credentials>
 <SOAP-ENV:Body>
   <Document:GetTemplateStreamFromId>
    <Document:TemplateId xsi:type="xsd:int">0</Document:TemplateId>
    <Document:UiCulture xsi:type="xsd:string"></Document:UiCulture>
   </Document:GetTemplateStreamFromId>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## GetTemplateStreamFromId Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices812="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices811="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Document="http://www.superoffice.net/ws/crm/NetServer/Services81">
 <SOAP-ENV:Body>
  <Document:GetTemplateStreamFromIdResponse>
   <Document:Response xsi:type="xsd:base64Binary"></Document:Response>
  </Document:GetTemplateStreamFromIdResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
