# Teams

## Get teams

* `GET /teams` - Returns all teams.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|name | String|
|persons | List<Integer>, List ID of persons|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
[
   {
      "id":1,
      "name":"Tech team",
      "persons":[1,2,3],
      "created_by":1,
      "updated_by":1,
      "created_at":"2020-01-14T18:46:56Z",
      "updated_at":"2020-01-14T18:47:58Z"
   }, ...
]
```

## Get team

* `GET /teams/{teamId}` - Returns a specific team.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|name | String|
|persons | List<Integer>, List ID of persons|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
{
  "id":1,
  "name":"Tech team",
  "persons":[1,2,3],
  "created_by":1,
  "updated_by":1,
  "created_at":"2020-01-14T18:46:56Z",
  "updated_at":"2020-01-14T18:47:58Z"
}
```

## Create team

* `POST /teams` - Creates a new team. Returns the same object as getting a single team.

|Request fields | Description/format|
|------------ | -------------|
|name | (Required) String|
|persons | List<Integer>, List ID of persons|

### Sample JSON request
POST https://api.forecast.it/api/v1/teams

```javascript
{
   "name":"Leadership",
   "persons":[1,5]
}
```

## Update team

* `PUT /teams/{teamId}` - Updates a team. Returns the same object as getting a single team.

|Request fields | Description/format|
|------------ | -------------|
|name | String|
|persons | List<Integer>, List ID of persons|

### Sample JSON request
PUT https://api.forecast.it/api/v1/teams/1

```javascript
{
   "name":"Team 42"
}
```

## Delete team

* `DELETE /teams/{teamId}` - Deletes a team.

### Sample JSON request
DELETE https://api.forecast.it/api/v1/teams/1
