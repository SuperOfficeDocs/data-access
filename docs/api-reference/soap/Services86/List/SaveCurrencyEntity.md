---
uid: services86-list-savecurrencyentity
title: Services86.ListAgent.SaveCurrencyEntity SOAP
Generated: true
---

# Services86 List SaveCurrencyEntity SOAP

SOAP request and response examples **Remote/Services86/List.svc**
Implemented by the <see cref="M:SuperOffice.Services86.IListAgent.SaveCurrencyEntity">SuperOffice.Services86.IListAgent.SaveCurrencyEntity</see> method.

## SaveCurrencyEntity

Updates the existing CurrencyEntity or creates a new CurrencyEntity if the id parameter is 0.

* **currencyEntity:** The CurrencyEntity that is saved.

**Returns:** New or updated CurrencyEntity


[WSDL file for Services86/List](../Services86-List.md)

Obtain a ticket from the [Services86/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## SaveCurrencyEntity Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices862="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices861="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:List="http://www.superoffice.net/ws/crm/NetServer/Services86">
  <List:ApplicationToken>1234567-1234-9876</List:ApplicationToken>
  <List:Credentials>
    <List:Ticket>7T:1234abcxyzExample==</List:Ticket>
  </List:Credentials>
 <SOAP-ENV:Body>
   <List:SaveCurrencyEntity>
    <List:CurrencyEntity xsi:type="List:CurrencyEntity">
     <List:CurrencyId xsi:type="xsd:int">0</List:CurrencyId>
     <List:Name xsi:type="xsd:string"></List:Name>
     <List:Tooltip xsi:type="xsd:string"></List:Tooltip>
     <List:Rank xsi:type="xsd:short">0</List:Rank>
     <List:Rate xsi:type="xsd:double">0.0</List:Rate>
     <List:Units xsi:type="xsd:double">0.0</List:Units>
     <List:Deleted xsi:type="xsd:boolean">false</List:Deleted>
    </List:CurrencyEntity>
   </List:SaveCurrencyEntity>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## SaveCurrencyEntity Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices862="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices861="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:List="http://www.superoffice.net/ws/crm/NetServer/Services86">
 <SOAP-ENV:Body>
  <List:SaveCurrencyEntityResponse>
   <List:Response xsi:type="List:CurrencyEntity">
    <List:CurrencyId xsi:type="xsd:int">0</List:CurrencyId>
    <List:Name xsi:type="xsd:string"></List:Name>
    <List:Tooltip xsi:type="xsd:string"></List:Tooltip>
    <List:Rank xsi:type="xsd:short">0</List:Rank>
    <List:Rate xsi:type="xsd:double">0.0</List:Rate>
    <List:Units xsi:type="xsd:double">0.0</List:Units>
    <List:Deleted xsi:type="xsd:boolean">false</List:Deleted>
   </List:Response>
  </List:SaveCurrencyEntityResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
