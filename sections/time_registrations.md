# Time registrations

## Get time registrations

* `GET /time_registrations` - Returns all time registrations.

**Only one of project, card or non_project_time is filled!**

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|person | Integer, ID of person|
|project | Integer, ID of project|
|card | Integer, ID of card|
|non_project_time | Integer, ID of non project time|
|time_registered | Integer, time registered in minutes|
|date | Date|
|notes | String|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
[
   {
      "id":1,
      "person":1,
      "project":null,
      "card":1,
      "non_project_time":null,
      "time_registered":480,
      "date":"2017-01-14",
      "notes":"Did work on login page",
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:561Z",
      "updated_at":"2017-01-14T18:47:581Z"
   }, ...
]
```

## Get all time registrations in a project

* `GET /projects/{projectId}/time_registrations` - Returns all time registrations in a project.

**Only one of project, card or non_project_time is filled!**

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|person | Integer, ID of person|
|project | Integer, ID of project|
|card | Integer, ID of card|
|non_project_time | Integer, ID of non project time|
|time_registered | Integer, time registered in minutes|
|date | Date|
|notes | String|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

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
      "created_at":"2017-01-14T18:46:561Z",
      "updated_at":"2017-01-14T18:47:581Z"
   }, ...
]
```
## Get all time registrations for a given person

* `GET /persons/{personId}/time_registrations` - Returns all time registrations for a given person.

**Only one of project, card or non_project_time is filled!**

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|person | Integer, ID of person|
|project | Integer, ID of project|
|card | Integer, ID of card|
|non_project_time | Integer, ID of non project time|
|time_registered | Integer, time registered in minutes|
|date | Date|
|notes | String|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
[
   {
      "id":1,
      "person":1,
      "project":null,
      "card":1,
      "non_project_time":null,
      "time_registered":480,
      "date":"2017-01-14",
      "notes":"Did work on login page",
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:561Z",
      "updated_at":"2017-01-14T18:47:581Z"
   }, ...
]
```

## Get time registration

* `GET /time_registrations/{time_registrationId}` - Returns a specific time registration.

**Only one of project, card or non_project_time is filled!**

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|person | Integer, ID of person|
|project | Integer, ID of project|
|card | Integer, ID of card|
|non_project_time | Integer, ID of non project time|
|time_registered | Integer, time registered in minutes|
|date | Date|
|notes | String|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
{
   "id":1,
   "person":1,
   "project":null,
   "card":1,
   "non_project_time":null,
   "time_registered":480,
   "date":"2017-01-14",
   "notes":"Did work on login page",
   "created_by":1,
   "updated_by":1,
   "created_at":"2017-01-14T18:46:561Z",
   "updated_at":"2017-01-14T18:47:581Z"
}
```

## Create time registration

* `POST /time_registrations` - Creates a new time registration. Returns the same object as getting a single time registration.

|Request fields | Description/format|
|------------ | -------------|
|person | (Required) Integer, ID of person|
|project | (Required*) Integer, ID of project|
|card | (Required*) Integer, ID of card|
|non_project_time | (Required*) Integer, ID of non project time|
|time_registered | (Required) Integer, time registered in minutes|
|date | (Required) Date|
|notes | String|

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

* `PUT /time_registrations/{time_registrationId}` - Updates a time registration. Returns the same object as getting a single time registration.

|Request fields | Description/format|
|------------ | -------------|
|time_registered | Integer, time registered in minutes|
|date | Date|
|notes | String|

### Sample JSON request
PUT https://api.forecast.it/api/v1/time_registrations/1

```javascript
{
   "time_registered":120
}
```

## Delete time registration

* `DELETE /time_registrations/{time_registrationId}` - Deletes a time registration.

### Sample JSON request
DELETE https://api.forecast.it/api/v1/time_registrations/1
