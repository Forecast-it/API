# Persons

**NOTE: persons with the user_type "SYSTEM" can only be fetched and not created or updated. These are used internal in Forecast for things like integrations.**

## Get persons

-  `GET /persons` - Returns all persons.

| Response fields     | Description/format                                                                     |
| ------------------- | -------------------------------------------------------------------------------------- |
| id                  | Integer                                                                                |
| first_name          | String                                                                                 |
| last_name           | String                                                                                 |
| email               | String                                                                                 |
| user_type           | String {"SYSTEM", "VIRTUAL", "CLIENT", "COLLABORATOR", "MANAGER","CONTROLLER","ADMIN"} |
| client_id           | Integer, ID of client                                                                  |
| holiday_calendar_id | Integer, ID of holiday calendar                                                        |
| monday              | Integer, working hours in minutes                                                      |
| tuesday             | Integer, working hours in minutes                                                      |
| wednesday           | Integer, working hours in minutes                                                      |
| thursday            | Integer, working hours in minutes                                                      |
| friday              | Integer, working hours in minutes                                                      |
| saturday            | Integer, working hours in minutes                                                      |
| sunday              | Integer, working hours in minutes                                                      |
| active              | Boolean                                                                                |
| default_role        | Integer, ID of default role                                                            |
| cost                | Decimal, cost from the current cost period                                             |
| language            | String {"SPANISH", "DANISH", "FRENCH", "ENGLISH_EU", "ENGLISH_UK", "ENGLISH_US"}       |
| created_by          | Integer, ID of person                                                                  |
| updated_by          | Integer, ID of person                                                                  |
| created_at          | Date                                                                                   |
| updated_at          | Date                                                                                   |

### Sample JSON response

```javascript
[
   {
      "id":1,
      "first_name":"John",
      "last_name":"Smith",
      "email":"js@domain.com",
      "user_type":"ADMIN",
      "client_id": null,
      "holiday_calendar_id": 1,
      "monday":480,
      "tuesday":480,
      "wednesday":480,
      "thursday":480,
      "friday":480,
      "saturday":0,
      "sunday":0,
      "active":true,
      "default_role":29,
      "cost":100,
      "language":"DANISH",
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z"
   }, ...
]
```

## Get person

-  `GET /persons/{personId}` - Returns a specific person.

| Response fields     | Description/format                                                                     |
| ------------------- | -------------------------------------------------------------------------------------- |
| id                  | Integer                                                                                |
| first_name          | String                                                                                 |
| last_name           | String                                                                                 |
| email               | String                                                                                 |
| user_type           | String {"SYSTEM", "VIRTUAL", "CLIENT", "COLLABORATOR", "MANAGER","CONTROLLER","ADMIN"} |
| client_id           | Integer, ID of client                                                                  |
| holiday_calendar_id | Integer, ID of holiday calendar                                                        |
| monday              | Integer                                                                                |
| tuesday             | Integer                                                                                |
| wednesday           | Integer                                                                                |
| thursday            | Integer                                                                                |
| friday              | Integer                                                                                |
| saturday            | Integer                                                                                |
| sunday              | Integer                                                                                |
| active              | Boolean                                                                                |
| default_role        | JSON (Role)                                                                            |
| cost                | Decimal, cost from the current cost period                                             |
| language            | String {"SPANISH", "DANISH", "FRENCH", "ENGLISH_EU", "ENGLISH_UK", "ENGLISH_US"}       |
| created_by          | Integer, ID of person                                                                  |
| updated_by          | Integer, ID of person                                                                  |
| created_at          | Date                                                                                   |
| updated_at          | Date                                                                                   |

### Sample JSON response

```javascript
{
   "id":1,
   "first_name":"John",
   "last_name":"Smith",
   "email":"js@domain.com",
   "user_type":"ADMIN",
   "client_id": null,
   "holiday_calendar_id": 1,
   "monday":480,
   "tuesday":480,
   "wednesday":480,
   "thursday":480,
   "friday":480,
   "saturday":0,
   "sunday":0,
   "active":true,
   "default_role": {...},
   "cost":100,
   "language":"DANISH",
   "created_by":1,
   "updated_by":1,
   "created_at":"2017-01-14T18:46:56Z",
   "updated_at":"2017-01-14T18:47:58Z"
}
```

## Get person projects

-  `GET /persons/{personId}/projects` - Returns a specific person's projects.

| Response fields              | Description/format                             |
| ---------------------------- | ---------------------------------------------- |
| id                           | Integer                                        |
| company_project_id           | Integer                                        |
| name                         | String                                         |
| connected_project            | Integer, ID of connected project               |
| stage                        | String (PLANNING, RUNNING, HALTED, DONE)       |
| status_color                 | String (GREEN, YELLOW, RED)                    |
| status_description           | String                                         |
| description                  | String                                         |
| color                        | String                                         |
| estimation_units             | String (HOURS, POINTS)                         |
| minutes_per_estimation_point | Integer                                        |
| budget                       | Double                                         |
| billable                     | Boolean                                        |
| use_sprints                  | Boolean                                        |
| sprint_length                | Integer                                        |
| start_date                   | Date                                           |
| end_date                     | Date                                           |
| card_levels                  | Integer, deprecated. Use 'task_levels' instead |
| task_levels                  | Integer (1 or 2)                               |
| client                       | Integer, ID of client                          |
| rate_card                    | Integer, ID of rate card                       |
| remaining_auto_calculated    | Boolean                                        |
| use_project_allocations      | Boolean                                        |
| labels                       | List<Integer>, List ID of labels               |
| external_refs                | List of references to other systems            |
| created_by                   | Integer, ID of person                          |
| updated_by                   | Integer, ID of person                          |
| created_at                   | Date                                           |
| updated_at                   | Date                                           |

### Sample JSON response

```javascript
[
   {
      "id":1,
      "company_project_id":1,
      "name":"Website project",
      "stage":"PLANNING",
      "status": "GREEN",
      "status_description": "",
      "description": "",
      "color": "#FF7C75",
      "estimation_units": "HOURS",
      "minutes_per_estimation_point": 480,
      "holiday_calendar_id": 1,
      "budget": 1234.56,
      "billable": true,
      "use_sprints": true,
      "sprint_length": 14,
      "start_date": "2017-01-01",
      "end_date": "2018-01-01",
      "task_levels": 1,
      "client": 1,
      "rate_card": 1,
      "remaining_auto_calculated": false,
      "use_project_allocations": true,
      "labels": [1,2],
      "external_refs": [],
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z"
   }, ...
```

## Create person

-  `POST /persons` - Creates a new person. Returns the same object as getting a single person.

| Request fields      | Description/format                                                                        |
| ------------------- | ----------------------------------------------------------------------------------------- |
| first_name          | String                                                                                    |
| last_name           | String                                                                                    |
| email               | String                                                                                    |
| user_type           | (Required\*) String {"VIRTUAL", "CLIENT", "COLLABORATOR", "MANAGER","CONTROLLER","ADMIN"} |
| client_id           | Integer, ID of client                                                                     |
| holiday_calendar_id | Integer, ID of holiday calendar                                                           |
| monday              | Integer, if not set, taken from company                                                   |
| tuesday             | Integer, if not set, taken from company                                                   |
| wednesday           | Integer, if not set, taken from company                                                   |
| thursday            | Integer, if not set, taken from company                                                   |
| friday              | Integer, if not set, taken from company                                                   |
| saturday            | Integer, if not set, taken from company                                                   |
| sunday              | Integer, if not set, taken from company                                                   |
| default_role        | Integer, id of the default role                                                           |
| cost                | Decimal, cost to be used in the current cost period                                       |
| language            | String {"SPANISH", "DANISH", "FRENCH", "ENGLISH_EU", "ENGLISH_UK", "ENGLISH_US"}          |

\* Person with client_id can only be "VIRTUAL" or "CLIENT" user_type. Person without client_id cannot have "CLIENT" user_type

### Sample JSON request

POST https://api.forecast.it/api/v1/persons

```javascript
{
   "first_name":"John",
   "last_name":"Smith",
   "email":"js@domain.com",
   "user_type":"ADMIN",
   "holiday_calendar_id": 1,
   "monday":480,
   "tuesday":480,
   "wednesday":480,
   "thursday":480,
   "friday":480,
   "saturday":0,
   "sunday":0,
   "default_role":4,
   "cost":100,
}
```

## Update person

-  `PUT /persons/{personId}` - Updates a person. Returns the same object as getting a single person.

| Request fields      | Description/format                                                               |
| ------------------- | -------------------------------------------------------------------------------- |
| first_name          | String                                                                           |
| last_name           | String                                                                           |
| email               | String                                                                           |
| user_type           | String\* {"VIRTUAL", "CLIENT", "COLLABORATOR", "MANAGER","CONTROLLER","ADMIN"}   |
| holiday_calendar_id | Integer, ID of holiday calendar                                                  |
| monday              | Integer                                                                          |
| tuesday             | Integer                                                                          |
| wednesday           | Integer                                                                          |
| thursday            | Integer                                                                          |
| friday              | Integer                                                                          |
| saturday            | Integer                                                                          |
| sunday              | Integer                                                                          |
| active              | Boolean\*                                                                        |
| default_role        | Integer, id of the default role                                                  |
| cost                | Decimal, cost to be used in the current cost period                              |
| language            | String {"SPANISH", "DANISH", "FRENCH", "ENGLISH_EU", "ENGLISH_UK", "ENGLISH_US"} |

\* Person with client_id can only be "VIRTUAL" or "CLIENT" user_type and cannot have active equal to false. Person without client_id cannot have "CLIENT" user_type

### Sample JSON request

PUT https://api.forecast.it/api/v1/persons/1

```javascript
{
   "first_name":"John",
   "last_name":"Doe"
}
```

## Delete person\*

\* Only person with client_id not equal to null can be deleted

-  `DELETE /persons/{personId}` - Deletes a person.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/persons/1

## Get person timer information

-  `GET /persons/{personId}/timer` - Returns a specific persons timer information.

| Response fields | Description/format                                   |
| --------------- | ---------------------------------------------------- |
| start_time      | Date                                                 |
| card            | Integer, deprecated. Use 'task' instead              |
| task            | Integer, id of the task that the timer is started on |

### Sample JSON response

```javascript
{
   "start_time":"2018-01-14T18:46:56Z",
   "task":1
}
```

## Start person timer

-  `PUT /persons/{personId}/timer/start` - Start the timer on a person. Returns the same object as getting a single persons timer.

| Request fields | Description/format                                                                                     |
| -------------- | ------------------------------------------------------------------------------------------------------ |
| card           | Integer, deprecated. Use 'task' instead                                                                |
| task           | Integer, id of the task to start the timer on. This is optional and can be set when stopping the timer |

### Sample JSON request

PUT https://api.forecast.it/api/v1/persons/1/timer/start

```javascript
{
   "task":1
}
```

## Stop person timer

-  `PUT /persons/{personId}/timer/stop` - Stop the timer on a person.

| Request fields | Description/format                                 |
| -------------- | -------------------------------------------------- |
| card           | Integer, deprecated. Use 'task' instead            |
| task           | Integer, id of the task to register the time on    |
| project        | Integer, id of the project to register the time on |

-  Either a task or project must be set here. If the task was set when starting the timer, this can be omitted.

### Sample JSON request

PUT https://api.forecast.it/api/v1/persons/1/timer/stop

```javascript
{
   "task":1
}
```

## Reset person timer

-  `DELETE /persons/{personId}/timer` - Resets a persons timer.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/persons/1/timer
