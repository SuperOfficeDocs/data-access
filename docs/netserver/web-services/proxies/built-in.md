---
title: Calling SOAP using the NetServer proxy
uid: call_soap_ws_nuget
description: Calling SOAP using the NetServer proxy
author: Bergfrid Dias
so.date: 11.26.2021
keywords: API, web services, proxy, WebAPI, SOAP, SuperOffice.Service.dll, modes, DefaultMode
so.topic: howto
# so.envir:
# so.client:
---

# Calling SOAP using the NetServer proxy

This section explains how to access SuperOffice web services from .NET using SuperOffice tools.

Whether targeting a local or remote database, an **SoSession** is the object that maintains a user's principal. The **secret** is calculated for us during the `Authenticate` call. The proxy objects returned will automatically add the SOAP authentication header for us. This makes working with the SOAP services much simpler. See the [Authentication][2] section for more information.

> [!NOTE]
> There is no secret used here: the username + password is passed in clear-text, so you should use HTTPS if you are going to be doing this over the open internet.

## <a name="binary"></a>Directly with binaries

In this case, everything runs within the same process.

![03][img1]

To call a NetServer service through the binaries:

1. Add the following NetServer binaries to your application (project references).

    * SoCore.dll
    * SuperOffice.Service.dll
    * SuperOffice.Service.Implementation.dll

2. In the application’s configuration file, set `DefaultMode` to **Local**.

    ```XML
    <Services>
      <addkey="DefaultMode" value="Local" />
    </Services>
    ```

3. Calling the web service (authenticate and get entity). Use the namespaces of the binaries in the `using` section of your code file:

    ```csharp
    using SuperOffice.CRM.Services;

    using (SoSession mySession = SoSession.Authenticate("sam", "sam"))
    {
      //Instantiate the Contact Entity
      using(ContactAgent contactAgent = new ContactAgent())
      {
        //Create a Contacts Array and assign values
        Contact[] myContacts = new Contact[5];
        myContacts = contactAgent.GetMyContacts();

        ContactEntity contactEntity = contactAgent.CreateDefaultContactEntity();
        contactEntity.Name = "Supra Inc.";
        // ... populate contact properties
        contactAgent.SaveContactEntity(contactEntity);
      }
    }
    ```

Here, the `GetContactAgent` will check the config file and return an object that lives in the *Services.Implementation.dll*. This implementation will in turn use the database directly to work out the result. In this case, there is no web-service call involved in calling the NetServer service.

## <a name="iis"></a>Through a proxy as a web service

The application calls the services proxy, which calls the remote web services via SOAP. This corresponds to the following diagram:

![04][img2]

To call a NetServer service through a proxy as a web service:

1. Set up the NetServer-provided web services as an application in IIS. Make sure that all the following DLLs are included in the *Bin* directory of the website. You will also need the SVC files.

    * SOCore.dll
    * SoDateBase.dll
    * SuperOffice.Plugins.dll
    * SuperOffice.Services.dll - Internal interface declarations
    * SuperOffice.Services.Implementation.dll - The business logic implementation
    * SuperOffice.Services.Wcf.dll - The WCF interface declarations
    * SuperOffice.Services.WcfService.dll - The WCF web service logic; calls *SuperOffice.Services.dll*
    * SuperOffice.Web.Globalization.dll - Translation utilities
    * ICSharpCode.SharpZipLib.dll

2. In the application’s configuration file, set `DefaultMode` to **Remote**.

    ```XML
    <Services>
      <addkey="DefaultMode" value="Remote" />
      <addkey="RemoteBaseURL" value="http://hostname/WebServices/" />
    </Services>
    ```

3. Now you can call the web services using the same agent pattern as before.

Here, we use `http://localhost/SuperOffice/SoPrincipal.svc` and `http://localhost/SuperOffice/Contact.svc` as the web service references. The web reference folder is *ContactRef*.

[!code-csharp[CS](includes/servicestest1.cs)]

The proxy object will use Microsoft's WSE toolkit to do a SOAP call to the remote URL specified in the config file. If WSE is not installed, an error will occur during the processing of a configuration file required to service this request.

## Configuration

Microsoft’s Web-Service Enhancements are used to provide the SOAP message handling, while the *web.config* file of the web services must also contain the right WSE sections. Add this to the *web.config* file:

```XML
<system.web>
  <webServices>
    <soapExtensionTypes></soapExtensionTypes>
    <soapServerProtocolFactory type="Microsoft.Web.Services3.WseProtocolFactory,
        Microsoft.Web.Services3, Version=3.0.0.0, Culture=neutral,
        PublicKeyToken=31bf3856ad364e35"/>
    <soapExtensionImporterTypes>
      <add type="Microsoft.Web.Services3.Description.WseExtensionImporter,
         Microsoft.Web.Services3, Version=3.0.0.0, Culture=neutral,
         PublicKeyToken=31bf3856ad364e35"/>
    </soapExtensionImporterTypes>
  </webServices>
  <customErrors mode="RemoteOnly"/>
  <authentication mode="None"/>
  <authorization>
    <allow users="*"/>
  </authorization>
  <identity impersonate="true"/>
  <sessionState mode="InProc" stateConnectionString="tcpip=127.0.0.1:42424" 
    sqlConnectionString="data source=127.0.0.1;Trusted_Connection=yes" cookieless="false"  
    timeout="20"/>
  <globalization requestEncoding="utf-8" responseEncoding="utf-8"/>
</system.web>

<microsoft.web.services3>
</microsoft.web.services3>
```

## \<Services> section in web.config

We have to have a `web.config` file in the web service as well. In that config file, the service section should look like this:

```XML
<Services>
  <!-- Mode can be Local, Remote, Switch -->
  <add key="DefaultMode" value="Local" />

  <!-- Default mode for the switch.  Can be Local or Remote -->
  <add key="SwitchDefault" value="Remote" />

  <!-- Timeout before failover in seconds -->
  <add key="SwitchFailover" value="60" />

  <!-- Base URL for remote services -->
  <add key="RemoteBaseURL" value="" />
</Services>
```

Here we have set the `DefaultMode` to *Local* because the services will be called from DLLs that reside in the local machine that is hosting the web service.

## \<Data> section in web.config

These are not the only config data that should be in the `web.config` file! The `Data` section is also very important. Below is a sample data section of a `web.config` file.

```XML
<Data>
  <Session>
    <add key="Mode" value="Thread" />
  </Session>

  <Database>
    <add key="DatabaseMajor" value="MSSQL" />
    <add key="DatabaseMinor" value="8" />
    <add key="Server" value="eccolwxpbwi" />
    <add key="Database" value="SuperOfficeDemo" />
    <add key="CommandTimeOut" value="300" />
    <add key="TablePrefix" value="CRM5" />
    <add key="ConnectionString" value="Server=[@Server];Database=[@Database];User ID=[@User];Password=[@Password]" />
  </Database>

  <ImplicitAnonymous>
    <add key="Allowed" value="True" />
    <add key="DBUser" value="crm5" />
    <add key="DBPassword" value="crm5myd" />
    <add key="CommonDBConnection" value="True" />
    <add key="SoUser" value="ANONYMOUS" />
    <add key="SoPassword" value="ANONYMOUS" />
  </ImplicitAnonymous>

  <Explicit>
    <add key="ExternalPersonAllowed" value="True" />
    <add key="EmployeeAllowed" value="True" />
    <add key="SystemAllowed" value="True" />
    <add key="DBUser" value="crm5" />
    <add key="DBPassword" value="crm5myd" />
    <add key="CommonDBConnection" value="True" />
  </Explicit>
</Data>
```

The database attributes that are specified here will be used when logging into the database and selecting what is the server and what is the actual database name will be also done from what we specify here.

## \<Cryptography> section in web.config

> [!NOTE]
> If you have a cluster of web servers, it is very important to keep the `cryptography` section of `web.config` files the same in all cluster machines. For example, if the below cryptography section is used in one `web.config` file, all other `web.config` files in the cluster **must maintain the same secret**.

```XML
<Cryptography>
  <add key="SymmetricKey" value="ttkggjjj5uiuuGTREdfdsfsfkoKKwqeqeGGGkjuiuJJ=" />
  <add key="SymmetricIV" value="aBL3Kh0mXHzn+NvXkSS/Lg==" />
  <add key="SymmetricSecret" value="SupperOffice Testing" />
</Cryptography>
```

## <a name="modes"></a>Service communication modes

The constructors return implementation objects that talk directly to the database or to return proxy objects that talk to the back-end via SOAP. The advantage of this is that it gives flexibility since you can run everything on one box or two separate boxes without changing the program. Only the config file needs to be changed.

The diagram depicts the data path taken when communicating with the Services layer.

![Service communication modes and data path][img3]

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

### Local mode

When opted to operate in local mode, *SuperOffice.Services.dll* is not actually making web service calls.

Instead, it uses both Rows and OSQL to populate lite-serializable versions of intrinsic types, such as Appointment, Contact, and Person. These are the same objects returned by calling the web service, but in this case, **don't require a round-trip across the internet**. Smart, huh?

### Remote mode

In remote mode, *SuperOffice.Services.dll* uses proxy classes that are, to some degree, similar versions of what you get when generating proxy classes with SVCUTIL.exe. These objects, however, are enhanced a magnitude greater to increase completeness and usability when submitting calls to and receiving data from NetServer web services.

The URL of the remote web services is determined by the SuperOffice->Service-> RemoteBaseURL configuration setting.

When read from the configuration file by *SuperOffice.Services.dll*, the "Remote" indicates that the interfaces are implemented by SuperOffice.Services\[version\].Wcf.dll and related files. In this case, the data path originating from the client traverses SuperOffice.Services\[version\].Wcf.dll, across the internet to the web service endpoints, *SuperOffice.Services.WcfService.dll*, which then calls into a local copy of SuperOffice.Services.dll.

At this point, the data path starts all over again (same as local mode), but local to the Remote location. Now on the remote server, SuperOffice.Services.Implementation.dll leverages both Row and OSQL layers to conduct transactions with the database. The implementation populates the lite-objects, returns them to the SuperOffice.Services.Wcf.dll, which then passes the data back to the client proxy.

### Switch mode

Switch mode, when set, will attempt to communicate with the setting defined in Services-SwitchDefault. If unable to communicate successfully, NetServer will switch to the other setting option (Local or Remote) and attempt to communicate again.

## Summary

* When running locally, the new ContactAgent() returns a `ContactAgentImpl` that lives in the *SuperOffice.CRM.Services.Implementation.dll*.
* When running remotely, the new ContactAgent() returns a `ContactAgentProxy` that lives in the *SuperOffice.CRM.Services.Proxy.dll*.

The application code cannot tell the difference between the two because the `GetContactAgent()` call only promises to return something which implements the `ContactAgent` interface – which both the local implementation and the proxy object do.

<!-- Referenced links -->

<!-- Referenced images -->
[img1]: media/image003.gif
[img2]: media/image004.gif
[img3]: media/servicedatapath-sm.png
