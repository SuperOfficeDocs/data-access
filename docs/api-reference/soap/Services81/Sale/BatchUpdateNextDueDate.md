---
uid: services81-sale-batchupdatenextduedate
title: Services81.SaleAgent.BatchUpdateNextDueDate SOAP
Generated: true
---

# Services81 Sale BatchUpdateNextDueDate SOAP

SOAP request and response examples **Remote/Services81/Sale.svc**
Implemented by the <see cref="M:SuperOffice.Services81.ISaleAgent.BatchUpdateNextDueDate">SuperOffice.Services81.ISaleAgent.BatchUpdateNextDueDate</see> method.

## BatchUpdateNextDueDate






[WSDL file for Services81/Sale](../Services81-Sale.md)

Obtain a ticket from the [Services81/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## BatchUpdateNextDueDate Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices812="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices811="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Sale="http://www.superoffice.net/ws/crm/NetServer/Services81">
  <Sale:ApplicationToken>1234567-1234-9876</Sale:ApplicationToken>
  <Sale:Credentials>
    <Sale:Ticket>7T:1234abcxyzExample==</Sale:Ticket>
  </Sale:Credentials>
 <SOAP-ENV:Body>
   <Sale:BatchUpdateNextDueDate>
   </Sale:BatchUpdateNextDueDate>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## BatchUpdateNextDueDate Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices812="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices811="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Sale="http://www.superoffice.net/ws/crm/NetServer/Services81">
 <SOAP-ENV:Body>
  <Sale:BatchUpdateNextDueDateResponse>
  </Sale:BatchUpdateNextDueDateResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
