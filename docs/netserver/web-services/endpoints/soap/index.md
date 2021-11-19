---
title: SOAP
uid: soap
description: SOAP API
author: Bergfrid Dias
so.date: 11.19.2021
keywords: API, web services, endpoints, SOAP, Agents
so.topic: concept
---

# SOAP API

WCF/SOAP requests and responses.

## Available endpoints

* [Services88][1]
* [Services87][2]
* [Services86][3]
* [Services85][4]
* [Services84][5]

> [!NOTE]
> The above endpoints should not be confused with the legacy [SOAP interface of SuperOffice Service][6].

## Calling

**Pre-requisite:** [update the configuration files][7]

The following example shows how we may retrieve a `ContactEntity` using the `IContactAgent`.

```csharp
using SuperOffice;
using SuperOffice.CRM.Services;

using(SoSession newSession = SoSession.Authenticate("sam", "sam"))
{
  //Retrieving a Contact Entity from a service agent
  //Instantiating a Contact Agent
  using(ContactAgent myContactAgent = new ContactAgent())
  {
    //Retrieving a Contact Entity carrier from a service call
    ContactEntity myContactEntity = myContactAgent.GetContactEntity(5);

    //Retrieving values of the carrier properties
    string conName = myContactEntity.Name;
    string conDept = myContactEntity.Department;
  }
}
```

Here, we have created an instance of the `IContactAgent` using the `GetContactAgent` method exposed by the `AgentFactory` class. Next, we use the created implementation of the `IContactAgent` to retrieve the `ContactEntity` as shown below.

```csharp
ContactEntity newConEnt = newConAgt.GetContactEntity(5);
```

> [!NOTE]
> The `IContactAgent` class provides methods such as `GetAddress`, `GetAddressByCountry`, `GetContact`, `DeleteContactEntity`, and many more, which can be used in a manner similar to the above.

<!-- Referenced links -->
[1]: ../../../api-reference/soap/Services88/index.md
[2]: ../../../api-reference/soap/Services87/index.md
[3]: ../../../api-reference/soap/Services86/index.md
[4]: ../../../api-reference/soap/Services85/index.md
[5]: ../../../api-reference/soap/Services84/index.md
[6]: ../../../service-soap/overview.md
[7]: ../../proxy/config.md

<!-- Referenced images -->
