---
uid: services83-filemanager-readfilepart
title: Services83.FileManagerAgent.ReadFilePart SOAP
Generated: true
---

# Services83 FileManager ReadFilePart SOAP

SOAP request and response examples **Remote/Services83/FileManager.svc**
Implemented by the <see cref="M:SuperOffice.Services83.IFileManagerAgent.ReadFilePart">SuperOffice.Services83.IFileManagerAgent.ReadFilePart</see> method.

## ReadFilePart





[WSDL file for Services83/FileManager](../Services83-FileManager.md)

Obtain a ticket from the [Services83/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## ReadFilePart Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices831="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:FileManager="http://www.superoffice.net/ws/crm/NetServer/Services83">
  <FileManager:ApplicationToken>1234567-1234-9876</FileManager:ApplicationToken>
  <FileManager:Credentials>
    <FileManager:Ticket>7T:1234abcxyzExample==</FileManager:Ticket>
  </FileManager:Credentials>
 <SOAP-ENV:Body>
   <FileManager:ReadFilePart>
    <FileManager:DocumentId xsi:type="xsd:int">0</FileManager:DocumentId>
    <FileManager:FilePosition xsi:type="xsd:long">0</FileManager:FilePosition>
    <FileManager:Length xsi:type="xsd:int">0</FileManager:Length>
   </FileManager:ReadFilePart>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## ReadFilePart Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices831="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:FileManager="http://www.superoffice.net/ws/crm/NetServer/Services83">
 <SOAP-ENV:Body>
  <FileManager:ReadFilePartResponse>
   <FileManager:Response xsi:type="xsd:string"></FileManager:Response>
   <FileManager:Length xsi:type="xsd:int">0</FileManager:Length>
  </FileManager:ReadFilePartResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
