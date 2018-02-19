# Non project time

## Get non project time

* `GET /non_project_time` - Returns all non project time.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|name | String|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
[
   {
      "id":1,
      "name":"Vacation",
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z"
   }, ...
]
```

## Get non project time

* `GET /non_project_time/{non_project_timeId}` - Returns a specific non project time.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|name | String|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
{
   "id":1,
   "name":"Vacation",
   "created_by":1,
   "updated_by":1,
   "created_at":"2017-01-14T18:46:56Z",
   "updated_at":"2017-01-14T18:47:58Z"
}
```

## Create non project time

* `POST /non_project_time` - Creates a new non project time. Returns the same object as getting a single non project time.

|Request fields | Description/format|
|------------ | -------------|
|name | (Required) String|

### Sample JSON request
POST https://api.forecast.it/api/v1/non_project_time

```javascript
{
   "name":"Sickness",
}
```

## Update non project time

* `PUT /non_project_time/{non_project_timeId}` - Updates a non project time. Returns the same object as getting a single non project time.

|Request fields | Description/format|
|------------ | -------------|
|name | String|

### Sample JSON request
PUT https://api.forecast.it/api/v1/non_project_time/1

```javascript
{
   "name":"Meetings",
}
```

## Delete non project time

* `DELETE /non_project_time/{non_project_timeId}` - Deletes a non project time.

### Sample JSON request
DELETE https://api.forecast.it/api/v1/non_project_time/1