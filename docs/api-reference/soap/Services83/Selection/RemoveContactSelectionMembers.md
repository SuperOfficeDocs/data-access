---
uid: services83-selection-removecontactselectionmembers
title: Services83.SelectionAgent.RemoveContactSelectionMembers SOAP
Generated: true
---

# Services83 Selection RemoveContactSelectionMembers SOAP

SOAP request and response examples **Remote/Services83/Selection.svc**
Implemented by the <see cref="M:SuperOffice.Services83.ISelectionAgent.RemoveContactSelectionMembers">SuperOffice.Services83.ISelectionAgent.RemoveContactSelectionMembers</see> method.

## RemoveContactSelectionMembers

Removes members from the selection as  specified in the collection of ContactPersonId.

* **selectionId:** The id of the selection where to members will be removed.
* **contactPersonIds:** A collection of ContactPersonId to remove from the static selection.



[WSDL file for Services83/Selection](../Services83-Selection.md)

Obtain a ticket from the [Services83/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## RemoveContactSelectionMembers Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices832="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices831="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Selection="http://www.superoffice.net/ws/crm/NetServer/Services83">
  <Selection:ApplicationToken>1234567-1234-9876</Selection:ApplicationToken>
  <Selection:Credentials>
    <Selection:Ticket>7T:1234abcxyzExample==</Selection:Ticket>
  </Selection:Credentials>
 <SOAP-ENV:Body>
   <Selection:RemoveContactSelectionMembers>
    <Selection:SelectionId xsi:type="xsd:int">0</Selection:SelectionId>
    <Selection:ContactPersonIds xsi:type="Selection:ArrayOfContactPersonId">
     <Selection:ContactPersonId xsi:type="Selection:ContactPersonId">
      <Selection:PersonId xsi:type="xsd:int">0</Selection:PersonId>
      <Selection:ContactId xsi:type="xsd:int">0</Selection:ContactId>
     </Selection:ContactPersonId>
    </Selection:ContactPersonIds>
   </Selection:RemoveContactSelectionMembers>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## RemoveContactSelectionMembers Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices832="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices831="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Selection="http://www.superoffice.net/ws/crm/NetServer/Services83">
 <SOAP-ENV:Body>
  <Selection:RemoveContactSelectionMembersResponse>
  </Selection:RemoveContactSelectionMembersResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
