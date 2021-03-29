---
uid: services82-userdefinedfieldinfo-setuserdefinedpageonefield
title: Services82.UserDefinedFieldInfoAgent.SetUserDefinedPageOneField SOAP
Generated: true
---

# Services82 UserDefinedFieldInfo SetUserDefinedPageOneField SOAP

SOAP request and response examples **Remote/Services82/UserDefinedFieldInfo.svc**
Implemented by the <see cref="M:SuperOffice.Services82.IUserDefinedFieldInfoAgent.SetUserDefinedPageOneField">SuperOffice.Services82.IUserDefinedFieldInfoAgent.SetUserDefinedPageOneField</see> method.

## SetUserDefinedPageOneField

Sets a user defined fields as page one field.

* **ownerType:** The user-defined field owner entity
* **udefFieldId:** The id of the udeffield to set as page one field
* **userGroupId:** The usergroup id to associate the page one field with.
* **fieldLineNo:** Page one line number



[WSDL file for Services82/UserDefinedFieldInfo](../Services82-UserDefinedFieldInfo.md)

Obtain a ticket from the [Services82/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## SetUserDefinedPageOneField Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices822="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices821="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:UserDefinedFieldInfo="http://www.superoffice.net/ws/crm/NetServer/Services82">
  <UserDefinedFieldInfo:ApplicationToken>1234567-1234-9876</UserDefinedFieldInfo:ApplicationToken>
  <UserDefinedFieldInfo:Credentials>
    <UserDefinedFieldInfo:Ticket>7T:1234abcxyzExample==</UserDefinedFieldInfo:Ticket>
  </UserDefinedFieldInfo:Credentials>
 <SOAP-ENV:Body>
   <UserDefinedFieldInfo:SetUserDefinedPageOneField>
    <UserDefinedFieldInfo:OwnerType xsi:type="UserDefinedFieldInfo:UDefType">Invalid</UserDefinedFieldInfo:OwnerType>
    <UserDefinedFieldInfo:UdefFieldId xsi:type="xsd:int">0</UserDefinedFieldInfo:UdefFieldId>
    <UserDefinedFieldInfo:UserGroupId xsi:type="xsd:int">0</UserDefinedFieldInfo:UserGroupId>
    <UserDefinedFieldInfo:FieldLineNo xsi:type="xsd:int">0</UserDefinedFieldInfo:FieldLineNo>
   </UserDefinedFieldInfo:SetUserDefinedPageOneField>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## SetUserDefinedPageOneField Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices822="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices821="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:UserDefinedFieldInfo="http://www.superoffice.net/ws/crm/NetServer/Services82">
 <SOAP-ENV:Body>
  <UserDefinedFieldInfo:SetUserDefinedPageOneFieldResponse>
  </UserDefinedFieldInfo:SetUserDefinedPageOneFieldResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
