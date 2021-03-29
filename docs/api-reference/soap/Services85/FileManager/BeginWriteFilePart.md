---
uid: services85-filemanager-beginwritefilepart
title: Services85.FileManagerAgent.BeginWriteFilePart SOAP
Generated: true
---

# Services85 FileManager BeginWriteFilePart SOAP

SOAP request and response examples **Remote/Services85/FileManager.svc**
Implemented by the <see cref="M:SuperOffice.Services85.IFileManagerAgent.BeginWriteFilePart">SuperOffice.Services85.IFileManagerAgent.BeginWriteFilePart</see> method.

## BeginWriteFilePart





[WSDL file for Services85/FileManager](../Services85-FileManager.md)

Obtain a ticket from the [Services85/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## BeginWriteFilePart Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices851="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:FileManager="http://www.superoffice.net/ws/crm/NetServer/Services85">
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
 xmlns:NetServerServices851="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:FileManager="http://www.superoffice.net/ws/crm/NetServer/Services85">
 <SOAP-ENV:Body>
  <FileManager:BeginWriteFilePartResponse>
  </FileManager:BeginWriteFilePartResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
