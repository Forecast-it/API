# Workflow columns

## Get project workflow columns

* `GET /projects/{projectId}/workflow_columns` - Returns all workflow columns of the project.

| Response fields                   | Description/format              |
| --------------------------------- | ------------------------------- |
| id                                | Integer                         |
| connected_project_workflow_column | Integer                         |
| name                              | String                          |
| category                          | String (TODO, INPROGRESS, DONE) |
| sort_order                        | Integer                         |
| created_by                        | Integer, ID of person           |
| updated_by                        | Integer, ID of person           |
| created_at                        | Date                            |
| updated_at                        | Date                            |

### Sample JSON response

```javascript
[
   {
      "id":1,
      "connected_project_workflow_column":2,
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

## Get connected project workflow columns

* `GET /connected_projects/{connectedProjectId}/workflow_columns` - Returns all workflow columns of the connected project.

| Response fields | Description/format              |
| --------------- | ------------------------------- |
| id              | Integer                         |
| name            | String                          |
| category        | String (TODO, INPROGRESS, DONE) |
| sort_order      | Integer                         |
| created_by      | Integer, ID of person           |
| updated_by      | Integer, ID of person           |
| created_at      | Date                            |
| updated_at      | Date                            |

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

## Get project workflow column

* `GET /projects/{projectId}/workflow_columns/{workflow_columnId}` - Returns a specific project workflow column.

| Response fields                   | Description/format              |
| --------------------------------- | ------------------------------- |
| id                                | Integer                         |
| connected_project_workflow_column | Integer                         |
| name                              | String                          |
| category                          | String (TODO, INPROGRESS, DONE) |
| sort_order                        | Integer                         |
| created_by                        | Integer, ID of person           |
| updated_by                        | Integer, ID of person           |
| created_at                        | Date                            |
| updated_at                        | Date                            |

### Sample JSON response

```javascript
{
   "id":1,
   "connected_project_workflow_column":2,
   "name":"To do",
   "category":"TODO",
   "sort_order":1,
   "created_by":1,
   "updated_by":1,
   "created_at":"2017-01-14T18:46:56Z",
   "updated_at":"2017-01-14T18:47:58Z"
}
```

## Get connected project workflow column

* `GET /connected_projects/{connectedProjectId}/workflow_columns/{workflow_columnId}` - Returns a specific connected project workflow column.

| Response fields | Description/format              |
| --------------- | ------------------------------- |
| id              | Integer                         |
| name            | String                          |
| category        | String (TODO, INPROGRESS, DONE) |
| sort_order      | Integer                         |
| created_by      | Integer, ID of person           |
| updated_by      | Integer, ID of person           |
| created_at      | Date                            |
| updated_at      | Date                            |

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

## Create project workflow column

* `POST /projects/{projectId}/workflow_columns` - Creates a new project workflow column. Returns the same object as getting a single workflow column.

| Request fields | Description/format                                 |
| -------------- | -------------------------------------------------- |
| name           | (Required) String                                  |
| category       | String (TODO, INPROGRESS, DONE) (Defaults to TODO) |
| sort_order     | Integer (Defaults to the last column)              |

### Sample JSON request

POST https://api.forecast.it/api/v1/projects/1/workflow_columns

```javascript
{
   "name":"In progress",
   "category":"INPROGRESS",
   "sort_order":2,
}
```

## Create connected project workflow column

* `POST /connected_projects/{connectedProjectId}/workflow_columns` - Creates a new connected project workflow column. Returns the same object as getting a single workflow column.

| Request fields | Description/format                                 |
| -------------- | -------------------------------------------------- |
| name           | (Required) String                                  |
| category       | String (TODO, INPROGRESS, DONE) (Defaults to TODO) |
| sort_order     | Integer (Defaults to the last column)              |

### Sample JSON request

POST https://api.forecast.it/api/v1/connected_projects/1/workflow_columns

```javascript
{
   "name":"In progress",
   "category":"INPROGRESS",
   "sort_order":2,
}
```

## Update project workflow column

* `PUT /projects/{projectId}/workflow_columns/{workflow_columnId}` - Updates project workflow column. Returns the same object as getting a single workflow column.

| Request fields | Description/format                                 |
| -------------- | -------------------------------------------------- |
| name           | (Required) String                                  |
| category       | String (TODO, INPROGRESS, DONE) (Defaults to TODO) |
| sort_order     | Integer (Defaults to the last column)              |

### Sample JSON request

PUT https://api.forecast.it/api/v1/projects/1/workflow_columns/1

```javascript
{
   "name":"Not done yet"
}
```

## Update connected project workflow column

* `PUT /connected_projects/{connectedProjectId}/workflow_columns/{workflow_columnId}` - Updates connected project workflow column. Returns the same object as getting a single workflow column.

| Request fields | Description/format                                 |
| -------------- | -------------------------------------------------- |
| name           | (Required) String                                  |
| category       | String (TODO, INPROGRESS, DONE) (Defaults to TODO) |
| sort_order     | Integer (Defaults to the last column)              |

### Sample JSON request

PUT https://api.forecast.it/api/v1/connected_projects/1/workflow_columns/1

```javascript
{
   "name":"Not done yet"
}
```

## Delete project workflow column

* `DELETE /projects/{projectId}/workflow_columns/{workflow_columnId}` - Deletes project workflow column. Does not delete cards in the workflow column.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/projects/1/workflow_columns/1

## Delete connected project workflow column

* `DELETE /connected_projects/{connectedProjectId}/workflow_columns/{workflow_columnId}` - Deletes connected project workflow column. Does not delete cards in the workflow column.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/connected_projects/1/workflow_columns/1
