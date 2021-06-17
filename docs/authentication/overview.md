---
title: SuperOffice Authentication
uid: authentication_overview
description: Overview of SuperOffice API authentication.
author: AnthonyYates
so.date: 05.08.2018
keywords: security, identity
so.topic: concept
so.envir: onsite, online
# so.client:
---

# SuperOffice Authentication

## Introduction

One of the hardest things about getting started with new technologies is knowing where to begin. When it comes to application development and integrations, the obvious place is authentication.

SuperOffice has multiple data access layers, so let's start with an overview of what the SuperOffice APIs have to offer.

**Overview of common SuperOffice API surface:**

![auth][img1]

SuperOffice **COM APIs** have been around the longest. The 2 main interfaces, **IApplication** and **IDatabase**, facilitate access to the Windows client application and the database. While `IApplication` exposes the capabilities to drive the application, `IDatabase` provides the capability to read and write to and from the SuperOffice database without having the Windows client running.

While SuperOffice Customer Service (CS) capabilities are vast, most of the functionality revolves around processing support tickets and internal processes using script automation. The CS SOAP services are limited, whereas the NetServer web services surface is much larger and the primary target for interacting with SuperOffice business entities. This article will not cover any more information about CS.

SuperOffice **NetServer SOAP web services** are a complete set of service endpoints that support 100% of the SuperOffice web-client functionality - which is more than the Windows client and COM could ever claim. CS depends on NetServer web services, as well as all the quote functionality in the Window client!

NetServer code, comprised of business entity classes as well as row & row collections, supports the entire web services stack. All of this functionality gets pushed through NetServer's [Objectified SQL (OSQL)][2] classes for database-vendor-specific SQL generation.

### Reading advice

The objective of this article is to introduce you to how to get past the first hurdle, authentication. All of the following sections assume you have access to a correctly configured SuperOffice database. Each section will define all of the dependencies required to be in place for you to be able to successfully authenticate with the corresponding API.

> [!NOTE]
> The development environment used in these examples is Visual Studio and the language used C#.
>
> If you don't have one of the SuperOffice clients installed (Windows or Web), you will want to **download the Expander SDK** to have the necessary DLLs and COM interop libraries to complete the code examples below. The latest available for download at the time of this article was SuperOffice 7.5.

## SuperOffice Online

Read about online authentication in the [online environment][3] documentation.

## COM

Read about COM authentication in the [onsite authentication][6] section.

## <a name="skip-to-netserver"></a>NetServer configuration

All NetServer integrations **that use SuperOffice assemblies** require settings in an application's configuration file, *app.config* or *web.config*. This is not the case for custom web service proxies or REST. This applies only when an application makes a file reference to *SOCore.dll*, *SoDatabase.dll*, and other required SuperOffice DLLs.

Below is a configuration file with only the bare essential SuperOffice sections defined:

[!code-xml[XML](includes/idatabase-config.xml)]

> [!NOTE]
> The **Data element** contains the session, database, and explicit sections. Often, the cause of connectivity problems lays here.

### Session

`Session` determines how the authenticated session will exist at runtime. There are 3 options by default: Process, Context, and Thread. Each session option determines where in memory the authenticated session will be available from.

| Session option | Availability of authenticated SoSession |
|---|---|
| Process | to all synchronization contexts and threads |
| Context | only to routines passed to the same synchronization context |
| Thread  | only on that thread - if another non-authenticated thread tried to use the SuperOffice API to get data, NetServer would throw an exception. |

### Database

The `Database` section is used to define your database-specific details and will look slightly different than the example if you are targeting DB2 or Oracle. More information about the database section can be found in the [NetServer configuration reference][5].

### Explicit

The `Explicit` section allows an application to determine what type of users are authorized to use this application, as well as must set the database credentials, which map to both a database server user and a SuperOffice system user.

## NetServer Core & Service proxy authentication using SoSession

While most data access layers require only database credentials for access database resources, SuperOffice requires a valid SuperOffice user too when authenticating using NetServer.

The user must establish an **SoSession**, which is an `IPrincipal` container and has several overloads for authentication. Read about SoSession in the [onsite authentication][7] section.

## NetServer web service custom proxies

If you are not developing solutions using Microsoft .NET and can't reference the SuperOffice assemblies, you must rely on your technology stack to either generate SOAP proxies or roll your own.

In many cases, such as PHP and Python, applications depend on loading the WSDL file for interacting with SuperOffice web services. We make those files available for downloads along in the [SOAP web services API reference][1].

With the WSDL files and using a tool like SOAPUI, raw SOAP requests are sent to SuperOffice endpoints for testing. You can, for example, use SOAPUI or compose the SOAP request manually with Fiddler2:

### [SOAPUI](#tab/wsdl-1)

![soapui][img5]

### [Fiddler2](#tab/wsdl-2)

![fiddler][img6]

***

## SuperOffice REST / WebAPI web services

To successfully use the REST APIs (introduced in SuperOffice version 8), you must pass along credentials in each request header.

Below is an HTML page that contains a few text boxes for determining where, or what version of, the services reside, user name, and password. With this required information, the user can specify a project ID and click the **Get** button to execute an XMLHttpRequest.

![request-page][img7]

### Basic

As seen earlier, the `setRequestHeader` method is used to add the Authorization header key entry with a value equal to "Basic " plus a base64 encoded representation of the user name, plus a colon, and password. Note the space following the word *Basic*. In the JavaScript code, we use the built-in DOM `window.btoa(...)` method to convert the value to base64.

### SOTicket

Alternatively, if the HTML page is running in the context of a SuperOffice web panel, and the application passes in the user's `SoCredential.Ticket`, the REST request header also supports SOTicket, instead of Basic. In that case, the Authentication header value is "SOTicket " plus the ticket string. Once again, notice the space following *SOTicket*.

[!code-html[HTML](includes/rest-auth.html)]

> [!NOTE]
> In this case, don't use the `window.btos(...)` method to convert a Ticket to base64 because the **ticket value is already base64 encoded**.

## Conclusion

SuperOffice supports several different access points to SuperOffice APIs. Without knowing where to begin, it makes it almost impossible to successfully build an integration. The first place most applications must begin with is authentication, Once authentication is understood, and understanding at what data access level your application will integrate with SuperOffice, the remaining tasks should just be learning about the various entity and service APIs for reading and writing data to the SuperOffice database.

<!-- Referenced links -->

[1]: ../api-reference/soap/index.md
[2]: ../netserver/osql/index.md
[3]: ../../../superoffice-docs/docs/identity-management/federated-auth.md
[5]: ../netserver/config/data.md
[6]: onsite/com/index.md
[7]: onsite/sosession/index.md

<!-- Referenced images -->
[img1]: media/authenticate-overview.png
[img5]: media/services-authenticate-soapui.png
[img6]: media/services-authenticate-fiddler.png
[img7]: media/simple-rest-page.png
