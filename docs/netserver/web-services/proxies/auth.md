---
uid: calling_ws
title: Calling NetServer web services
description: Calling NetServer web services
author: Bergfrid Dias
so.date: 11.18.2021
keywords: API, web services, endpoints, NetServer
so.topic: concept
---

# Authentication

Whether targeting a local or remote database, an SoSession is the object that maintains a user's principal. In the case of remote calls, the SoSession.SoPrincipal.SoIdentity property is used to construct an SoCredentialsHeader object, which gets serialized and passed in the SOAP header for authentication and authorization in the remote web service. See the [Authentication][2] section for more information about authentication.

This method uses the `SoSession` object from the SoCore to handle the authentication logic for us. The **secret** is calculated for us during the `Authenticate` call. The proxy objects returned by the agent factory will automatically add the SOAP authentication header for us. This makes working with the service API much simpler.

What will happen behind the scene is the Proxy DLL will generate the SOAP header using the credentials and makes the SOAP call.

This is the recommended calling pattern. The `Session` object is scoped with `using()` so that it is automatically closed at the end of the scope.

You can use `SoSession.Suspend` and `Continue` to avoid authenticating all the time.

## Direct Web Service Authentication

When calling a NetServer web service directly, first instantiate a proxy object, for example, the service object itself (Contact, Appointment, or Project), then set the SoCredentials property. Finally, make calls against the service to save or retrieve data.

The following example demonstrates how to call the web service through a Visual Studio WebReference proxy object.

**Direct web service authentication:**

```csharp
public ContactEntity GetContact()
{
    Contact ws = new Contact();
    ws.SoCredentials = new SoCredentialsHeader();
    // Get the ticket from the principal web service.
    ws.SoCredentials.Secret = GetTicket("JR", "password");
    ContactEntity contactEntity = ws.GetContact(3);
    return contactEntity;
}


public string GetTicket(string username, string password)
{
    SoPrincipalClient client = new SoPrincipalClient();

    SoTimeZone timezone;
    SoExtraInfo extraInfo;
    SoCredentials credentials;
    SOPrincipalCarrier principal;
    bool authSuccess = false;
    bool success = false;
    SoExceptionInfo exInfo = pc.AuthenticateUsernamePassword(
                "",
                username,
                password,
                out extraInfo,
                out success,
                out timezone,
                out principal,
                out credentials,
                out authSuccess
                );
            if (exInfo != null)
                throw new SoServiceException(exInfo);
    return credentials.Ticket;
```

The first thing is to instantiate a Contact proxy object. Next, before any methods are called, the SoCredentials proxy property is set to a new SoCredentialsHeader instance, and then set accordingly.

SoCredentials is an object representation of the SoCredentialsHeader element, which is an element in the SOAP message header. Each time a method is called against the web service, these credentials are sent along with it. This is mandatory the order to successfully authenticate against the web service. If any one of these values is wrong, the most likely result will be a SoapHeaderException, accompanied by the "Server unavailable, please try later " message.

**SOAP Message:**

```xml
<xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
    <soap:Header>
      <SoCredentials xmlns="http://www.superoffice.net/ws/crm/2005/04/Netserver20">
          <Ticket>NHoZChzE8hxd4XkJOc8yAQ==<Ticket>
      </SoCredentials>
    <soap:Header>
    <soap:Body>
        <GetContact xmlns="http://www.superoffice.net/ws/crm/2005/04/Netserver20">
            <contactId>3</contactId>
        <GetContact>
    <soap:Body>
<soap:Envelope>
```

## SoSession

A session retrieves data regarding the currently logged-in user and keeps them in the cache. Session Cache holds authentication information about the logged-in user, the associate of the user, business ID of the company that the user belongs to, reference data, and many more. Each time a new user logs in a session is created.

* [Create session][4]
* [Suspend session][5]

## How authentication works

> [!NOTE]
> In CRM 7 the secret is not used anymore. Instead, you must acquire a ticket from an authentication web service first. The ticket is what you send in the header instead of the secret.

The Service `WcfSoPrincipalService` is responsible for carrying out authentication.

`AuthenticateImplicit` tries to authenticate with whatever information possible. This information is most likely to be an Active Directory user.

`AuthenticateUsernamePassword` authenticates using a username and password. This can be a username and password of a domain user.

A successful response to Authentication is a Ticket that is passed in the SOAP header of the subsequent requests.

It is required that the web services are hosted on a machine that is a member of the Active Directory to support Active Directory Integration.

<!-- Referenced links -->
[2]: ../authentication/overview.md
[4]: ../../authentication/onsite/sosession/create.md
[5]: ../../authentication/onsite/sosession/suspend.md
