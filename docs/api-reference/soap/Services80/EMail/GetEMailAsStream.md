---
uid: services80-email-getemailasstream
title: Services80.EMailAgent.GetEMailAsStream SOAP
Generated: true
---

# Services80 EMail GetEMailAsStream SOAP

SOAP request and response examples **Remote/Services80/EMail.svc**
Implemented by the <see cref="M:SuperOffice.Services80.IEMailAgent.GetEMailAsStream">SuperOffice.Services80.IEMailAgent.GetEMailAsStream</see> method.

## GetEMailAsStream

Retrieve an e-mail optionally stripping attachments as a stream

* **connectionInfo:** All information needed to connect to the mailserver
* **messageServerId:** Unique ID for the e-mail to retrieve
* **stripAttachments:** If true, do not include attachments in stream

**Returns:** The attachment as a stream


[WSDL file for Services80/EMail](../Services80-EMail.md)

Obtain a ticket from the [Services80/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## GetEMailAsStream Request

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
   <EMail:GetEMailAsStream>
    <EMail:ConnectionInfo xsi:type="EMail:EMailConnectionInfo">
     <EMail:ServerName xsi:type="xsd:string"></EMail:ServerName>
     <EMail:UserName xsi:type="xsd:string"></EMail:UserName>
     <EMail:Password xsi:type="xsd:string"></EMail:Password>
     <EMail:Folder xsi:type="xsd:string"></EMail:Folder>
     <EMail:UseSSL xsi:type="xsd:boolean">false</EMail:UseSSL>
    </EMail:ConnectionInfo>
    <EMail:MessageServerId xsi:type="xsd:int">0</EMail:MessageServerId>
    <EMail:StripAttachments xsi:type="xsd:boolean">false</EMail:StripAttachments>
   </EMail:GetEMailAsStream>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## GetEMailAsStream Response

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
  <EMail:GetEMailAsStreamResponse>
   <EMail:Response xsi:type="xsd:base64Binary"></EMail:Response>
  </EMail:GetEMailAsStreamResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
