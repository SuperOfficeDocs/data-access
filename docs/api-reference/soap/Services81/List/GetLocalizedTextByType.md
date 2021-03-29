---
uid: services81-list-getlocalizedtextbytype
title: Services81.ListAgent.GetLocalizedTextByType SOAP
Generated: true
---

# Services81 List GetLocalizedTextByType SOAP

SOAP request and response examples **Remote/Services81/List.svc**
Implemented by the <see cref="M:SuperOffice.Services81.IListAgent.GetLocalizedTextByType">SuperOffice.Services81.IListAgent.GetLocalizedTextByType</see> method.

## GetLocalizedTextByType

Returns a localized text based on the resource id for the selected language.

* **textType:** Type of the localized text
* **resourceId:** The resource id. This id has different meaning based on the LocalizedTextType.
* **languageId:** The LCID number of the language.

**Returns:** A LocalizedText carrier.


[WSDL file for Services81/List](../Services81-List.md)

Obtain a ticket from the [Services81/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## GetLocalizedTextByType Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices812="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices811="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:List="http://www.superoffice.net/ws/crm/NetServer/Services81">
  <List:ApplicationToken>1234567-1234-9876</List:ApplicationToken>
  <List:Credentials>
    <List:Ticket>7T:1234abcxyzExample==</List:Ticket>
  </List:Credentials>
 <SOAP-ENV:Body>
   <List:GetLocalizedTextByType>
    <List:TextType xsi:type="List:LocalizedTextType">Unknown</List:TextType>
    <List:ResourceId xsi:type="xsd:int">0</List:ResourceId>
    <List:LanguageId xsi:type="xsd:int">0</List:LanguageId>
   </List:GetLocalizedTextByType>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## GetLocalizedTextByType Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices812="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices811="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:List="http://www.superoffice.net/ws/crm/NetServer/Services81">
 <SOAP-ENV:Body>
  <List:GetLocalizedTextByTypeResponse>
   <List:Response xsi:type="List:LocalizedText">
    <List:LanguageId xsi:type="xsd:int">0</List:LanguageId>
    <List:ResourceId xsi:type="xsd:int">0</List:ResourceId>
    <List:Text xsi:type="xsd:string"></List:Text>
    <List:Type xsi:type="List:LocalizedTextType">Unknown</List:Type>
    <List:LocalizedTextId xsi:type="xsd:int">0</List:LocalizedTextId>
    <List:IsBuiltIn xsi:type="xsd:boolean">false</List:IsBuiltIn>
   </List:Response>
  </List:GetLocalizedTextByTypeResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
