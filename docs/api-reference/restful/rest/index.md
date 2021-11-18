# SuperOffice REST API v1

Welcome to the SuperOffice WebAPI.

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
