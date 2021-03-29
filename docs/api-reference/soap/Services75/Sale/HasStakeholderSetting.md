---
uid: services75-sale-hasstakeholdersetting
title: Services75.SaleAgent.HasStakeholderSetting SOAP
Generated: true
---

# Services75 Sale HasStakeholderSetting SOAP

SOAP request and response examples **Remote/Services75/Sale.svc**
Implemented by the <see cref="M:SuperOffice.Services75.ISaleAgent.HasStakeholderSetting">SuperOffice.Services75.ISaleAgent.HasStakeholderSetting</see> method.

## HasStakeholderSetting



* **saleId:** 



[WSDL file for Services75/Sale](../Services75-Sale.md)

Obtain a ticket from the [Services75/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## HasStakeholderSetting Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices752="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices751="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Sale="http://www.superoffice.net/ws/crm/NetServer/Services75">
  <Sale:ApplicationToken>1234567-1234-9876</Sale:ApplicationToken>
  <Sale:Credentials>
    <Sale:Ticket>7T:1234abcxyzExample==</Sale:Ticket>
  </Sale:Credentials>
 <SOAP-ENV:Body>
   <Sale:HasStakeholderSetting>
    <Sale:SaleId xsi:type="xsd:int">0</Sale:SaleId>
   </Sale:HasStakeholderSetting>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## HasStakeholderSetting Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices752="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices751="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Sale="http://www.superoffice.net/ws/crm/NetServer/Services75">
 <SOAP-ENV:Body>
  <Sale:HasStakeholderSettingResponse>
   <Sale:Response xsi:type="xsd:boolean">false</Sale:Response>
  </Sale:HasStakeholderSettingResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
