---
uid: services75-quote-deletepricelist
title: Services75.QuoteAgent.DeletePriceList SOAP
Generated: true
---

# Services75 Quote DeletePriceList SOAP

SOAP request and response examples **Remote/Services75/Quote.svc**
Implemented by the <see cref="M:SuperOffice.Services75.IQuoteAgent.DeletePriceList">SuperOffice.Services75.IQuoteAgent.DeletePriceList</see> method.

## DeletePriceList

Deletes a pricelist from the database

* **priceListId:** Primary key of the price list



[WSDL file for Services75/Quote](../Services75-Quote.md)

Obtain a ticket from the [Services75/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## DeletePriceList Request

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
   <Quote:DeletePriceList>
    <Quote:PriceListId xsi:type="xsd:int">0</Quote:PriceListId>
   </Quote:DeletePriceList>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## DeletePriceList Response

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
  <Quote:DeletePriceListResponse>
  </Quote:DeletePriceListResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
