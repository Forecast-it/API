# Persons

## Get persons

* `GET /persons` - Returns all persons.

|Response fields | Description/format|
|------------ | -------------|
|url | String, URL to the person|
|id | Integer|
|first_name | String|
|last_name | String|
|email | String|
|user_type | String|
|monday | Integer|
|tuesday | Integer|
|wednesday | Integer|
|thursday | Integer|
|friday | Integer|
|saturday | Integer|
|sunday | Integer|
|active | Boolean|
|default_role | Integer|
|cost | Integer|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
[
   {
      "url":"https://api.forecast.it/api/v1/person/1",
      "id":1,
      "first_name":"John",
      "last_name":"Smith",
      "email":"js@domain.com",
      "user_type":"ADMIN",
      "monday":480,
      "tuesday":480,
      "wednesday":480,
      "thursday":480,
      "friday":480,
      "saturday":480,
      "sunday":480,
      "active":true,
      "default_role":29,
      "cost":100,
      "created_at":"2017-01-14T18:46:56+01:00",
      "updated_at":"2017-01-14T18:47:58+01:00"
   }, ...
]
```

## Get person

* `GET /persons/{personId}` - Returns a specific person.

|Response fields | Description/format|
|------------ | -------------|
|url | String, URL to the person|
|id | Integer|
|first_name | String|
|last_name | String|
|email | String|
|user_type | String|
|monday | Integer|
|tuesday | Integer|
|wednesday | Integer|
|thursday | Integer|
|friday | Integer|
|saturday | Integer|
|sunday | Integer|
|active | Boolean|
|default_role | JSON (Role)|
|cost | Integer|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
{
   "url":"https://api.forecast.it/api/v1/persons/1",
   "id":1,
   "first_name":"John",
   "last_name":"Smith",
   "email":"js@domain.com",
   "user_type":"ADMIN",
   "monday":480,
   "tuesday":480,
   "wednesday":480,
   "thursday":480,
   "friday":480,
   "saturday":480,
   "sunday":480,
   "active":true,
   "default_role": {...},
   "cost":100,
   "created_at":"2017-01-14T18:46:56+01:00",
   "updated_at":"2017-01-14T18:47:58+01:00"
}
```

## Create person

* `POST /persons` - Creates a new person.

|Response fields | Description/format|
|------------ | -------------|
|first_name | (Required) String|
|last_name | (Required) String|
|email | (Required) String|
|user_type | String|
|monday | Integer|
|tuesday | Integer|
|wednesday | Integer|
|thursday | Integer|
|friday | Integer|
|saturday | Integer|
|sunday | Integer|
|active | Boolean|
|default_role | (Required) Integer, id of the default role|
|cost | Integer|

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
   "saturday":480,
   "sunday":480,
   "active":true,
   "default_role":4,
   "cost":100,
}
```

## Update person

* `PUT /persons/{personId}` - Updates a person.

|Response fields | Description/format|
|------------ | -------------|
|first_name | String|
|last_name | String|
|email | String|
|active | Boolean|
|default_role | Integer, id of the default role|

### Sample JSON request
PUT https://api.forecast.it/api/v1/persons/1

```javascript
{
   "first_name":"John",
   "last_name":"Doe"
}
```

## Delete person

* `DELETE /persons/{personId}` - Deletes a person.

### Sample JSON request
DELETE https://api.forecast.it/api/v1/persons/1