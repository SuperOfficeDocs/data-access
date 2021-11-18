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

This method takes an appointment entity as parameter, so this needs to be in the POST body.

The result of the service call is returned as JSON.
