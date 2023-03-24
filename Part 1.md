# API Description


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
			"description": "Information regarding bus schedules in Winnipeg."
		},
		{
			"name": "stop",
			"description": "Information regarding bus stop schedules in Winnipeg."
		}
	]
}
```

# Sample Request