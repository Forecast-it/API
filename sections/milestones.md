# Milestones

## Get milestones

* `GET /projects/{projectId}/milestones` - Returns all milestones of the project.

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
      "name":"Milestone 1",
      "start_date":"2017-01-14",
      "end_date":"2017-06-14",
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:561Z",
      "updated_at":"2017-01-14T18:47:581Z"
   }, ...
]
```

## Get milestone

* `GET /projects/{projectId}/milestones/{milestoneId}` - Returns a specific milestone.

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
   "name":"Milestone 1",
   "start_date":"2017-01-14",
   "end_date":"2017-06-14",
   "created_by":1,
   "updated_by":1,
   "created_at":"2017-01-14T18:46:561Z",
   "updated_at":"2017-01-14T18:47:581Z"
}
```

## Create milestone

* `POST /projects/{projectId}/milestones` - Creates a new milestone. Returns the same object as getting a single milestone.

|Request fields | Description/format|
|------------ | -------------|
|name | (Required) String|
|start_date | Date|
|end_date | Date|

### Sample JSON request
POST https://api.forecast.it/api/v1/projects/1/milestones

```javascript
{
   "name":"Milestone 2",
   "start_date":"2017-06-14",
   "end_date":"2017-09-14"
}
```

## Update milestone

* `PUT /projects/{projectId}/milestones/{milestoneId}` - Updates an milestone. Returns the same object as getting a single milestone.

|Request fields | Description/format|
|------------ | -------------|
|name | String|
|start_date | Date|
|end_date | Date|

### Sample JSON request
PUT https://api.forecast.it/api/v1/projects/1/milestones/1

```javascript
{
   "name":"Milestone 3",
}
```

## Delete milestone

* `DELETE /projects/{projectId}/milestones/{milestoneId}` - Deletes a milestone. Does not delete cards in the milestone.

### Sample JSON request
DELETE https://api.forecast.it/api/v1/projects/1/milestones/1