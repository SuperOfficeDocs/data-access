---
uid: services75-filemanager-beginwritefilepart
title: Services75.FileManagerAgent.BeginWriteFilePart SOAP
Generated: true
---

# Services75 FileManager BeginWriteFilePart SOAP

SOAP request and response examples **Remote/Services75/FileManager.svc**
Implemented by the <see cref="M:SuperOffice.Services75.IFileManagerAgent.BeginWriteFilePart">SuperOffice.Services75.IFileManagerAgent.BeginWriteFilePart</see> method.

## BeginWriteFilePart





[WSDL file for Services75/FileManager](../Services75-FileManager.md)

Obtain a ticket from the [Services75/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## BeginWriteFilePart Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices751="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:FileManager="http://www.superoffice.net/ws/crm/NetServer/Services75">
  <FileManager:ApplicationToken>1234567-1234-9876</FileManager:ApplicationToken>
  <FileManager:Credentials>
    <FileManager:Ticket>7T:1234abcxyzExample==</FileManager:Ticket>
  </FileManager:Credentials>
 <SOAP-ENV:Body>
   <FileManager:BeginWriteFilePart>
    <FileManager:DocumentId xsi:type="xsd:int">0</FileManager:DocumentId>
   </FileManager:BeginWriteFilePart>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## BeginWriteFilePart Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices751="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:FileManager="http://www.superoffice.net/ws/crm/NetServer/Services75">
 <SOAP-ENV:Body>
  <FileManager:BeginWriteFilePartResponse>
  </FileManager:BeginWriteFilePartResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
