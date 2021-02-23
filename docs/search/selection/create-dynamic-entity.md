---
# Mandatory fields.
title: create_dynamic_selection_entity      # (Required) Very important for SEO.
description: Creating a dynamic selection using entities # (Required) Important for SEO.
author: {github-id}             # Your GitHub alias.
so.date: 05.11.2016
keywords: search
so.topic: howto            # article, howto, reference, concept, guide

# Optional fields. Don't forget to remove # if you need a field.
# so.envir:                     # cloud or onsite
# so.client:                    # online, web, win, pocket, or mobile
---

# Creating a dynamic selection using entities

As the word implies, a dynamic selection is **a selection that is bound to change dynamically** and it’s **based on search criteria** and not just static members.

A typical criterion would be "Add all contacts with a specific business type". This would cause the member count of this selection to increase each time a new contact is added to the database that matches the business type specified as a search criterion for this selection. You may have as many search criteria as you want.

Here, we'll show you how to do this [using entities][1].

## Code

[!code-csharp[CS](includes/create-dynamic-entity.cs)]

## Walk-through

In the above example, we have created a selection using entities and then we have used the providers to add the restriction for the members that should be added to the created selection. The creation of the selection is pretty straight forward so we will just explain how to add search criteria.

We have created an array of `ArchiveRestriontionInfo` objects since we will add more than one restriction. When you are specifying the restriction, you have to specify the criteria using 3 parameters:

* the field name
* the operator
* the value

Here, we have said give us the contacts with name starting with the letter c and give us the contacts in the business that corresponds to row ID 4 of the `business` table.

Once we have the restrictions ready, we need to store them against the selection to tell the system that this restriction is for a particular selection. We can do this with a `RestrictionCriteriaStorage` provider. We can save our restrictions using the `SaveRestriction` method. In the `SaveRestriction` method, the second parameter will act as the key. If you want you can access this criterion using this key.

Now that we have completed the job, you can open SuperOffice and view this selection. You can see the contacts that we wanted listed under the selection.

![03][img1]

<!-- Referenced links -->
[1]: ../../entities/index.md

<!-- Referenced images -->
[img1]: media/image003.jpg