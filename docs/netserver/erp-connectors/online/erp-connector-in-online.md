---
title: erp_sync       
description:                    
author: {github-id}             # Your GitHub alias.
keywords:
---

# ERP Sync Connectors

The **SuperOffice ERP Integration Server** (EIS) was introduced in SuperOffice CRM in version 7.5, and provides partners an API to create Sync Connectors that handle the synchronization of data between SuperOffice and an ERP system.

While this article is not an instruction on how to build an ERP Sync Connector, the [existing documentation does a great job of that][1], it is an instructional read that defines an additional requirement when building ERP Connectors for SuperOffice Online.

## Architecture

The standard architecture for ERP synchronization includes the ERP Integration Server (EIS), hosted as a service that facilitates all synchronization tasks. In the middle layer are the administrative aspects of the architecture; where consultants or administrators register connectors and establish connections.

![architecture-simplified][img1]

On the right is the remote ERP Connector, a remote web site that exposes the web service that implements the IErpConnector interface. This is where SuperOffice will connect in order to obtain ERP data.

## Configure

When administrators configure an ERP Sync Connector inside SuperOffice today, they must fill in a Sync Connector name and a Sync Connector URL.

![editsyncconnector][img2]

The Sync Connector name will be used as a reference for all connections created to this connector, and the Sync Connector URL specifies where SuperOffice EIS will contact to synchronize data.

SuperOffice EIS will periodically invoke the web services to conduct data synchronization. This invocation is a blind call, meaning that no exchange of credentials or security layers exist between SuperOffice and the web site hosting the web services. This configuration works great for onsite customer installations where both SuperOffice CRM and the ERP system reside inside the secure network, but leaves much to be desired in the online environment.

## Continue reading

* [Security][2]
* [API changes][3]

<!-- Referenced links -->
[1]: https://community.superoffice.com/documentation/SDK/SO.NetServer.Data.Access/html/DevelopersGuide-ERPConnectors-ERPSyncConnectorInterface-ERPSyncConnectorInterface.htm
[2]: secure-in-online.md
[3]: example-api.md

<!-- Referenced images -->
[img1]: media/architecture-simplified.png
[img2]: media/editsyncconnector.png