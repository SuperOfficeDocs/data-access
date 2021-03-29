---
uid: services83-report-deletereportlabellayoutentity
title: Services83.ReportAgent.DeleteReportLabelLayoutEntity SOAP
Generated: true
---

# Services83 Report DeleteReportLabelLayoutEntity SOAP

SOAP request and response examples **Remote/Services83/Report.svc**
Implemented by the <see cref="M:SuperOffice.Services83.IReportAgent.DeleteReportLabelLayoutEntity">SuperOffice.Services83.IReportAgent.DeleteReportLabelLayoutEntity</see> method.

## DeleteReportLabelLayoutEntity

Deletes the ReportLabelLayoutEntity

* **reportLabelLayoutEntityId:** The identity of the ReportLabelLayoutEntity



[WSDL file for Services83/Report](../Services83-Report.md)

Obtain a ticket from the [Services83/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## DeleteReportLabelLayoutEntity Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices832="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices831="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Report="http://www.superoffice.net/ws/crm/NetServer/Services83">
  <Report:ApplicationToken>1234567-1234-9876</Report:ApplicationToken>
  <Report:Credentials>
    <Report:Ticket>7T:1234abcxyzExample==</Report:Ticket>
  </Report:Credentials>
 <SOAP-ENV:Body>
   <Report:DeleteReportLabelLayoutEntity>
    <Report:ReportLabelLayoutEntityId xsi:type="xsd:int">0</Report:ReportLabelLayoutEntityId>
   </Report:DeleteReportLabelLayoutEntity>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## DeleteReportLabelLayoutEntity Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices832="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices831="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Report="http://www.superoffice.net/ws/crm/NetServer/Services83">
 <SOAP-ENV:Body>
  <Report:DeleteReportLabelLayoutEntityResponse>
  </Report:DeleteReportLabelLayoutEntityResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
