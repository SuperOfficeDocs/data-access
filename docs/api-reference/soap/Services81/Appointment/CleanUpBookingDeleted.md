---
uid: services81-appointment-cleanupbookingdeleted
title: Services81.AppointmentAgent.CleanUpBookingDeleted SOAP
Generated: true
---

# Services81 Appointment CleanUpBookingDeleted SOAP

SOAP request and response examples **Remote/Services81/Appointment.svc**
Implemented by the <see cref="M:SuperOffice.Services81.IAppointmentAgent.CleanUpBookingDeleted">SuperOffice.Services81.IAppointmentAgent.CleanUpBookingDeleted</see> method.

## CleanUpBookingDeleted

Deletes all appointments(within the appointmentIds array) with status BookingDeleted.

* **appointmentIds:** 



[WSDL file for Services81/Appointment](../Services81-Appointment.md)

Obtain a ticket from the [Services81/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## CleanUpBookingDeleted Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices812="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices811="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Appointment="http://www.superoffice.net/ws/crm/NetServer/Services81">
  <Appointment:ApplicationToken>1234567-1234-9876</Appointment:ApplicationToken>
  <Appointment:Credentials>
    <Appointment:Ticket>7T:1234abcxyzExample==</Appointment:Ticket>
  </Appointment:Credentials>
 <SOAP-ENV:Body>
   <Appointment:CleanUpBookingDeleted>
    <Appointment:AppointmentIds xsi:type="NetServerServices812:ArrayOfint">
     <NetServerServices812:int xsi:type="xsd:int">0</NetServerServices812:int>
    </Appointment:AppointmentIds>
   </Appointment:CleanUpBookingDeleted>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## CleanUpBookingDeleted Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices812="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices811="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Appointment="http://www.superoffice.net/ws/crm/NetServer/Services81">
 <SOAP-ENV:Body>
  <Appointment:CleanUpBookingDeletedResponse>
   <Appointment:Response xsi:type="xsd:int">0</Appointment:Response>
  </Appointment:CleanUpBookingDeletedResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
