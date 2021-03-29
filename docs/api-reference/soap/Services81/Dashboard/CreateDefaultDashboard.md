---
uid: services81-dashboard-createdefaultdashboard
title: Services81.DashboardAgent.CreateDefaultDashboard SOAP
Generated: true
---

# Services81 Dashboard CreateDefaultDashboard SOAP

SOAP request and response examples **Remote/Services81/Dashboard.svc**
Implemented by the <see cref="M:SuperOffice.Services81.IDashboardAgent.CreateDefaultDashboard">SuperOffice.Services81.IDashboardAgent.CreateDefaultDashboard</see> method.

## CreateDefaultDashboard

Loading default values into a new Dashboard.
NetServer calculates default values (e.g. Country) on the entity, which is required when creating/storing a new instance


**Returns:** New Dashboard with default values


[WSDL file for Services81/Dashboard](../Services81-Dashboard.md)

Obtain a ticket from the [Services81/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## CreateDefaultDashboard Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices811="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Dashboard="http://www.superoffice.net/ws/crm/NetServer/Services81">
  <Dashboard:ApplicationToken>1234567-1234-9876</Dashboard:ApplicationToken>
  <Dashboard:Credentials>
    <Dashboard:Ticket>7T:1234abcxyzExample==</Dashboard:Ticket>
  </Dashboard:Credentials>
 <SOAP-ENV:Body>
   <Dashboard:CreateDefaultDashboard>
   </Dashboard:CreateDefaultDashboard>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## CreateDefaultDashboard Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices811="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Dashboard="http://www.superoffice.net/ws/crm/NetServer/Services81">
 <SOAP-ENV:Body>
  <Dashboard:CreateDefaultDashboardResponse>
   <Dashboard:Response xsi:type="Dashboard:Dashboard">
    <Dashboard:DashboardId xsi:type="xsd:int">0</Dashboard:DashboardId>
    <Dashboard:AssociateId xsi:type="xsd:int">0</Dashboard:AssociateId>
    <Dashboard:Caption xsi:type="xsd:string"></Dashboard:Caption>
    <Dashboard:Layout xsi:type="Dashboard:DashboardLayout">None</Dashboard:Layout>
    <Dashboard:Tiles xsi:type="Dashboard:ArrayOfDashboardTile">
     <Dashboard:DashboardTile xsi:type="Dashboard:DashboardTile">
      <Dashboard:DashboardTileId xsi:type="xsd:int">0</Dashboard:DashboardTileId>
      <Dashboard:Caption xsi:type="xsd:string"></Dashboard:Caption>
      <Dashboard:Description xsi:type="xsd:string"></Dashboard:Description>
      <Dashboard:AssociateId xsi:type="xsd:int">0</Dashboard:AssociateId>
      <Dashboard:Config xsi:type="xsd:string"></Dashboard:Config>
      <Dashboard:Type xsi:type="Dashboard:DashboardTileType">None</Dashboard:Type>
      <Dashboard:EntityType xsi:type="Dashboard:DashboardTileEntityType">None</Dashboard:EntityType>
     </Dashboard:DashboardTile>
    </Dashboard:Tiles>
   </Dashboard:Response>
  </Dashboard:CreateDefaultDashboardResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
