---
uid: services75-timezone-setbasetimezoneid
title: Services75.TimeZoneAgent.SetBaseTimeZoneId SOAP
Generated: true
---

# Services75 TimeZone SetBaseTimeZoneId SOAP

SOAP request and response examples **Remote/Services75/TimeZone.svc**
Implemented by the <see cref="M:SuperOffice.Services75.ITimeZoneAgent.SetBaseTimeZoneId">SuperOffice.Services75.ITimeZoneAgent.SetBaseTimeZoneId</see> method.

## SetBaseTimeZoneId

Set the base timezone id.

* **timezoneId:** The timezone id to save

**Returns:** Returns true if setting of base timezone was done


[WSDL file for Services75/TimeZone](../Services75-TimeZone.md)

Obtain a ticket from the [Services75/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## SetBaseTimeZoneId Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices751="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:TimeZone="http://www.superoffice.net/ws/crm/NetServer/Services75">
  <TimeZone:ApplicationToken>1234567-1234-9876</TimeZone:ApplicationToken>
  <TimeZone:Credentials>
    <TimeZone:Ticket>7T:1234abcxyzExample==</TimeZone:Ticket>
  </TimeZone:Credentials>
 <SOAP-ENV:Body>
   <TimeZone:SetBaseTimeZoneId>
    <TimeZone:TimezoneId xsi:type="xsd:int">0</TimeZone:TimezoneId>
   </TimeZone:SetBaseTimeZoneId>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## SetBaseTimeZoneId Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices751="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:TimeZone="http://www.superoffice.net/ws/crm/NetServer/Services75">
 <SOAP-ENV:Body>
  <TimeZone:SetBaseTimeZoneIdResponse>
   <TimeZone:Response xsi:type="xsd:boolean">false</TimeZone:Response>
  </TimeZone:SetBaseTimeZoneIdResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
