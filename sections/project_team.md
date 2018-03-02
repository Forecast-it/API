# Project team

## Get project persons

* `GET /projects/{projectId}/team` - Returns all persons of the project.

|Response fields | Description/format|
|------------ | -------------|
|person_id | Integer, ID of person|
|project_role | Integer, ID of role|
|project_contact | Boolean|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
[
   {
      "person_id":1,
      "project_role":1,
      "project_contact":false,
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z"
   }, ...
]
```

## Get project person

* `GET /projects/{projectId}/team/{personId}` - Returns a specific project person.

|Response fields | Description/format|
|------------ | -------------|
|person_id | Integer, ID of person|
|project_role | Integer, ID of role|
|project_contact | Boolean|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
{
   "person_id":1,
   "project_role":1,
   "project_contact":false,
   "created_by":1,
   "updated_by":1,
   "created_at":"2017-01-14T18:46:56Z",
   "updated_at":"2017-01-14T18:47:58Z"
}
```

## Add person to project team

* `POST /projects/{projectId}/team` - Adds a person to a project team. Returns the same object as getting a single project person.

|Request fields | Description/format|
|------------ | -------------|
|person_id | (Required) Integer, ID of person|
|project_role | (Required) Integer, ID of role|
|project_contact | Boolean (Defaults to false)|

### Sample JSON request
POST https://api.forecast.it/api/v1/projects/1/team

```javascript
{
   "person_id":1,
   "project_role":1
}
```

## Update person in team

* `PUT /projects/{projectId}/team/{personId}` - Updates a person in the project. Returns the same object as getting a single project person.

|Request fields | Description/format|
|------------ | -------------|
|project_role | Integer, ID of role|
|project_contact | Boolean|

### Sample JSON request
PUT https://api.forecast.it/api/v1/projects/1/team/1

```javascript
{
   "project_role":2,
}
```

## Remove person from project

* `DELETE /projects/{projectId}/team/{personId}` - Removes a person from a project.

### Sample JSON request
DELETE https://api.forecast.it/api/v1/projects/1/team/1