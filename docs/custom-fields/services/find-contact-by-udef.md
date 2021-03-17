---
# Mandatory fields.
title: find_contact_by_udef       # (Required) Very important for SEO.
description: Find a contact using a udef field # (Required) Important for SEO.
author: {github-id}             # Your GitHub alias.
so.date: 06.24.2016
keywords:
so.topic: howto              # article, howto, reference, concept, guide

# Optional fields. Don't forget to remove # if you need a field.
# so.envir:                     # cloud or onsite
# so.client:                    # online, web, win, pocket, or mobile
---

# Find a contact using a udef field

This example creates the criteria directly on the client and saves and executes the find in one call.

```csharp
using SuperOffice;
using SuperOffice.CRM.Services;
using SuperOffice.CRM.ArchiveLists
using(SoSession.Authenticate( "SAL1", "" ))
{
  using(FindAgent agent = new FindAgent())
  {
    string[] fields = new string[1] { "contactUdef/SuperOffice:1" };
    ArchiveRestrictionInfo[] restrictions = agent.GetSpecifiedCriteriaInformationWithDefaults( "Criteria", "findcontact", "associate=12345", fields, null ).Restrictions;
    restrictions[0].Values = new string[1] { "s" };
    restrictions[0].IsActive = true
    FindResults find = agent.FindFromRestrictions( restrictions, "findcontact", 50, 0 );
    DumpResult( find.ArchiveColumns, find.ArchiveRows );
  }
}
```

> [!NOTE]
> [DumpResult()][1] is a private helper method that you can easily add to your code.

<!-- Referenced links -->
[1]: ../../search/ifindagent/dump-result.md