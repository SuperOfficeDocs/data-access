---
uid: services81-preference-deletepreferences
title: Services81.PreferenceAgent.DeletePreferences SOAP
Generated: true
---

# Services81 Preference DeletePreferences SOAP

SOAP request and response examples **Remote/Services81/Preference.svc**
Implemented by the <see cref="M:SuperOffice.Services81.IPreferenceAgent.DeletePreferences">SuperOffice.Services81.IPreferenceAgent.DeletePreferences</see> method.

## DeletePreferences

Delete some preferences by id

* **ids:** The ids of the preference to delete

**Returns:** This method has no return value


[WSDL file for Services81/Preference](../Services81-Preference.md)

Obtain a ticket from the [Services81/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## DeletePreferences Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices812="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices811="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Preference="http://www.superoffice.net/ws/crm/NetServer/Services81">
  <Preference:ApplicationToken>1234567-1234-9876</Preference:ApplicationToken>
  <Preference:Credentials>
    <Preference:Ticket>7T:1234abcxyzExample==</Preference:Ticket>
  </Preference:Credentials>
 <SOAP-ENV:Body>
   <Preference:DeletePreferences>
    <Preference:Ids xsi:type="NetServerServices812:ArrayOfint">
     <NetServerServices812:int xsi:type="xsd:int">0</NetServerServices812:int>
    </Preference:Ids>
   </Preference:DeletePreferences>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## DeletePreferences Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices812="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices811="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Preference="http://www.superoffice.net/ws/crm/NetServer/Services81">
 <SOAP-ENV:Body>
  <Preference:DeletePreferencesResponse>
  </Preference:DeletePreferencesResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
