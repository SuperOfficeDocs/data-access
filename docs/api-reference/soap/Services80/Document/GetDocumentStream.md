---
uid: services80-document-getdocumentstream
title: Services80.DocumentAgent.GetDocumentStream SOAP
Generated: true
---

# Services80 Document GetDocumentStream SOAP

SOAP request and response examples **Remote/Services80/Document.svc**
Implemented by the <see cref="M:SuperOffice.Services80.IDocumentAgent.GetDocumentStream">SuperOffice.Services80.IDocumentAgent.GetDocumentStream</see> method.

## GetDocumentStream

Get the document as a stream

* **documentId:** SuperOffice document id

**Returns:** The document as a Stream. This stream can be read once and clients should not assume it remains valid after a ReadToEnd or Close.


[WSDL file for Services80/Document](../Services80-Document.md)

Obtain a ticket from the [Services80/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## GetDocumentStream Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices802="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices801="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Document="http://www.superoffice.net/ws/crm/NetServer/Services80">
  <Document:ApplicationToken>1234567-1234-9876</Document:ApplicationToken>
  <Document:Credentials>
    <Document:Ticket>7T:1234abcxyzExample==</Document:Ticket>
  </Document:Credentials>
 <SOAP-ENV:Body>
   <Document:GetDocumentStream>
    <Document:DocumentId xsi:type="xsd:int">0</Document:DocumentId>
   </Document:GetDocumentStream>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## GetDocumentStream Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices802="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices801="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Document="http://www.superoffice.net/ws/crm/NetServer/Services80">
 <SOAP-ENV:Body>
  <Document:GetDocumentStreamResponse>
   <Document:Response xsi:type="xsd:base64Binary"></Document:Response>
  </Document:GetDocumentStreamResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
