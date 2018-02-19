# Workflow columns

## Get workflow columns

* `GET /projects/{projectId}/workflow_columns` - Returns all workflow columns of the project.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|name | String|
|category | String (TODO, INPROGRESS, DONE)|
|sort_order | Integer|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
[
   {
      "id":1,
      "name":"To do",
      "category":"TODO",
      "sort_order":1,
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z"
   }, ...
]
```

## Get workflow column

* `GET /projects/{projectId}/workflow_columns/{workflow_columnId}` - Returns a specific workflow column.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|name | String|
|category | String (TODO, INPROGRESS, DONE)|
|sort_order | Integer|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
{
   "id":1,
   "name":"To do",
   "category":"TODO",
   "sort_order":1,
   "created_by":1,
   "updated_by":1,
   "created_at":"2017-01-14T18:46:56Z",
   "updated_at":"2017-01-14T18:47:58Z"
}
```

## Create workflow column

* `POST /projects/{projectId}/workflow_columns` - Creates a new workflow column. Returns the same object as getting a single workflow column.

|Request fields | Description/format|
|------------ | -------------|
|name | (Required) String|
|category | String (TODO, INPROGRESS, DONE) (Defaults to TODO)|
|sort_order | Integer (Defaults to the last column)|

### Sample JSON request
POST https://api.forecast.it/api/v1/projects/1/workflow_columns

```javascript
{
   "name":"In progress",
   "category":"INPROGRESS",
   "sort_order":2,
}
```

## Update workflow column

* `PUT /projects/{projectId}/workflow_columns/{workflow_columnId}` - Updates an workflow column. Returns the same object as getting a single workflow column.

|Request fields | Description/format|
|------------ | -------------|
|name | (Required) String|
|category | String (TODO, INPROGRESS, DONE) (Defaults to TODO)|
|sort_order | Integer (Defaults to the last column)|

### Sample JSON request
PUT https://api.forecast.it/api/v1/projects/1/workflow_columns/1

```javascript
{
   "name":"Not done yet"
}
```

## Delete workflow column

* `DELETE /projects/{projectId}/workflow_columns/{workflow_columnId}` - Deletes a workflow column. Does not delete cards in the workflow column.

### Sample JSON request
DELETE https://api.forecast.it/api/v1/projects/1/workflow_columns/1