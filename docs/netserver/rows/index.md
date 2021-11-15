---
title: rows
description: SuperOffice database Rows layer
author: {github-id}
keywords:
---

# Rows

## High-Level Database Layer (Rows)

HDB rows are very similar to that of ADO.NET DataTable and DataRow objects. The NetServer DataTable equivalent is a rows collection, such as PersonRows, whereas the DataRow equivalent is a single row object, such as PersonRow.

Rows can represent one or more rows from a database table. Additionally, for every table in a SuperOffice database, there is a corresponding Row and Rows object.

Unlike entity models, where an entity property may contain data fetched from other tables, Row types only contain foriegn key ID values that point to the data details in another table.

Each row contains a TableInfo property. TableInfo types are a schema type that contains all of the information pertaining to the schema of the table field layout.

The TableInfo property contains properties for the table name and definition, the database name, and a useful method to lookup fields by field name, called FindField. The TableInfo object is similar to an ADO.NET DataTable.Columns property, in that it exposes all of the columns as FieldInfo objects through the TableInfo.All property. TableInfo.All returns an array of FieldInfo objects, one for each column in the table. For example, with the PersonRow object, the PersonRow.TableInfo.All property details all of the columns available in the Person table. The result of running the following code would write out all 42 column names to the debug window. With each FieldInfo object, there are properties for the fields data type, the parent table, and many useful Argument methods, such as Between, GreaterThan, LessThan, and Like, to test the value of the field in the current row.

**Accesssing all columns of a PersonRow object:**

```csharp
PersonRow person = new PersonRow.IdxPersonId(7);
FieldInfo [] fields = person.TableInfo.All;

foreach (FieldInfo fld in fields)
{
    Debug.WriteLine(fld.Name);
}
```

In contrast to the limited number of inner index fetcher classes for a single Row object, the Rows object expose many Idx fields to conduct useful queries.

**Code demonstrating available inner index classes of the PersonRows class:**

![x][img5]

Below, we see again how easy it is to use the inner index classes as fetcher objects. The code demonstrates how to use the inner IdxContactId class to establish the criteria for the records returned in the result set. In this example, we see that passing in a value of 3 will limit the number of PersonRow objects in the PersonRows object to only the records in the database where the contact_id field is the value 3.

**How the inner index class IdxContactId fetches a collection of PersonRow, PersonRows:**

```csharp
PersonRows people = new PersonRows.IdxContactId(3);

foreach (PersonRow personRow in people)

{
    Debug.Assert(personRow.ContactId == 3);
}
```

As seen in Entities, each inner Idx fetcher class has a cooresponding static helper method, i.e. PersonRows.GetFromIdxName.

### Custom Search Queries

Both entity and row types contain an inner class called CustomSearch. CustomSearch queries allow you to go above and beyond that of index queries, as seen in Figures One and Two. NetServer provides the ability to append additional criteria to a given object or collection search by setting the Restriction property. Even greater query capability is available by including other TableInfo objects for join selections on the JoinRestriction property.

For example, Figure Four demonstrates a simple custom search. The results of the custom search are predicable; the people object will be a PersonCollection containing all of the people in the Person table. This means that for each row in the Person table, there will be one Person in the PersonCollection.

**Simple Custom Search:**

```csharp
PersonCollection.CustomSearch peopleSearch = new PersonCollection.CustomSearch();
PersonCollection people = peopleSearch.ToPersonCollection();
```

What if you wanted to see all Person entities who were born after January 1, 1970. The following code demonstrates a custom search to implement such a query.

**Custom search to return all person rows with a birthday greater than January 1, 1970:**

```csharp
PersonCollection.CustomSearch peopleSearch = new PersonCollection.CustomSearch();
peopleSearch.Restriction = peopleSearch.TableInfo.DayOfBirth.GreaterThan(S.Parameter(newDateTime(1970, 1, 1)));
PersonCollection people = peopleSearch.ToPersonCollection();
```

Notice that the Restriction property accepts an Argument object as a type. Ok, so this is not explicitly shown by looking at the above code, but that is what implicitly gets set in the Restriction. Encapsulated in the architecture, Restriction inherits from the type QueryElement, as does Argument. Other types, such as GreaterThan, LessThan, Equal, Like, ultimately end up inheriting from QueryElement. Internally, custom search functionality is handled using the Visitor pattern, but that is far beyond the scope of this article and will not be discussed here. Luckily, we as developers using NetServer do not need to know exactly how this is implemented. All we need to know is that, in order for us to define our desired results, all we need to do is stick to using the properties exposed by the custom search object TableInfo property to establish criteria.

Lets take the custom search one step further and set the criteria to return only the people from the contact with a contact_id value of 3, and those who were born after January 1, 1970.

**Custom search for people who are a member of a Contact where contact_id is 3, and those who were born after January 1, 1970:**

```csharp
PersonCollection.CustomSearch peopleSearch = new PersonCollection.CustomSearch();

peopleSearch.Restriction =
                    peopleSearch.TableInfo.ContactId.Equal(S.Parameter(3)).And(
                    peopleSearch.TableInfo.DayOfBirth.GreaterThan(S.Parameter(newDateTime(1970, 1, 1))));

PersonCollection people = peopleSearch.ToPersonCollection();
```

Notice how the Argument can contain more than one type of Argument to send to the underlying query. In this case, it leverages the Restriction And method to append a new Argument to the search query. Restriction also contains an Or method, to append OR statements to the query criteria.

## Rows

Rows are simple, straightforward persistence objects. Each table in the database has a corresponding Row object and Rows collection.

The row objects **do not contain any business logic**, so here you need to maintain the relationship between rows yourself.

You can use row objects to read and update the database. Each row object supports queries and `Save` and `Delete` methods.

```csharp
using SuperOffice.CRM.Rows;
using SuperOffice;
using(SoSession mySession = SoSession.Authenticate("SAL0", ""))
{
  //retrieve the contact row that we want to change
  ContactRow theContact = ContactRow.GetFromIdxContactId(1234);

  //get the name
  String name = theContact.Name;

  //retrieve the address of the contact using the address type
  // and the contact ID
  AddressRow theAddressRow = AddressRow.GetFromIdxAtypeIdxOwnerId(
      SuperOffice.Data.AddressType.ContactPostalAddress, 1234);

  //change the address
  theAddressRow.City = "Oslo";

  //save the changed address row
  theAddressRow.Save();
}
```

The Address row will have the `owner_id` field set to 1234, and the `atypeidx` field set to 1 (postal address for contact).

All Rows are provided under the `SuperOffice.CRM.Rows` namespace.

A Row represents a row in a table of the database. Rows can contain and expose properties of basic data types only (String, Double, Int, and so on).

## Basic CRUD operations

To **create** a basic Row, you have to use the `CreateNew` method of the `Row` class (that you are going to create). Then you will want to populate its properties with data.

**Retrieving** data from a particular row of a table in the database can easily be done via Rows. Either by using the `Idx` class or the `CustomSearch`.

When data is retrieved through a Row, it is temporarily stored (**cashed**) in the instance. This instance can be used to make changes to the data, but the database is not affected until those changes are **updated** using the `Save()` method.

By using the `Delete()` method, we can delete a Row as well. In this case, it will **delete an entire row** from the database.

## Working with Rows through Entities

An Entity may have properties that are of the type Row. A property of row type directly refers to a particular row of a table.

For example, in the `Sale` Entity, the `Associate` property would refer to the `Associate` table and would contain the columns that are in the `Associate` table as its properties.

## Examples

* [Add list item using rows][1]

<!-- Referenced links -->
[1]: ../lists/row/add-list-item.md

<!-- Referenced images -->
[img5]: media/personrowsobject.gif
