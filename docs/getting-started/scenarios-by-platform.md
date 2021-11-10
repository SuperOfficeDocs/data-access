---
uid: api_scenarios_by_platform
title: Integration scenarios by platform
description: Integration scenarios by platform
author: Tony Yates
so.date: 11.10.2021
keywords: api, integration point
so.topic: concept
so.envir: cloud, onsite
so.client: win, web
---

# Integration scenarios by platform

To gain a better understanding of what types of integrations are possible, the remainder of this article is going to discuss each SuperOffice client and NetServer to help clarify which integration approach is best for your specific needs.

## Window client

A flagship CRM platform, the SuperOffice CRM client has been the leading SuperOffice CRM product since 1989. SuperOffice CRM was created to support the needs of the salesperson by making his everyday life easier – and make it so user-friendly and elegant that the user would want to use it.

The Windows client exposes many hooks that make it easy for vendors to create a seamless experience with their applications. Integrations have full-duplex type communications, providing integrations the ability to receive notifications when users perform actions, immediately process the data concerned, and even switch the user's context and show important relevant information related to that action.

**Integration points:**

* COM API
* Automation Engine (vbScript and JScript scripts)
* Event Subscriptions (internal scripts and external COM subscriptions)
* Web Panels
* Buttons to launch external applications
* Document Plugin (NetServer-based since version 8)
* Sentry Plugin (COM)
* Email Plugin (COM)

**Related SDK**:

* [IApplicationCOM API][5]
* [IDatabaseCOM API][6]

## Web client (onsite)

Available since 2007, the SuperOffice Web client has enjoyed a wide adoption by many on-site customer installations. The product has several advantages over the Windows client. For example, customers can install SuperOffice on a web server that is accessible both near and far without having to pay extra license fees for disconnected functionality such as Travel or incur the extra maintenance costs for maintaining Travel Gateway and the processing of .up and .dwn files.

SuperOffice CRM Web also enjoys many integration capabilities. I would go so far as to say that it is the most extensible CRM platform available today! With the ability to modify and adapt the user's experience, manipulate the data processing and logic, nearly every component in the SuperOffice CRM Web stack is over-ridable and extensible for complementary functionality or control.

**Integration points:**

* Add controls to existing pages
* Add custom dialogs
* Override default functionality and inject custom logic into
  * DataHandlers (create, update, delete of page data
  * Archive Providers (read-only search providers
  * Most buttons
* Add custom views (tabs or preview pane options)
* Add web panels

**Related SDK**:

* [Web client SDK][7]

## Web client (online)

Both SuperOffice on-site installations and CRM Online applications use the same NetServer web service APIs. The only difference between the two environments is how integrations are authenticated. While on-site integrations have a more direct approach, supplying credentials, CRM Online integrations must use [federated authentication][8].

Federated authentication is a way SuperOffice can provide a single-sign-in experience for multi-tenant users and applications that serve multi-tenant installations.

The SuperOffice CRM Online environment hosts an app store with several partner integrations. These integrations are comprised of Business to Consumer (B2C) applications. Most applications expose functionality inside SuperOffice by adding web panels in relevant areas, while others add a button that opens a web page to the application. All application vendors have their own cloud platforms to manage customers and tenant users.

You can find out more information about CRM Online integration points by reading the CRM Online SDK pages.

**Integration points (online)**:

* Custom Lists
* Custom List Items
* User-defined Fields
* Web Panels
* Custom buttons (navigator and button bar)
* Access to Web Services, including webhooks (see NetServer Architecture below).

**Related SDK**:

* [CRM Online SDK][9]

## Customer Service

There are several articles available that explain in detail many of the internal automation integration points provided by SuperOffice CS. There are not, however, too many external integration points to discuss. The ones that do exist are primarily the CS legacy [SOAP services][10]. It must be said that these services have not evolved for quite some time, and do not appear to be on any road map. That said, there are a few major installations that do leverage these endpoints, and therefore they are not likely to fade away any time soon either. Similar to the Windows client COM APIs, these APIs are in the future not likely to change.

There are no prebuilt SuperOffice proxies available for these APIs. You must use a proxy generator appropriate for your target technology platform, or use raw SOAP requests, to use these services.

**Integrations points:**

* SOAP Services (**Not available in Online**) (available at `http://<domain>/scripts/SOAP.exe?action=<endpoint>`. Available action parameters:
  * customer
  * ticket
  * admin

**Related SDK**:

* [Customer Service][10]

<!-- Referenced links -->
[5]: https://github.com/SuperOffice/SDK-Doc/tree/master/COM.IApplication
[6]: https://github.com/SuperOffice/SDK-Doc/tree/master/COM.IDatabase
[7]: ../api-reference/web/index.md
[8]: ../../../superoffice-docs/docs/identity-management/federated-auth.md
[9]: ../api-reference/webapi/index.md
[10]: ../netserver/services/reference/index.md

<!-- Referenced images -->
