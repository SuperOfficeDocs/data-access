---
title: NetServer Client element
uid: ns_config_client
description: Configuration values related to NetServer client configuration, extension of ClientConfigurationProvider.
so.date: 12.07.2021
author: Bergfrid Dias
keywords: config, NetServer, web.config, ClientConfigurationProvider, Client, ApplicationName, ApplicationInstance, HelpFilesBaseUrl, ExportPageSize, ApplicationTitle, WebAppUsage, ClientCacheKey, UrlSchemeOverride, UrlHostOverride, UrlPortOverride, GoogleImportDispatcher, GoogleImportClientId, GoogleImportClientSecret, MasterDcfConfigHashKeyFormat, NetServicesStatusUrl, NetServicesNextDate, ShowWelcomeDialogs, WWW3Url
so.topic: reference
so.envir: onsite
so.client: web
---

# NetServer Client element (SuperOffice only)

Configuration values related to client configuration, extension of `ClientConfigurationProvider`.

```XML
<Client>
  <add key="ExportPageSize" value="10" />
</Client>
```

| Name | Description | Default |
|---|---|---|
| ApplicationInstance | Web client instance name - used to resolve page config files. | Web - **Don't change!** |
| ApplicationName | Web client application name - used to resolve page config files. | WebClient - **Don't change!** |
| ApplicationTitle | Application title. | SuperOffice® CRM |
| ClientCacheKey | Cache key that is appended (if it exists) to the query string for JavaScript and CSS includes. | |
| ExportPageSize | | 10000 |
| GoogleImportClientId | Client ID when importing from Google. | |
| GoogleImportClientSecret | Client secret when importing from Google. | |
| GoogleImportDispatcher | URL to import from Google. | |
| HelpFilesBaseUrl | Override the help files location - to support local deployments. | |
| MasterDcfConfigHashKeyFormat | The format key used to generate a unique DCF page config hash.<br>{0} = MachineName; {1} = Build-label;{2} = Assembly version | 0 |
| NetServicesNextDate | Override the Next Check Date preference for NetServices Status checking. Useful for testing. YYYY.MM.DD | |
| NetServicesStatusUrl | Override the default NetServices Status URL with this value. Useful for testing. | |
| ShowWelcomeDialogs | Allow automated tests to disable WebTools and welcome dialogs. | |
| UrlHostOverride | Overridden value of host, like: `web.superoffice.com`. | |
| UrlPortOverride | Overridden value of port, like: 80 or 443. | |
| UrlSchemeOverride | Overridden value of scheme (HTTP or HTTPS). | |
| WebAppUsage | Enable the collection of Web Client usage statistics (only view usage, no references to actual data). | |
| WWW3Url | The root-URL of the global SuperOffice www3 host. | |

See the [NetServer Core reference][1] for details about handling this programmatically.

<!-- Referenced links -->
[1]: <xref:SuperOffice.Configuration.ConfigFile.Client>
