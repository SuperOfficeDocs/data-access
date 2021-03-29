---
uid: services81-project-setduplicaterulesstatus
title: Services81.ProjectAgent.SetDuplicateRulesStatus SOAP
Generated: true
---

# Services81 Project SetDuplicateRulesStatus SOAP

SOAP request and response examples **Remote/Services81/Project.svc**
Implemented by the <see cref="M:SuperOffice.Services81.IProjectAgent.SetDuplicateRulesStatus">SuperOffice.Services81.IProjectAgent.SetDuplicateRulesStatus</see> method.

## SetDuplicateRulesStatus

Set which duplicate rules should be active or not

* **rules:** Duplicate rules to update active status for



[WSDL file for Services81/Project](../Services81-Project.md)

Obtain a ticket from the [Services81/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## SetDuplicateRulesStatus Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices812="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices811="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Project="http://www.superoffice.net/ws/crm/NetServer/Services81">
  <Project:ApplicationToken>1234567-1234-9876</Project:ApplicationToken>
  <Project:Credentials>
    <Project:Ticket>7T:1234abcxyzExample==</Project:Ticket>
  </Project:Credentials>
 <SOAP-ENV:Body>
   <Project:SetDuplicateRulesStatus>
    <Project:Rules xsi:type="Project:ArrayOfDuplicateRule">
     <Project:DuplicateRule xsi:type="Project:DuplicateRule">
      <Project:Name xsi:type="xsd:string"></Project:Name>
      <Project:DisplayName xsi:type="xsd:string"></Project:DisplayName>
      <Project:DisplayTooltip xsi:type="xsd:string"></Project:DisplayTooltip>
      <Project:IsActive xsi:type="xsd:boolean">false</Project:IsActive>
     </Project:DuplicateRule>
    </Project:Rules>
   </Project:SetDuplicateRulesStatus>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## SetDuplicateRulesStatus Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices812="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices811="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Project="http://www.superoffice.net/ws/crm/NetServer/Services81">
 <SOAP-ENV:Body>
  <Project:SetDuplicateRulesStatusResponse>
  </Project:SetDuplicateRulesStatusResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
