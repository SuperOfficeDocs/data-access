---
title: NetServer Data element
uid: ns_config_data
description: The NetServer Data configuration section contains subsections for managing the database connection and session handling.
so.date: 12.07.2021
author: Bergfrid Dias
keywords: config, NetServer, web.config, Database, CommandTimeout, ConnectionString, DatabaseMajor, DatabaseMinor, DatabaseName, DefaultReadUncommitted, DisableSqlTrackingComments, DisableUserInSqlTrackingComments, DynamicLoadedConnectionType, DynamicLoadedDataBaseDriver, ImpersonateDatabaseUser, Server, TablePrefix, Explicit, PartnerAllowed, EmployeeAllowed, AnonymousAllowed, DBUser, DBPassword, CommonDBConnection, Session, Mode, ReauthenticateOnDeserialization, CacheCheckInterval, ForceCacheRefreshInterval, SystemAllowed
so.topic: reference
so.envir: onsite
---

# NetServer Data element

The data configuration section contains four subsections for managing the database connection and session handling.

[!code-xml[the SuperOffice section group](includes/data-element.xml)]

## Database

Configuration values for database connectivity define the location and database-vendor-specific settings.

| Name | Description | Default |
|---|---|---|
| CacheCheckInterval | Number of seconds to check if caches are outdated and need to be refreshed. 0 will disable the timer. | |
| CommandTimeout | Timeout in seconds for the command to wait for a response from the database. | |
| ConnectionString | The formatted connection string template placeholders (`Server=[@Server];Database=[@Database];User ID=[@User];Password=[@Password]`). The number of parameters in the `ConnectionString` key will vary from one database vendor software to another, so will the names of the parameters. Vendor database software differences must be taken into consideration when setting this configuration key. The above example displays the configurations for an MSSQL database. | |
| DatabaseMajor | Major name of database provider. Options: MSSQL, Oracle, Sybase, and DB2 (legacy only). | |
| DatabaseMinor | Version number of database. | |
| DatabaseName | Name of the database. Also used for a distinct service name. | |
| DefaultReadUncommitted | Should SELECTs by default run in "ReadUncommitted" isolation level, lessening locking contention (especially on SQL Server)? | true |
| DisableSqlTrackingComments | If true, then comments that usually precede generated SQL to identify the operation and user will not be generated at all; may help performance on Oracle which thinks it has to re-parse everything if a comment changes. | false |
| DisableUserInSqlTrackingComments | If true, then comments that usually precede generated SQL to identify the operation will not contain associate information; may help performance on Oracle which thinks it has to re-parse everything if a comment changes. | false |
| DynamicLoadedConnectionType | Returns the type of connection to open. | |
| DynamicLoadedDataBaseDriver | Returns the name of the ADO.NET driver to load. | |
| ForceCacheRefreshInterval | Number of seconds before caches are force refreshed. 0 will disable the timer. | |
| ImpersonateDatabaseUser | Should the DbUser be logged in with windows and impersonated when connecting to the database to support database integrated authentication. | false |
| Server | The server name where the database is located. | |
| TablePrefix | The prefix of the SuperOffice CRM tables in the database. | |

## Explicit

Configuration section for authentication behavior when users are explicitly authenticated, typically by calling `SoSession.Authenticate` or the corresponding WCF service.

| Name | Description | Default |
|---|---|---|
| AnonymousAllowed | Is anonymous user access allowed? | false |
| CommonDBConnection | Use the same connection string for all users, applying the common User and Password from this section, vs. using the one provided elsewhere. | true |
| DBPassword | Database user password. | |
| DBUser | Database user when running on behalf of explicitly authenticated users | |
| EmployeeAllowed | Is employee access allowed? | true |
| PartnerAllowed | Is partner access allowed? | |
| SystemAllowed | Is system user access allowed? | |

## Session

 This section governs session handling - what is the scope/storage of the session state, and so on.

| Name | Description |
|---|---|
| Mode | The mode of the session: Thread, Context, HttpContext, Process.<br>Maps to a class name that provides session storage. |
| ReauthenticateOnDeserialization | A full re-authentication is carried out each time the session is de-serialized (e.g. from the session server). |

When in Mode **Thread**, every session requires the [suspend][1] and continue methods to be called for each query task. Here, each thread executed in NetServer will have sessions that are stored in the implication of different threads and have different session values stored in them. If you want to suspend a session, you must call the suspend method which returns a string with the session values. Should you wish to continue that session, you must call the continue method and pass the string with session values in it as a parameter.

When in Mode **Context**, your session only requires authentication and a closure. Here, once you authenticate a session it will be for the lifetime of the session. It is not necessary to call continue and suspend methods. The session values for this configuration will be stored in a context static manner.

See the [NetServer Core reference][2] for details about handling this programmatically.

<!-- Referenced links -->
[1]: ../../authentication/onsite/sosession/suspend.md
[2]: <xref:SuperOffice.Configuration.ConfigFile.Data>
