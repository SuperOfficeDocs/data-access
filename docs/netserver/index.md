---
uid: what_is_netserver
title: What is Netserver / Understanding NetServer
description: NetServer is a multi-tiered database access layer that bridges communication between clients and the SuperOffice database.
author: AnthonyYates
so.date: 11.29.2021
keywords: API, NetServer, HDB, RDB, entity, row, archive, OSQL, web service, services
so.topic: concept
so.envir: cloud, onsite
so.client: win, web
---

# Understanding NetServer

All SuperOffice clients, in one form or another, depend on NetServer for database access. While each client has its own extensibility points, NetServer also has extensibility points. Some of NetServer's extensibility options surface to the clients, such as the [Document Plug-in][14].

As a **multi-tiered database access layer** that bridges communications between clients and the SuperOffice database, NetServer uses database-independent database access code, as well as high-level web services for both the SuperOffice Web and mobile clients.

![NetServer architecture][img3]

In a nutshell, NetServer is a layered, **factory-driven** library that enables developers to conduct Create, Read, Update and Delete (CRUD) operations to the SuperOffice database, and more. Whether deploying a solution to a local SuperOffice database installation or operating in a distributed environment, NetServer exposes an array of application programming interface (API) approaches to facilitate a wide range of solution implementations.

Although the terrain is vast and complex and can be somewhat intimidating at first, the NetServer APIs accommodate a wide variety of developers by layering the architecture in various intuitive abstractions. The layered aspect of NetServer invites developers to tap into the database from several facets. In this article, we will guide you through the various regions of NetServer, show you the attractions, as well as point out the areas to avoid.

## Persistence layers

SuperOffice NetServer provides several **persistence layers**, each one allowing more fine-grain control than the next.

![NetServer architecture, detailed][img4]

You can choose to work at the level that suits you best. **Webhooks** are supported at both the low and high levels of NetServer.

### Domain-level APIs (NetServer Core)

The lowest layer of NetServer, the domain-level development APIs, is generally used by a client or application server. This layer does the heavy lifting and is responsible for **marshaling all the model-based data into raw SQL**.

* [SQL data objects (OSQL)][1]: Low-level, high-performance, database-independent objectified SQL.
* [Row and Rows][2]: Medium-level data table and data row-level access.
* [Entities][3]: High-level business model classes that abstract multiple table joins.
* [Archive][4] and MDO Providers: provide complex search capabilities across the entire database.

### Service-orientated APIs

The highest level of NetServer data access is the service-orientated architecture and consists of:

* [Web service endpoints][5] based on **REST**ful WebAPI and WCF **SOAP**: IIS application used by SuperOffice Web and Mobile.
* Web service proxies: Service agent pattern .NET assemblies used by clients to access the service endpoints.

An important aspect of NetServer web service development is its **deployment flexibility**. It's capable of being embedded in a domain-centric fat client application, as well as a thin client deployed with NetServer service proxies for data access across the internet.

The following sections present an overview of the NetServer API and the different aspects of NetServers service offerings. Each level is described briefly below and in detail in the linked sections.

## Web services layer

At the highest level, encapsulated in the **SuperOffice.Services namespace**, is an **agent** pattern-derived API that in terms of deployment is quite flexible. Access and modification to data in the database, using service objects, will always be coded the same, whether the application and database are located on the same server, or operating in a distributed environment. This flexibility does come at a performance price though.

[Read more about web services.][5]

## Archives

An [archive][4] is a **configurable multi-column list** that flattens the complex relationships between tables into a simple grid.

Archives simplify **searching and retrieving** collections of related data efficiently. The archive system is very flexible and supports many different providers. Each provider describes a set of related **columns** from the database. Each provider supports a set of methods for finding out what columns are available.

## Relational database layer (entities)

The relational database (RDB) layer, conceptually the **business logic** layer, is encapsulated within the **SuperOffice.Entities namespace**. Relational database objects, such as `Contact`, `ContactCollection`, `Person`, and `PersonCollection`, are all found here. These objects abstract away the complexities required to access and present information from the database.

RDB objects expose the data as neat and logical objects commonly referred to as [entities][3]. Entities **represent real-world objects**, such as companies and people.

> [!TIP]
> This layer is great for **creating and saving** new entities, such as creating a new `Contact` or `Sale`, but is not as efficient as one of the lower layers when retrieving information.

[Read more about Entities.][3]

## High-level database layer (rows)

The high-level database (HDB) layer, found under the **SuperOffice.Rows namespace**, is a table-object view of the database. This layer exposes **database tables** and the information they contain as row objects, such as `ContactRow` and `ContactRows`.

Unlike RDB object properties, which are full-blown entities themselves, HDB object properties contain **ID values** that represent ID field values in a corresponding table.

> [!NOTE]
> The Row objects **do not contain any business logic**, so here you need to maintain the relationship between rows yourself.

[Read more about Row and Rows.][2]

## SuperOffice database interface layer (OSQL)

At the lowest levels of the framework is a database-independent objectified SQL library.

[OSQL][1] encompasses all **common SQL elements**, such as SELECT, JOIN, WHERE, AND, OR, and so forth. It exposes all of these elements as **class objects**, to be constructed and leveraged in an "object-orientated" manner.

OSQL has the **best performance** of all NetServer API layers. When using OSQL to create code, the code will be more responsive and efficient than when using the Services, RDB, or the HDB layers.

[Read more about OSQL.][1]

## Programming with NetServer APIs

When programming with the NetServer API, other than calling the web services directly, every solution needs a SuperOffice-specific section group in your application configuration file. This means adding a SuperOffice-specific section group to an *app.config* file for Windows Forms applications, or the *web.config* file for an ASP.NET web application.

The SuperOffice section group contains configuration options relevant NetServer operations, such as logging, document handling, security, database options, and so forth. Everything you need to know about the SuperOffice configuration options is well-defined in the [NetServer configuration documentation][12].

> [!NOTE]
> The more control over the queries you have, the more responsibility you take on for handling ensuring that relationships and keys are maintained properly.

All types of technology platforms, including Java, PHP, Python, Ruby, and many more can integrate with NetServer web services. Any technology stack that supports web services can connect to and exchange data with SuperOffice NetServer. SuperOffice supplies .NET proxy assemblies only. All other technology platforms must generate their own proxies, or use raw SOAP/XML, to access the web services.

> [!TIP]
> Before you start coding, brush up on your knowledge about [SuperOffice authentication][13].

### Factory pattern

**Factory** is the location in the code at which objects are constructed. The intent of employing this pattern is to isolate the creation of objects from their usage. This allows the new derived types to be introduced into the code with no change to the code that uses the base objects. The use of these patterns makes it possible to interchange the classes without changing the code that uses them even at runtime. However, the employment of this pattern incurs the risk of unnecessary complexity and extra work in the initial writing of code.

The NetServer implementation of the Factory patterns consists of an Interface named `IPrivateFactory` that is located in the `SuperOffice.Factory` namespace. The Factory hides the details about the settings from the user. Some of the factory patterns exposed through the NetServer include `ConnectionFactory` that is mostly seen by the user compared to the `AddressFactory`, which is used mostly within the NetServer code.

Since the user mostly views the `ConnectionFactory` during the next few sections, Factory patterns will be explained in terms of the `ConnectionFactory`. Depending on the service mode setup, the `ConnectionFactory` will give back different objects.

For example, `ConnectionFactory.GetConnection` returns an `SoConnection`. This could be configured in a way such that it would return another sub-class of `SoConnection`.

The Factory pattern requires that you replace our standard class with your class, which means you have to make all SuperOffice functions plus your own functions, – this means an extra bit of work. This makes the Plugin pattern simpler than the Factory pattern because you only have to provide the functionality in your own plugin. Once the sub-class is ready, the user needs to set it up in the config file. When it has been set up, the Factory would automatically return the user-defined class instead of the standard class, since the Factory looks in the config file to check whether the standard class has been replaced with the user’s own implementation. The config file points to the assembly, which contains the user’s custom class or plugin. For Example:

```XML
<Factory>
  <DynamicLoad>
    <add key="MyFactory" value="C:\NetServer\Server\Feature SIX\bin\Debug\ MyFactory.dll" />
  </DynamicLoad>
</Factory>
```

Below is an example of the use of the get ConnectionFactory.

```csharp
using SuperOffice.Data;
using SuperOffice.Data.SQL;
//Create a DataSet of the Contact table
ContactTableInfo conTableInfo = TablesInfo.GetContactTableInfo();
//SQL Statement
Select newSelect = S.NewSelect();
newSelect.ReturnFields.Add(conTableInfo.Name,
conTableInfo.Department);
newSelect.Restriction = conTableInfo.ContactId.In(S.Parameter(10));
using(SuperOffice.SoSession mySession =
SuperOffice.SoSession.Authenticate("SAM", "sam"))
{
  if (mySession == null) return;
  //Establish a Connection with the Database
  SoConnection newConn = ConnectionFactory.GetConnection();
  SoCommand newComm = newConn.CreateCommand();
  newComm.SqlCommand = newSelect;
  newConn.Open();
  SoDataReader newReader = newComm.ExecuteReader();
  //Retrieve the Date
  while (newReader.Read())
  {
    string conName = newReader.GetString(0);
  }
  //Close Reader and Dispose of the Session
  newReader.Close();
  mySession.Dispose();
}
```

For us to use the `ConnectionFactory`, the `SuperOffice.Data` namespace has been called. After a `DataSet` of the `Contact` table has been created using OSQL statements.

To use the connection, we create an instance of the `SoConnection` using the `ConnectionFactory`, `GetConnection` method.

The `newConn` variable may contain an `SoConnection` object, or it may contain a sub-class of `SoConnection`. The factory controls what sort of object is returned. The factory is configured using the *app.config* file.

## Summary

This has been a high-level view of NetServer. As you can see, there is a vast difference between the different approaches. Be aware though that, just because one layer takes longer to complete than another, it does not imply that a layer should be ignored. Each query type has its place in the development world when used judiciously.

<!-- Referenced links -->
[1]: osql/index.md
[2]: rows/index.md
[3]: entities/index.md
[4]: archive-providers/index.md
[5]: web-services/index.md
[6]: ../api-reference/soap/index.md
[7]: ../api-reference/netserver/services/index.md
[8]: ../api-reference/netserver/core/index.md
[9]: webhooks/index.md
[10]: ../api-reference/webapi/index.md
[11]: ../../../crmscript/docs/overview/index.md
[12]: config/index.md
[13]: ../authentication/overview.md
[14]: ../documents/plugins/soarc-document-plugin.md

<!-- Referenced images -->
[img1]: media/netserverhilevelview.png
[img3]: media/netserver-components-overview.png
[img4]: media/netserverarchitecture-blue-650.png
