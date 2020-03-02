# Time registrations

## Get time registrations

-  `GET v2/time_registrations` - Returns all time registrations.
-  `GET v2/time_registrations?updated_after=DDMMYYYYTHHmmss` - Returns all time registrations that have been updated after the specified time. Example value: `16022018T210047`.
-  `GET v2/time_registrations?date_after=DDMMYYYY` - Returns all time registrations that have a date value after the specified date. Example value: `16022018`.

| Response fields  | Description/format                  |
| ---------------- | ----------------------------------- |
| id               | Integer                             |
| person           | Integer, ID of person               |
| project          | Integer, ID of project              |
| card             | Integer, ID of card                 |
| non_project_time | Integer, ID of non project time     |
| time_registered  | Integer, time registered in minutes |
| date             | Date                                |
| notes            | String                              |
| created_by       | Integer, ID of person               |
| updated_by       | Integer, ID of person               |
| created_at       | Date                                |
| updated_at       | Date                                |

### Sample JSON response

```javascript
[
   {
      "id":1,
      "person":1,
      "project":1,
      "card":1,
      "non_project_time":null,
      "time_registered":480,
      "date":"2017-01-14",
      "notes":"Did work on login page",
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z"
   }, ...
]
```

## Get all time registrations in a project

-  `GET v2/projects/{projectId}/time_registrations` - Returns all time registrations in a project.
-  `GET v2/projects/{projectId}/time_registrations?updated_after=DDMMYYYYTHHmmss` - Returns all time registrations in a project that have been updated after the specified time. Example value: `16022018T210047`.
-  `GET v2/projects/{projectId}/time_registrations?date_after=DDMMYYYY` - Returns all time registrations that have a date value after the specified date. Example value: `16022018`.

| Response fields  | Description/format                  |
| ---------------- | ----------------------------------- |
| id               | Integer                             |
| person           | Integer, ID of person               |
| project          | Integer, ID of project              |
| card             | Integer, ID of card                 |
| non_project_time | Integer, ID of non project time     |
| time_registered  | Integer, time registered in minutes |
| date             | Date                                |
| notes            | String                              |
| created_by       | Integer, ID of person               |
| updated_by       | Integer, ID of person               |
| created_at       | Date                                |
| updated_at       | Date                                |

### Sample JSON response

```javascript
[
   {
      "id":1,
      "person":1,
      "project":1,
      "card":null,
      "non_project_time":null,
      "time_registered":480,
      "date":"2017-01-14",
      "notes":"Did work on login page",
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z"
   }, ...
]
```

## Get all time registrations for a given person

-  `GET v2/persons/{personId}/time_registrations` - Returns all time registrations for a given person.
-  `GET v2/persons/{personId}/time_registrations?updated_after=DDMMYYYYTHHmmss` - Returns all time registrations for a given person that have been updated after the specified time. Example value: `16022018T210047`.
-  `GET v2/persons/{personId}/time_registrations?date_after=DDMMYYYY` - Returns all time registrations that have a date value after the specified date. Example value: `16022018`.

| Response fields  | Description/format                  |
| ---------------- | ----------------------------------- |
| id               | Integer                             |
| person           | Integer, ID of person               |
| project          | Integer, ID of project              |
| card             | Integer, ID of card                 |
| non_project_time | Integer, ID of non project time     |
| time_registered  | Integer, time registered in minutes |
| date             | Date                                |
| notes            | String                              |
| created_by       | Integer, ID of person               |
| updated_by       | Integer, ID of person               |
| created_at       | Date                                |
| updated_at       | Date                                |

### Sample JSON response

```javascript
[
   {
      "id":1,
      "person":1,
      "project":1,
      "card":1,
      "non_project_time":null,
      "time_registered":480,
      "date":"2017-01-14",
      "notes":"Did work on login page",
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z"
   }, ...
]
```

## Get time registration

-  `GET v2/time_registrations/{time_registrationId}` - Returns a specific time registration.

| Response fields  | Description/format                  |
| ---------------- | ----------------------------------- |
| id               | Integer                             |
| person           | Integer, ID of person               |
| project          | Integer, ID of project              |
| card             | Integer, ID of card                 |
| non_project_time | Integer, ID of non project time     |
| time_registered  | Integer, time registered in minutes |
| date             | Date                                |
| notes            | String                              |
| created_by       | Integer, ID of person               |
| updated_by       | Integer, ID of person               |
| created_at       | Date                                |
| updated_at       | Date                                |

### Sample JSON response

```javascript
{
   "id":1,
   "person":1,
   "project":1,
   "card":1,
   "non_project_time":null,
   "time_registered":480,
   "date":"2017-01-14",
   "notes":"Did work on login page",
   "created_by":1,
   "updated_by":1,
   "created_at":"2017-01-14T18:46:56Z",
   "updated_at":"2017-01-14T18:47:58Z"
}
```

## Create time registration

-  `POST /time_registrations` - Creates a new time registration. Returns the same object as getting a single time registration.

| Request fields   | Description/format                             |
| ---------------- | ---------------------------------------------- |
| person           | (Required) Integer, ID of person               |
| project          | (Required\*) Integer, ID of project            |
| card             | (Required\*) Integer, ID of card               |
| non_project_time | (Required\*) Integer, ID of non project time   |
| time_registered  | (Required) Integer, time registered in minutes |
| date             | (Required) Date                                |
| notes            | String                                         |

\* Either a project, card or non_project_time must be supplied

### Sample JSON request

POST https://api.forecast.it/api/v1/time_registrations

```javascript
{
   "person":1,
   "card":1,
   "time_registered":480,
   "date":"2017-01-15",
   "notes":"Did work on logout page"
}
```

## Update time registration

-  `PUT /time_registrations/{time_registrationId}` - Updates a time registration. Returns the same object as getting a single time registration.

| Request fields  | Description/format                  |
| --------------- | ----------------------------------- |
| time_registered | Integer, time registered in minutes |
| date            | Date                                |
| notes           | String                              |

### Sample JSON request

PUT https://api.forecast.it/api/v1/time_registrations/1

```javascript
{
   "time_registered":120
}
```

## Delete time registration

-  `DELETE /time_registrations/{time_registrationId}` - Deletes a time registration.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/time_registrations/1

## Get deleted time registrations

-  `GET /time_registrations/deleted` - Returns all time registrations that have been deleted.
-  `GET /time_registrations/deleted?updated_after=DDMMYYYYTHHmmss` - Returns all time registrations that have been deleted. after the specified time. Example value: `16022018T210047`.

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
