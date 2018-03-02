# Sprints

## Get sprints

* `GET /projects/{projectId}/sprints` - Returns all sprints of the project.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|name | String|
|start_date | Date|
|end_date | Date|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
[
   {
      "id":1,
      "name":"sprint 1",
      "start_date":"2017-01-14",
      "end_date":"2017-01-28",
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z"
   }, ...
]
```

## Get sprint

* `GET /projects/{projectId}/sprints/{sprintId}` - Returns a specific sprint.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|name | String|
|start_date | Date|
|end_date | Date|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
{
   "id":1,
   "name":"sprint 1",
   "start_date":"2017-01-14",
   "end_date":"2017-01-28",
   "created_by":1,
   "updated_by":1,
   "created_at":"2017-01-14T18:46:56Z",
   "updated_at":"2017-01-14T18:47:58Z"
}
```

## Create sprint

* `POST /projects/{projectId}/sprints` - Creates a new sprint. Returns the same object as getting a single sprint.

|Request fields | Description/format|
|------------ | -------------|
|name | (Required) String|
|start_date | (Required) Date|
|end_date | (Required) Date|

### Sample JSON request
POST https://api.forecast.it/api/v1/projects/1/sprints

```javascript
{
   "name":"sprint 2",
   "start_date":"2017-02-14",
   "end_date":"2017-02-28"
}
```

## Update sprint

* `PUT /projects/{projectId}/sprints/{sprintId}` - Updates an sprint. Returns the same object as getting a single sprint.

|Request fields | Description/format|
|------------ | -------------|
|name | String|
|start_date | Date|
|end_date | Date|

### Sample JSON request
PUT https://api.forecast.it/api/v1/projects/1/sprints/1

```javascript
{
   "name":"Sprint 3"
}
```

## Delete sprint

* `DELETE /projects/{projectId}/sprints/{sprintId}` - Deletes a sprint. Does not delete cards in the sprint.

### Sample JSON request
DELETE https://api.forecast.it/api/v1/projects/1/sprints/1