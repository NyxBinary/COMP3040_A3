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