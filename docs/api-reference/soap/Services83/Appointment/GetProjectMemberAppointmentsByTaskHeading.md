---
uid: services83-appointment-getprojectmemberappointmentsbytaskheading
title: Services83.AppointmentAgent.GetProjectMemberAppointmentsByTaskHeading SOAP
Generated: true
---

# Services83 Appointment GetProjectMemberAppointmentsByTaskHeading SOAP

SOAP request and response examples **Remote/Services83/Appointment.svc**
Implemented by the <see cref="M:SuperOffice.Services83.IAppointmentAgent.GetProjectMemberAppointmentsByTaskHeading">SuperOffice.Services83.IAppointmentAgent.GetProjectMemberAppointmentsByTaskHeading</see> method.

## GetProjectMemberAppointmentsByTaskHeading

Method that returns a specified number of appointments of a specific appointment task heading within a time range. The appointments belong to the projects where the person specified is member. Task represents the different types of activities, like “Phone call”, “Meeting” and so on. The heading represents a grouping or filtering of tasks.

* **personId:** The project member's person id
* **startTime:** The start of the time interval we want appointments from. This will usually be the current time.
* **endTime:** The end of the time interval.
* **count:** The maximum number of appointments that should be returned. -1 means no count restrictions.
* **taskHeadingId:** The task heading id. The heading represents a grouping or filtering of tasks. Task represents the different types of activities, like “Phone call”, “Meeting” and so on.

**Returns:** Array of Appointments.


[WSDL file for Services83/Appointment](../Services83-Appointment.md)

Obtain a ticket from the [Services83/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## GetProjectMemberAppointmentsByTaskHeading Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices832="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices831="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Appointment="http://www.superoffice.net/ws/crm/NetServer/Services83">
  <Appointment:ApplicationToken>1234567-1234-9876</Appointment:ApplicationToken>
  <Appointment:Credentials>
    <Appointment:Ticket>7T:1234abcxyzExample==</Appointment:Ticket>
  </Appointment:Credentials>
 <SOAP-ENV:Body>
   <Appointment:GetProjectMemberAppointmentsByTaskHeading>
    <Appointment:PersonId xsi:type="xsd:int">0</Appointment:PersonId>
    <Appointment:StartTime xsi:type="xsd:dateTime">2021-03-25T21:34:59Z</Appointment:StartTime>
    <Appointment:EndTime xsi:type="xsd:dateTime">2021-03-25T21:34:59Z</Appointment:EndTime>
    <Appointment:Count xsi:type="xsd:int">0</Appointment:Count>
    <Appointment:TaskHeadingId xsi:type="xsd:int">0</Appointment:TaskHeadingId>
   </Appointment:GetProjectMemberAppointmentsByTaskHeading>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## GetProjectMemberAppointmentsByTaskHeading Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices832="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices831="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Appointment="http://www.superoffice.net/ws/crm/NetServer/Services83">
 <SOAP-ENV:Body>
  <Appointment:GetProjectMemberAppointmentsByTaskHeadingResponse>
   <Appointment:Response xsi:type="Appointment:ArrayOfAppointment">
    <Appointment:Appointment xsi:type="Appointment:Appointment">
     <Appointment:AppointmentId xsi:type="xsd:int">0</Appointment:AppointmentId>
     <Appointment:StartDate xsi:type="xsd:dateTime">2021-03-25T21:34:59Z</Appointment:StartDate>
     <Appointment:EndDate xsi:type="xsd:dateTime">2021-03-25T21:34:59Z</Appointment:EndDate>
     <Appointment:Type xsi:type="Appointment:AppointmentType">Unknown</Appointment:Type>
     <Appointment:Task xsi:type="xsd:string"></Appointment:Task>
     <Appointment:AssociateFullName xsi:type="xsd:string"></Appointment:AssociateFullName>
     <Appointment:ContactName xsi:type="xsd:string"></Appointment:ContactName>
     <Appointment:Description xsi:type="xsd:string"></Appointment:Description>
     <Appointment:PersonFullName xsi:type="xsd:string"></Appointment:PersonFullName>
     <Appointment:PersonId xsi:type="xsd:int">0</Appointment:PersonId>
     <Appointment:ContactId xsi:type="xsd:int">0</Appointment:ContactId>
     <Appointment:ProjectId xsi:type="xsd:int">0</Appointment:ProjectId>
     <Appointment:ProjectName xsi:type="xsd:string"></Appointment:ProjectName>
     <Appointment:IsPublished xsi:type="xsd:boolean">false</Appointment:IsPublished>
     <Appointment:AssociateId xsi:type="xsd:int">0</Appointment:AssociateId>
     <Appointment:ColorIndex xsi:type="xsd:short">0</Appointment:ColorIndex>
     <Appointment:IsFree xsi:type="xsd:boolean">false</Appointment:IsFree>
     <Appointment:HasAlarm xsi:type="xsd:boolean">false</Appointment:HasAlarm>
     <Appointment:IsAlldayEvent xsi:type="xsd:boolean">false</Appointment:IsAlldayEvent>
     <Appointment:Private xsi:type="Appointment:AppointmentPrivate">Public</Appointment:Private>
     <Appointment:PriorityId xsi:type="xsd:int">0</Appointment:PriorityId>
     <Appointment:PriorityName xsi:type="xsd:string"></Appointment:PriorityName>
     <Appointment:TaskType xsi:type="Appointment:TaskType">Unknown</Appointment:TaskType>
     <Appointment:IsBookingMain xsi:type="xsd:boolean">false</Appointment:IsBookingMain>
     <Appointment:IsRecurrence xsi:type="xsd:boolean">false</Appointment:IsRecurrence>
     <Appointment:IsBooking xsi:type="xsd:boolean">false</Appointment:IsBooking>
     <Appointment:ActiveDate xsi:type="xsd:dateTime">2021-03-25T21:34:59Z</Appointment:ActiveDate>
     <Appointment:AssignmentStatus xsi:type="Appointment:AssignmentStatus">Unknown</Appointment:AssignmentStatus>
     <Appointment:InvitationStatus xsi:type="Appointment:InvitationStatus">Unknown</Appointment:InvitationStatus>
     <Appointment:BookingType xsi:type="Appointment:BookingType">Unknown</Appointment:BookingType>
     <Appointment:Completed xsi:type="Appointment:ActivityStatus">Unknown</Appointment:Completed>
     <Appointment:RecurringPattern xsi:type="Appointment:RecurrencePattern">Unknown</Appointment:RecurringPattern>
     <Appointment:RecurringStartDate xsi:type="xsd:dateTime">2021-03-25T21:34:59Z</Appointment:RecurringStartDate>
     <Appointment:RecurringEndDate xsi:type="xsd:dateTime">2021-03-25T21:34:59Z</Appointment:RecurringEndDate>
     <Appointment:MotherId xsi:type="xsd:int">0</Appointment:MotherId>
     <Appointment:AssignedBy xsi:type="xsd:int">0</Appointment:AssignedBy>
     <Appointment:AssignedByFullName xsi:type="xsd:string"></Appointment:AssignedByFullName>
     <Appointment:RejectReason xsi:type="xsd:string"></Appointment:RejectReason>
     <Appointment:Location xsi:type="xsd:string"></Appointment:Location>
     <Appointment:AlarmLeadTime xsi:type="NetServerServices831:duration"></Appointment:AlarmLeadTime>
     <Appointment:SaleId xsi:type="xsd:int">0</Appointment:SaleId>
     <Appointment:SaleName xsi:type="xsd:string"></Appointment:SaleName>
     <Appointment:AssociateName xsi:type="xsd:string"></Appointment:AssociateName>
     <Appointment:CreatedDate xsi:type="xsd:dateTime">2021-03-25T21:34:59Z</Appointment:CreatedDate>
     <Appointment:CreatedBy xsi:type="xsd:string"></Appointment:CreatedBy>
     <Appointment:CreatedByFullName xsi:type="xsd:string"></Appointment:CreatedByFullName>
     <Appointment:CreatedByAssociateId xsi:type="xsd:int">0</Appointment:CreatedByAssociateId>
    </Appointment:Appointment>
   </Appointment:Response>
  </Appointment:GetProjectMemberAppointmentsByTaskHeadingResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
