---
uid: services81-report-getreportlabellayoutentity
title: Services81.ReportAgent.GetReportLabelLayoutEntity SOAP
Generated: true
---

# Services81 Report GetReportLabelLayoutEntity SOAP

SOAP request and response examples **Remote/Services81/Report.svc**
Implemented by the <see cref="M:SuperOffice.Services81.IReportAgent.GetReportLabelLayoutEntity">SuperOffice.Services81.IReportAgent.GetReportLabelLayoutEntity</see> method.

## GetReportLabelLayoutEntity

Gets a ReportLabelLayoutEntity object.

* **reportLabelLayoutEntityId:** The identifier of the ReportLabelLayoutEntity object

**Returns:** ReportLabelLayoutEntity


[WSDL file for Services81/Report](../Services81-Report.md)

Obtain a ticket from the [Services81/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## GetReportLabelLayoutEntity Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices812="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices811="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Report="http://www.superoffice.net/ws/crm/NetServer/Services81">
  <Report:ApplicationToken>1234567-1234-9876</Report:ApplicationToken>
  <Report:Credentials>
    <Report:Ticket>7T:1234abcxyzExample==</Report:Ticket>
  </Report:Credentials>
 <SOAP-ENV:Body>
   <Report:GetReportLabelLayoutEntity>
    <Report:ReportLabelLayoutEntityId xsi:type="xsd:int">0</Report:ReportLabelLayoutEntityId>
   </Report:GetReportLabelLayoutEntity>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## GetReportLabelLayoutEntity Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices812="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices811="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Report="http://www.superoffice.net/ws/crm/NetServer/Services81">
 <SOAP-ENV:Body>
  <Report:GetReportLabelLayoutEntityResponse>
   <Report:Response xsi:type="Report:ReportLabelLayoutEntity">
    <Report:ReportLabelLayoutId xsi:type="xsd:int">0</Report:ReportLabelLayoutId>
    <Report:Name xsi:type="xsd:string"></Report:Name>
    <Report:Description xsi:type="xsd:string"></Report:Description>
    <Report:Orientation xsi:type="Report:ReportPaperOrientation">None</Report:Orientation>
    <Report:PaperWidth xsi:type="xsd:unsignedInt">0</Report:PaperWidth>
    <Report:PaperHeight xsi:type="xsd:unsignedInt">0</Report:PaperHeight>
    <Report:LeftMargin xsi:type="xsd:unsignedInt">0</Report:LeftMargin>
    <Report:RightMargin xsi:type="xsd:unsignedInt">0</Report:RightMargin>
    <Report:TopMargin xsi:type="xsd:unsignedInt">0</Report:TopMargin>
    <Report:BottomMargin xsi:type="xsd:unsignedInt">0</Report:BottomMargin>
    <Report:CountColumns xsi:type="xsd:short">0</Report:CountColumns>
    <Report:CountRows xsi:type="xsd:short">0</Report:CountRows>
   </Report:Response>
  </Report:GetReportLabelLayoutEntityResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
