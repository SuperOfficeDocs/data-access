---
uid: calling_ws
title: Calling NetServer web services
description: Calling NetServer web services
author: Bergfrid Dias
so.date: 11.18.2021
keywords: API, web services, endpoints, NetServer
so.topic: concept
---

# Calling

If your services are configured to use SOAP, then each method call is a SOAP call that will travel over the network.

An agent consumes and returns carrier objects. Through a given agent you can manipulate a carrier.

The following example shows how we may retrieve a `ContactEntity` using the `IContactAgent`.

```csharp
using SuperOffice;
using SuperOffice.CRM.Services;

using(SoSession newSession = SoSession.Authenticate("sam", "sam"))
{
  //Retrieving a Contact Entity from a service agent
  //Instantiating a Contact Agent
  using(ContactAgent newConAgt = new ContactAgent())
  { 
    //Retrieving a Contact Entity carrier from a service call
    ContactEntity newConEnt = newConAgt.GetContactEntity(5);

    //Retrieving values of the carrier properties
    string conName = newConEnt.Name;
    string conDept = newConEnt.Department;
  }
}
```

In the example above, we have created an instance of the `IContactAgent` with use of the `GetContactAgent` method exposed by the `AgentFactory` class. Next, we use the created implementation of the `IContactAgent` to retrieve the `ContactEntity` as shown below.

```csharp
ContactEntity newConEnt = newConAgt.GetContactEntity(5);
```

> [!NOTE]
> The `IContactAgent` class provides methods such as `GetAddress`, `GetAddressByCountry`, `GetContact`, `DeleteContactEntity`, and many more, which can be used in a manner similar to the above.

## Code Example

So, what does all of this look like in code? The following code shows creating a session with the [SOAP proxies][1] to create ContactAgent - to communicate with the Contact web service, using the ContactAgent to create and save a new ContactEntity.

```csharp
using (SuperOffice.SoSession session = SuperOffice.SoSession.Authenticate("user", "password"))

```csharp
using (SuperOffice.SoSession session = SuperOffice.SoSession.Authenticate("user", "password"))
{
    SuperOffice.Services.ContactAgent contactAgent = new SuperOffice.Services.ContactAgent();
    ContactEntity contactEntity = contactAgent.CreateDefaultContactEntity();
    contactEntity.Name = "Supra Inc.";
// ... populate contact properties
    contactAgent.SaveContactEntity(contactEntity);
}
```

Whether targeting a local or remote database, an SoSession is the object that maintains a user's principal. In the case of remote calls, the SoSession.SoPrincipal.SoIdentity property is used to construct an SoCredentialsHeader object, which gets serialized and passed in the SOAP header for authentication and authorization in the remote web service. See the [Authentication][2] section for more information about authentication.

All action operations are facilitated through that Agent derived type.

## Alternative .NET Solutions

There are two immediate alternatives to using the SuperOffice.Services.dll for .Net developers. The first, and easiest, is to simply add a Service Reference to the specific web service and make calls through that proxy. The second alternative is to use Microsoft's SVCUTIL tool to generate a client proxy for each web service your interesting in, such as Appointment.svc or Contact.svc.

Both alternatives generate method stubs to make asynchronous calls, however, there are still system limitations imposed when making more than two simultaneous calls. To remedy that you'll need to look further into how the .Net framework manages connections. The following configuration snippet allows you to configure your application to allow more than two, the default, simultaneous connections. Otherwise, when there are more than two, they are queued and executed synchronously.

**Example connectionManagement section:**

```xml
<configuration>
    <system.net>
        <connectionManagement>
            <add address="http://www.mysrv.com/websvc/"maxconnection = "4" />
            <add address="*"maxconnection = "2" />
        </connectionManagement>
    </system.net>
</configuration>
```

## Alternative Java Solutions

For Java developers, although no thorough explanation that details how to create a proxy class for Java clients exists here. There is, however, an excellent section explaining just that on Sun's website, see [Creating Web Service Clients[10]. When it comes to authentication and authorization, each web request requires an SoCredentialsHeader element. In that element is a Ticket element. Because the ticket is a composite of data, it can be tricky to generate one correctly. When consuming .NET web services from other platforms, like Java and PHP, there is additional complexity as well. For example, the ticket ay needs to be prepacked with the UTF-8 Byte Order Mark (BOM).

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

Regarding NetServer services authentication, probably the most important thing to do first is to determine how you intend to leverage the web services provided by NetServer. Will you decide to use the [SOAP proxies][1] in your project, create your own client proxy or use the [REST][3] endpoints and implement all of the functionality yourself? Either way, the service-oriented aspects of NetServer web services provide many means to an end.

<!-- Referenced links -->
[1]: https://www.nuget.org/packages/SuperOffice.NetServer.Services
[2]: ../authentication/overview.md
[3]: ../api-reference/restful/index.md
[10]: http://java.sun.com/developer/technicalArticles/J2EE/j2ee_ws/index.html#use

<!-- Referenced images -->
