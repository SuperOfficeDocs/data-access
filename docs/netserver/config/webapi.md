---
title: WebApi element
uid: ns_config_webapi
description: NetServer WebApi element
so.date: 12.07.2021
author: Bergfrid Dias
keywords: config, NetServer, web.config, authentication, WebAPI, AuthorizeWithImplicit, AuthorizeWithTicket, AuthorizeWithUsername, CORSEnable, CORSOrigin, CORS, authorize, authentication, security
so.topic: reference
so.envir: onsite
---

# NetServer WebApi element

Configuration values related to the WebApi web services.

```XML
<WebApi>
  <add key="AuthorizeWithUsername" value="true" />
  <add key="AuthorizeWithTicket" value="true" />
  <add key="AuthorizeWithImplicit" value="false" />
  <add key="CORSEnable" value="true" />
  <add key="CORSOrigin" value="http://foo.bar http://localhost/ http://localhost *" />
</WebApi>
```

| Name | Description | Default
|---|---|---|
| AuthorizeWithImplicit | Allow WebAPI to authorize with implicit identity from IIS.| true |
| AuthorizeWithTicket | Allow WebAPI to authorize with session tickets. | true |
| AuthorizeWithUsername | Allow WebAPI to authorize with username + password. |  true |
| CORSEnable | Allow 3rd party web pages to call WebAPI from the browser.| false |
| CORSOrigin | If CORS is enabled, define space-delimited Origins that are allowed to call the WebAPI from the browser. Example value: `"http://foo.bar http://localhost/ http://localhost *"`. | |

See the [NetServer Core reference][1] for details about handling this programmatically.

<!-- Referenced links -->
[1]: <xref:SuperOffice.Configuration.ConfigFile.WebApi>
