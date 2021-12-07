---
title: Documents element
uid: ns_config_documents
description: NetServer configuration used to access the SuperOffice documents.
so.date: 12.07.2021
author: Bergfrid Dias
keywords: config, NetServer, web.config, Documents, ArchiveDomain, ArchivePath, ArchivePassword, ArchiveUser, BufferSize, CanCreateDocumentTemplates, ImpersonateUser, TemplatePath, TemporaryPath, SO_ARC
so.topic: reference
so.envir: onsite
---

# NetServer Documents element

This configuration is used to access the SuperOffice documents. It is used by NetServer to identify which document archive and temporary directory are used.

To restrict access to the document archive, specify domain credentials with read and write access to the archive for NetServer to impersonate.

```XML
<Documents>
  <add key="ArchivePath" value="c:\so_arc\" />
  <add key="TemporaryPath" value="c:\temp\" />
  <add key="ImpersonateUser" value="false" />
  <add key="ArchiveUser" value="" />
  <add key="ArchivePassword" value="" />
  <add key="ArchiveDomain" value="" />
  <add key="BufferSize" value="1024" />
</Documents>
```

| Name | Description | Default |
|---|---|---|
| ArchiveDomain | Domain of the user to impersonate. | |
| ArchivePath | Path for SO_ARC. Even if the so arc is not used, the default path for the document template folder is calculated from this folder. | |
| ArchivePath1 - ArchivePath10 | Alternative/additional archive path to search for documents | |
| ArchivePassword | Password of the user to impersonate. | |
| ArchiveUser | Username of the user to impersonate. | |
| BufferSize | Size in kilobytes of the internal buffer used for file handling. | 1024 |
| CanCreateDocumentTemplates | New document templates can be stored in SoArc. | |
| ImpersonateUser | Impersonate the user to access the document archive. If true, see section ArchiveUser for further reference. | |
| TemplatePath | Path to document templates. If this value is not specified, the "Template" folder under ArchivePath is assumed. | |
| TemporaryPath | Temporary folder for working with documents. If this value does not exist, the environment variable "TEMP" is used to find the temporary folder. | |

See the [NetServer Core reference][1] for details about handling this programmatically.

<!-- Referenced links -->
[1]: <xref:SuperOffice.Configuration.ConfigFile.Documents>
