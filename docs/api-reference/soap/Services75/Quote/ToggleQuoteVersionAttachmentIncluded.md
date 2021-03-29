---
uid: services75-quote-togglequoteversionattachmentincluded
title: Services75.QuoteAgent.ToggleQuoteVersionAttachmentIncluded SOAP
Generated: true
---

# Services75 Quote ToggleQuoteVersionAttachmentIncluded SOAP

SOAP request and response examples **Remote/Services75/Quote.svc**
Implemented by the <see cref="M:SuperOffice.Services75.IQuoteAgent.ToggleQuoteVersionAttachmentIncluded">SuperOffice.Services75.IQuoteAgent.ToggleQuoteVersionAttachmentIncluded</see> method.

## ToggleQuoteVersionAttachmentIncluded

Toggle the 'included' state of a quote version attachment

* **quoteVersionAttachmentId:** The ID of the quote version attachment row

**Returns:** The new state


[WSDL file for Services75/Quote](../Services75-Quote.md)

Obtain a ticket from the [Services75/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## ToggleQuoteVersionAttachmentIncluded Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices752="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices751="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Quote="http://www.superoffice.net/ws/crm/NetServer/Services75">
  <Quote:ApplicationToken>1234567-1234-9876</Quote:ApplicationToken>
  <Quote:Credentials>
    <Quote:Ticket>7T:1234abcxyzExample==</Quote:Ticket>
  </Quote:Credentials>
 <SOAP-ENV:Body>
   <Quote:ToggleQuoteVersionAttachmentIncluded>
    <Quote:QuoteVersionAttachmentId xsi:type="xsd:int">0</Quote:QuoteVersionAttachmentId>
   </Quote:ToggleQuoteVersionAttachmentIncluded>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## ToggleQuoteVersionAttachmentIncluded Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices752="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices751="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Quote="http://www.superoffice.net/ws/crm/NetServer/Services75">
 <SOAP-ENV:Body>
  <Quote:ToggleQuoteVersionAttachmentIncludedResponse>
   <Quote:Response xsi:type="xsd:boolean">false</Quote:Response>
  </Quote:ToggleQuoteVersionAttachmentIncludedResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
