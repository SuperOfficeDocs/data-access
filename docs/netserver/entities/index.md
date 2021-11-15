---
title: entities
description: 
author: {github-id}
keywords:
---

# Entities

## Relational Database Layer

As I discussed in the previous article, Entities is the layer at which all database entities are exposed. Conceptually, these are the NetServer business objects, such as Contact, Address, and Appointment. When you need to work with people models, for example, you get or create a Person entity. When you need to work with projects, you get or create a Project entity.

Entities are objects that may contain property values that are fetched by more than just the primary object table. In the case of a Person entity, the primary object table being the Person table. A Person.Contact property is a class object that is structured and populated in such a way that take into account settings from more tables than just the Person table.

There are three types of entity types: one entity, entity collections, and entity lists.

Entity are logical real-world objects that make up the business models, such as Contact, Person, Appointment, and so forth. Entity collections are simply collections of the business models, such as ContactCollection, PersonCollection, and AppointmentCollection. Entity lists are similar to entity models, but instead of collections or row objects as properties, list items contain real data values for each property.

The following code demonstrates one way to iterate over the appointments of a person. The Person class is first instantiated by using the inner index searcher class, IdxPersonId. This inner index class is the equivalent of a pseudo method, Person.GetPersonById(...). Every entity object contains at least one inner Idx fetcher class. Each Idx fetcher is also exposed as a static **GetFromIdx** method, i.e. Person.GetFromIdxPersonId.

In the iteration, for every appointment in the Person.Appointments collection, if the appointment type equals type inDiary, meaning the appointment is in the persons diary (calendar), then we will write out some details of the appointment to the console window.

```csharp
using (SoSession session = SoSession.Authenticate("JR", ""))
{
    Person person = new Person.IdxPersonId(7);

    foreach (Appointment apt in person.Appointments)
    {
        //Show Diary Appointments
        if (apt.Type == AppointmentType.inDiary)
        {
            Console.WriteLine(string.Format("ID: {0}\tTask Name: {1}\tStatus: {2}\tDue Date: {3}",
               apt.AppointmentId, apt.Task.Name, apt.Status.ToString(),
               apt.DoBy.ToString()));
         }
    }
}
```

Notice how easy it is to access all of the appointments and appointment information belonging to a person. There is no need to write complex SQL queries that join multiple other tables and establishing criteria, to gain access all of the details pertaining to the appointment. All complex properties of the appointment are easily accessible.

Its also important to note that the value of many entity properties are retrieved from the database when the property is accessed, not when the object itself is initialized. This is sometimes referred to as lazy fetching.

The following code demonstrates again how to leverage an entities inner Index class to fetch the business object - in this case a Contact. Notice how easy it is to logically drill down into the entity and intuitively access the data it contains. Once again, no complex SQL query is required to access the properties of the Contact object.

```csharp
Contact contact = new Contact.IdxContactId(7);
PersonCollection people = contact.Persons;

foreach (Person person in people)
{
    Debug.Assert(person.Contact.Name == contact.Name);
}
```

## Entity Property Types

Whether programming with system data types, or class object data types, properties are just data types. In this section though, I think it is important to note the property data types you are likely to encounter from NetServer Entities. Many of the business object properties bridge the divide between Entity objects and Row objects, and share the same properties.

In many cases, entity properties are intrinsic data types, such as integers and strings. This is the case when working with Entity lists. Other entity properties are entity collections, such as the Contact.Persons property which is of type PersonCollection.

Another common type found in entity properties is of type Row. For example, the Contact.Business property is actually a Row object, of type BusinessRow. Entity properties of type XRow, where X is the name of the property, are similar to that of ADO.NET DataRows. These data types are discussed more in the Row Layer section below.

Each entity object also has a Row property, and this is a direct link to the corresponding HDB Row object. The type is explained in detail in the following section.

The final entity property type you will encounter, which is also categorically in the Rows layer, is a TableInfo type. Every entity type has a TableInfo property that describes the schema of the base entity object. TableInfo discussed more in the Row Layer section.

![x][img4]

## Entities

An entity is a **composite object**, which contains several related rows in one object. The entity handles maintaining the relationships for you.

> [!NOTE]
> Entities are business objects – not all tables have a corresponding entity.

An entity is suitable for **one-at-a-time work**. Each entity will load its sub-objects greedily, so loading an entity will load its related data in one big SELECT. Entity collections should be used with care, since accessing a sub-entity of an item in the collection in a loop may trigger an extra SELECT for each item in the collection.

You can use an entity's properties without worrying about the relationship details in the database. The `PostalAddress` is related to the `Contact` through an `owner_id` and `atype_idx` field, but these details are hidden by the entity:

```csharp
using SuperOffice;
using SuperOffice.CRM.Entities;
using(SoSession mySession = SoSession.Authenticate("SAL0", ""))
{
  //Get a contact through Idx class
  Contact theContact = Contact.GetFromIdxContactId(1234);

  //Access the Name property
  string name = theContact.Name;

  //Update the postal address
  theContact.PostalAddress.City = "Oslo";

  // Saves the address row
  theContact.Save();
}
```

This is the NetServer Entities layer, which uses Entities to represent business objects to the user of NetServer. All Entities are provided under the `SuperOffice.CRM.Entities namespace`.

Entities consist of properties, which can be of basic data types such as `String`, `Double`, and `Int` and of complex types specific to SuperOffice such `Entities`, `Entity Collections`, `Row`, and `Rows`.

Each Entity has its relevant Entity Collection. For example, the Appointment Entity has simple properties like ColorIndex and EndDate. It also has complex properties like Contact (a Contact Entity) and AppointmentText (a TextRow object).

We have divided the properties of an Entity as Basic properties, Entity properties, Row properties, EntityCollection properties and Rows properties.

We show how to perform CRUD operation on an Entity and its properties in multiple ways, but the result will be the same.

## Why use an Entity

Entities such as Contact, Person, and Sale represent business objects. The main advantage of this is that it will help you to convert a business scenario to an IT solution. Further, Entities consist of data collected from multiple tables with the appropriate relationship created, whereas in Row type it consists of data only single table, which would make it difficult for you when developing application solutions. These are some of the considerations to be noted when selecting to use Entities.

## Entity types

Following is a list of the existing entities and their relevant Collection Entities.

| Entity | Collection |
|---|---|
| Appointment | AppointmentCollection |
| Contact | ContactCollection |
| Document | DocumentCollection |
| Person | PersonCollection |
| Project | ProjectCollection |
| ProjectMember | ProjectMemberCollection |
| Sale | SaleCollection |
| Selection | SelectionCollection |

## Basic CRUD operations

To **create** a basic Entity, you have to use the `CreateNew` method of the `Entity` class (that you are going to create). Then you will want to populate its properties with data.

**Retrieving** data from a particular Entity in the database is done either by using the `GetFromIdx` class or the `CustomSearch`.

When data is retrieved through an Entity, it is temporarily stored (**cashed**) in the instance. This instance can be used to make changes to the data, but the database is not affected until those changes are **updated** using the `Save()` method.

<!-- Referenced links -->

<!-- Referenced images -->
[img4]: media/persontableinfo.gif
