---
uid: services83-list-getdocumenttemplatelist
title: Services83.ListAgent.GetDocumentTemplateList SOAP
Generated: true
---

# Services83 List GetDocumentTemplateList SOAP

SOAP request and response examples **Remote/Services83/List.svc**
Implemented by the <see cref="M:SuperOffice.Services83.IListAgent.GetDocumentTemplateList">SuperOffice.Services83.IListAgent.GetDocumentTemplateList</see> method.

## GetDocumentTemplateList

Gets an array of DocumentTemplate objects.

* **documentTemplateIds:** The identifiers of the DocumentTemplate object

**Returns:** Array of DocumentTemplate objects


[WSDL file for Services83/List](../Services83-List.md)

Obtain a ticket from the [Services83/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## GetDocumentTemplateList Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices832="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices831="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:List="http://www.superoffice.net/ws/crm/NetServer/Services83">
  <List:ApplicationToken>1234567-1234-9876</List:ApplicationToken>
  <List:Credentials>
    <List:Ticket>7T:1234abcxyzExample==</List:Ticket>
  </List:Credentials>
 <SOAP-ENV:Body>
   <List:GetDocumentTemplateList>
    <List:DocumentTemplateIds xsi:type="NetServerServices832:ArrayOfint">
     <NetServerServices832:int xsi:type="xsd:int">0</NetServerServices832:int>
    </List:DocumentTemplateIds>
   </List:GetDocumentTemplateList>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## GetDocumentTemplateList Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices832="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices831="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:List="http://www.superoffice.net/ws/crm/NetServer/Services83">
 <SOAP-ENV:Body>
  <List:GetDocumentTemplateListResponse>
   <List:Response xsi:type="List:ArrayOfDocumentTemplate">
    <List:DocumentTemplate xsi:type="List:DocumentTemplate">
     <List:DocumentTemplateId xsi:type="xsd:int">0</List:DocumentTemplateId>
     <List:Name xsi:type="xsd:string"></List:Name>
     <List:Tooltip xsi:type="xsd:string"></List:Tooltip>
     <List:SaveInDb xsi:type="xsd:short">0</List:SaveInDb>
     <List:Filename xsi:type="xsd:string"></List:Filename>
     <List:DefaultOref xsi:type="xsd:string"></List:DefaultOref>
     <List:RecordType xsi:type="List:DocTmplType">Unknown</List:RecordType>
     <List:Deleted xsi:type="xsd:short">0</List:Deleted>
     <List:Direction xsi:type="List:DocTmplDirection">Unknown</List:Direction>
     <List:AutoeventId xsi:type="xsd:int">0</List:AutoeventId>
     <List:QuoteDocType xsi:type="List:DocTmplQuoteType">None</List:QuoteDocType>
    </List:DocumentTemplate>
   </List:Response>
  </List:GetDocumentTemplateListResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
