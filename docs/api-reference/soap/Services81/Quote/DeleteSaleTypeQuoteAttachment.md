---
uid: services81-quote-deletesaletypequoteattachment
title: Services81.QuoteAgent.DeleteSaleTypeQuoteAttachment SOAP
Generated: true
---

# Services81 Quote DeleteSaleTypeQuoteAttachment SOAP

SOAP request and response examples **Remote/Services81/Quote.svc**
Implemented by the <see cref="M:SuperOffice.Services81.IQuoteAgent.DeleteSaleTypeQuoteAttachment">SuperOffice.Services81.IQuoteAgent.DeleteSaleTypeQuoteAttachment</see> method.

## DeleteSaleTypeQuoteAttachment

Deletes the sale type quote attachment with the given id

* **saleTypeQuoteAttachmentId:** The ID of the sale type quote attachment row to delete



[WSDL file for Services81/Quote](../Services81-Quote.md)

Obtain a ticket from the [Services81/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## DeleteSaleTypeQuoteAttachment Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices812="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices811="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Quote="http://www.superoffice.net/ws/crm/NetServer/Services81">
  <Quote:ApplicationToken>1234567-1234-9876</Quote:ApplicationToken>
  <Quote:Credentials>
    <Quote:Ticket>7T:1234abcxyzExample==</Quote:Ticket>
  </Quote:Credentials>
 <SOAP-ENV:Body>
   <Quote:DeleteSaleTypeQuoteAttachment>
    <Quote:SaleTypeQuoteAttachmentId xsi:type="xsd:int">0</Quote:SaleTypeQuoteAttachmentId>
   </Quote:DeleteSaleTypeQuoteAttachment>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## DeleteSaleTypeQuoteAttachment Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices812="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices811="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Quote="http://www.superoffice.net/ws/crm/NetServer/Services81">
 <SOAP-ENV:Body>
  <Quote:DeleteSaleTypeQuoteAttachmentResponse>
  </Quote:DeleteSaleTypeQuoteAttachmentResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
