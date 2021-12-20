# Skills

## Get skills

* `GET /skills` - Returns all skills.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|name | String|
|categoryId | Integer|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
[
   {
      "id":1,
      "name":"Java",
      "categoryId":1,
      "created_by":1,
      "updated_by":1,
      "created_at":"2020-01-14T18:46:56Z",
      "updated_at":"2020-01-14T18:47:58Z"
   }, ...
]
```

## Get skill

* `GET /skills/{skillId}` - Returns a specific skill.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|name | String|
|categoryId | Integer|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
{
   "id":1,
   "name":"Java",
   "categoryId":1,
   "created_by":1,
   "updated_by":1,
   "created_at":"2020-01-14T18:46:56Z",
   "updated_at":"2020-01-14T18:47:58Z"
}
```

## Create skill

* `POST /skills` - Creates a new skill. Returns the same object as getting a single skill.

|Request fields | Description/format|
|------------ | -------------|
|name | (Required) String|
|categoryId | Integer|
|assignedPersons | List<Integer>, List ID of persons|

### Sample JSON request
POST https://api.forecast.it/api/v1/skills

```javascript
{
   "name":"Python",
   "categoryId":1,
   "assignedPersons": [1, 2]
}
```

## Update skill

* `PUT /skills/{skillId}` - Updates a skill. Returns the same object as getting a single skill.

|Request fields | Description/format|
|------------ | -------------|
|name | String|
|categoryId | Integer|
|assignedPersons | List<Integer>, List ID of persons|

### Sample JSON request
PUT https://api.forecast.it/api/v1/skills/1

```javascript
{
   "name":"C++",
   "categoryId":1,
   "assignedPersons": [1, 2]
}
```

## Delete skill

* `DELETE /skills/{skillId}` - Deletes a skill.

### Sample JSON request
DELETE https://api.forecast.it/api/v1/skills/1
