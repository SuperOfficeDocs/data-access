---
uid: intro-to-superoffice-apis
title: Introduction to SuperOffice APIs
description: Introducing SuperOffice APIs
author: Tony Yates
so.date: 11.15.2021
keywords: api, getting started, integration point
so.topic: concept
so.envir: cloud, onsite
so.client: win, web
---

# Introducing SuperOffice APIs

It can sometimes be daunting for people new to SuperOffice programming to know where to begin. With several platforms, for both customer relationship management (CRM) and customer service (CS), it can be difficult to understand which application programming interface (API) is appropriate for which platform.

There are several levels of SuperOffice extensibility, and these are commonly defined as configuration, UI workflow, scripting, external APIs, and internal APIs.

![ExtensibilityStairs][img2]

The first two levels of extensibility are exposed inside the admin UI pages of SuperOffice. These are features commonly managed by system administrators and SuperOffice consultants and are used to tailor SuperOffice to individual customer needs.

The **scripting level** pertains to a few different features that provide similar functionality, albeit by different means. [CRMScript][3] is a SuperOffice scripting dialect similar to JavaScript and is managed inside the administrative pages of SuperOffice. **NetServer scripting** is an Application Server capability that is accessible onsite only.

**External APIs** refer to SuperOffice web services and provide complete data access for both SuperOffice clients and online applications.

**Internal APIs** refer to the nearly limitless amount of customization capabilities that most onsite installations leverage to provide everything from custom pages and dialogs, document and sentry plugins, and so much more.

## Platforms (SuperOffice clients)

SuperOffice supports different forms of scripting automation. [SuperOffice Service][4] (CS), available for both onsite and online, supports scripting automation and accounts for the majority of integrations. SuperOffice CRM on the other hand is available as four unique platforms, each of which has its own extensibility characteristics:

* [Windows client][5]
* [Onsite Web client][6]
* [Online Web client][7]
* Mobile clients: SuperOffice Mobile and Pocket CRM

These first three CRM clients support many forms of integration, but the mobile clients do not: SuperOffice Mobile and Pocket CRM support custom web panels that are configurable on each device, but that is all; They do not expose any external integration points.

## Online vs. onsite extensibility

Since 2005, SuperOffice has heavily invested in building APIs that enable partners and customers to build integrations that encompass everything from the database schema changes up to modifying UI elements in the application interface.

![CustomCode][img1]

With this breadth of customization capability in onsite installations, it's sometimes hard for legacy partner applications to adapt to move their application to the cloud.

### Limitations

There are multiple online limitations when compared to onsite installations. Online applications are much more strict, and only have a subset of extensible capabilities.

With onsite installation, there is one web server hosting SuperOffice sites, and the owners can do whatever they like with their installation.

Online tenants, on the other hand, share application file sets. Therefore, any compiled assemblies that are exposed to one installation would inadvertently expose those same customizations across all shared tenants. Since that cannot be securely and effectively isolated, **no one is permitted to deploy custom compiled assemblies to an online tenant**.

![Online APIs][img3]

**Security and hosting restrictions** in Online force both standard and custom applications to adapt in ways that support the features and functions they can provide, and accept the limitations that restrict the things they cannot.

SuperOffice will continue to invest in research and development that in the future will be able to deliver equivalent onsite customization capabilities to SuperOffice CRM Online, however, a timeline for this is not available. This policy decision is related to security reasons, and SuperOffice is not willing to compromise tenant security.

## Automation vs. integration

The APIs that enable external integration with SuperOffice typically mean applications that are compiled into executables and run in their own process. However, there are also important internal integration points in SuperOffice that are just as important.

The difference between the two is that [internal automation][14] primarily deals with scripting languages while most [external integrations][15] use a compiled program using .NET, Java, or Delphi.

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
| UI Workflow   | Triggers            | Service        | X | X |
|               | SuperMacro          | Service        | X | X |
|               | Extra Tables        | Service        | X | X |
|               | Custom Screens      | Service        | X | X |
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
| Database      | Continuous Database | Sales, Service | X | |
|               | SQL Scripts         | Sales, Service | X | |

## Conclusion

Whether constructing a small internal automation routine or building a complex integration, SuperOffice has many integration options. Once you get past the problem of knowing with which SuperOffice platforms you are integrating, it becomes a matter of just choosing the right API for your solution.

With the understanding that each SuperOffice platform provides a lot of integrations points, and knowing that any problem can have multiple solutions, it's important to consider all options before you decide which approach to take. Assistance and guidance are available. Please use the [developer forums][1] to ask for recommendations, or you may submit integration questions directly to SuperOffice at [sdk@superoffice.com][2].

Read more about each platform API in the SDK documentation.

<!-- Referenced links -->
[1]: https://community.superoffice.com/en/developer/forum/
[2]: mailto:sdk@superoffice.com
[3]: ../../../crmscript/docs/overview/index.md
[4]: extend-service.md
[5]: extend-win.md
[6]: extend-web-onsite.md
[7]: extend-web-online.md
[8]: ../api-reference/restful/index.md
[9]: ../api-reference/soap/index.md
[10]: ../netserver/webhooks/index.md
[11]: ../netserver/erp-connectors/index.md
[12]: ../netserver/quote-connectors/index.md
[13]: ../../../superoffice-docs/docs/mirroring/overview.md
[14]: internal-automation.md
[15]: external-integration.md

<!-- Referenced images -->
[img1]: media/web-client-custom-code.png
[img2]: media/extensibilitystairs.png
[img3]: media/onlineapis.png
[img5]: media/integration-points.png
