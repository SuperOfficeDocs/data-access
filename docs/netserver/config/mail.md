---
title: Mail element
uid: ns_config_Mail
description: NetServer Mail component configuration options.
so.date: 12.07.2021
author: Bergfrid Dias
keywords: config, NetServer, web.config, Mail, NumberOfDaysToDownload, Reader, Sender
so.topic: reference
so.envir: onsite
---
# NetServer Mail element (SuperOffice only)

Mail component configuration options.

```XML
<Mail>
  <Component>
    <add key="Reader" value="EasyMail" />
    <add key="Sender" value="EasyMail" />
  </Component>
</Mail>
```

## Component

| Name | Description |
|---|---|
| NumberOfDaysToDownload | Initial number of days to fetch mail for. |
| Reader | The Key used for mail reader. |
| Sender | The Key used for mail sender. |

See the [NetServer Core reference][1] for details about handling this programmatically.

<!-- Referenced links -->
[1]: <xref:SuperOffice.Configuration.ConfigFile.Mail>
