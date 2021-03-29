---
uid: services80-userdefinedfieldinfo-detectunpublishedchanges
title: Services80.UserDefinedFieldInfoAgent.DetectUnpublishedChanges SOAP
Generated: true
---

# Services80 UserDefinedFieldInfo DetectUnpublishedChanges SOAP

SOAP request and response examples **Remote/Services80/UserDefinedFieldInfo.svc**
Implemented by the <see cref="M:SuperOffice.Services80.IUserDefinedFieldInfoAgent.DetectUnpublishedChanges">SuperOffice.Services80.IUserDefinedFieldInfoAgent.DetectUnpublishedChanges</see> method.

## DetectUnpublishedChanges

Detect changes to the admin version (unpublished)

* **ownerType:** The owner type

**Returns:** Returns true if changes where found


[WSDL file for Services80/UserDefinedFieldInfo](../Services80-UserDefinedFieldInfo.md)

Obtain a ticket from the [Services80/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## DetectUnpublishedChanges Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices802="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices801="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:UserDefinedFieldInfo="http://www.superoffice.net/ws/crm/NetServer/Services80">
  <UserDefinedFieldInfo:ApplicationToken>1234567-1234-9876</UserDefinedFieldInfo:ApplicationToken>
  <UserDefinedFieldInfo:Credentials>
    <UserDefinedFieldInfo:Ticket>7T:1234abcxyzExample==</UserDefinedFieldInfo:Ticket>
  </UserDefinedFieldInfo:Credentials>
 <SOAP-ENV:Body>
   <UserDefinedFieldInfo:DetectUnpublishedChanges>
    <UserDefinedFieldInfo:OwnerType xsi:type="UserDefinedFieldInfo:UDefType">Invalid</UserDefinedFieldInfo:OwnerType>
   </UserDefinedFieldInfo:DetectUnpublishedChanges>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## DetectUnpublishedChanges Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices802="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices801="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:UserDefinedFieldInfo="http://www.superoffice.net/ws/crm/NetServer/Services80">
 <SOAP-ENV:Body>
  <UserDefinedFieldInfo:DetectUnpublishedChangesResponse>
   <UserDefinedFieldInfo:Response xsi:type="xsd:boolean">false</UserDefinedFieldInfo:Response>
  </UserDefinedFieldInfo:DetectUnpublishedChangesResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
