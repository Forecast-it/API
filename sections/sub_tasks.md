# Sub tasks

> [!CAUTION]
> **DEPRECATED**
> <br/>
> **NB: These endpoints refer to the old subtasks which have been deprecated. To do's are still available via these, but for the new subtasks please see our documentation on tasks.**

## Get task sub tasks

-  `GET /tasks/{taskId}/sub_tasks` - Returns all sub tasks for a task.

| Response fields | Description/format                      |
| --------------- | --------------------------------------- |
| id              | Integer                                 |
| card            | Integer, deprecated. Use 'task' instead |
| task            | Integer, ID of task                     |
| name            | String                                  |
| description     | String                                  |
| estimate        | Integer (minutes)                       |
| done            | Boolean                                 |
| created_by      | Integer, ID of person                   |
| updated_by      | Integer, ID of person                   |
| created_at      | Date                                    |
| updated_at      | Date                                    |

### Sample JSON response

```javascript
[
   {
      "id": 2,
      "card": 2,
      "task": 2,
      "name": "Design",
      "description": null,
      "estimate": 480,
      "done": false,
      "created_by": 1,
      "updated_by": 1,
      "created_at": "2018-03-28T11:52:51Z",
      "updated_at": "2018-03-28T11:52:51Z"
   }, ...
]
```

## Get project sub tasks

-  `GET /projects/{projectId}/sub_tasks` - Returns all sub tasks for a project.

| Response fields | Description/format                      |
| --------------- | --------------------------------------- |
| id              | Integer                                 |
| card            | Integer, deprecated. Use 'task' instead |
| task            | Integer, ID of task                     |
| name            | String                                  |
| description     | String                                  |
| estimate        | Integer (minutes)                       |
| done            | Boolean                                 |
| created_by      | Integer, ID of person                   |
| updated_by      | Integer, ID of person                   |
| created_at      | Date                                    |
| updated_at      | Date                                    |

### Sample JSON response

```javascript
[
   {
      "id": 2,
      "card": 2,
      "task": 2,
      "name": "Design",
      "description": null,
      "estimate": 480,
      "done": false,
      "created_by": 1,
      "updated_by": 1,
      "created_at": "2018-03-28T11:52:51Z",
      "updated_at": "2018-03-28T11:52:51Z"
   }, ...
]
```

## Get sub task

-  `GET /sub_tasks/{subTaskId}` - Returns a specific subtask.

| Response fields | Description/format                      |
| --------------- | --------------------------------------- |
| id              | Integer                                 |
| card            | Integer, deprecated. Use 'task' instead |
| task            | Integer, ID of task                     |
| name            | String                                  |
| description     | String                                  |
| estimate        | Integer (minutes)                       |
| done            | Boolean                                 |
| created_by      | Integer, ID of person                   |
| updated_by      | Integer, ID of person                   |
| created_at      | Date                                    |
| updated_at      | Date                                    |

### Sample JSON response

```javascript
{
   "id": 2,
   "card": 2,
   "task": 2,
   "name": "Design",
   "description": null,
   "estimate": 480,
   "done": false,
   "created_by": 1,
   "updated_by": 1,
   "created_at": "2018-03-28T11:52:51Z",
   "updated_at": "2018-03-28T11:52:51Z"
}
```

## Create sub task

-  `POST /sub_tasks` - Creates a new sub task. Returns the same object as getting a single sub task.

| Request fields | Description/format                      |
| -------------- | --------------------------------------- |
| card           | Integer, deprecated. Use 'task' instead |
| task           | (Required) Integer, ID of parent task   |
| name           | String                                  |
| description    | String                                  |
| estimate       | Integer (minutes)                       |
| done           | Boolean                                 |

### Sample JSON request

POST https://api.forecast.it/api/v1/sub_tasks

```javascript
{
   "name":"Design",
   "task":2
}
```

## Update sub task

-  `PUT /sub_tasks/{subTaskId}` - Updates a sub task. Returns the same object as getting a single sub task.

| Request fields | Description/format |
| -------------- | ------------------ |
| name           | String             |
| description    | String             |
| estimate       | Integer (minutes)  |
| done           | Boolean            |

### Sample JSON request

PUT https://api.forecast.it/api/v1/sub_tasks/1

```javascript
{
   "name":"Design and other work"
}
```

## Delete sub task

-  `DELETE /sub_tasks/{subTaskId}` - Deletes a sub task.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/sub_tasks/1
