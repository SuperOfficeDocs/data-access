---
uid: services81-viewstate-sethistorylengthprefvalue
title: Services81.ViewStateAgent.SetHistoryLengthPrefValue SOAP
Generated: true
---

# Services81 ViewState SetHistoryLengthPrefValue SOAP

SOAP request and response examples **Remote/Services81/ViewState.svc**
Implemented by the <see cref="M:SuperOffice.Services81.IViewStateAgent.SetHistoryLengthPrefValue">SuperOffice.Services81.IViewStateAgent.SetHistoryLengthPrefValue</see> method.

## SetHistoryLengthPrefValue

Set the logged on user's preferred history list length.

* **length:** The new history list lenght



[WSDL file for Services81/ViewState](../Services81-ViewState.md)

Obtain a ticket from the [Services81/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## SetHistoryLengthPrefValue Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices812="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices811="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:ViewState="http://www.superoffice.net/ws/crm/NetServer/Services81">
  <ViewState:ApplicationToken>1234567-1234-9876</ViewState:ApplicationToken>
  <ViewState:Credentials>
    <ViewState:Ticket>7T:1234abcxyzExample==</ViewState:Ticket>
  </ViewState:Credentials>
 <SOAP-ENV:Body>
   <ViewState:SetHistoryLengthPrefValue>
    <ViewState:Length xsi:type="xsd:int">0</ViewState:Length>
   </ViewState:SetHistoryLengthPrefValue>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## SetHistoryLengthPrefValue Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices812="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices811="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:ViewState="http://www.superoffice.net/ws/crm/NetServer/Services81">
 <SOAP-ENV:Body>
  <ViewState:SetHistoryLengthPrefValueResponse>
  </ViewState:SetHistoryLengthPrefValueResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
