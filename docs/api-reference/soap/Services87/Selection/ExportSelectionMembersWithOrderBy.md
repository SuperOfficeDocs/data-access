---
uid: services87-selection-exportselectionmemberswithorderby
title: Services87.SelectionAgent.ExportSelectionMembersWithOrderBy SOAP
Generated: true
---

# Services87 Selection ExportSelectionMembersWithOrderBy SOAP

SOAP request and response examples **Remote/Services87/Selection.svc**
Implemented by the <see cref="M:SuperOffice.Services87.ISelectionAgent.ExportSelectionMembersWithOrderBy">SuperOffice.Services87.ISelectionAgent.ExportSelectionMembersWithOrderBy</see> method.

## ExportSelectionMembersWithOrderBy

ExportSelectionMembers will generate a string that is the result of substituting the template variables with values from selectionmembers.

* **selectionId:** The id of the selection to generate the exported file.
* **templateName:** The templateName parameter is the relative path of a .sxf file template. The .sxf files can be found in \template or in the user folder of the so archive.
* **useContacts:** If the selection contains other members than contacts, setting this to true will export the contact archive of the selection.
* **orderBy:** OrderBy. &lt;Column,OrderBySortType&gt;

**Returns:** Returns a unicode byte array with the file to export to the user.


[WSDL file for Services87/Selection](../Services87-Selection.md)

Obtain a ticket from the [Services87/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## ExportSelectionMembersWithOrderBy Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices872="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices871="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Selection="http://www.superoffice.net/ws/crm/NetServer/Services87">
  <Selection:ApplicationToken>1234567-1234-9876</Selection:ApplicationToken>
  <Selection:Credentials>
    <Selection:Ticket>7T:1234abcxyzExample==</Selection:Ticket>
  </Selection:Credentials>
 <SOAP-ENV:Body>
   <Selection:ExportSelectionMembersWithOrderBy>
    <Selection:SelectionId xsi:type="xsd:int">0</Selection:SelectionId>
    <Selection:TemplateName xsi:type="xsd:string"></Selection:TemplateName>
    <Selection:UseContacts xsi:type="xsd:boolean">false</Selection:UseContacts>
    <Selection:OrderBy xsi:type="xsd:string"></Selection:OrderBy>
   </Selection:ExportSelectionMembersWithOrderBy>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## ExportSelectionMembersWithOrderBy Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices872="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices871="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Selection="http://www.superoffice.net/ws/crm/NetServer/Services87">
 <SOAP-ENV:Body>
  <Selection:ExportSelectionMembersWithOrderByResponse>
   <Selection:Response xsi:type="xsd:base64Binary"></Selection:Response>
  </Selection:ExportSelectionMembersWithOrderByResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
