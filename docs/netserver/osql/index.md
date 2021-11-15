---
title: osql
description: SuperOffice Objectified SQL
author: {github-id}
so.date: 11.05.2016
keywords: data-access
---

# SuperOffice Objectified SQL

OSQL is the lowest layer of the NetServer API that provides a programmatic query language for reading and writing data to and from a SuperOffice database. It’s the objectified equivalent to writing database Structured Query Language (SQL) and is the most performing of all NetServer API layers. You can think of it as the SuperOffice Database Interface (SODBIF).

OSQL is the lowest-level API. This is a database-independent SQL that is compile-time checked (unlike SQL strings which are checked at run-time). Objectified SQL (OSQL) lets you build your own queries and SQL commands, without worrying about Oracle’s peculiarities.

Another advantage is that the OSQL layer automatically adds transaction logging, computed fields updating, and security to your queries so that you don’t have to worry about these tedious details.

**Transactionlogging** means that every time you update a field, you don’t have to manually add a new row to the `traveltransactionlog` table yourself.

Computed fields are fields like the soundex fields or the last-updated-date fields. The OSQL system handles these for you.

Security means that the OSQL system will not return hidden or private data to users who are not authorized to see it. It will also prevent updates to rows that are supposed to be locked for the user. This makes working with SuperOffice data much easier.

The security system works by rewriting your query behind the scenes – so a simple query across the document table will join in the appointment and visiblefor tables. The security system needs data from these tables to work out if you can see each record or not.

```csharp
using SuperOffice.CRM.Data;
using SuperOffice.Data.SQL;
using SuperOffice.Data;
using SuperOffice;
using(SoSession mySession = SoSession.Authenticate("SAL0", ""))
{
  //retrieve the table info
  ContactTableInfo c = TablesInfo.GetContactTableInfo();

  //Creating an Instance of the Update Class of the person table
  Select contactQuery = S.NewSelect();
  contactQuery.ReturnFields.Add( c.ContactId, c.Name, c.Department );
  contactQuery.Restriction = c.ContactId.Equal( S.Parameter(1234) );

  using( QueryExecutionHelper qeh = new QueryExecutionHelper(contactQuery) )
  {
    while( qeh.Reader.Read() )
    {
      string name = qeh.Reader.GetString( c.Name );
    }
  }
}
```

The `ContactTableInfo` object represents an alias to a table in the database.

It exposes properties that represent the fields in the table, as well as dictionary information about the table (like its name, table-number in the dictionary). Each field also contains dictionary information (like the field type, size, name).

The fields support composition using SQL-like methods: `c.ContactId.Equal( S.Parameter(1234) )` or `c.Name.Like( S.Parameter( "SuperOffice%") )`

SuperOffice introduces its own language to write queries so that it is independent of the underlying database. Therefore with the use of SuperOffice Objectified SQL (OSQL), you can write queries without worrying about the database anymore.

NetServer exposes many layers of its API to do the same functionality. OSQL is the lowest layer of the NetServer API that provides a programmatic query language for reading and writing data to and from a SuperOffice database. It’s the objectified equivalent to writing database Structured Query Language (SQL) and is the most performing of all NetServer API layers. You can think of it as the SuperOffice Database Interface (SODBIF).

![x][img1]

In the [syntax][1] section, we will be comparing SuperOffice Objectified SQL with SQL while explaining how SuperOffice Objectified SQL is used.

## Target audience

Those who have previously worked with T-SQL, Stored Procedures, and those who don't find it intimidating to get close to the database, would enjoy using OSQL rather than using Service, Row, and Entities. However, there are many things to consider, and be aware of, when you are getting closer to the core since there’s a whole number of different ways that you may be trapped or buried when creating your own inserts, updates, and deletes outside of the business objects within the NetServer.

The advantage is that when using the OSQL to create code, the code would be more responsive and efficient than when using the Services, RDB, or the HDB layers.

## Why use OSQL?

Any calls that are made through the higher layers of the architecture would go through the OSQL layer. Therefore, anything that can be done through the Service, RDB, and HDB layer can also be done through this layer. The examples aim to show how you could achieve the same results as achieved through the higher layer of NetServer.

One of the main advantages compared to the HDB layer is that when using the HDB layer, you would have to use several different HDB rows for most of the results whereas when using OSQL you may create your own customized rows.

A better way of getting the required information with the least amount of calls to the database is to construct a SELECT statement using OSQL.

For us to use OSQL, the following three namespaces are necessary.

* SuperOffice.CRM.Data
* SuperOffice.Data
* SuperOffice.Data.SQL

Additional namespaces may be required based on your requirements.

<!-- Referenced links -->
[1]: and-clause.md

<!-- Referenced images -->
[img1]: media/intro-osql2.png
