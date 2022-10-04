# To do's

## Get task to do's

-  `GET /tasks/{taskId}/to_dos` - Returns all to do's for a task.

| Response fields | Description/format                      |
| --------------- | --------------------------------------- |
| id              | Integer                                 |
| task            | Integer, ID of task                     |
| name            | String                                  |
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
      "task": 2,
      "name": "Design",
      "done": false,
      "created_by": 1,
      "updated_by": 1,
      "created_at": "2023-03-28T11:52:51Z",
      "updated_at": "2023-03-28T11:52:51Z"
   }, ...
]
```

## Get project to do's

-  `GET /projects/{projectId}/to_dos` - Returns all to do's for a project.

| Response fields | Description/format                      |
| --------------- | --------------------------------------- |
| id              | Integer                                 |
| task            | Integer, ID of task                     |
| name            | String                                  |
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
      "task": 2,
      "name": "Design",
      "done": false,
      "created_by": 1,
      "updated_by": 1,
      "created_at": "2023-03-28T11:52:51Z",
      "updated_at": "2023-03-28T11:52:51Z"
   }, ...
]
```

## Get to do

-  `GET /to_dos/{toDoId}` - Returns a specific subtask.

| Response fields | Description/format                      |
| --------------- | --------------------------------------- |
| id              | Integer                                 |
| task            | Integer, ID of task                     |
| name            | String                                  |
| done            | Boolean                                 |
| created_by      | Integer, ID of person                   |
| updated_by      | Integer, ID of person                   |
| created_at      | Date                                    |
| updated_at      | Date                                    |

### Sample JSON response

```javascript
{
   "id": 2,
   "task": 2,
   "name": "Design",
   "done": false,
   "created_by": 1,
   "updated_by": 1,
   "created_at": "2023-03-28T11:52:51Z",
   "updated_at": "2023-03-28T11:52:51Z"
}
```

## Create to do

-  `POST /to_dos` - Creates a new to do. Returns the same object as getting a single to do.

| Request fields | Description/format                      |
| -------------- | --------------------------------------- |
| task           | (Required) Integer, ID of parent task   |
| name           | String                                  |
| done           | Boolean                                 |

### Sample JSON request

POST https://api.forecast.it/api/v3/to_dos

```javascript
{
   "name":"Design",
   "task":2
}
```

## Update to do

-  `PUT /to_dos/{toDoId}` - Updates a to do. Returns the same object as getting a single to do.

| Request fields | Description/format |
| -------------- | ------------------ |
| name           | String             |
| done           | Boolean            |

### Sample JSON request

PUT https://api.forecast.it/api/v3/to_dos/1

```javascript
{
   "name":"Design and other work"
}
```

## Delete to do

-  `DELETE /to_dos/{toDoId}` - Deletes a to do.

### Sample JSON request

DELETE https://api.forecast.it/api/v3/to_dos/1
