# Persons

**NOTE: persons with the user_type "SYSTEM" can only be fetched and not created or updated. These are used internal in Forecast for things like integrations.**

## Get persons

* `GET /persons` - Returns all persons.

| Response fields | Description/format                                                                     |
| --------------- | -------------------------------------------------------------------------------------- |
| id              | Integer                                                                                |
| first_name      | String                                                                                 |
| last_name       | String                                                                                 |
| email           | String                                                                                 |
| user_type       | String {"SYSTEM", "VIRTUAL", "CLIENT", "COLLABORATOR", "MANAGER","CONTROLLER","ADMIN"} |
| client_id       | Integer, ID of client                                                                  |
| monday          | Integer, working hours in minutes                                                      |
| tuesday         | Integer, working hours in minutes                                                      |
| wednesday       | Integer, working hours in minutes                                                      |
| thursday        | Integer, working hours in minutes                                                      |
| friday          | Integer, working hours in minutes                                                      |
| saturday        | Integer, working hours in minutes                                                      |
| sunday          | Integer, working hours in minutes                                                      |
| active          | Boolean                                                                                |
| default_role    | Integer, ID of default role                                                            |
| cost            | Decimal                                                                                |
| created_by      | Integer, ID of person                                                                  |
| updated_by      | Integer, ID of person                                                                  |
| created_at      | Date                                                                                   |
| updated_at      | Date                                                                                   |

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
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z"
   }, ...
]
```

## Get person

* `GET /persons/{personId}` - Returns a specific person.

| Response fields | Description/format                                                                     |
| --------------- | -------------------------------------------------------------------------------------- |
| id              | Integer                                                                                |
| first_name      | String                                                                                 |
| last_name       | String                                                                                 |
| email           | String                                                                                 |
| user_type       | String {"SYSTEM", "VIRTUAL", "CLIENT", "COLLABORATOR", "MANAGER","CONTROLLER","ADMIN"} |
| client_id       | Integer, ID of client                                                                  |
| monday          | Integer                                                                                |
| tuesday         | Integer                                                                                |
| wednesday       | Integer                                                                                |
| thursday        | Integer                                                                                |
| friday          | Integer                                                                                |
| saturday        | Integer                                                                                |
| sunday          | Integer                                                                                |
| active          | Boolean                                                                                |
| default_role    | JSON (Role)                                                                            |
| cost            | Decimal                                                                                |
| created_by      | Integer, ID of person                                                                  |
| updated_by      | Integer, ID of person                                                                  |
| created_at      | Date                                                                                   |
| updated_at      | Date                                                                                   |

### Sample JSON response

```javascript
{
   "id":1,
   "first_name":"John",
   "last_name":"Smith",
   "email":"js@domain.com",
   "user_type":"ADMIN",
   "client_id": null,
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
   "created_by":1,
   "updated_by":1,
   "created_at":"2017-01-14T18:46:56Z",
   "updated_at":"2017-01-14T18:47:58Z"
}
```

## Create person

* `POST /persons` - Creates a new person. Returns the same object as getting a single person.

| Request fields | Description/format                                                                        |
| -------------- | ----------------------------------------------------------------------------------------- |
| first_name     | String                                                                                    |
| last_name      | String                                                                                    |
| email          | String                                                                                    |
| user_type      | (Required\*) String {"VIRTUAL", "CLIENT", "COLLABORATOR", "MANAGER","CONTROLLER","ADMIN"} |
| client_id      | Integer, ID of client                                                                     |
| monday         | Integer, if not set, taken from company                                                   |
| tuesday        | Integer, if not set, taken from company                                                   |
| wednesday      | Integer, if not set, taken from company                                                   |
| thursday       | Integer, if not set, taken from company                                                   |
| friday         | Integer, if not set, taken from company                                                   |
| saturday       | Integer, if not set, taken from company                                                   |
| sunday         | Integer, if not set, taken from company                                                   |
| default_role   | Integer, id of the default role                                                           |
| cost           | Decimal                                                                                   |

\* Person with client_id can only be "VIRTUAL" or "CLIENT" user_type. Person without client_id cannot have "CLIENT" user_type

### Sample JSON request

POST https://api.forecast.it/api/v1/persons

```javascript
{
   "first_name":"John",
   "last_name":"Smith",
   "email":"js@domain.com",
   "user_type":"ADMIN",
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

* `PUT /persons/{personId}` - Updates a person. Returns the same object as getting a single person.

| Request fields | Description/format                                                             |
| -------------- | ------------------------------------------------------------------------------ |
| first_name     | String                                                                         |
| last_name      | String                                                                         |
| email          | String                                                                         |
| user_type      | String\* {"VIRTUAL", "CLIENT", "COLLABORATOR", "MANAGER","CONTROLLER","ADMIN"} |
| monday         | Integer                                                                        |
| tuesday        | Integer                                                                        |
| wednesday      | Integer                                                                        |
| thursday       | Integer                                                                        |
| friday         | Integer                                                                        |
| saturday       | Integer                                                                        |
| sunday         | Integer                                                                        |
| active         | Boolean\*                                                                      |
| default_role   | Integer, id of the default role                                                |
| cost           | Decimal                                                                        |

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

* `DELETE /persons/{personId}` - Deletes a person.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/persons/1
