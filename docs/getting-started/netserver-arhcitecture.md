---
uid: superoffice_netserver_architecture
title: NetServer architecture
description: NetServer architecture
author: Tony Yates
so.date: 11.15.2021
keywords: API, NetServer
so.topic: concept
so.envir: cloud, onsite
so.client: win, web
---

# NetServer architecture

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
