# Phases

## Get phases

- `GET /projects/{projectId}/phases` - Returns all phases of the project.

| Response fields | Description/format    |
| --------------- | --------------------- |
| id              | Integer               |
| name            | String                |
| project_id      | Integer               |
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
      "name":"Phase 1",
      "start_date":"2017-01-14",
      "end_date":"2017-06-14",
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z"
   }, ...
]
```

## Get phase

- `GET /projects/{projectId}/phases/{phaseId}` - Returns a specific phase.
- `GET /phases/{phaseId}` - Returns a specific phase.

| Response fields | Description/format    |
| --------------- | --------------------- |
| id              | Integer               |
| name            | String                |
| project_id      | Integer               |
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
     "name":"Phase 1",
     "start_date":"2017-01-14",
     "end_date":"2017-06-14",
     "created_by":1,
     "updated_by":1,
     "created_at":"2017-01-14T18:46:56Z",
     "updated_at":"2017-01-14T18:47:58Z"
}
```

## Get all phases

- `GET /phases` - Returns all phases of all projects.

| Response fields | Description/format    |
| --------------- | --------------------- |
| id              | Integer               |
| name            | String                |
| project_id      | Integer               |
| start_date      | Date                  |
| end_date        | Date                  |
| created_by      | Integer, ID of person |
| updated_by      | Integer, ID of person |
| created_at      | Date                  |
| updated_at      | Date                  |

### Sample JSON response

GET https://api.forecast.it/api/v4/phases

```javascript
[
   {
      "id":1,
      "name":"Phase 1",
      "start_date":"2017-01-14",
      "end_date":"2017-06-14",
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z"
   }, ...
]
```

## Create phase

- `POST /projects/{projectId}/phases` - Creates a new phase. Returns the same object as getting a single phase.

| Request fields | Description/format |
| -------------- | ------------------ |
| name           | (Required) String  |
| start_date     | Date               |
| end_date       | Date               |

### Sample JSON request

POST https://api.forecast.it/api/v1/projects/1/phases

```javascript
{
   "name":"Phase 2",
   "start_date":"2017-06-14",
   "end_date":"2017-09-14"
}
```

## Update phase

- `PUT /projects/{projectId}/phases/{phaseId}` - Updates a phase. Returns the same object as getting a single phase.

| Request fields | Description/format |
| -------------- | ------------------ |
| name           | String             |
| start_date     | Date               |
| end_date       | Date               |

### Sample JSON request

PUT https://api.forecast.it/api/v1/projects/1/phases/1

```javascript
{
   "name":"Phase 3"
}
```

## Delete phase

- `DELETE /projects/{projectId}/phases/{phaseId}` - Deletes a phase. Does not delete tasks in the phase.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/projects/1/phases/1
