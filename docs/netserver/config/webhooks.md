---
title: Webhooks element
uid: ns_config_webhooks
description: NetServer configuration related to webhooks - events broadcast to remote servers.
so.date: 12.07.2021
author: Bergfrid Dias
keywords: config, NetServer, web.config, Webhooks, EnableWebhooks, NumThreads, RequireHttps, Timeout, ValidateHttps
so.topic: reference
so.envir: onsite
---

# NetServer Webhooks element

Configure values related to webhooks - events broadcast to remote servers.

```XML
<Webhooks>
  <add key="EnableWebhooks" value="true" />
  <add key="RequireHttps" value="true" />
  <add key="ValidateHttps" value="true" />
</Webhooks>
```

| Name | Description | Default |
|---|---|---|
| EnableWebhooks | Broadcast events to remote servers. | false |
| NumThreads | How many background threads to run for dispatching webhooks. | 0 = scale automatically according to demand |
| RequireHttps | Require webhooks target URLs to use HTTPS protocol. Should only be turned off during development. | true |
| Timeout | Stop background threads after X number of seconds of idle time. | 30 seconds |
| ValidateHttps | Require valid public HTTPS certificates. Self-signed or expired certs on webhook target URLs are refused. Should only be turned off during development. | true |

See the [NetServer Core reference][1] for details about handling this programmatically.

<!-- Referenced links -->
[1]: <xref:SuperOffice.Configuration.ConfigFile.Webhooks>
