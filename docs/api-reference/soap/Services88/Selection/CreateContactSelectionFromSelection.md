---
uid: services88-selection-createcontactselectionfromselection
title: Services88.SelectionAgent.CreateContactSelectionFromSelection SOAP
Generated: true
---

# Services88 Selection CreateContactSelectionFromSelection SOAP

SOAP request and response examples **Remote/Services88/Selection.svc**
Implemented by the <see cref="M:SuperOffice.Services88.ISelectionAgent.CreateContactSelectionFromSelection">SuperOffice.Services88.ISelectionAgent.CreateContactSelectionFromSelection</see> method.

## CreateContactSelectionFromSelection

Creates a new selection based on selection members from an existing selection.

* **selectionId:** The id of the selection to copy members from.
* **name:** The name of the new selection.
* **targetSelectionType:** The type of ContactSelection to create. The type can be static or dynamic. If the original selection to copy from is static, the SelectionType can only be static. If the original selection is dynamic, both a static and dynamic selection can be created.
* **copyMembers:** If true, the members from the original selection will be added to the newly created selection.

**Returns:** Returns the newly created SelectionEntity.


[WSDL file for Services88/Selection](../Services88-Selection.md)

Obtain a ticket from the [Services88/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## CreateContactSelectionFromSelection Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices882="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices881="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Selection="http://www.superoffice.net/ws/crm/NetServer/Services88">
  <Selection:ApplicationToken>1234567-1234-9876</Selection:ApplicationToken>
  <Selection:Credentials>
    <Selection:Ticket>7T:1234abcxyzExample==</Selection:Ticket>
  </Selection:Credentials>
 <SOAP-ENV:Body>
   <Selection:CreateContactSelectionFromSelection>
    <Selection:SelectionId xsi:type="xsd:int">0</Selection:SelectionId>
    <Selection:Name xsi:type="xsd:string"></Selection:Name>
    <Selection:TargetSelectionType xsi:type="Selection:SelectionType">Static</Selection:TargetSelectionType>
    <Selection:CopyMembers xsi:type="xsd:boolean">false</Selection:CopyMembers>
   </Selection:CreateContactSelectionFromSelection>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## CreateContactSelectionFromSelection Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices882="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices881="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Selection="http://www.superoffice.net/ws/crm/NetServer/Services88">
 <SOAP-ENV:Body>
  <Selection:CreateContactSelectionFromSelectionResponse>
   <Selection:Response xsi:type="Selection:SelectionEntity">
    <Selection:Description xsi:type="xsd:string"></Selection:Description>
    <Selection:Postit xsi:type="xsd:string"></Selection:Postit>
    <Selection:Associate xsi:type="Selection:Associate">
     <Selection:AssociateId xsi:type="xsd:int">0</Selection:AssociateId>
     <Selection:Name xsi:type="xsd:string"></Selection:Name>
     <Selection:PersonId xsi:type="xsd:int">0</Selection:PersonId>
     <Selection:Rank xsi:type="xsd:short">0</Selection:Rank>
     <Selection:Tooltip xsi:type="xsd:string"></Selection:Tooltip>
     <Selection:Type xsi:type="Selection:UserType">Unknown</Selection:Type>
     <Selection:GroupIdx xsi:type="xsd:int">0</Selection:GroupIdx>
     <Selection:FullName xsi:type="xsd:string"></Selection:FullName>
     <Selection:FormalName xsi:type="xsd:string"></Selection:FormalName>
     <Selection:Deleted xsi:type="xsd:boolean">false</Selection:Deleted>
     <Selection:EjUserId xsi:type="xsd:int">0</Selection:EjUserId>
     <Selection:UserName xsi:type="xsd:string"></Selection:UserName>
    </Selection:Associate>
    <Selection:CreatedBy xsi:type="Selection:Associate">
     <Selection:AssociateId xsi:type="xsd:int">0</Selection:AssociateId>
     <Selection:Name xsi:type="xsd:string"></Selection:Name>
     <Selection:PersonId xsi:type="xsd:int">0</Selection:PersonId>
     <Selection:Rank xsi:type="xsd:short">0</Selection:Rank>
     <Selection:Tooltip xsi:type="xsd:string"></Selection:Tooltip>
     <Selection:Type xsi:type="Selection:UserType">Unknown</Selection:Type>
     <Selection:GroupIdx xsi:type="xsd:int">0</Selection:GroupIdx>
     <Selection:FullName xsi:type="xsd:string"></Selection:FullName>
     <Selection:FormalName xsi:type="xsd:string"></Selection:FormalName>
     <Selection:Deleted xsi:type="xsd:boolean">false</Selection:Deleted>
     <Selection:EjUserId xsi:type="xsd:int">0</Selection:EjUserId>
     <Selection:UserName xsi:type="xsd:string"></Selection:UserName>
    </Selection:CreatedBy>
    <Selection:UpdatedBy xsi:type="Selection:Associate">
     <Selection:AssociateId xsi:type="xsd:int">0</Selection:AssociateId>
     <Selection:Name xsi:type="xsd:string"></Selection:Name>
     <Selection:PersonId xsi:type="xsd:int">0</Selection:PersonId>
     <Selection:Rank xsi:type="xsd:short">0</Selection:Rank>
     <Selection:Tooltip xsi:type="xsd:string"></Selection:Tooltip>
     <Selection:Type xsi:type="Selection:UserType">Unknown</Selection:Type>
     <Selection:GroupIdx xsi:type="xsd:int">0</Selection:GroupIdx>
     <Selection:FullName xsi:type="xsd:string"></Selection:FullName>
     <Selection:FormalName xsi:type="xsd:string"></Selection:FormalName>
     <Selection:Deleted xsi:type="xsd:boolean">false</Selection:Deleted>
     <Selection:EjUserId xsi:type="xsd:int">0</Selection:EjUserId>
     <Selection:UserName xsi:type="xsd:string"></Selection:UserName>
    </Selection:UpdatedBy>
    <Selection:SelectionCategory xsi:type="Selection:SelectionCategory">
     <Selection:Id xsi:type="xsd:int">0</Selection:Id>
     <Selection:Value xsi:type="xsd:string"></Selection:Value>
     <Selection:Tooltip xsi:type="xsd:string"></Selection:Tooltip>
    </Selection:SelectionCategory>
    <Selection:GroupIdx xsi:type="xsd:int">0</Selection:GroupIdx>
    <Selection:IncludePerson xsi:type="xsd:int">0</Selection:IncludePerson>
    <Selection:MemberCount xsi:type="xsd:unsignedInt">0</Selection:MemberCount>
    <Selection:Name xsi:type="xsd:string"></Selection:Name>
    <Selection:PostitTextId xsi:type="xsd:int">0</Selection:PostitTextId>
    <Selection:CreatedDate xsi:type="xsd:dateTime">2021-03-25T21:37:10Z</Selection:CreatedDate>
    <Selection:SelectionId xsi:type="xsd:int">0</Selection:SelectionId>
    <Selection:SoundEx xsi:type="xsd:string"></Selection:SoundEx>
    <Selection:Source xsi:type="xsd:short">0</Selection:Source>
    <Selection:TextId xsi:type="xsd:int">0</Selection:TextId>
    <Selection:UpdatedDate xsi:type="xsd:dateTime">2021-03-25T21:37:10Z</Selection:UpdatedDate>
    <Selection:UpdatedCount xsi:type="xsd:short">0</Selection:UpdatedCount>
    <Selection:Visibility xsi:type="xsd:short">0</Selection:Visibility>
    <Selection:SelectionType xsi:type="Selection:SelectionType">Static</Selection:SelectionType>
    <Selection:CompanyUnique xsi:type="xsd:boolean">false</Selection:CompanyUnique>
    <Selection:TargetTableNumber xsi:type="xsd:int">0</Selection:TargetTableNumber>
    <Selection:TargetTableName xsi:type="xsd:string"></Selection:TargetTableName>
    <Selection:Completed xsi:type="xsd:boolean">false</Selection:Completed>
    <Selection:LeftSelectionId xsi:type="xsd:int">0</Selection:LeftSelectionId>
    <Selection:RightSelectionId xsi:type="xsd:int">0</Selection:RightSelectionId>
    <Selection:SelectionUnionType xsi:type="Selection:SelectionUnionType">Unknown</Selection:SelectionUnionType>
    <Selection:MainProviderName xsi:type="xsd:string"></Selection:MainProviderName>
    <Selection:ShadowProviderName xsi:type="xsd:string"></Selection:ShadowProviderName>
    <Selection:ChartKey xsi:type="xsd:string"></Selection:ChartKey>
    <Selection:LastLoaded xsi:type="xsd:dateTime">2021-03-25T21:37:10Z</Selection:LastLoaded>
    <Selection:LastLoadedBy xsi:type="xsd:int">0</Selection:LastLoadedBy>
    <Selection:LastLoadedByAssociate xsi:type="Selection:Associate">
     <Selection:AssociateId xsi:type="xsd:int">0</Selection:AssociateId>
     <Selection:Name xsi:type="xsd:string"></Selection:Name>
     <Selection:PersonId xsi:type="xsd:int">0</Selection:PersonId>
     <Selection:Rank xsi:type="xsd:short">0</Selection:Rank>
     <Selection:Tooltip xsi:type="xsd:string"></Selection:Tooltip>
     <Selection:Type xsi:type="Selection:UserType">Unknown</Selection:Type>
     <Selection:GroupIdx xsi:type="xsd:int">0</Selection:GroupIdx>
     <Selection:FullName xsi:type="xsd:string"></Selection:FullName>
     <Selection:FormalName xsi:type="xsd:string"></Selection:FormalName>
     <Selection:Deleted xsi:type="xsd:boolean">false</Selection:Deleted>
     <Selection:EjUserId xsi:type="xsd:int">0</Selection:EjUserId>
     <Selection:UserName xsi:type="xsd:string"></Selection:UserName>
    </Selection:LastLoadedByAssociate>
    <Selection:LastMembershipChange xsi:type="xsd:dateTime">2021-03-25T21:37:10Z</Selection:LastMembershipChange>
    <Selection:LastMembershipChangeBy xsi:type="xsd:int">0</Selection:LastMembershipChangeBy>
    <Selection:LastMembershipChangeByAssociate xsi:type="Selection:Associate">
     <Selection:AssociateId xsi:type="xsd:int">0</Selection:AssociateId>
     <Selection:Name xsi:type="xsd:string"></Selection:Name>
     <Selection:PersonId xsi:type="xsd:int">0</Selection:PersonId>
     <Selection:Rank xsi:type="xsd:short">0</Selection:Rank>
     <Selection:Tooltip xsi:type="xsd:string"></Selection:Tooltip>
     <Selection:Type xsi:type="Selection:UserType">Unknown</Selection:Type>
     <Selection:GroupIdx xsi:type="xsd:int">0</Selection:GroupIdx>
     <Selection:FullName xsi:type="xsd:string"></Selection:FullName>
     <Selection:FormalName xsi:type="xsd:string"></Selection:FormalName>
     <Selection:Deleted xsi:type="xsd:boolean">false</Selection:Deleted>
     <Selection:EjUserId xsi:type="xsd:int">0</Selection:EjUserId>
     <Selection:UserName xsi:type="xsd:string"></Selection:UserName>
    </Selection:LastMembershipChangeByAssociate>
    <Selection:MainHeading xsi:type="xsd:string"></Selection:MainHeading>
    <Selection:MemberTabHeading xsi:type="xsd:string"></Selection:MemberTabHeading>
    <Selection:MailingsProviderName xsi:type="xsd:string"></Selection:MailingsProviderName>
    <Selection:VisibleFor xsi:type="Selection:ArrayOfVisibleFor">
     <Selection:VisibleFor xsi:type="Selection:VisibleFor">
      <Selection:VisibleId xsi:type="xsd:int">0</Selection:VisibleId>
      <Selection:Visibility xsi:type="Selection:Visibility">All</Selection:Visibility>
      <Selection:DisplayValue xsi:type="xsd:string"></Selection:DisplayValue>
     </Selection:VisibleFor>
    </Selection:VisibleFor>
   </Selection:Response>
  </Selection:CreateContactSelectionFromSelectionResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
