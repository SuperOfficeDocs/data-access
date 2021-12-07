---
title: Services element
uid: ns_config_services
description: NetServer Services element
so.date: 12.07.2021
author: Bergfrid Dias
keywords: config, NetServer, web.config, Services, web services, ApplicationToken, DefaultMode, RemoteBaseURL, SwitchDefault, SwitchFailover
so.topic: reference
so.envir: onsite
---

# NetServer Services element

Configuration settings used to manage SuperOffice web services.

```XML
<Services>
  <add key="DefaultMode" value="Local" />
  <add key="SwitchDefault" value="Remote" />
  <add key="SwitchFailover" value="60" />
  <add key="RemoteBaseURL" value="http://localhost/remote/services88/" />
  <add key="ApplicationToken" value="" />
</Services>
```

| Name | Description | Default |
|---|---|---|
| ApplicationToken | Application token passed with services to identify the client application. | |
| DefaultMode | Mode used for Service calls. Options are Local or Remote. | Local |
| RemoteBaseURL | Base URL for remote web services. This value will be overridden by `WebServices.RemoteBaseURL`. | `http://localhost/webs/SuperOffice.Web.Services` |
| SwitchDefault | If DefaultMode is unsuccessful, default mode for the switch. | Remote |
| SwitchFailover | Timeout before failover in seconds. | 60. |

See the [NetServer Core reference][1] for details about handling this programmatically.

<!-- Referenced links -->
[1]: <xref:SuperOffice.Configuration.ConfigFile.Services>
