---
uid: intro-to-superoffice-apis
title: Introduction to SuperOffice APIs
description: Introducing SuperOffice APIs
author: Tony Yates
so.date: 11.25.2021
keywords: api, getting started, integration point, scripting, Jscript, Javascript, VB.NET, C#
so.topic: concept
so.envir: cloud, onsite
so.client: win, web, service
---

# Introducing SuperOffice APIs

It can sometimes be daunting for people new to SuperOffice programming to know where to begin. With several platforms, for both customer relationship management (CRM) and customer service (CS), it can be difficult to understand which application programming interface (API) is appropriate for which platform.

## Extensibility levels

There are several levels of SuperOffice extensibility, and these are commonly defined as configuration, UI workflow, scripting, external APIs, and internal APIs.

![ExtensibilityStairs][img2]

The first two levels of extensibility are exposed inside the admin UI pages of SuperOffice. These are features commonly managed by system administrators and SuperOffice consultants and are used to tailor SuperOffice to individual customer needs.

The **scripting level** pertains to a few different features that provide similar functionality, albeit by different means. [CRMScript][3] is a SuperOffice scripting dialect similar to JavaScript and is managed inside the administrative pages of SuperOffice. [NetServer scripting][16] is an Application Server capability that is accessible onsite only.

**External APIs** provide complete data access for both SuperOffice clients and online applications. This level includes SuperOffice COM APIs and the [NetServer API landscape][15].

**Internal APIs** are the nearly limitless amount of customization capabilities that most onsite installations leverage to provide everything from custom pages and dialogs, document and sentry plugins, and so much more.

## Online vs. onsite extensibility

Since 2005, SuperOffice has heavily invested in building APIs that enable partners and customers to build integrations that encompass everything from the database schema changes up to modifying UI elements in the application interface.

![Onsite extensibility diagram][img1]

With this breadth of customization capability in onsite installations, it's sometimes hard for legacy partner applications to adapt to move their application to the cloud.

Online applications are much more strict, and only have a subset of extensible capabilities.

![Online APIs][img3]

With onsite installation, there is one web server hosting SuperOffice sites, and the owners can do whatever they like with their installation.

Online tenants, on the other hand, share application file sets. Therefore, any compiled assemblies that are exposed to one installation would inadvertently expose those same customizations across all shared tenants.

> [!NOTE]
> Since compiled assemblies can't be securely and effectively isolated, **no one is permitted to deploy custom compiled assemblies to an online tenant**.

**Security and hosting restrictions** in Online force both standard and custom applications to adapt in ways that support the features and functions they can provide, and accept the limitations that restrict the things they can't.

SuperOffice will continue to invest in research and development to deliver equivalent onsite customization capabilities to SuperOffice CRM Online. However, a timeline for this is not available. This policy decision is related to security reasons, and SuperOffice is not willing to compromise tenant security.

## Platforms (SuperOffice clients)

SuperOffice supports different forms of scripting automation. [SuperOffice Service][4] (CS) supports scripting automation and accounts for the majority of integrations. SuperOffice CRM on the other hand is available as four unique platforms, each of which has its own extensibility characteristics:

* [Windows client][5]
* [Onsite Web client][6]
* [Online Web client][7]
* Mobile clients: SuperOffice Mobile and Pocket CRM

These first three CRM clients support many forms of integration, but the mobile clients do not: SuperOffice Mobile and Pocket CRM support custom web panels that are configurable on each device, but that is all. They don't expose any external integration points.

### Recommended APIs for each platform

The list of available APIs for integrations decreases the closer they are to online. That is just the nature of the respective environment and not the limitations of the platforms or APIs.

| | Windows | Web | Online |
|---|:-:|:-:|:-:|
| COM | X | | |
| NetServer Core | X | X | |
| NetServer Web Services | X | X | X |

* From NetServer Core, Web supports NetServer script events only.
* Using NetServer web services, the configuration must be set to Local Mode for Windows and Local or Remote mode for Web.

There are virtually no limitations as to which API you leverage when building an integration that targets just the Windows client. If, however, your requirements include both the Windows client and the Web client, the available API options decrease. This is not necessarily a bad thing though. Sometimes it just makes technological sense to build an integration using only one of the available APIs. Gor example, it doesn't make sense to use the COM-based API in today's web service architectures.

> [!NOTE]
> Although it sometimes can't be avoided, we generally discourage building integrations that leverage more than one of our APIs in the same solution.

Although integrations in SuperOffice CRM Online can display visual elements, such as partner applications through a web panel, the Web client in SuperOffice CRM Online only supports service-orientated integrations today. Meaning that all data access routines must use the web services APIs. Considering the SuperOffice Web client relies exclusively on these APIs, and has more functionality than the Windows user and administration clients, the capability of the web service APIs should never be considered inferior. The web service APIs should be given serious consideration for nearly all scenarios.

## Automation vs. integration

The APIs that enable external integration with SuperOffice typically mean applications that are **compiled into executables** and run in their own process. However, there are also important internal integration points in SuperOffice that are just as important.

The difference between the two is that automation primarily deals with [scripting languages][14] while most integrations use a compiled program using .NET, Java, or Delphi.

**Automation** allows an application to execute code when an event occurs inside the client. These events occur when an action takes place such as when a dialog is opened, or a person is created.

While automation code is usually defined by customer requirements, consultants often create routines that assist with common tasks. Automation code can perform just about any task imaginable, but generally involve validating, transforming, and/or moving data. These types of routines are commonly discussed in the [developer forums][1].

Internal automation APIs are very useful for managing predetermined routines based on customers' requirements and providing user interaction within the application. They can make complex multiple-step tasks easier by programmatically automating the mundane details, and let the user focus on the task at hand.

**NetServer**, although used as an umbrella term that encapsulates a variety of data access capabilities, is just as much if not more extensible than the SuperOffice clients. With constructs such as low-level database objects to high-level business objects, to higher-level web services and web service proxy libraries, NetServer is itself an extensible SuperOffice product.

SuperOffice has several partners and 3rd party vendors who have built tightly-coupled integrations with SuperOffice using external APIs. The different types of integrations built range from tiny edge-case security plugins to integrations with completely new document management systems. There are even complete enterprise resource planning systems that leverage SuperOffice CRM as the heart of its ecosystem.

## At a glance

![Integration points -screenshot][img5]

The following table compares some of the most common extensibility points and defines which capabilities are possible in both environments.

| Level | Extensibility | Client | Onsite | Online |
|---|---|---|:-:|:-:|
| Configuration | Preferences         | Sales, Service | X | X |
|               | Lists               | Sales, Service | X | X |
|               | User-defined Fields | Sales          | X | X |
|               | SAINT               | Sales          | X | X |
|               | Sales Guide         | Sales          | X | X |
|               | Project Guide       | Sales          | X | X |
| UI Workflow   | Drive the application UI | Sales     | X | |
|               | Triggers            | Service        | X | X |
|               | SuperMacro          | Service        | X | X |
|               | Extra Tables        | Service        | X | X |
|               | Custom Screens      | Service        | X | X |
|               | Web panels          | Sales, Service | X | X |
|               | Zapier              | Sales, Service | | X |
| Scripting     | CRMScript           | Service        | X | X |
|               | NetServer Service   | Sales, Service | X | |
|               | Windows Client      | Sales          | X | |
| External APIs | [SOAP][9]           | Sales, Service | X | X |
|               | [Restful][8]        | Sales, Service | X | X |
|               | [Quote Connector][12]    | Sales | X | X |
|               | [ERP Sync Connector][11] | Sales | X | X |
|               | [Database Mirroring][13] | Sales, Service | | X |
| Internal APIs | Custom Pages        | Sales          | X | |
|               | Custom Dialogs      | Sales          | X | |
|               | DataHandlers        | Sales          | X | |
|               | Ajax Methods        | Sales          | X | |
|               | Archive Providers   | Sales          | X | |
|               | MDO Providers       | Sales          | X | |
|               | Document Plugins    | Sales          | X | |
|               | Sentry Plugins      | Sales          | X | |
|               | Batch Task Plugins  | Sales          | X | |
| Database      | Database access API | Sales, Service | X | X |
|               | Continuous Database | Sales, Service | X | |
|               | SQL Scripts         | Sales, Service | X | |

Each platform has strengths and weaknesses that are dependent on the environment in which it is deployed.

## Conclusion

Whether constructing a small internal automation routine or building a complex integration, SuperOffice has many integration options. Once you get past the problem of knowing with which SuperOffice platforms you are integrating, it becomes a matter of just choosing the right API for your solution.

With the understanding that each SuperOffice platform provides a lot of integrations points, and knowing that any problem can have multiple solutions, it's important to consider all options before you decide which approach to take. Assistance and guidance are available. Please use the [developer forums][1] to ask for recommendations, or you may submit integration questions directly to SuperOffice at [sdk@superoffice.com][2].

Read more about each platform API in the SDK documentation.

<!-- Referenced links -->
[1]: https://community.superoffice.com/en/developer/forum/
[2]: mailto:sdk@superoffice.com
[3]: ../../../crmscript/docs/overview/index.md
[4]: ../../../superoffice-docs/docs/service/integrate/index.md
[5]: ../../../superoffice-docs/docs/onsite/integrate/win-client/index.md
[6]: ../../../superoffice-docs/docs/onsite/integrate/web-client/index.md
[7]: ../../../superoffice-docs/docs/online/integrate/index.md
[8]: ../api-reference/restful/index.md
[9]: ../api-reference/soap/index.md
[10]: ../netserver/webhooks/index.md
[11]: ../netserver/erp-connectors/index.md
[12]: ../netserver/quote-connectors/index.md
[13]: ../../../superoffice-docs/docs/mirroring/overview.md
[14]: scripting-languages.md
[15]: ../netserver/index.md
[16]: ../../../superoffice-docs/docs/automation/netserver-scripting/index.md

<!-- Referenced images -->
[img1]: media/web-client-custom-code.png
[img2]: media/extensibilitystairs.png
[img3]: media/onlineapis.png
[img5]: media/integration-points.png
