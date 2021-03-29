---
uid: services82-mdo-getlistnames
title: Services82.MDOAgent.GetListNames SOAP
Generated: true
---

# Services82 MDO GetListNames SOAP

SOAP request and response examples **Remote/Services82/MDO.svc**
Implemented by the <see cref="M:SuperOffice.Services82.IMDOAgent.GetListNames">SuperOffice.Services82.IMDOAgent.GetListNames</see> method.

## GetListNames

Returns a list of all MDO List names. These names can also be used with the Archive agent as ProviderNames.


**Returns:** Array of list names.


[WSDL file for Services82/MDO](../Services82-MDO.md)

Obtain a ticket from the [Services82/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## GetListNames Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices822="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices821="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:MDO="http://www.superoffice.net/ws/crm/NetServer/Services82">
  <MDO:ApplicationToken>1234567-1234-9876</MDO:ApplicationToken>
  <MDO:Credentials>
    <MDO:Ticket>7T:1234abcxyzExample==</MDO:Ticket>
  </MDO:Credentials>
 <SOAP-ENV:Body>
   <MDO:GetListNames>
   </MDO:GetListNames>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## GetListNames Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices822="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices821="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:MDO="http://www.superoffice.net/ws/crm/NetServer/Services82">
 <SOAP-ENV:Body>
  <MDO:GetListNamesResponse>
   <MDO:Response xsi:type="NetServerServices822:ArrayOfstring">
    <NetServerServices822:string xsi:type="xsd:string"></NetServerServices822:string>
   </MDO:Response>
  </MDO:GetListNamesResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
