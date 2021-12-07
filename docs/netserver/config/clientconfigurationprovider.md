---
title: ClientConfigurationProvider
uid: ns_config_client_configuration
description: NetServer configuration for the Web client configuration data provider.
so.date: 12.07.2021
author: Bergfrid Dias
keywords: config, NetServer, web.config, ClientConfigurationProvider, FilePath, CacheConfigurations, CacheUserPreferences, ValidateConfigurations, CustomPath
so.topic: reference
so.envir: onsite
so.client: web
---

# NetServer ClientConfigurationProvider element (SuperOffice only)

Configuration for the Web client configuration data provider.

```XML
<ClientConfigurationProvider>
  <add key="CacheConfigurations" value="false" />
</ClientConfigurationProvider>
```

| Name | Description | Default |
|---|---|---|
| CacheConfigurations | Should GUI config data be cached? | |
| CacheUserPreferences | Should user preferences be cached? | true |
| CustomPath | List of alternate paths for GUI .config files. When more than one, each additional path must have a numbered suffix (CustomPath1, CustomPath2, ...) | |
| FilePath | File path for standard .config files. | |
| ValidateConfigurations | Should GUI config data be validated runtime? | |

See the [NetServer Core reference][1] for details about handling this programmatically.

<!-- Referenced links -->
[1]: <xref:SuperOffice.Configuration.ConfigFile.ClientConfigurationProvider>
