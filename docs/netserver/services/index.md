---
uid: netserver-web-services-overview
title: NetServer web services
description: SuperOffice NetServer web services
author: {github-id}
so.date:
keywords:
so.topic: concept
---

# SuperOffice NetServer services

## Service Layer

Global access to SuperOffice data is easy to achieve through leveraging the service-orientated aspects of NetServer. One way to communicate with NetServer web services is to use Microsoft's ServiceModel Metadata Utility Tool ([SVCUTIL.exe][8] to generate a client proxy class for a particular NetServer web service, for example Appointment.svc or Contact.svc. Another way is to create a Visual Studio Service Reference and communicate with the services through that proxy. The most complete way, however, is to reference the pre-packaged, all-in-one factory-driven proxy, SuperOffice.Services.dll.

There is flexibility in using SuperOffice proxies. Not only are all of the complexities involved with communicating with web services done for you, but also in the ability to code once and have your application work both local or remote simply by changing a single configuration setting - SuperOffice->Services->DefaultMode. Under the hood, however, there are significant differences between the different modes, Local, Remote, and Switch.

Within the services layer, most development will involve IAgent-derived types and Carrier types. Agents are used to execute actions, for example call methods, while Carrier objects, such as Person and PersonEntity are mere data containers. As your will soon come to realize, carrier entities better resemble Entity objects, where an entity property, such as the PersonEntity.Contact, is a populated object that contains all relational information pertaining to the corresponding contact - including name, address, contact ID, phone collection, and more. In contrast, carrier objects (not ending in Entity) such as Contact and Person, are more similar to Row objects. Carrier object properties represent identity values correlating to the identity field in the corresponding table. For example, the Person.ContactId property is of type integer and correlates to the contact_id field in the Contact table.

### Service Communication Modes

When opted to operate in local mode, SuperOffice.Services.dll is not actually making web service calls. Instead, it uses Rows and OSQL to populate lite-serializable versions of intrinsic types, such as Appointment, Contact, and Person. These are the same objects returned by calling the web service, but in this case, do not require a round-trip across the internet. Smart, huh?

In remote mode, SuperOffice.Services.dll uses proxy classes that are, to some degree, similar versions of what you get when generating proxy classes with SVCUTIL.exe. These objects, however, are enhanced a magnitude greater to increase completeness and usability when submitting calls to and receiving data from NetServer web services. The URL of the remote web services is determined by the SuperOffice->Service-> RemoteBaseURL configuration setting.

Switch mode, when set, will attempt to communicate with the setting defined in Services-SwitchDefault. If unable to communicate successfully, NetServer will switch to the other setting option (Local or Remote) and attempt to communicate again.

### Data Paths

Below is a diagram that depicts the data path taken when communicating with the Services layer.

![x][img3]

The Client represents a .net application that has referenced SuperOffice.Services.dll. The lines below, depending on the Services->DefaultMode configuration setting, represent the data path to communicate with the database.

If the DefaultMode is "Local", which means that the application resides on the same server as the database, or within the same domain, then factory mechanisms in SuperOffice.Services.dll return interface implementations from SuperOffice.Services.Implementation.dll. This assembly leverages both Rows and OSQL layers to conduct transactions between the application and the database.

When DefaultMode is set to "Remote", a significantly different data path is used. When read from the configuration file by SuperOffice.Services.dll, the "Remote" indicates that the interfaces are implemented by SuperOffice.Services\[version\].Wcf.dll and related files. In this case, the data path originating from the client traverses SuperOffice.Services\[version\].Wcf.dll, across the internet to the web service endpoints, SuperOffice.Services.WcfService.dll, which then calls into a local copy of SuperOffice.Services.dll. At this point, the data path starts all over again as depicted in the Client Local mode, but local to the Remote location. Now on the remote server, SuperOffice.Services.Implementation.dll leverages both Row and OSQL layers to conduct transactions with the database. The implementation populates the lite-objects, returns them to the SuperOffice.Services.Wcf.dll, which then passes the data back to the client proxy.

### Code Example

So, what does all of this look like in code? **Figure Three** shows: creating a session with the [SOAP proxies](https://www.nuget.org/packages/SuperOffice.NetServer.Services) to create ContactAgent - to communicate with the Contact web service, using the ContactAgent to create and save a new ContactEntity.

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

Whether targeting a local or remote database, an SoSession is the object that maintains a user's principal. In the case of remote calls, the SoSession.SoPrincipal.SoIdentity property is used to construct an SoCredentialsHeader object, which gets serialized and passed in the SOAP header for authentication and authorization in the remote web service. See the [Authentication](../authentication/overview.md) section for more information about authentication.

All action operations are facilitated through that Agent derived type.

### Alternative .NET Solutions

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

### Alternative Java Solutions

For Java developers, although no thorough explanation that details how to create a proxy class for Java clients exists here. There is, however, an excellent section explaining just that on Sun's website, see [Creating Web Service Clients[10]. When it comes to authentication and authorization, each web request requires an SoCredentialsHeader element. In that element is a Ticket element. Because the ticket is a composite of data, it can be tricky to generate one correctly. When consuming .NET web services from other platforms, like Java and PHP, there is additional complexity as well. For example, the ticket ay needs to be prepacked with the UTF-8 Byte Order Mark (BOM).

### Direct Web Service Authentication

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

Regarding NetServer services authentication, probably the most important thing to do first is to determine how you intend to leverage the web services provided by NetServer. Will you decide to use the [SOAP proxies](https://www.nuget.org/packages/SuperOffice.NetServer.Services) in your project, create your own client proxy or use the [REST](../api-reference/restful/index.md) endpoints and implement all of the functionality yourself? Either way, the service-oriented aspects of NetServer web services provide many means to an end.

## Web services

When you are calling a web service, you typically **don’t have direct access to the database**. This is the highest level for working with NetServer.

A typical service call looks like this when using the NetServer helper classes:

```csharp
using SuperOffice.CRM.Services;
using SuperOffice;
using(SoSession mySession = SoSession.Authenticate("SAL0", ""))
{
  //Create a Contact Agent
  IContactAgent myContactAgent = AgentFactory.GetContactAgent();

  //Get a Contact carrier through the Contact Agent
  ContactEntity myContact = myContactAgent.GetContactEntity(1234);

  //Retrieving the Name Property of the Contact
  string name = myContact.Name;

  // warning: hard-coded address layout assumption!
  string city = myContact.Address[2][1];
}
```

A service is primarily a method exposed by the NetServer to manipulate the data or enhance the presentation of the data in the SuperOffice database. In the NetServer the services infrastructure has been built using the [agent][1] and [carrier][2] software patterns. **The agent object presents the services and the carrier object represents the data passed back and forth to the server by the agent, depending on the configuration.**

All SuperOffice CRM Online applications depend on NetServer web services for database access. NetServer is a multi-tiered database access layer that bridges communication between clients and the SuperOffice database. NetServer access in our online environment is achieved by using either REST or SOAP web services.

All the services are called through an agent that is designed to handle a specific business area, for example, there will be a dedicated agent to handle the services intended for the sales area. All the agents live in the `SuperOffice.CRM.Services` namespace.

## Objective

The objective of the NetServer services is to provide a simple yet powerful API to access SuperOffice CRM functionality. The service API lets you work with the database without having to know the details of how data is stored inside the database. It presents a high-level API where all the hard work of language decoding, security checks, database selects, and joining tables are handled for you. A single service call will represent many database queries and contain business logic, user-preference checking, and default handling.

## SoSession

A session retrieves data regarding the currently logged-in user and keeps them in the cache. Session Cache holds authentication information about the logged-in user, associate of the user, business ID of the company that the user belongs to, reference data, and many more. Each time a new user logs in a session is created.

* [Create session][3]
* [Suspend session][4]

## Architecture

Each installation and online tenant expose NetServer web services for all clients, including SuperOffice Web, PocketCRM, and partner application clients. The web services are bundled in your Expander Services subscription.

![netserver-web-service][img1]

## Service-orientated data access

The highest level of NetServer data access consists of web service endpoints and web service proxies.

### WCF SOAP and RESTful WebAPI endpoints

This is where you find the IIS application used by SuperOffice Web and PocketCRM.

Which API is right for your situation? Read [Online Development - What API to Use][5] to understand the implications to determine which is best for you.

### Web service proxies

For SOAP-based clients, NetServer .NET assemblies use a service agent pattern to work with business entities used by clients to access the service endpoints. These are available as [NuGet packages][6]

## Calling web services

One call to the web services can hide or include multiple database queries, business logic, user-preference checks, and default handling. For SuperOffice CRM Online, you have the option to:

* use NetServer Proxies ([NuGet packages][6])
* generate a custom proxy by adding a web service
* use RESTful [WebAPI endpoints][7]
* use RESTful [Agent endpoints][8]

Your application is not allowed to place .net assemblies in a tenant web application and must use the web services for all interactions.

<!-- Referenced links -->
[1]: agents/index.md
[2]: carriers/index.md
[3]: ../../authentication/onsite/sosession/create.md
[4]: ../../authentication/onsite/sosession/suspend.md
[5]: ../../../../superoffice-docs/docs/apps/getting-started/what-api-to-use.md
[6]: https://www.nuget.org/packages/SuperOffice.NetServer.Services
[7]: ../../api-reference/restful/rest/index.md
[8]: ../../api-reference/restful/agent/index.md
[9]: https://msdn.microsoft.com/en-us/library/aa347733(v=vs.110).aspx
[10]: http://java.sun.com/developer/technicalArticles/J2EE/j2ee_ws/index.html#use

<!-- Referenced images -->
[img1]: media/netserver-web-services.png
[img3]: media/servicedatapath-sm.png
