---
uid: services75-report-getreportentity
title: Services75.ReportAgent.GetReportEntity SOAP
Generated: true
---

# Services75 Report GetReportEntity SOAP

SOAP request and response examples **Remote/Services75/Report.svc**
Implemented by the <see cref="M:SuperOffice.Services75.IReportAgent.GetReportEntity">SuperOffice.Services75.IReportAgent.GetReportEntity</see> method.

## GetReportEntity

Gets a ReportEntity object.

* **reportEntityId:** The identifier of the ReportEntity object

**Returns:** ReportEntity


[WSDL file for Services75/Report](../Services75-Report.md)

Obtain a ticket from the [Services75/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## GetReportEntity Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices752="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices751="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Report="http://www.superoffice.net/ws/crm/NetServer/Services75">
  <Report:ApplicationToken>1234567-1234-9876</Report:ApplicationToken>
  <Report:Credentials>
    <Report:Ticket>7T:1234abcxyzExample==</Report:Ticket>
  </Report:Credentials>
 <SOAP-ENV:Body>
   <Report:GetReportEntity>
    <Report:ReportEntityId xsi:type="xsd:int">0</Report:ReportEntityId>
   </Report:GetReportEntity>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## GetReportEntity Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices752="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices751="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Report="http://www.superoffice.net/ws/crm/NetServer/Services75">
 <SOAP-ENV:Body>
  <Report:GetReportEntityResponse>
   <Report:Response xsi:type="Report:ReportEntity">
    <Report:ReportId xsi:type="xsd:int">0</Report:ReportId>
    <Report:ReportCategory xsi:type="Report:ReportCategory">None</Report:ReportCategory>
    <Report:Description xsi:type="xsd:string"></Report:Description>
    <Report:ReportLayout xsi:type="Report:ReportLayout">Unknown</Report:ReportLayout>
    <Report:Name xsi:type="xsd:string"></Report:Name>
    <Report:AssociateId xsi:type="xsd:int">0</Report:AssociateId>
    <Report:TemplateId xsi:type="xsd:int">0</Report:TemplateId>
    <Report:Published xsi:type="xsd:boolean">false</Report:Published>
   </Report:Response>
  </Report:GetReportEntityResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
