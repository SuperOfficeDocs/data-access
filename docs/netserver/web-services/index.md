---
uid: netserver-web-services-overview
title: NetServer web services
description: SuperOffice NetServer web services
author: Bergfrid Dias
so.date: 11.18.2021
keywords: API, web services, endpoints, proxy, NetServer, SOAP, REST
so.topic: concept
---

# SuperOffice NetServer web services

[NetServer exposes many layers][12] of its API to do the same functionality.
The web services are the highest level for working with NetServer. This layer consists of [web service endpoints][11] based on WCF **SOAP** and **REST**ful WebAPI (IIS application) and web service proxies.

Each installation and online tenant exposes NetServer web services for all clients, including SuperOffice Web, SuperOffice Mobile, and partner application clients.

When you are calling a web service, you usually **don’t have direct access to the database**.

## Why use web services?

The objective of the NetServer web services is to provide a simple yet powerful API to access SuperOffice CRM functionality.

The web services let you work with the database without having to know the details of how data is stored inside the database. The service layer present a high-level API where all the hard work of language decoding, security checks, database selects, and joining tables are handled for you. A single service call will represent many database queries and contain business logic, user-preference checking, and default handling.

All SuperOffice CRM Online applications depend on NetServer web services for database access. NetServer access in our online environment is achieved by using either REST or SOAP web services.

## What is a service?

A service is primarily a method exposed by the NetServer to manipulate the data or enhance the presentation of the data in the SuperOffice database.

![NetServer web services][img1]

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

## Agent and carrier pattern

SuperOffice has created a set of objects based on the **Agent pattern** that will perform your work for you. The goal of the pattern is to make it clear when you are making potentially expensive service calls.

All services are called through an agent that is designed to handle a specific **business area**, for example, there will be a dedicated agent to handle the services intended for the sales area.

An **agent** is a class that exposes a set of methods. All agents live in the **SuperOffice.CRM.Services namespace**. A typical agent has methods for inserting, retrieving, updating, and deleting data. Each method on the agent corresponds to one service call.

```csharp
IContactAgent newConAgt = new ContactAgent();
```

The code segment above shows how we create a `ContactAgent`. The agent is the class factory that loads the local or remote agent based on the config file settings.

Once the agent has been created, we may use it to access the different methods exposed by the agent. These methods would vary according to the agent created.

A **carrier** is an object that carries data between the Agent and the NetServer services. There are two kinds of carriers: simple read-only carriers and complex entity carriers. The main difference is that entity carriers can be updated and sent back for saving to the database while read-only carriers cannot be saved back to the database.

### Read-only carriers

A read-only carrier is a **simple object**. It exposes its properties primarily as simple string values or ID values correlating to the ID field in the corresponding table. For example:

* A read-only carrier will expose the country property as a country name and not as a country sub-object.
* The `Person.ContactId` property is of type integer and correlates to the `contact_id` field in the `Contact` table.

The advantage of the read-only carrier is its simplicity and you can avoid many overheads by working with an entity carrier.

Below is an example that displays how to load a read-only carrier using an Agent.

```csharp
using SuperOffice.CRM.Services;

ContactAgent contactAgent = new ContactAgent();
Contact myContact = contactAgent.GetContact(4);
string myContactName = myContact.Name;
string myContactCategory = myContact.CategoryName;
string myContactWebUrl = myContact.URL;
```

Here, the `ContactAgent` will return a `Contact` read-only object through the `GetContact` method. These kinds of objects are what we call read-only carriers.

### Entity carriers

An entity carrier is an [entity][1] object. Unlike in read-only carriers, an entity carrier exposes its properties as objects that are populated with more detailed data. The properties will expose their properties since the properties in entity objects are objects themselves. For example, the `PersonEntity.Contact` is a populated object that contains all relational information pertaining to the corresponding contact - including name, address, contact ID, phone collection, and more.

The example below displays how to retrieve a `Contact` entity object through the `GetContactEntity` method of the `ContactAgent`.

```csharp
using SuperOffice.CRM.Services;

ContactAgent contactAgent = new ContactAgent();

ContactEntity myContact = contactAgent.GetContactEntity(4);

string myContactName = myContact.Name;
string myContactCategory = myContact.Category.Value;
string myContactWebUrl = myContact.Urls.Length > 0 ? myContact.Urls[0].Value : "";
```

To summarize: **The agent object presents the services and the carrier object (such as Person and PersonEntity) represents the data passed back and forth to the server by the agent, depending on the configuration.** Agents are used to execute actions, for example call methods.

Carrier entities resemble Entity objects. In contrast, carrier objects (not ending in Entity) such as Contact and Person, are more similar to **Row objects**.

## Calling web services TBD

The web services are bundled in your Developer Tools subscription.

One way to communicate with NetServer web services is to use Microsoft's ServiceModel Metadata Utility Tool ([SVCUTIL.exe][8] to generate a client proxy class for a particular NetServer web service, for example Appointment.svc or Contact.svc.

Another way is to create a Visual Studio Service Reference and communicate with the services through that proxy.

The most complete way, however, is to reference the pre-packaged, all-in-one factory-driven proxy, SuperOffice.Services.dll.

There is flexibility in using SuperOffice **proxies**. Not only are all of the complexities involved with communicating with web services done for you, but also in the ability to code once and have your application work both local or remote simply by changing a single configuration setting - SuperOffice->Services->DefaultMode. Under the hood, however, there are significant differences between the different modes, Local, Remote, and Switch.

For SOAP-based clients, NetServer .NET assemblies use a service agent pattern to work with business entities used by clients to access the service endpoints. These are available as [NuGet packages][6]

One call to the web services can hide or include multiple database queries, business logic, user-preference checks, and default handling. For SuperOffice CRM Online, you have the option to:

* use NetServer Proxies ([NuGet packages][6])
* generate a custom proxy by adding a web service
* use RESTful [WebAPI endpoints][7]
* use RESTful [Agent endpoints][8]

Your application is not allowed to place .net assemblies in a tenant web application and must use the web services for all interactions.

## SoSession

A session retrieves data regarding the currently logged-in user and keeps them in the cache. Session Cache holds authentication information about the logged-in user, associate of the user, business ID of the company that the user belongs to, reference data, and many more. Each time a new user logs in a session is created.

* [Create session][3]
* [Suspend session][4]

<!-- Referenced links -->
[1]: ../entities/index.md
[3]: ../../authentication/onsite/sosession/create.md
[4]: ../../authentication/onsite/sosession/suspend.md
[5]: ../../../../superoffice-docs/docs/apps/getting-started/what-api-to-use.md
[6]: https://www.nuget.org/packages/SuperOffice.NetServer.Services
[7]: ../../api-reference/restful/rest/index.md
[8]: ../../api-reference/restful/agent/index.md
[9]: https://msdn.microsoft.com/en-us/library/aa347733(v=vs.110).aspx
[10]: http://java.sun.com/developer/technicalArticles/J2EE/j2ee_ws/index.html#use
[11]: endpoints.md
[12]: ../index.md

<!-- Referenced images -->
[img1]: media/netserver-web-services.png
