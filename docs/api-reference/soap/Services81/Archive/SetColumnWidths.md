---
uid: services81-archive-setcolumnwidths
title: Services81.ArchiveAgent.SetColumnWidths SOAP
Generated: true
---

# Services81 Archive SetColumnWidths SOAP

SOAP request and response examples **Remote/Services81/Archive.svc**
Implemented by the <see cref="M:SuperOffice.Services81.IArchiveAgent.SetColumnWidths">SuperOffice.Services81.IArchiveAgent.SetColumnWidths</see> method.

## SetColumnWidths

Set the column widths for the given set of columns and GUI name.

* **guiName:** String that identifies the archive in the GUI, must be the same when fetching and storing configurations, but does not otherwise have to match anything.
* **columnWidths:** Array of column widths. A column width is specified either as a fixed number of character (10c) or as a percentage (10%). Percentages will be recalculated so that they add up to exactly 100 when the configuration is fetched again.



[WSDL file for Services81/Archive](../Services81-Archive.md)

Obtain a ticket from the [Services81/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## SetColumnWidths Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices812="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices811="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Archive="http://www.superoffice.net/ws/crm/NetServer/Services81">
  <Archive:ApplicationToken>1234567-1234-9876</Archive:ApplicationToken>
  <Archive:Credentials>
    <Archive:Ticket>7T:1234abcxyzExample==</Archive:Ticket>
  </Archive:Credentials>
 <SOAP-ENV:Body>
   <Archive:SetColumnWidths>
    <Archive:GuiName xsi:type="xsd:string"></Archive:GuiName>
    <Archive:ColumnWidths xsi:type="NetServerServices812:ArrayOfstring">
     <NetServerServices812:string xsi:type="xsd:string"></NetServerServices812:string>
    </Archive:ColumnWidths>
   </Archive:SetColumnWidths>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## SetColumnWidths Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices812="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices811="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Archive="http://www.superoffice.net/ws/crm/NetServer/Services81">
 <SOAP-ENV:Body>
  <Archive:SetColumnWidthsResponse>
  </Archive:SetColumnWidthsResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
