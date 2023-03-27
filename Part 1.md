# API Description

This is a sample Manitoba Bus Service Server based on the OpenAPI 3.0 specification. This server offers a free API that provides bus and bus stop schedules in Manitoba for a given day. The API has endpoints that list bus schedules and bus stop locations and schedules based on the parameters provided.

# Endpoint with Parameters

- /bus (GET the list of existing busses as an array)
	- /{bus id}/{date} (added parameters to GET the schedule of the bus on the specified date, date as DDMMYYYY format)
- /stop (GET the list of existing bus stops as an array)
	- /{bus stop id}/{date} (addaed parameters to GET the bus stop schedule on the specified date, date as DDMMYYYY format)

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

# Sample Request
* To get the list of existing bus stops, send a GET request to:
```
GET /stop
```
#### If the request is successful, the API will return a JSON object with an array of bus stops. For example:
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

* To get the schedule for bus stop with id "1234" on March 27th, 2023, send a GET request to:
```
GET /stop/1234/27032023
```
#### If the request is successful, the API will return a JSON object with the bus stop schedule for the specified date
```json

{
    "stop_id": "1234",
    "date": "27032023",
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
