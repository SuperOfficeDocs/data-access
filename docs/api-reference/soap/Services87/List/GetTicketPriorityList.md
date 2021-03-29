---
uid: services87-list-getticketprioritylist
title: Services87.ListAgent.GetTicketPriorityList SOAP
Generated: true
---

# Services87 List GetTicketPriorityList SOAP

SOAP request and response examples **Remote/Services87/List.svc**
Implemented by the <see cref="M:SuperOffice.Services87.IListAgent.GetTicketPriorityList">SuperOffice.Services87.IListAgent.GetTicketPriorityList</see> method.

## GetTicketPriorityList

Gets an array of TicketPriority objects.

* **ticketPriorityIds:** The identifiers of the TicketPriority object

**Returns:** Array of TicketPriority objects


[WSDL file for Services87/List](../Services87-List.md)

Obtain a ticket from the [Services87/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## GetTicketPriorityList Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices872="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices871="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:List="http://www.superoffice.net/ws/crm/NetServer/Services87">
  <List:ApplicationToken>1234567-1234-9876</List:ApplicationToken>
  <List:Credentials>
    <List:Ticket>7T:1234abcxyzExample==</List:Ticket>
  </List:Credentials>
 <SOAP-ENV:Body>
   <List:GetTicketPriorityList>
    <List:TicketPriorityIds xsi:type="NetServerServices872:ArrayOfint">
     <NetServerServices872:int xsi:type="xsd:int">0</NetServerServices872:int>
    </List:TicketPriorityIds>
   </List:GetTicketPriorityList>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## GetTicketPriorityList Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices872="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices871="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:List="http://www.superoffice.net/ws/crm/NetServer/Services87">
 <SOAP-ENV:Body>
  <List:GetTicketPriorityListResponse>
   <List:Response xsi:type="List:ArrayOfTicketPriority">
    <List:TicketPriority xsi:type="List:TicketPriority">
     <List:Id xsi:type="xsd:int">0</List:Id>
     <List:Value xsi:type="xsd:string"></List:Value>
     <List:Tooltip xsi:type="xsd:string"></List:Tooltip>
    </List:TicketPriority>
   </List:Response>
  </List:GetTicketPriorityListResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
