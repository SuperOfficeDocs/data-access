---
uid: services83-sale-hasguide
title: Services83.SaleAgent.HasGuide SOAP
Generated: true
---

# Services83 Sale HasGuide SOAP

SOAP request and response examples **Remote/Services83/Sale.svc**
Implemented by the <see cref="M:SuperOffice.Services83.ISaleAgent.HasGuide">SuperOffice.Services83.ISaleAgent.HasGuide</see> method.

## HasGuide

Does this sale have a sale guide associated with its sale type?

* **saleId:** Sale id

**Returns:** True if the sale has a guide


[WSDL file for Services83/Sale](../Services83-Sale.md)

Obtain a ticket from the [Services83/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## HasGuide Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices832="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices831="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Sale="http://www.superoffice.net/ws/crm/NetServer/Services83">
  <Sale:ApplicationToken>1234567-1234-9876</Sale:ApplicationToken>
  <Sale:Credentials>
    <Sale:Ticket>7T:1234abcxyzExample==</Sale:Ticket>
  </Sale:Credentials>
 <SOAP-ENV:Body>
   <Sale:HasGuide>
    <Sale:SaleId xsi:type="xsd:int">0</Sale:SaleId>
   </Sale:HasGuide>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## HasGuide Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices832="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices831="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Sale="http://www.superoffice.net/ws/crm/NetServer/Services83">
 <SOAP-ENV:Body>
  <Sale:HasGuideResponse>
   <Sale:Response xsi:type="xsd:boolean">false</Sale:Response>
  </Sale:HasGuideResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
