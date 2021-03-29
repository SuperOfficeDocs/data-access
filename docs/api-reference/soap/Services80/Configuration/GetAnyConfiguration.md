---
uid: services80-configuration-getanyconfiguration
title: Services80.ConfigurationAgent.GetAnyConfiguration SOAP
Generated: true
---

# Services80 Configuration GetAnyConfiguration SOAP

SOAP request and response examples **Remote/Services80/Configuration.svc**
Implemented by the <see cref="M:SuperOffice.Services80.IConfigurationAgent.GetAnyConfiguration">SuperOffice.Services80.IConfigurationAgent.GetAnyConfiguration</see> method.

## GetAnyConfiguration

Get one defined configuration fragment, with full reference resolution and parsing applied. This is essentially the same service as the GetPageConfiguration, except that this service is not locked to objects of type Page.

* **application:** The application name, for instance Six.Web
* **instance:** The instance name, for instance Main
* **item:** The configuration item name (first component of file name)
* **type:** The configuration item type (second component of file name)

**Returns:** Fully resolved and parsed configuration XML, as string.


[WSDL file for Services80/Configuration](../Services80-Configuration.md)

Obtain a ticket from the [Services80/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## GetAnyConfiguration Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices802="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices801="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Configuration="http://www.superoffice.net/ws/crm/NetServer/Services80">
  <Configuration:ApplicationToken>1234567-1234-9876</Configuration:ApplicationToken>
  <Configuration:Credentials>
    <Configuration:Ticket>7T:1234abcxyzExample==</Configuration:Ticket>
  </Configuration:Credentials>
 <SOAP-ENV:Body>
   <Configuration:GetAnyConfiguration>
    <Configuration:Application xsi:type="xsd:string"></Configuration:Application>
    <Configuration:Instance xsi:type="xsd:string"></Configuration:Instance>
    <Configuration:Item xsi:type="xsd:string"></Configuration:Item>
    <Configuration:Type xsi:type="xsd:string"></Configuration:Type>
   </Configuration:GetAnyConfiguration>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## GetAnyConfiguration Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices802="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices801="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Configuration="http://www.superoffice.net/ws/crm/NetServer/Services80">
 <SOAP-ENV:Body>
  <Configuration:GetAnyConfigurationResponse>
   <Configuration:Response xsi:type="xsd:string"></Configuration:Response>
  </Configuration:GetAnyConfigurationResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
