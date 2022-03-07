# Skill Categories

## Get skill categories

* `GET /skill_categories` - Returns all skill categories.

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
      "name":"Programming",
      "created_by":1,
      "updated_by":1,
      "created_at":"2020-01-14T18:46:56Z",
      "updated_at":"2020-01-14T18:47:58Z"
   }, ...
]
```

## Get skill category

* `GET /skill_categories/{skillCategoryId}` - Returns a specific skill category.

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
   "name":"Programming",
   "created_by":1,
   "updated_by":1,
   "created_at":"2020-01-14T18:46:56Z",
   "updated_at":"2020-01-14T18:47:58Z"
}
```

## Create skill category

* `POST /skill_categories` - Creates a new skill category. Returns the same object as getting a single skill category.

|Request fields | Description/format|
|------------ | -------------|
|name | (Required) String|
|assignedSkills | List<Integer>, List ID of skills|

### Sample JSON request
POST https://api.forecast.it/api/v1/skill_categories

```javascript
{
   "name":"Programming",
   "assignedSkills": [1, 2]
}
```

## Update skill category

* `PUT /skill_categories/{skillCategoryId}` - Updates a skill category. Returns the same object as getting a single skill category.

|Request fields | Description/format|
|------------ | -------------|
|name | String|
|assignedSkills | List<Integer>, List ID of skills|

### Sample JSON request
PUT https://api.forecast.it/api/v1/skill_categories/1

```javascript
{
   "name":"Programming",
   "assignedSkills": [1, 2]
}
```

## Delete skill category

* `DELETE /skill_categories/{skillCategoryId}` - Deletes a skill category.

### Sample JSON request
DELETE https://api.forecast.it/api/v1/skill_categories/1
