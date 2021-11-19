---
title: Calling SOAP using the NetServer proxy
uid: call_soap_ws_nuget
description: Calling SOAP using the NetServer proxy
author: Bergfrid Dias
so.date: 11.18.2021
keywords: API, web services, proxy, WebAPI, SOAP, SuperOffice.Service.dll
so.topic: howto
# so.envir:
# so.client:
---

# Calling SOAP using the NetServer proxy

This section explains how to access SuperOffice web services from .NET using SuperOffice tools.

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

<!-- Referenced links -->
[1]: modes.md

<!-- Referenced images -->
[img1]: media/image003.gif
[img2]: media/image004.gif
