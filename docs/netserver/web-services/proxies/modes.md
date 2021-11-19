---
uid: netserver-ws-modes
title: Service communication modes
description: Service communication modes
author: Bergfrid Dias
so.date: 11.19.2021
keywords: API, web services, DefaultMode, SuperOffice.Services.dll
so.topic: concept
---

# Service communication modes

The Agent factory returns implementation objects that talk directly to the database or to return proxy objects that talk to the back-end via SOAP. The advantage of this is that it gives flexibility since you can run everything on one box or two separate boxes without changing the program. Only the config file needs to be changed.

The diagram depicts the data path taken when communicating with the Services layer.

![x][img3]

The Client represents a .NET application that has referenced *SuperOffice.Services.dll*. The lines below, depending on the Services->DefaultMode configuration setting, represent the data path to communicate with the database.

The following section of the config file shows where the web services are turned on:

```XML
<Services>
  <!-- Mode can be Local, Remote, Switch -->
  <add key="DefaultMode" value="Local" />

  <!-- Default mode for the switch. Can be Local or Remote -->
  <add key="SwitchDefault"  value="Remote" />

  <!-- Timeout before failover in seconds -->
  <add key="SwitchFailover" value="60" />

  <!-- Base URL for remote services -->
  <add key="RemoteBaseURL" value="http://localhost/Webs/SuperOffice.Services.Stub" />

  <!-- URL to the Data Set Definition file -->
  <add key="DataSetDefinitionURL" value="http://localhost/Webs/SuperOffice.Services.Stub/dsd.xml" />
</Services>
```

> [!TIP]
> Use local mode when the application resides on the same server as the database or within the same domain.

## Local mode

When opted to operate in local mode, *SuperOffice.Services.dll* is not actually making web service calls.

Instead, it uses both Rows and OSQL to populate lite-serializable versions of intrinsic types, such as Appointment, Contact, and Person. These are the same objects returned by calling the web service, but in this case, **don't require a round-trip across the internet**. Smart, huh?

## Remote mode

In remote mode, *SuperOffice.Services.dll* uses proxy classes that are, to some degree, similar versions of what you get when generating proxy classes with SVCUTIL.exe. These objects, however, are enhanced a magnitude greater to increase completeness and usability when submitting calls to and receiving data from NetServer web services.

The URL of the remote web services is determined by the SuperOffice->Service-> RemoteBaseURL configuration setting.

When read from the configuration file by *SuperOffice.Services.dll*, the "Remote" indicates that the interfaces are implemented by SuperOffice.Services\[version\].Wcf.dll and related files. In this case, the data path originating from the client traverses SuperOffice.Services\[version\].Wcf.dll, across the internet to the web service endpoints, *SuperOffice.Services.WcfService.dll*, which then calls into a local copy of SuperOffice.Services.dll.

At this point, the data path starts all over again (same as local mode), but local to the Remote location. Now on the remote server, SuperOffice.Services.Implementation.dll leverages both Row and OSQL layers to conduct transactions with the database. The implementation populates the lite-objects, returns them to the SuperOffice.Services.Wcf.dll, which then passes the data back to the client proxy.

## Switch mode

Switch mode, when set, will attempt to communicate with the setting defined in Services-SwitchDefault. If unable to communicate successfully, NetServer will switch to the other setting option (Local or Remote) and attempt to communicate again.

## Conclusion

* When running locally, the new ContactAgent() returns a `ContactAgentImpl` that lives in the *SuperOffice.CRM.Services.Implementation.dll*.
* When running remotely, the new ContactAgent() returns a `ContactAgentProxy` that lives in the *SuperOffice.CRM.Services.Proxy.dll*.

The application code cannot tell the difference between the two because the `GetContactAgent()` call only promises to return something which implements the `IContactAgent` interface – which both the local implementation and the proxy object do.

<!-- Referenced links -->

<!-- Referenced images -->
[img3]: media/servicedatapath-sm.png
