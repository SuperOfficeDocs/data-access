---
uid: services81-saint-savestatusmonitor
title: Services81.SaintAgent.SaveStatusMonitor SOAP
Generated: true
---

# Services81 Saint SaveStatusMonitor SOAP

SOAP request and response examples **Remote/Services81/Saint.svc**
Implemented by the <see cref="M:SuperOffice.Services81.ISaintAgent.SaveStatusMonitor">SuperOffice.Services81.ISaintAgent.SaveStatusMonitor</see> method.

## SaveStatusMonitor

Updates the existing StatusMonitor or creates a new StatusMonitor if the id parameter is empty

* **statusMonitor:** The StatusMonitor that is saved.

**Returns:** New or updated StatusMonitor


[WSDL file for Services81/Saint](../Services81-Saint.md)

Obtain a ticket from the [Services81/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## SaveStatusMonitor Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices812="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices811="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Saint="http://www.superoffice.net/ws/crm/NetServer/Services81">
  <Saint:ApplicationToken>1234567-1234-9876</Saint:ApplicationToken>
  <Saint:Credentials>
    <Saint:Ticket>7T:1234abcxyzExample==</Saint:Ticket>
  </Saint:Credentials>
 <SOAP-ENV:Body>
   <Saint:SaveStatusMonitor>
    <Saint:StatusMonitor xsi:type="Saint:StatusMonitor">
     <Saint:OwnerTable xsi:type="xsd:int">0</Saint:OwnerTable>
     <Saint:Rank xsi:type="xsd:int">0</Saint:Rank>
     <Saint:DefaultTask xsi:type="xsd:int">0</Saint:DefaultTask>
     <Saint:DefaultTaskText xsi:type="xsd:string"></Saint:DefaultTaskText>
     <Saint:IsVisual xsi:type="xsd:boolean">false</Saint:IsVisual>
     <Saint:LastGenerated xsi:type="xsd:dateTime">2021-03-25T21:34:36Z</Saint:LastGenerated>
     <Saint:Description xsi:type="xsd:string"></Saint:Description>
     <Saint:Name xsi:type="xsd:string"></Saint:Name>
     <Saint:StatusMonitorId xsi:type="xsd:int">0</Saint:StatusMonitorId>
     <Saint:PictureId xsi:type="xsd:int">0</Saint:PictureId>
     <Saint:NeedsUpdate xsi:type="xsd:boolean">false</Saint:NeedsUpdate>
     <Saint:Deleted xsi:type="xsd:boolean">false</Saint:Deleted>
     <Saint:NumMatches xsi:type="xsd:int">0</Saint:NumMatches>
     <Saint:NumNeedUpdate xsi:type="xsd:int">0</Saint:NumNeedUpdate>
    </Saint:StatusMonitor>
   </Saint:SaveStatusMonitor>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## SaveStatusMonitor Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices812="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices811="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Saint="http://www.superoffice.net/ws/crm/NetServer/Services81">
 <SOAP-ENV:Body>
  <Saint:SaveStatusMonitorResponse>
   <Saint:Response xsi:type="Saint:StatusMonitor">
    <Saint:OwnerTable xsi:type="xsd:int">0</Saint:OwnerTable>
    <Saint:Rank xsi:type="xsd:int">0</Saint:Rank>
    <Saint:DefaultTask xsi:type="xsd:int">0</Saint:DefaultTask>
    <Saint:DefaultTaskText xsi:type="xsd:string"></Saint:DefaultTaskText>
    <Saint:IsVisual xsi:type="xsd:boolean">false</Saint:IsVisual>
    <Saint:LastGenerated xsi:type="xsd:dateTime">2021-03-25T21:34:36Z</Saint:LastGenerated>
    <Saint:Description xsi:type="xsd:string"></Saint:Description>
    <Saint:Name xsi:type="xsd:string"></Saint:Name>
    <Saint:StatusMonitorId xsi:type="xsd:int">0</Saint:StatusMonitorId>
    <Saint:PictureId xsi:type="xsd:int">0</Saint:PictureId>
    <Saint:NeedsUpdate xsi:type="xsd:boolean">false</Saint:NeedsUpdate>
    <Saint:Deleted xsi:type="xsd:boolean">false</Saint:Deleted>
    <Saint:NumMatches xsi:type="xsd:int">0</Saint:NumMatches>
    <Saint:NumNeedUpdate xsi:type="xsd:int">0</Saint:NumNeedUpdate>
   </Saint:Response>
  </Saint:SaveStatusMonitorResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
