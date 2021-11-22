---
title: Proxies
uid: ws_proxies
description: Proxies
author: Bergfrid Dias
so.date: 11.22.2021
keywords: API, web services, proxy, WebAPI, SOAP
so.topic: concept
---

# Proxies

## SOAP

If your services are configured to use SOAP, each method call is a SOAP call that will travel over the network. SOAP calls can be made by .NET or Java clients.

There is flexibility in using SuperOffice **proxies**. Not only are all of the complexities involved with communicating with web services done for you, but also in the ability to code once and have your application work both local or remote simply by changing a single configuration setting - `DefaultMode`. Under the hood, however, there are significant differences between the different modes, Local, Remote, and Switch.

**Options:**

* Use NetServer proxies ([NuGet packages][6])
* Generate a [custom proxy][3] by adding a web service

### NetServer proxies

The most complete way is to reference the pre-packaged, all-in-one factory-driven proxy, **SuperOffice.Services.dll**.

You can either:

* [Call directly with binaries][1]
* [Call through a proxy as a web service][2]

### Custom proxies

* One way to communicate with NetServer web services is to use Microsoft's ServiceModel Metadata Utility Tool ([SVCUTIL.exe][9] to generate a client proxy class for a particular NetServer web service, for example, *Appointment.svc* or *Contact.svc*.

* Another way is to create a Visual Studio Service Reference and communicate with the services through that proxy.

## Wrapped or unwrapped

Proxy generators can generate calls in one of 2 ways: wrapped or unwrapped. The SOAP calls described by the WSDL take one parameter and return one result object. All the parameters to the call are placed on the parameter object. The proxy generator can choose to present the parameters as one object or as a list of parameters.

**Wrapped proxies** match the WSDL call and use one parameter object. A call using a wrapped proxy looks like this:

```csharp
Req r = new Req();
r.param1 = "foo";
r.param2 = 42;
Response res = agent.SomeMethod( r );
```

The order of the parameters is not important, because there is only one parameter to the call. The properties on the parameter object can be initialized in any order without affecting the call.

By unwrapping the parameter object, the method signature looks more like a normal function call. A call using an **unwrapped proxy** looks like this:

```csharp
Response res = agent.SomeMethod( "foo", 42 );
```

The agent proxy will then copy the parameters into the request object and make the SOAP call for you. The unwrapped proxy is more familiar to developers.

The problem with unwrapping is that the order of parameters is lost unless the WSDL contains extra info. For 7.0, this information is not present, so unwrapped proxies will not always match the parameter order shown in the documentation.

The documentation says: `void SomeCall( name, associateId, flag )` The Wrapped proxy will have a request parameter object like this: `void SomeCall( SomeCallRequest request );` The order of the parameters is not significant.

The unwrapped proxy will look like this, with the parameters in alphabetical order:

```csharp
void SomeCall( int associateId, bool flag, string name );
```

In a future release, the parameters will be tagged with ordering information, making life for non-.NET clients simpler. But for now, you will need to pay careful attention to the order of parameters when making unwrapped SOAP proxy calls.

## WebApi client library

<!-- Referenced links -->
[1]: built-in.md#binary
[2]: built-in.md#iis
[3]: custom.md
[6]: https://www.nuget.org/packages/SuperOffice.NetServer.Services
[9]: https://docs.microsoft.com/en-us/dotnet/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe
