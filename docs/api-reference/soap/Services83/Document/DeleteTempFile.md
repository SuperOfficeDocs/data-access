---
uid: services83-document-deletetempfile
title: Services83.DocumentAgent.DeleteTempFile SOAP
Generated: true
---

# Services83 Document DeleteTempFile SOAP

SOAP request and response examples **Remote/Services83/Document.svc**
Implemented by the <see cref="M:SuperOffice.Services83.IDocumentAgent.DeleteTempFile">SuperOffice.Services83.IDocumentAgent.DeleteTempFile</see> method.

## DeleteTempFile

Delete a temporary file created with CreateTempFile.

* **filename:** Name of temporary file to delete.



[WSDL file for Services83/Document](../Services83-Document.md)

Obtain a ticket from the [Services83/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## DeleteTempFile Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices832="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices831="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Document="http://www.superoffice.net/ws/crm/NetServer/Services83">
  <Document:ApplicationToken>1234567-1234-9876</Document:ApplicationToken>
  <Document:Credentials>
    <Document:Ticket>7T:1234abcxyzExample==</Document:Ticket>
  </Document:Credentials>
 <SOAP-ENV:Body>
   <Document:DeleteTempFile>
    <Document:Filename xsi:type="xsd:string"></Document:Filename>
   </Document:DeleteTempFile>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## DeleteTempFile Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices832="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices831="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Document="http://www.superoffice.net/ws/crm/NetServer/Services83">
 <SOAP-ENV:Body>
  <Document:DeleteTempFileResponse>
  </Document:DeleteTempFileResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
