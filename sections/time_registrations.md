# Time registrations

## Get time registrations

- `GET v3/time_registrations` - Returns all time registrations. (DEPRECATED - please see the v4 endpoints)
- `GET v3/time_registrations?updated_after=YYYYMMDDTHHmmss` - Returns all time registrations that have been updated after the specified time. Example value: `20200216T210047`. (DEPRECATED - please see the v4 endpoints)
- `GET v3/time_registrations?date_after=YYYYMMDD` - Returns all time registrations that have a date value after the specified date. Example value: `20200216`. (DEPRECATED - please see the v4 endpoints)

- `GET v4/time_registrations` - Returns all time registrations. Paginated.
- `GET v4/time_registrations/updated_after/YYYYMMDDTHHmmss` - Returns all time registrations that have been updated after the specified time. Example value: `20200216T210047`. Paginated.
- `GET v4/time_registrations/date_after/YYYYMMDD` - Returns all time registrations that have a date value after the specified date. Example value: `20200216`. Paginated.

| Response fields             | Description/format                                   |
| --------------------------- | ---------------------------------------------------- |
| id                          | Integer                                              |
| person                      | Integer, ID of person                                |
| project                     | Integer, ID of project                               |
| role                        | Integer, ID of role                                  |
| phase                       | Integer, ID of project **Only v4**                   |
| card                        | Integer, deprecated. Use task instead. **Only v3**   |
| task                        | Integer, ID of task                                  |
| task_project                | Integer, ID of project of task (if any). **Only v4** |
| non_project_time            | Integer, ID of non project time                      |
| time_registered             | Integer, time registered in minutes                  |
| billable_minutes_registered | Integer, billable time registered in minutes         |
| date                        | Date                                                 |
| notes                       | String                                               |
| approval_status             | String (NOT_SUBMITTED, SUBMITTED, APPROVED)          |
| invoice_entry               | Integer                                              |
| invoice                     | Integer                                              |
| created_by                  | Integer, ID of person                                |
| updated_by                  | Integer, ID of person                                |
| created_at                  | Date                                                 |
| updated_at                  | Date                                                 |

### Sample JSON response

```javascript
[
   {
      "id":1,
      "person":1,
      "project":null,
      "role": 10,
      "card":1,
      "task":1,
      "task_project":1,
      "non_project_time":null,
      "time_registered":480,
      "billable_minutes_registered":360,
      "date":"2017-01-14",
      "notes":"Did work on login page",
      "approval_status": "APPROVED",
      "invoice_entry": null,
      "invoice": 6065,
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z"
   }, ...
]
```

## Get all time registrations in a project

- `GET v3/projects/{projectId}/time_registrations` - Returns all time registrations in a project.
- `GET v3/projects/{projectId}/time_registrations?updated_after=YYYYMMDDTHHmmss` - Returns all time registrations in a project that have been updated after the specified time. Example value: `20200216T210047`.
- `GET v3/projects/{projectId}/time_registrations?date_after=YYYYMMDD` - Returns all time registrations that have a date value after the specified date. Example value: `20200216`.

| Response fields             | Description/format                           |
| --------------------------- | -------------------------------------------- |
| id                          | Integer                                      |
| person                      | Integer, ID of person                        |
| project                     | Integer, ID of project                       |
| role                        | Integer, ID of role                          |
| card                        | Integer, deprecated. Use task instead        |
| task                        | Integer, ID of task                          |
| non_project_time            | Integer, ID of non project time              |
| time_registered             | Integer, time registered in minutes          |
| billable_minutes_registered | Integer, billable time registered in minutes |
| date                        | Date                                         |
| notes                       | String                                       |
| approval_status             | String (NOT_SUBMITTED, SUBMITTED, APPROVED)  |
| created_by                  | Integer, ID of person                        |
| updated_by                  | Integer, ID of person                        |
| created_at                  | Date                                         |
| updated_at                  | Date                                         |

### Sample JSON response

```javascript
[
   {
      "id":1,
      "person":1,
      "project":1,
      "role": 10,
      "card":null,
      "task":null,
      "non_project_time":null,
      "time_registered":480,
      "billable_minutes_registered":360,
      "date":"2017-01-14",
      "notes":"Did work on login page",
      "approval_status": "APPROVED",
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z"
   }, ...
]
```

## Get all time registrations for a given person

- `GET v3/persons/{personId}/time_registrations` - Returns all time registrations for a given person.
- `GET v3/persons/{personId}/time_registrations?updated_after=YYYYMMDDTHHmmss` - Returns all time registrations for a given person that have been updated after the specified time. Example value: `20200216T210047`.
- `GET v3/persons/{personId}/time_registrations?date_after=YYYYMMDD` - Returns all time registrations that have a date value after the specified date. Example value: `20200216`.

| Response fields             | Description/format                           |
| --------------------------- | -------------------------------------------- |
| id                          | Integer                                      |
| person                      | Integer, ID of person                        |
| project                     | Integer, ID of project                       |
| role                        | Integer, ID of role                          |
| card                        | Integer, deprecated. Use task instead        |
| task                        | Integer, ID of task                          |
| non_project_time            | Integer, ID of non project time              |
| time_registered             | Integer, time registered in minutes          |
| billable_minutes_registered | Integer, billable time registered in minutes |
| date                        | Date                                         |
| notes                       | String                                       |
| approval_status             | String (NOT_SUBMITTED, SUBMITTED, APPROVED)  |
| created_by                  | Integer, ID of person                        |
| updated_by                  | Integer, ID of person                        |
| created_at                  | Date                                         |
| updated_at                  | Date                                         |

### Sample JSON response

```javascript
[
   {
      "id":1,
      "person":1,
      "project":1,
      "role": 10,
      "card":1,
      "task":1,
      "non_project_time":null,
      "time_registered":480,
      "billable_minutes_registered":360,
      "date":"2017-01-14",
      "notes":"Did work on login page",
      "approval_status": "APPROVED",
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z"
   }, ...
]
```

## Get time registration

- `GET v3/time_registrations/{time_registrationId}` - Returns a specific time registration.

| Response fields             | Description/format                           |
| --------------------------- | -------------------------------------------- |
| id                          | Integer                                      |
| person                      | Integer, ID of person                        |
| project                     | Integer, ID of project                       |
| role                        | Integer, ID of role                          |
| card                        | Integer, deprecated. Use task instead        |
| task                        | Integer, ID of task                          |
| non_project_time            | Integer, ID of non project time              |
| time_registered             | Integer, time registered in minutes          |
| billable_minutes_registered | Integer, billable time registered in minutes |
| date                        | Date                                         |
| notes                       | String                                       |
| approval_status             | String (NOT_SUBMITTED, SUBMITTED, APPROVED)  |
| created_by                  | Integer, ID of person                        |
| updated_by                  | Integer, ID of person                        |
| created_at                  | Date                                         |
| updated_at                  | Date                                         |

### Sample JSON response

```javascript
{
   "id":1,
   "person":1,
   "project":1,
   "role": 10,
   "card":1,
   "task":1,
   "non_project_time":null,
   "time_registered":480,
   "billable_minutes_registered":360,
   "date":"2017-01-14",
   "notes":"Did work on login page",
   "approval_status": "APPROVED",
   "created_by":1,
   "updated_by":1,
   "created_at":"2017-01-14T18:46:56Z",
   "updated_at":"2017-01-14T18:47:58Z"
}
```

## Create time registration

- `POST /time_registrations` - Creates a new time registration. Returns the same object as getting a single time registration.

| Request fields              | Description/format                             |
| --------------------------- | ---------------------------------------------- |
| person                      | (Required) Integer, ID of person               |
| project                     | (Required\*) Integer, ID of project            |
| role                        | Integer, ID of role                            |
| card                        | Integer, deprecated. Use task instead          |
| task                        | (Required\*) Integer, ID of task               |
| non_project_time            | (Required\*) Integer, ID of non project time   |
| time_registered             | (Required) Integer, time registered in minutes |
| billable_minutes_registered | Integer, billable time registered in minutes   |
| date                        | (Required) Date                                |
| notes                       | String                                         |

\* Either a project, task or non_project_time must be supplied

### Sample JSON request

POST https://api.forecast.it/api/v1/time_registrations

```javascript
{
   "person":1,
   "role": 10,
   "task":1,
   "time_registered":480,
   "billable_minutes_registered":360,
   "date":"2017-01-15",
   "notes":"Did work on logout page"
}
```

### Invalid time registrations

If your company has decided to validate time registration API requests against the company's Time Registration Settings, the following error messages may occur as the result of your request:

| Error                                                                    |
| ------------------------------------------------------------------------ |
| "Time Registration Date is invalid"                                      |
| "Time Registration is not allowed on Done Tasks"                         |
| "Time Registration is not allowed on Projects"                           |
| "Time Registration is not allowed to adjust Billable Minutes Registered" |
| "Time Registration is not allowed on Internal Time"                      |
| "Time Registration is not allowed to have a specified role"              |
| "Time Registration must include a Note"                                  |
| "Person registering Time must be assigned to the Task"                   |
| "Time Registration must be inside the Project's dates"                   |
| "Time Registration must be inside the Task's dates"                      |
| "Time Registration must not exceed the Remaining Estimate on the Task"   |

If any of these error messages are present, the time registration will not be created until the cause is corrected.

## Update time registration

- `PUT /time_registrations/{time_registrationId}` - Updates a time registration. Returns the same object as getting a single time registration.

| Request fields              | Description/format                           |
| --------------------------- | -------------------------------------------- |
| time_registered             | Integer, time registered in minutes          |
| billable_minutes_registered | Integer, billable time registered in minutes |
| role                        | Integer, ID of role                          |
| date                        | Date                                         |
| notes                       | String                                       |

### Sample JSON request

PUT https://api.forecast.it/api/v1/time_registrations/1

```javascript
{
   "time_registered":120,
   "role": 10
}
```

### Invalid time registrations

If your company has decided to validate time registration API requests against the company's Time Registration Settings, the following error messages may occur as the result of your request:

| Error                                                                    |
| ------------------------------------------------------------------------ |
| "Time Registration Date is invalid"                                      |
| "Time Registration is not allowed on Done Tasks"                         |
| "Time Registration is not allowed on Projects"                           |
| "Time Registration is not allowed to adjust Billable Minutes Registered" |
| "Time Registration is not allowed on Internal Time"                      |
| "Time Registration is not allowed to have a specified role"              |
| "Time Registration must include a Note"                                  |
| "Person registering Time must be assigned to the Task"                   |
| "Time Registration must be inside the Project's dates"                   |
| "Time Registration must be inside the Task's dates"                      |
| "Time Registration must not exceed the Remaining Estimate on the Task"   |

If any of these error messages are present, the time registration will not be updated until the cause is corrected.

## Delete time registration

- `DELETE /time_registrations/{time_registrationId}` - Deletes a time registration.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/time_registrations/1

## Get deleted time registrations

- `GET /v3/time_registrations/deleted` - Returns all time registrations that have been deleted.
- `GET /v3/time_registrations/deleted?updated_after=YYYYMMDDTHHmmss` - Returns all time registrations that have been deleted. after the specified time. Example value: `20200216T210047`.

| Response fields | Description/format                                         |
| --------------- | ---------------------------------------------------------- |
| id              | Integer, ID of the time registration that has been deleted |
| deleted_by      | Integer, ID of person                                      |
| deleted_at      | Date                                                       |

### Sample JSON response

```javascript
[
   {
      "id":1,
      "deleted_by":1,
      "deleted_at":"2017-01-14T18:46:56Z",
   }, ...
]
```
