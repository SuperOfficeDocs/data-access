---
uid: services80-email-createdefaultemailattachment
title: Services80.EMailAgent.CreateDefaultEMailAttachment SOAP
Generated: true
---

# Services80 EMail CreateDefaultEMailAttachment SOAP

SOAP request and response examples **Remote/Services80/EMail.svc**
Implemented by the <see cref="M:SuperOffice.Services80.IEMailAgent.CreateDefaultEMailAttachment">SuperOffice.Services80.IEMailAgent.CreateDefaultEMailAttachment</see> method.

## CreateDefaultEMailAttachment

Loading default values into a new EMailAttachment.
NetServer calculates default values (e.g. Country) on the entity, which is required when creating/storing a new instance


**Returns:** New EMailAttachment with default values


[WSDL file for Services80/EMail](../Services80-EMail.md)

Obtain a ticket from the [Services80/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## CreateDefaultEMailAttachment Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices802="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices801="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:EMail="http://www.superoffice.net/ws/crm/NetServer/Services80">
  <EMail:ApplicationToken>1234567-1234-9876</EMail:ApplicationToken>
  <EMail:Credentials>
    <EMail:Ticket>7T:1234abcxyzExample==</EMail:Ticket>
  </EMail:Credentials>
 <SOAP-ENV:Body>
   <EMail:CreateDefaultEMailAttachment>
   </EMail:CreateDefaultEMailAttachment>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## CreateDefaultEMailAttachment Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices802="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices801="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:EMail="http://www.superoffice.net/ws/crm/NetServer/Services80">
 <SOAP-ENV:Body>
  <EMail:CreateDefaultEMailAttachmentResponse>
   <EMail:Response xsi:type="EMail:EMailAttachment">
    <EMail:Description xsi:type="xsd:string"></EMail:Description>
    <EMail:Filename xsi:type="xsd:string"></EMail:Filename>
    <EMail:Size xsi:type="xsd:int">0</EMail:Size>
    <EMail:Type xsi:type="xsd:string"></EMail:Type>
    <EMail:Encoding xsi:type="xsd:string"></EMail:Encoding>
    <EMail:Id xsi:type="xsd:string"></EMail:Id>
    <EMail:Disposition xsi:type="xsd:string"></EMail:Disposition>
    <EMail:Stream xsi:type="xsd:base64Binary"></EMail:Stream>
   </EMail:Response>
  </EMail:CreateDefaultEMailAttachmentResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
