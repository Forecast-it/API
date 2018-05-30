# Sprints

## Get project sprints

* `GET /projects/{projectId}/sprints` - Returns all sprints of the project.

| Response fields          | Description/format                      |
| ------------------------ | --------------------------------------- |
| id                       | Integer                                 |
| connected_project_sprint | Integer, ID of connected project sprint |
| name                     | String                                  |
| start_date               | Date                                    |
| end_date                 | Date                                    |
| created_by               | Integer, ID of person                   |
| updated_by               | Integer, ID of person                   |
| created_at               | Date                                    |
| updated_at               | Date                                    |

### Sample JSON response

```javascript
[
   {
      "id":1,
      "connected_project_sprint": 2,
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

## Get connected project sprints

* `GET /connected_projects/{connectedProjectId}/sprints` - Returns all sprints of the connected project.

| Response fields | Description/format    |
| --------------- | --------------------- |
| id              | Integer               |
| name            | String                |
| start_date      | Date                  |
| end_date        | Date                  |
| created_by      | Integer, ID of person |
| updated_by      | Integer, ID of person |
| created_at      | Date                  |
| updated_at      | Date                  |

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

## Get project sprint

* `GET /projects/{projectId}/sprints/{sprintId}` - Returns a specific sprint of the project.

| Response fields          | Description/format                      |
| ------------------------ | --------------------------------------- |
| id                       | Integer                                 |
| connected_project_sprint | Integer, ID of connected project sprint |
| name                     | String                                  |
| start_date               | Date                                    |
| end_date                 | Date                                    |
| created_by               | Integer, ID of person                   |
| updated_by               | Integer, ID of person                   |
| created_at               | Date                                    |
| updated_at               | Date                                    |

### Sample JSON response

```javascript
{
   "id":1,
   "connected_project_sprint": 2,
   "name":"sprint 1",
   "start_date":"2017-01-14",
   "end_date":"2017-01-28",
   "created_by":1,
   "updated_by":1,
   "created_at":"2017-01-14T18:46:56Z",
   "updated_at":"2017-01-14T18:47:58Z"
}
```

## Get connected project sprint

* `GET /connected_projects/{connectedProjectId}/sprints/{sprintId}` - Returns a specific sprint of the connected project.

| Response fields | Description/format    |
| --------------- | --------------------- |
| id              | Integer               |
| name            | String                |
| start_date      | Date                  |
| end_date        | Date                  |
| created_by      | Integer, ID of person |
| updated_by      | Integer, ID of person |
| created_at      | Date                  |
| updated_at      | Date                  |

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

## Create project sprint

* `POST /projects/{projectId}/sprints` - Creates a new project sprint. Returns the same object as getting a single sprint.

| Request fields | Description/format |
| -------------- | ------------------ |
| name           | (Required) String  |
| start_date     | (Required) Date    |
| end_date       | (Required) Date    |

### Sample JSON request

POST https://api.forecast.it/api/v1/projects/1/sprints

```javascript
{
   "name":"sprint 2",
   "start_date":"2017-02-14",
   "end_date":"2017-02-28"
}
```

## Create connected project sprint

* `POST /connected_projects/{connectedProjectId}/sprints` - Creates a new connected project sprint. Returns the same object as getting a single sprint.

| Request fields | Description/format |
| -------------- | ------------------ |
| name           | (Required) String  |
| start_date     | (Required) Date    |
| end_date       | (Required) Date    |

### Sample JSON request

POST https://api.forecast.it/api/v1/connected_projects/1/sprints

```javascript
{
   "name":"sprint 2",
   "start_date":"2017-02-14",
   "end_date":"2017-02-28"
}
```

## Update project sprint

* `PUT /projects/{projectId}/sprints/{sprintId}` - Updates a project sprint. Returns the same object as getting a single sprint.

| Request fields | Description/format |
| -------------- | ------------------ |
| name           | String             |
| start_date     | Date               |
| end_date       | Date               |

### Sample JSON request

PUT https://api.forecast.it/api/v1/projects/1/sprints/1

```javascript
{
   "name":"Sprint 3"
}
```

## Update connected project sprint

* `PUT /connected_projects/{connectedProjectId}/sprints/{sprintId}` - Updates a connected project sprint. Returns the same object as getting a single sprint.

| Request fields | Description/format |
| -------------- | ------------------ |
| name           | String             |
| start_date     | Date               |
| end_date       | Date               |

### Sample JSON request

PUT https://api.forecast.it/api/v1/connected_projects/1/sprints/1

```javascript
{
   "name":"Sprint 3"
}
```

## Delete project sprint

* `DELETE /projects/{projectId}/sprints/{sprintId}` - Deletes a project sprint. Does not delete cards in the sprint.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/projects/1/sprints/1

## Delete connected project sprint

* `DELETE /connected_projects/{connectedProjectId}/sprints/{sprintId}` - Deletes a connected project sprint. Does not delete cards in the sprint.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/connected_projects/1/sprints/1
