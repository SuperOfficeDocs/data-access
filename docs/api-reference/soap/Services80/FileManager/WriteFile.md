---
uid: services80-filemanager-writefile
title: Services80.FileManagerAgent.WriteFile SOAP
Generated: true
---

# Services80 FileManager WriteFile SOAP

SOAP request and response examples **Remote/Services80/FileManager.svc**
Implemented by the <see cref="M:SuperOffice.Services80.IFileManagerAgent.WriteFile">SuperOffice.Services80.IFileManagerAgent.WriteFile</see> method.

## WriteFile





[WSDL file for Services80/FileManager](../Services80-FileManager.md)

Obtain a ticket from the [Services80/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## WriteFile Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices801="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:FileManager="http://www.superoffice.net/ws/crm/NetServer/Services80">
  <FileManager:ApplicationToken>1234567-1234-9876</FileManager:ApplicationToken>
  <FileManager:Credentials>
    <FileManager:Ticket>7T:1234abcxyzExample==</FileManager:Ticket>
  </FileManager:Credentials>
 <SOAP-ENV:Body>
   <FileManager:WriteFile>
    <FileManager:DocumentId xsi:type="xsd:int">0</FileManager:DocumentId>
    <FileManager:Document xsi:type="xsd:string"></FileManager:Document>
   </FileManager:WriteFile>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## WriteFile Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices801="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:FileManager="http://www.superoffice.net/ws/crm/NetServer/Services80">
 <SOAP-ENV:Body>
  <FileManager:WriteFileResponse>
  </FileManager:WriteFileResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
