---
uid: superoffice_external_integration_apis
title: External integration APIs
description: External integration APIs
author: Tony Yates
so.date: 11.10.2021
keywords: API, getting started, integration point, COM API, NetServer
so.topic: concept
so.envir: cloud, onsite
so.client: win, web
---

# External integration APIs

The term external API refers to all SuperOffice client products, SuperOffice COM APIs, and the NetServer API landscape.

**NetServer**, although used as an umbrella term that encapsulates a variety of data access capabilities, is just as much if not more extensible than the SuperOffice clients. With constructs such as low-level database objects to high-level business objects, to higher-level web services and web service proxy libraries, NetServer is itself an extensible SuperOffice product.

SuperOffice has several partners and 3rd party vendors who have built tightly-coupled integrations with SuperOffice using external APIs. The different types of integrations built range from tiny edge-case security plugins to integrations with completely new document management systems. There are even complete enterprise resource planning systems that leverage SuperOffice CRM as the heart of its ecosystem.

Where to get started depends on your target SuperOffice platform and your preferred technology stack.

The list of available APIs for integrations decreases the closer they are to online. That is just the nature of the respective environment and not the limitations of the platforms or APIs.

## Recommended APIs for each platform

| | Window | Web | Online |
|---|:-:|:-:|:-:|
| COM | x | | |
| NetServer Core | x | x | |
| NetServer Web Services | x | x | x |

From NetServer Core, Web supports NetServer script events only.
Using NetServer web services, the configuration must be set to Local Mode for Windows and Local or Remote mode for Web.

There are virtually no limitations as to which API you leverage when building an integration that targets just the Windows client. If, however, your requirements include both the Windows client and the Web client together, the available API options decrease. This is not necessarily a bad thing though. Sometimes it just makes technological sense to build an integration using only one of the available APIs. It does not make sense, for example, to use the COM-based API in today's web service architectures.

> [!NOTE]
> Although it sometimes can't be avoided, we generally discourage building integrations that leverage more than one of our APIs in the same solution.

Although integrations in SuperOffice CRM Online can display visual elements, such as partner applications through a web panel, the Web client in SuperOffice CRM Online only supports service-orientated integrations today. Meaning that all data access routines must use the web services APIs. Considering the SuperOffice Web client relies exclusively on these APIs, and has more functionality than the Windows user and administration clients, the capability of the web service APIs should never be considered inferior. The web service APIs should be given serious consideration for nearly all scenarios.

## NetServer architecture

All SuperOffice clients, in one form or another, depend on NetServer for database access. While each client has its own extensibility points, NetServer also has extensibility points. Some of NetServer's extensibility options surface to the clients, such as the Document Plug-in.

As a multi-tiered database access layer that bridges communications between clients and the SuperOffice database, NetServer uses database-independent database access code, as well as high-level web services for both the SuperOffice Web and mobile clients.

**NetServer conceptual overview:**

![x][img4]

[The lowest layer of NetServer][12], the domain-level development APIs, are generally used by a client or application server. This layer does the heavy lifting and is responsible for marshaling all the model-based data into raw SQL.

Listed below are the different aspects of NetServer core APIs.

* OSQL: Low-level, high-performance, database-independent objectified SQL.
* Rows and Rows: Medium-level data table and data row-level access
* Entities: High-level business model classes that abstract multiple table joins.
* Archive and MDO Providers: provide complex search capabilities across the entire database.

The highest level of NetServer data access is the service-orientated architecture and consists of:

* Web service endpoints based on WCF **SOAP** and **REST**ful WebAPI: IIS application used by SuperOffice Web and PocketCRM.
* Web service proxies: Service agent pattern .NET assemblies used by clients to access the service endpoints.

An important aspect of NetServer web service development is its **deployment flexibility**. It's capable of being embedded in a domain-centric fat client application, as well as a thin client deployed with NetServer service proxies for data access across the internet.

**Webhooks** are supported at both the low and high levels of NetServer.

All types of technology platforms, including Java, PHP, Python, Ruby, and many more can integrate with NetServer web services. Any technology stack that supports web services can connect to and exchange data with SuperOffice NetServer. SuperOffice only supplies .NET proxy assemblies. All other technology platforms must generate their own proxies, or use raw SOAP/XML, to access the web services.

**Integration points (low-level):**

* Document Plugin
* Sentry Plugin
* Add or override archive providers
* Add or override resources providers
* Multiple levels of database access

**Integration points (high-level):**

* [Webhooks][15]
* [SOAP][11]
* [REST][17]
* [CRMScript][3]

Related SDK:

* [NetServer Core SDK][18] (long loading time)
* [NetServer Web Services][19]

<!-- Referenced links -->
[3]: ../../../crmscript/docs/overview/index.md
[12]: ../netserver/what-is-netserver.md
[11]: ../netserver/services/reference/index.md
[15]: ../netserver/webhooks/index.md
[17]: ../api-reference/webapi/index.md
[18]: ../api-reference/netserver/core/index.md
[19]: ../api-reference/netserver/services/index.md

<!-- Referenced images -->
[img4]: media/netserverarchitecture-blue-650.png
