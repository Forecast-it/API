# Skill Persons

## Get skill persons

* `GET /skill_persons` - Returns all skill persons.

|Response fields | Description/format|
|------------ | -------------|
|personId | Integer, ID of person|
|skillId | Integer, ID of skill|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
[
   {
      "personId":1,
      "skillId":1,
      "created_by":1,
      "updated_by":1,
      "created_at":"2020-01-14T18:46:56Z",
      "updated_at":"2020-01-14T18:47:58Z"
   }, ...
]
```

## Get skill person

* `GET /skill_persons/{personId}/{skillId}` - Returns a specific skill person.

|Response fields | Description/format|
|------------ | -------------|
|personId | Integer, ID of person|
|skillId | Integer, ID of skill|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
{
   "personId":1,
   "skillId":1,
   "created_by":1,
   "updated_by":1,
   "created_at":"2020-01-14T18:46:56Z",
   "updated_at":"2020-01-14T18:47:58Z"
}
```

## Create skill person

* `POST /skill_persons` - Creates a new skill person. Returns the same object as getting a single skill person.

|Request fields | Description/format|
|------------ | -------------|
|personId | (required) Integer, ID of person|
|skillId | (required) Integer, ID of skill|

### Sample JSON request
POST https://api.forecast.it/api/v1/skill_persons

```javascript
{
   "personId":1,
   "skillId":1,
}
```

## Delete skill person

* `DELETE /skill_persons/{personId}/{skillId}` - Deletes a skill person.

### Sample JSON request
DELETE https://api.forecast.it/api/v1/skill_persons/1/1
