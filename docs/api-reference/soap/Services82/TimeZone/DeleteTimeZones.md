---
uid: services82-timezone-deletetimezones
title: Services82.TimeZoneAgent.DeleteTimeZones SOAP
Generated: true
---

# Services82 TimeZone DeleteTimeZones SOAP

SOAP request and response examples **Remote/Services82/TimeZone.svc**
Implemented by the <see cref="M:SuperOffice.Services82.ITimeZoneAgent.DeleteTimeZones">SuperOffice.Services82.ITimeZoneAgent.DeleteTimeZones</see> method.

## DeleteTimeZones

Deletes all time zone data (locations and rules) from the database




[WSDL file for Services82/TimeZone](../Services82-TimeZone.md)

Obtain a ticket from the [Services82/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## DeleteTimeZones Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices821="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:TimeZone="http://www.superoffice.net/ws/crm/NetServer/Services82">
  <TimeZone:ApplicationToken>1234567-1234-9876</TimeZone:ApplicationToken>
  <TimeZone:Credentials>
    <TimeZone:Ticket>7T:1234abcxyzExample==</TimeZone:Ticket>
  </TimeZone:Credentials>
 <SOAP-ENV:Body>
   <TimeZone:DeleteTimeZones>
   </TimeZone:DeleteTimeZones>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## DeleteTimeZones Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices821="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:TimeZone="http://www.superoffice.net/ws/crm/NetServer/Services82">
 <SOAP-ENV:Body>
  <TimeZone:DeleteTimeZonesResponse>
  </TimeZone:DeleteTimeZonesResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
