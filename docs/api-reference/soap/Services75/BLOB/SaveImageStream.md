---
uid: services75-blob-saveimagestream
title: Services75.BLOBAgent.SaveImageStream SOAP
Generated: true
---

# Services75 BLOB SaveImageStream SOAP

SOAP request and response examples **Remote/Services75/BLOB.svc**
Implemented by the <see cref="M:SuperOffice.Services75.IBLOBAgent.SaveImageStream">SuperOffice.Services75.IBLOBAgent.SaveImageStream</see> method.

## SaveImageStream

Stores an image in the database without linking it to a project or a person. It is possible to ChangePersonImage or ChangeProjectImage to attach image later.

* **type:** The type of the image.
* **image:** Image to store
* **description:** Image description

**Returns:** The blob id


[WSDL file for Services75/BLOB](../Services75-BLOB.md)

Obtain a ticket from the [Services75/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## SaveImageStream Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices751="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:BLOB="http://www.superoffice.net/ws/crm/NetServer/Services75">
  <BLOB:ApplicationToken>1234567-1234-9876</BLOB:ApplicationToken>
  <BLOB:Credentials>
    <BLOB:Ticket>7T:1234abcxyzExample==</BLOB:Ticket>
  </BLOB:Credentials>
 <SOAP-ENV:Body>
   <BLOB:SaveImageStream>
    <BLOB:Type xsi:type="BLOB:BlobLinkType">PersonImage</BLOB:Type>
    <BLOB:Image xsi:type="xsd:base64Binary"></BLOB:Image>
    <BLOB:Description xsi:type="xsd:string"></BLOB:Description>
   </BLOB:SaveImageStream>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## SaveImageStream Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices751="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:BLOB="http://www.superoffice.net/ws/crm/NetServer/Services75">
 <SOAP-ENV:Body>
  <BLOB:SaveImageStreamResponse>
   <BLOB:Response xsi:type="xsd:int">0</BLOB:Response>
  </BLOB:SaveImageStreamResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
