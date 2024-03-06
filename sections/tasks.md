# Tasks

(Formerly known as cards. See old docs here: [Cards](cards.md#cards))

## Get all tasks
- `GET /v4/tasks` - Returns all tasks in your account in a paginated response.
- `GET /v4/tasks/updated_after/YYYYMMDDTHHmmss` - Returns all tasks in your account that have been updated after the specified time in a paginated response. Example value: `20180216T210047`.

- `GET /v3/tasks` - Returns all tasks in your account (This may be a large dataset).
- `GET /v3/tasks/updated_after/YYYYMMDDTHHmmss` - Returns all tasks in your account that have been updated after the specified time. Example value: `20180216T210047`.

- `GET /v2/tasks` - Returns all tasks in your account (This may be a large dataset). ***DEPRECATED***
- `GET /v2/tasks?updated_after=YYYYMMDDTHHmmss` - Returns all tasks in your account that have been updated after the specified time. Example value: `20180216T210047`. ***DEPRECATED***

| Response fields  | Description/format                         |
| ---------------- |--------------------------------------------|
| id               | Integer                                    |
| company_card_id  | ***only v2*** Integer                      |
| company_task_id  | Integer                                    |
| title            | String                                     |
| description      | String                                     |
| project_id       | Integer, ID of project                     |
| parent_task_id   | Integer, ID of parent task                 |
| role             | Integer, ID of role                        |
| low_estimate     | ***only v2*** Decimal                      |
| high_estimate    | ***only v2*** Decimal                      |
| forecast         | ***only v2*** Decimal                      |
| estimate         | ***only v3 & v4*** Decimal                 |
| remaining        | Decimal                                    |
| approved         | Boolean                                    |
| start_date       | Date                                       |
| end_date         | Date                                       |
| bug              | Boolean                                    |
| high_priority    | Boolean                                    |
| un_billable      | Boolean                                    |
| blocked          | Boolean                                    |
| sprint           | Integer, ID of sprint                      |
| workflow_column  | Integer, ID of workflow column             |
| milestone        | Integer, ID of milestone                   |
| assigned_persons | List<Integer>, List ID of assigned persons |
| labels           | List<Integer>, List ID of labels           |
| owner_id         | Integer, ID of person                      |
| created_by       | Integer, ID of person                      |
| updated_by       | Integer, ID of person                      |
| created_at       | Date                                       |
| updated_at       | Date                                       |

### Sample JSON response

```javascript
[
   {
      "id":1,
      "company_card_id": 1,
      "company_task_id": 1,
      "title":"Design login screen",
      "description":"",
      "project_id":1,
      "parent_task_id":10,
      "role":1,
      "low_estimate":10.0,
      "high_estimate":20.0,
      "forecast":26.0,
      "remaining":26.0,
      "approved":true,
      "start_date":"2017-01-01",
      "end_date":"2017-01-20",
      "bug":false,
      "high_priority":false,
      "un_billable":false,
      "blocked":false,
      "sprint":1,
      "workflow_column":2,
      "milestone":1,
      "assigned_persons":[1,2,3],
      "labels":[1,2,3],
      "owner_id":1,
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z"
   }, ...
]
```

## Get tasks in project

- `GET /v3/projects/{projectId}/tasks` - Returns all tasks of the project.
- `GET /v3/projects/{projectId}/tasks/updated_after/YYYYMMDDTHHmmss` - Returns all tasks of the project that have been updated after the specified time. Example value: `20180216T210047`.

- `GET /v2/projects/{projectId}/tasks` - Returns all tasks of the project. ***DEPRECATED***
- `GET /v2/projects/{projectId}/tasks?updated_after=YYYYMMDDTHHmmss` - Returns all tasks of the project that have been updated after the specified time. Example value: `20180216T210047`. ***DEPRECATED***

| Response fields  | Description/format                                |
| ---------------- | ------------------------------------------------- |
| id               | Integer                                           |
| company_card_id  | ***only v2*** Integer                             |
| company_task_id  | Integer                                           |
| title            | String                                            |
| description      | String                                            |
| project_id       | Integer, ID of project                            |
| parent_task_id   | Integer, ID of parent task                        |
| role             | Integer, ID of role                               |
| low_estimate     | ***only v2*** Decimal                             |
| high_estimate    | ***only v2*** Decimal                             |
| forecast         | ***only v2*** Decimal                             |
| estimate         | ***only v3*** Decimal                             |
| remaining        | Decimal                                           |
| approved         | Boolean                                           |
| start_date       | Date                                              |
| end_date         | Date                                              |
| bug              | Boolean                                           |
| high_priority    | Boolean                                           |
| un_billable      | Boolean                                           |
| blocked          | Boolean                                           |
| sprint           | Integer, ID of sprint                             |
| workflow_column  | Integer, ID of workflow column                    |
| milestone        | Integer, ID of milestone                          |
| assigned_persons | List<Integer>, List ID of assigned persons        |
| labels           | List<Integer>, List ID of labels                  |
| owner_id         | Integer, ID of person                             |
| created_by       | Integer, ID of person                             |
| updated_by       | Integer, ID of person                             |
| created_at       | Date                                              |
| updated_at       | Date                                              |

### Sample JSON response

```javascript
[
   {
      "id":1,
      "company_card_id": 1,
      "company_task_id": 1,
      "title":"Design login screen",
      "description":"",
      "project_id":1,
      "parent_task_id":10,
      "role":1,
      "low_estimate":10.0,
      "high_estimate":20.0,
      "forecast":26.0,
      "remaining":26.0,
      "approved":true,
      "start_date":"2017-01-01",
      "end_date":"2017-01-20",
      "bug":false,
      "high_priority":false,
      "un_billable":false,
      "blocked":false,
      "sprint":1,
      "workflow_column":2,
      "milestone":1,
      "assigned_persons":[1,2,3],
      "labels":[1,2,3],
      "owner_id":1,
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z"
   }, ...
]
```

## Get task

- `GET /v3/tasks/{taskId}` - Returns a specific task.

- `GET /v2/tasks/{taskId}` - Returns a specific task. ***DEPRECATED***

| Response fields  | Description/format                                |
| ---------------- | ------------------------------------------------- |
| id               | Integer                                           |
| company_card_id  | ***only v2*** Integer                             |
| company_task_id  | Integer                                           |
| title            | String                                            |
| description      | String                                            |
| project_id       | Integer, ID of project                            |
| parent_task_id   | Integer, ID of parent task                        |
| role             | Integer, ID of role                               |
| low_estimate     | ***only v2*** Decimal                             |
| high_estimate    | ***only v2*** Decimal                             |
| forecast         | ***only v2*** Decimal                             |
| estimate         | ***only v3*** Decimal                             |
| remaining        | Decimal                                           |
| approved         | Boolean                                           |
| start_date       | Date                                              |
| end_date         | Date                                              |
| bug              | Boolean                                           |
| high_priority    | Boolean                                           |
| un_billable      | Boolean                                           |
| blocked          | Boolean                                           |
| sprint           | Integer, ID of sprint                             |
| workflow_column  | Integer, ID of workflow column                    |
| milestone        | Integer, ID of milestone                          |
| assigned_persons | List<Integer>, List ID of assigned persons        |
| labels           | List<Integer>, List ID of labels                  |
| owner_id         | Integer, ID of person                             |
| created_by       | Integer, ID of person                             |
| updated_by       | Integer, ID of person                             |
| created_at       | Date                                              |
| updated_at       | Date                                              |

### Sample JSON response

```javascript
{
   "id":1,
   "company_card_id": 1,
   "company_task_id": 1,
   "title":"Design login screen",
   "description":"",
   "role":1,
   "project_id":1, 
   "parent_task_id":10, 
   "low_estimate":10.0,
   "high_estimate":20.0,
   "forecast":26.0,
   "remaining":26.0,
   "approved":true,
   "start_date":"2017-01-01",
   "end_date":"2017-01-20",
   "bug":false,
   "high_priority":false,
   "un_billable":false,
   "blocked":false,
   "sprint":1,
   "workflow_column":2,
   "milestone":1,
   "assigned_persons":[1,2,3],
   "labels":[1,2,3],
   "owner_id":1,
   "created_by":1,
   "updated_by":1,
   "created_at":"2017-01-14T18:46:56Z",
   "updated_at":"2017-01-14T18:47:58Z"
}
```

## Get task by company task id

- `GET /v3/tasks/company_task_id/{companyTaskId}` - Returns a specific task.

- `GET /v2/tasks/company_task_id/{companyTaskId}` - Returns a specific task. ***DEPRECATED***

| Response fields  | Description/format                                |
| ---------------- | ------------------------------------------------- |
| id               | Integer                                           |
| company_card_id  | ***only v2*** Integer                             |
| company_task_id  | Integer                                           |
| title            | String                                            |
| description      | String                                            |
| project_id       | Integer, ID of project                            |
| parent_task_id   | Integer, ID of parent task                        |
| role             | Integer, ID of role                               |
| low_estimate     | ***only v2*** Decimal                             |
| high_estimate    | ***only v2*** Decimal                             |
| forecast         | ***only v2*** Decimal                             |
| estimate         | ***only v3*** Decimal                             |
| remaining        | Decimal                                           |
| approved         | Boolean                                           |
| start_date       | Date                                              |
| end_date         | Date                                              |
| bug              | Boolean                                           |
| high_priority    | Boolean                                           |
| un_billable      | Boolean                                           |
| blocked          | Boolean                                           |
| sprint           | Integer, ID of sprint                             |
| workflow_column  | Integer, ID of workflow column                    |
| milestone        | Integer, ID of milestone                          |
| assigned_persons | List<Integer>, List ID of assigned persons        |
| labels           | List<Integer>, List ID of labels                  |
| owner_id         | Integer, ID of person                             |
| created_by       | Integer, ID of person                             |
| updated_by       | Integer, ID of person                             |
| created_at       | Date                                              |
| updated_at       | Date                                              |

### Sample JSON response

```javascript
{
   "id":1,
   "company_card_id": 1,
   "company_task_id": 1,
   "title":"Design login screen",
   "description":"",
   "role":1,
   "project_id":1,
   "parent_task_id":10, 
   "low_estimate":10.0,
   "high_estimate":20.0,
   "forecast":26.0,
   "remaining":26.0,
   "approved":true,
   "start_date":"2017-01-01",
   "end_date":"2017-01-20",
   "bug":false,
   "high_priority":false,
   "un_billable":false,
   "blocked":false,
   "sprint":1,
   "workflow_column":2,
   "milestone":1,
   "assigned_persons":[1,2,3],
   "labels":[1,2,3],
   "owner_id":1,
   "created_by":1,
   "updated_by":1,
   "created_at":"2017-01-14T18:46:56Z",
   "updated_at":"2017-01-14T18:47:58Z"
}
```

## Get children tasks

- `GET /v3/tasks/{taskId}/children` - Returns an array of children tasks, that belongs to the specific task.

- `GET /v2/tasks/{taskId}/children` - Returns an array of children tasks, that belongs to the specific task. ***DEPRECATED***

| Response fields  | Description/format                                |
| ---------------- | ------------------------------------------------- |
| id               | Integer                                           |
| company_card_id  | ***only v2*** Integer                             |
| company_task_id  | Integer                                           |
| title            | String                                            |
| description      | String                                            |
| project_id       | Integer, ID of project                            |
| parent_task_id   | Integer, ID of parent task                        |
| role             | Integer, ID of role                               |
| low_estimate     | ***only v2*** Decimal                             |
| high_estimate    | ***only v2*** Decimal                             |
| forecast         | ***only v2*** Decimal                             |
| estimate         | ***only v3*** Decimal                             |
| remaining        | Decimal                                           |
| approved         | Boolean                                           |
| start_date       | Date                                              |
| end_date         | Date                                              |
| bug              | Boolean                                           |
| high_priority    | Boolean                                           |
| un_billable      | Boolean                                           |
| blocked          | Boolean                                           |
| sprint           | Integer, ID of sprint                             |
| workflow_column  | Integer, ID of workflow column                    |
| milestone        | Integer, ID of milestone                          |
| assigned_persons | List<Integer>, List ID of assigned persons        |
| labels           | List<Integer>, List ID of labels                  |
| owner_id         | Integer, ID of person                             |
| created_by       | Integer, ID of person                             |
| updated_by       | Integer, ID of person                             |
| created_at       | Date                                              |
| updated_at       | Date                                              |

### Sample JSON response

```javascript
[
   {
      "id":1,
      "company_card_id": 1,
      "company_task_id": 1,
      "title":"Design login screen",
      "description":"",
      "project_id":1,
      "parent_task_id":10,
      "role":1,
      "low_estimate":10.0,
      "high_estimate":20.0,
      "forecast":26.0,
      "remaining":26.0,
      "approved":true,
      "start_date":"2017-01-01",
      "end_date":"2017-01-20",
      "bug":false,
      "high_priority":false,
      "un_billable":false,
      "blocked":false,
      "sprint":1,
      "workflow_column":2,
      "milestone":1,
      "assigned_persons":[1,2,3],
      "labels":[1,2,3],
      "owner_id":1,
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z"
   }, ...
]
```


## Get comments for a task

- `GET /v2/tasks/{taskId}/comments` - Returns a task's comments.

| Response fields | Description/format                        |
| --------------- | ----------------------------------------- |
| id              | Integer                                   |
| card_id         | Integer, deprecated use 'task_id' instead |
| task_id         | Integer                                   |
| comment         | String                                    |
| created_at      | Date                                      |
| person_id       | Integer, ID of person                     |

### Sample JSON response

```javascript
[
   {
      "id":1,
      "card_id":5,
      "task_id":5,
      "comment":"<div>This is a comment.</div>",
      "created_at":"2019-01-14T18:46:56Z",
      "person_id":1
   }, ...
]
```
## Create comment on a task

- `POST /v2/tasks/{taskId}/comments` - Creates a new comment on a task and returns the created comment.

| Request fields   | Description/format                         |
| ---------------- | ------------------------------------------ |
| comment          | String                                     |
| person_id        | Integer, ID of a person                    |

### Sample JSON request

POST https://api.forecast.it/api/v2/tasks/2/comments

```javascript
{
   "comment":"Some comment",
   "person_id":1
}
```


## Create task

- `POST /v3/tasks` - Creates a new task. Returns the same object as getting a single task.

- `POST /v2/tasks` - Creates a new task. Returns the same object as getting a single task. ***DEPRECATED***

| Request fields   | Description/format                         |
| ---------------- | ------------------------------------------ |
| title            | String                                     |
| description      | String                                     |
| role             | Integer, ID of role                        |
| project_id       | (Required) Integer, ID of project          |
| parent_task_id   | Integer, ID of parent task                 |
| low_estimate     | ***only v2*** Decimal                      |
| high_estimate    | ***only v2*** Decimal                      |
| estimate         | ***only v3*** Decimal                      |
| approved         | Boolean (Defaults to true)                 |
| start_date       | Date                                       |
| end_date         | Date                                       |
| bug              | Boolean                                    |
| high_priority    | Boolean                                    |
| un_billable      | Boolean                                    |
| blocked          | Boolean                                    |
| sprint           | Integer, ID of sprint                      |
| workflow_column  | Integer, ID of workflow column             |
| milestone        | Integer, ID of milestone                   |
| assigned_persons | List<Integer>, List ID of assigned persons |
| labels           | List<Integer>, List ID of labels           |
| owner_id         | Integer, ID of person                      |

### Sample JSON request

POST https://api.forecast.it/api/v2/tasks

```javascript
{
   "title":"Implement login page",
   "role":2,
   "project_id":1,
   "parent_task_id":10, 
   "low_estimate":20.0,
   "high_estimate":40.0,
   "approved":true,
   "sprint":2,
   "owner_id":1
}
```

## Update task

- `PUT /v3/tasks/{taskId}` - Updates an task. Returns the same object as getting a single task.

- `PUT /v2/tasks/{taskId}` - Updates an task. Returns the same object as getting a single task. ***DEPRECATED***

| Request fields   | Description/format                                                                        |
| ---------------- | ----------------------------------------------------------------------------------------- |
| title            | String                                                                                    |
| description      | String                                                                                    |
| role             | Integer, ID of role                                                                       |
| project_id       | Integer, ID of project                                                                    |
| parent_task_id   | Integer, ID of parent task                                                                |
| low_estimate     | ***only v2*** Decimal                                                                     |
| high_estimate    | ***only v2*** Decimal                                                                     |
| estimate         | ***only v3*** Decimal                                                                     |
| remaining        | Decimal (available only if the task's project has remaining_auto_calculated set to false) |
| approved         | Boolean (Defaults to true)                                                                |
| start_date       | Date                                                                                      |
| end_date         | Date                                                                                      |
| bug              | Boolean                                                                                   |
| high_priority    | Boolean                                                                                   |
| un_billable      | Boolean                                                                                   |
| blocked          | Boolean                                                                                   |
| sprint           | Integer, ID of sprint                                                                     |
| workflow_column  | Integer, ID of workflow column                                                            |
| milestone        | Integer, ID of milestone                                                                  |
| assigned_persons | List<Integer>, List ID of assigned persons                                                |
| labels           | List<Integer>, List ID of labels                                                          |
| owner_id         | Integer, ID of person                                                                     |

### Sample JSON request

PUT https://api.forecast.it/api/v2/tasks/1

```javascript
{
   "title":"Implement and test login page"
}
```

## Delete task

- `DELETE /v2/tasks/{taskId}` - Deletes a task.

### Sample JSON request

DELETE https://api.forecast.it/api/v2/tasks/1

## Get deleted tasks

- `GET /v2/tasks/deleted` - Returns all tasks that have been deleted.
- `GET /v2/tasks/deleted?updated_after=YYYYMMDDTHHmmss` - Returns all tasks that have been deleted. after the specified time. Example value: `20180216T210047`.
- `GET /v2/tasks/deleted?includeAllFields=true` - Includes a greater list of fields on the deleted task.

#### Note that the 2 query parameters can be combined.

| Response fields | Description/format                            |
| --------------- | --------------------------------------------- |
| id              | Integer, ID of the task that has been deleted |
| deleted_by      | Integer, ID of person                         |
| deleted_at      | Date                                          |

#### If includeAllFields query parameter is set the below fields will also be returned:

| Response fields      | Description/format                                         |
| -------------------- | ---------------------------------------------------------- |
| company_task_id      | String, Your ID of the task that has been deleted - fx T46 |
| title                | String, Title of task                                      |
| description          | String, Description of task                                |
| low_estimate         | Decimal, Low estimate - if project is using hours          |
| high_estimate        | Decimal, High estimate - if project is using hours         |
| forecast             | Decimal, Forecast - if project is using hours              |
| low_estimate_points  | Decimal, Low estimate - if project is using points         |
| high_estimate_points | Decimal, High estimate - if project is using points        |
| forecast_points      | Decimal, Forecast - if project is using points             |
| start_date           | Date, Start date of task                                   |
| end_date             | Date, End date of task                                     |
| blocked              | Boolean, If task is blocked                                |
| bug                  | Boolean, If task is marked as a bug                        |
| billable             | Boolean, If task is billable                               |
| high_priority        | Boolean, If task is marked as high priority                |

### Sample JSON response

```javascript
[
   {
      "id":1,
      "deleted_by":1,
      "deleted_at":"2017-01-14T18:46:56Z",
   }, ...
]
```

### Sample JSON response - if includeAllFields query parameter is set:

```javascript
[
   {
        "id": 1,
        "deleted_by":1,
        "deleted_at":"2017-01-14T18:46:56Z",
        "company_task_id": "T1",
        "title": "Login Page",
        "description": "Design and build new login page",
        "low_estimate": 7,
        "high_estimate": 12,
        "forecast": 10.5,
        "low_estimate_points": null,
        "high_estimate_points": null,
        "forecast_points": null,
        "start_date": "2019-02-01",
        "end_date": "2019-02-05",
        "blocked": false,
        "bug": false,
        "billable": true,
        "high_priority": false
    }, ...
]
```
