---
uid: services84-pocket-setpushnotificationtagsfordevice
title: Services84.PocketAgent.SetPushNotificationTagsForDevice SOAP
Generated: true
---

# Services84 Pocket SetPushNotificationTagsForDevice SOAP

SOAP request and response examples **Remote/Services84/Pocket.svc**
Implemented by the <see cref="M:SuperOffice.Services84.IPocketAgent.SetPushNotificationTagsForDevice">SuperOffice.Services84.IPocketAgent.SetPushNotificationTagsForDevice</see> method.

## SetPushNotificationTagsForDevice

Specify what kind of notification events a device should receive push notifications for

* **deviceIdentifier:** The unique identifier for a device
* **tags:** A comma separated list of events this device should receive push events for



[WSDL file for Services84/Pocket](../Services84-Pocket.md)

Obtain a ticket from the [Services84/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## SetPushNotificationTagsForDevice Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices842="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices841="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Pocket="http://www.superoffice.net/ws/crm/NetServer/Services84">
  <Pocket:ApplicationToken>1234567-1234-9876</Pocket:ApplicationToken>
  <Pocket:Credentials>
    <Pocket:Ticket>7T:1234abcxyzExample==</Pocket:Ticket>
  </Pocket:Credentials>
 <SOAP-ENV:Body>
   <Pocket:SetPushNotificationTagsForDevice>
    <Pocket:DeviceIdentifier xsi:type="xsd:string"></Pocket:DeviceIdentifier>
    <Pocket:Tags xsi:type="xsd:string"></Pocket:Tags>
   </Pocket:SetPushNotificationTagsForDevice>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## SetPushNotificationTagsForDevice Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices842="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices841="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Pocket="http://www.superoffice.net/ws/crm/NetServer/Services84">
 <SOAP-ENV:Body>
  <Pocket:SetPushNotificationTagsForDeviceResponse>
  </Pocket:SetPushNotificationTagsForDeviceResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
