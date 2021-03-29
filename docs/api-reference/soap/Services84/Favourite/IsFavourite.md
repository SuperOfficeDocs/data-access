---
uid: services84-favourite-isfavourite
title: Services84.FavouriteAgent.IsFavourite SOAP
Generated: true
---

# Services84 Favourite IsFavourite SOAP

SOAP request and response examples **Remote/Services84/Favourite.svc**
Implemented by the <see cref="M:SuperOffice.Services84.IFavouriteAgent.IsFavourite">SuperOffice.Services84.IFavouriteAgent.IsFavourite</see> method.

## IsFavourite

Checks if a record in a table is a favourite for an associate

* **tableName:** Table name, transformed to and from numeric table id by the service layer.
* **recordId:** 
* **associateId:** 



[WSDL file for Services84/Favourite](../Services84-Favourite.md)

Obtain a ticket from the [Services84/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## IsFavourite Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices842="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices841="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Favourite="http://www.superoffice.net/ws/crm/NetServer/Services84">
  <Favourite:ApplicationToken>1234567-1234-9876</Favourite:ApplicationToken>
  <Favourite:Credentials>
    <Favourite:Ticket>7T:1234abcxyzExample==</Favourite:Ticket>
  </Favourite:Credentials>
 <SOAP-ENV:Body>
   <Favourite:IsFavourite>
    <Favourite:TableName xsi:type="xsd:string"></Favourite:TableName>
    <Favourite:RecordId xsi:type="xsd:int">0</Favourite:RecordId>
    <Favourite:AssociateId xsi:type="xsd:int">0</Favourite:AssociateId>
   </Favourite:IsFavourite>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## IsFavourite Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices842="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices841="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Favourite="http://www.superoffice.net/ws/crm/NetServer/Services84">
 <SOAP-ENV:Body>
  <Favourite:IsFavouriteResponse>
   <Favourite:Response xsi:type="xsd:boolean">false</Favourite:Response>
  </Favourite:IsFavouriteResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
