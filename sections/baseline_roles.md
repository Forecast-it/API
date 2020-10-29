# Baseline Roles

## Get all baseline roles in a project

- `GET /projects/{projectId}/baseline_roles` - Returns all baseline roles for a given project.

| Response fields         | Description/format                         |
| ----------------------- | ------------------------------------------ |
| id                      | Integer                                    |
| project                 | Integer, ID of project                     |
| milestone               | Integer, ID of milestone                   |
| role                    | Integer, ID of role                        |
| baseline_minutes        | Integer                                    |
| created_by              | Integer, ID of person                      |
| updated_by              | Integer, ID of person                      |
| created_at              | Date                                       |
| updated_at              | Date                                       |

### Sample JSON response

```javascript
[
   {
      "id": 1,
      "project": 1,
      "phase": 1,
      "role": 1,
      "baseline_minutes": 60,
      "created_by":1,
      "updated_by":1,
      "created_at":"2020-01-01T18:46:56Z",
      "updated_at":"2020-01-01T18:47:58Z"
   }, ...
]
```

## Get baseline roles for milestone

- `GET /projects/{projectId}/milestones/{milestoneId}/baseline_roles` - Returns all baseline roles for a given milestone.

| Response fields         | Description/format                         |
| ----------------------- | ------------------------------------------ |
| id                      | Integer                                    |
| project                 | Integer, ID of project                     |
| milestone               | Integer, ID of milestone                   |
| role                    | Integer, ID of role                        |
| baseline_minutes        | Integer                                    |
| created_by              | Integer, ID of person                      |
| updated_by              | Integer, ID of person                      |
| created_at              | Date                                       |
| updated_at              | Date                                       |

### Sample JSON response

```javascript
[
   {
      "id": 1,
      "project": 1,
      "phase": 1,
      "role": 1,
      "baseline_minutes": 60,
      "created_by":1,
      "updated_by":1,
      "created_at":"2020-01-01T18:46:56Z",
      "updated_at":"2020-01-01T18:47:58Z"
   }, ...
]
```

## Get baseline role

- `GET /projects/{projectId}/milestones/{milestoneId}/baseline_roles/{baselineRoleId}` - Returns a specific baseline role.

| Response fields         | Description/format                         |
| ----------------------- | ------------------------------------------ |
| id                      | Integer                                    |
| project                 | Integer, ID of project                     |
| milestone               | Integer, ID of milestone                   |
| role                    | Integer, ID of role                        |
| baseline_minutes        | Integer                                    |
| created_by              | Integer, ID of person                      |
| updated_by              | Integer, ID of person                      |
| created_at              | Date                                       |
| updated_at              | Date                                       |

### Sample JSON response

```javascript
[
   {
      "id": 1,
      "project": 1,
      "phase": 1,
      "role": 1,
      "baseline_minutes": 60,
      "created_by":1,
      "updated_by":1,
      "created_at":"2020-01-01T18:46:56Z",
      "updated_at":"2020-01-01T18:47:58Z"
   }, ...
]
```

## Create baseline role

-  `POST /projects/{projectId}/milestones/{milestoneId}/baseline_roles` - Creates a new baseline role. Returns the same object as getting a single baseline role.

| Request fields     | Description/format               |
| ------------------ | -------------------------------- |
| role               | (Required) Integer, ID of role   |
| baseline_minutes   | (Required) Integer               |

### Sample JSON request

POST https://api.forecast.it/api/v1/projects/1/milestones/1/baselines_roles

```javascript
{
     "role": 1,
     "baseline_minutes": 60
}
```

## Update baseline role

-  `PUT /projects/{projectId}/milestones/{milestoneId}/baseline_roles/{baselineRoleId}` - Updates a baseline role. Returns the same object as getting a single baseline role.

| Request fields   | Description/format                                                                        |
| ---------------- | ----------------------------------------------------------------------------------------- |
| baseline_minutes | Integer                                                                                   |

### Sample JSON request

PUT https://api.forecast.it/api/v1/projects/1/milestones/1/baseline_roles/1

```javascript
{
   "baseline_minutes": 120
}
```

## Delete baseline role

-  `DELETE /projects/{projectId}/milestones/{milestoneId}/baseline_roles/{baselineRoleId}` - Deletes a baseline role.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/projects/1/milestones/1/baseline_roles/1