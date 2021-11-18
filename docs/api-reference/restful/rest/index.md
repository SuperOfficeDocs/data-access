# SuperOffice REST API v1

Welcome to the SuperOffice WebAPI.

You can get the version number and build-date from the API endpoint.

    /api

Returns a block with the supported versions, and the NetServer version number.

If you don't ask specifically, you get the HTML representation. if you ask for
Javascript then you get the following:

```javascript
    { "v1": "http://www.example.com/crm/api/v1",
      "Version": "v1",
      "NetServerVersion": "8.1.6431.038",
      "NetServerAssembly": "8.1.0.0",
      "NetServerDate": "2017-08-10",
      "NetServer": "SuperOffice NetServer 8.1 Release (Build: 6431)",
      "NetServerLabel": "9729",
      "Services": "Services83",
      "Services80": "http://www.superoffice.net/ws/crm/NetServer/Services80",
      "Services81": "http://www.superoffice.net/ws/crm/NetServer/Services81",
      "Services82": "http://www.superoffice.net/ws/crm/NetServer/Services82",
      "Services83": "http://www.superoffice.net/ws/crm/NetServer/Services83",
    }
```

If you fetch the version URL, you get back a list of supported URLs:

     /api/v1

returns an array of URLs mapped to the HTTP methods they support, along with a bit documentation:

```javascript
{
    "http://localhost/WebApi/api/v1/Agents/Relation/CreateDefaultContactRelationEntity": {
        "POST": "Set default values into a new ContactRelationEntity."
    },
    "http://localhost/WebApi/api/v1/Agents/Relation/GetContactRelationEntity": {
        "POST": "?contactRelationEntityId={contactRelationEntityId}   Gets a ContactRelationEntity object."
    },
    "http://localhost/WebApi/api/v1/Agents/Relation/SaveContactRelation": {
        "POST": "Creates a new or updates an existing contact relation."
    },
    "http://localhost/WebApi/api/v1/Agents/Relation/DeleteContactRelation": {
        "POST": "Deletes the spesified contact relation."
    },
    "http://localhost/WebApi/api/v1/List/WebPanel": {
        "GET": "Gets description of WebPanelEntity list",
        "PUT": "Save the description of WebPanelEntity list"
    },
    "http://localhost/WebApi/api/v1/List/WebPanel/Items": {
        "GET": "Gets a list of all WebPanelEntity list items.",
        "POST": "Create a new WebPanelEntity list item"
    },
    "http://localhost/WebApi/api/v1/List/WebPanel/Items/{id}": {
        "GET": "Gets a WebPanelEntity list item.",
        "PUT": "Updates the existing WebPanelEntity",
        "DELETE": "Marks the existing WebPanelEntity as deleted."
    },
 	....
```

You can use this information to determine if the server supports the features you need.

## Building Blocks

The SuperOffice WebAPI has two major parts:

* **REST API** - URLs describe entities like person or sale.
* **Agents API** - the services API, accessible via HTTP.

## REST API

The REST API exposes objects as entities that can be retrieved using HTTP GET,
modified using HTTP PUT, created using HTTP POST, and deleted using HTTP DELETE.

### REST API - Entities

The REST API has the major entities (Company, Person, Project, Sale, etc) exposed.

    /api/v1/Contact
    /api/v1/Person
    /api/v1/Project
    /api/v1/Sale
    ...

The entities all have similar structures

    /api/v1/Contact

returns an ODATA feed of contact records. You can select fields,
order, filter the result using ODATA operations.

    /api/v1/Contact?$select=name,category&$filter=registeredDate before '2009-1-1'

This returns the contact id, name and category for contacts created before 2009.

    /api/v1/Contact/default

Returns a new blank entity.

    /api/v1/Contact/123

Returns the Contact with id 123.
This object can be PUT or DELETE - subject to the usual sentry restrictions. 
If your role does not allow you to update, then the web api won't give
you more access.

    /api/v1/Contact/123/Simple

Returns a simplified version of the entity. This cannot be updated or deleted, 
but it can be easier to work with - it does not have deeply nested structures, 
and does not support things like user defined fields.

Most of the entities have user defined fields, and expose information about the
layout here:

    /api/v1/Contact/UdefLayout

The actual user-defined field values are returned in the entity's **UserDefinedFields** property.

Many have related lists of other entities as well:
    
    /api/v1/Contact/123/Projects
    /api/v1/Contact/123/Sales

These lists are archives that you can filter and sort using OData operations.

### REST API - Lists

SuperOffice has a number of built-in lists (Category, Business, Position, etc).
You can add your own custom lists.

    /api/v1/List

Returns a list of lists.

    /api/v1/List/Category
    /api/v1/List/Business
    /api/v1/List/YourOwnList

These return meta-data about the list, including the list id.

    /api/v1/List/Category/Items
    /api/v1/List/Business/Items
    /api/v1/List/YourOwnList/Items

These return the list items in the given list. 

    /api/v1/MDOList

Gives you read access to hierarchical lists, and other list providers
in the system.

### REST API - Archives etc

**Archives**

    /api/v1/Archive/OwnerContacts?$select=contactId,name,orgnr
    /api/v1/Archive/EmailAddress?$select=fullName,emailAddress&$filter=contactId=12

The archive provider system is exposed as an OData endpoint. 

**User Preferences**

    /api/v1/Preference/section/keyname
    /api/v1/PreferenceDescription/section/keyname

User preferences and pref.descriptions can be read and updated.

**Foreign Keys**

    /api/v1/ForeignApp/Glops/Foobar/Key/Lookup/Contact/123

Returns the key called 'Lookup' from the foreign app 'Glops' for the 
Contact record 123.

**Strings**

    /api/v1/String/SR_YES?isoLangCode=sv

Built-in string resources can be read in supported languages.

### REST API - System

     /api/v1/User/Tony
     /api/v1/Role/12
     /api/v1/License/SuperOffice

Users, Roles, License stuff is exposed via simple endpoints.
If you have admin rights in your role, you can POST or PUT to update
system information.

## Agent API

The agents expose the latest Services agents and functions.

    /api/v1/Agents/Appointment/CalculateDays

GET this to get a description of the call. 
The method is not invoked using GET, even if the method is called **GetAppointment**.
To actually invoke the method, you need to POST to the endpoint:

    POST /api/v1/Agents/Appointment/CalculateDays
    { "Contact": { "ContactId": 123 },
      "AppointmentId": 1234,
      "Description": "string",
      "StartDate": "2017-06-06T13:02:55Z",
      "EndDate": "2017-06-06T13:02:55Z"
    }

This method takes an appointment entity as parameter, so this needs to 
be in the POST body.

The result of the service call is returned as JSON.

## Errors

Errors are returned using HTTP error codes, and as a JSON object:

    /api/v1/Contact/99999

Returns HTTP 404 Contact Not Found, and the following JSON result

```javascript
{
  "Error": true,
  "ErrorType": "SoNotFoundException",
  "ErrorMessage": "Contact id 99999 not found",
  "ErrorSource": "SuperOffice.Services.Implementation"
}
```
