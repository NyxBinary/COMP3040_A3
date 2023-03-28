# API Description

This is an example Manitoba Bus Service API formatted for OpenAPI 3.0. This service offers an API that provides bus and bus stop schedules in Manitoba for a given day, free of charge. This API has endpoints that list bus schedules, in addition to bus stop locations and associated schedules based on the parameters provided.

# Endpoint with Parameters

- /bus (GET the list of existing busses as an array)
	- /{bus id}/{date} (added parameters to GET the schedule of the bus on the specified date, date as DD-MM-YYYY format)
- /stop (GET the list of existing bus stops as an array)
	- /{bus stop id}/{date} (addaed parameters to GET the bus stop schedule on the specified date, date as DD-MM-YYYY format)

# Description of Resources

```json
{
	resources: [
		{
			"name": "bus",
			"description": "Information regarding bus schedules in Manitoba."
		},
		{
			"name": "stop",
			"description": "Information regarding bus stop schedules in Manitoba."
		}
	]
}
```

# Sample Requests

* To get the list of existing bus stops, a user can send a GET request with the following format:

```
GET /stop
```

Upon a successful request, the API will return a JSON object with an array of bus stops.

```json
{
    "stops": [
        {
            "id": "1",
            "name": "University of Manitoba Bus station",
            "description": "This is a bus stop at the University of Manitoba Fort Garry campus"
        },
        {
            "id": "2",
            "name": "Portage Ave. and Main St.",
            "description": "This is a bus stop on Portage Ave. and Main St."
        }
    ]
}
```

---

* To get the schedule for bus stop with id "1234" on March 27th, 2023, a user can send a GET request with the following format:

```
GET /stop/1234/27-03-2023
```

Upon a successful request, the API will return a JSON object with the bus stop schedule for the date specified.

```json

{
    "stop_id": "1234",
    "date": "27-03-2023",
    "schedule": [
        {
            "bus_id": "662",
            "arrival_time": "09:00",
            "departure_time": "09:01"
        },
        {
            "bus_id": "672",
            "arrival_time": "9:15",
            "departure_time": "9:16"
        },
        {
            "bus_id": "75",
            "arrival_time": "11:00",
            "departure_time": "11:01"
        }
    ]
}
```
