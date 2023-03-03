# Placeholders

## Get placeholders

* `GET /placeholders` - Returns all placeholders.

| Response fields  | Description/format    |
|------------------|-----------------------|
| id               | Integer               |
| name             | String                |
| role_id          | Integer               |
| project_id       | Integer               |
| project_group_id | Integer               |
| department_id    | Integer               |
| created_by       | Integer, ID of person |
| updated_by       | Integer, ID of person |
| created_at       | Date                  |
| updated_at       | Date                  |

### Sample JSON response

```json
[
  {
    "id": 2476,
    "name": "Java Developer",
    "role_id": 15,
    "project_id": 2817,
    "department_id": 41,
    "created_by": 34,
    "updated_by": 34,
    "created_at": "2023-02-28T14:15:46+01:00",
    "updated_at": "2023-02-28T14:15:46+01:00"
  },
  ...
]
```

## Get placeholders for project

* `GET /projects/{projectId}/placeholders` - Returns all placeholders for a project.

| Response fields  | Description/format    |
|------------------|-----------------------|
| id               | Integer               |
| name             | String                |
| role_id          | Integer               |
| project_id       | Integer               |
| project_group_id | Integer               |
| department_id    | Integer               |
| created_by       | Integer, ID of person |
| updated_by       | Integer, ID of person |
| created_at       | Date                  |
| updated_at       | Date                  |

### Sample JSON response

```json
[
  {
    "id": 2476,
    "name": "Java Developer",
    "role_id": 15,
    "project_id": 2817,
    "department_id": 41,
    "created_by": 34,
    "updated_by": 34,
    "created_at": "2023-02-28T14:15:46+01:00",
    "updated_at": "2023-02-28T14:15:46+01:00"
  },
  ...
]
```

## Get placeholders for connected project

* `GET /connected_projects/{connectedProjectId}/placeholders` - Returns all placeholders for a project.

| Response fields  | Description/format    |
|------------------|-----------------------|
| id               | Integer               |
| name             | String                |
| role_id          | Integer               |
| project_id       | Integer               |
| project_group_id | Integer               |
| department_id    | Integer               |
| created_by       | Integer, ID of person |
| updated_by       | Integer, ID of person |
| created_at       | Date                  |
| updated_at       | Date                  |

### Sample JSON response

```json
[
  {
    "id": 2476,
    "name": "Java Developer",
    "role_id": 15,
    "project_id": 2817,
    "department_id": 41,
    "created_by": 34,
    "updated_by": 34,
    "created_at": "2023-02-28T14:15:46+01:00",
    "updated_at": "2023-02-28T14:15:46+01:00"
  },
  ...
]
```

## Get placeholder

* `GET /placeholders/{placeholderId}` - Returns a specific placeholder.

| Response fields  | Description/format                                                                        |
|------------------|-------------------------------------------------------------------------------------------|
| id               | Integer                                                                                   |
| name             | String                                                                                    |
| role_id          | Integer                                                                                   |
| project_id       | Integer                                                                                   |
| project_group_id | Integer                                                                                   |
| department_id    | Integer                                                                                   |
| team_ids         | List of [teamId](teams.md): Integer                                                       |
| skills           | List of objects ([skillId](skills.md): Integer, [skillLevelId](skill_levels.md): Integer) |
| created_by       | Integer, ID of person                                                                     |
| updated_by       | Integer, ID of person                                                                     |
| created_at       | Date                                                                                      |
| updated_at       | Date                                                                                      |

### Sample JSON response

```json
{
  "id": 2489,
  "name": "Awesome",
  "role_id": 15,
  "project_id": 2817,
  "department_id": 42,
  "team_ids": [
    1,
    2
  ],
  "skills": [
    {
      "skillId": 123,
      "skillLevelId": 25
    },
    {
      "skillId": 207,
      "skillLevelId": 26
    }
  ],
  "created_by": 34,
  "updated_by": 34,
  "created_at": "2023-03-02T13:33:20+01:00",
  "updated_at": "2023-03-02T13:34:04+01:00"
}
```

## Create placeholder

* `POST /placeholders` - Creates a new placeholder.

| Request fields   | Description/format                                                                        |
|------------------|-------------------------------------------------------------------------------------------|
| name             | String                                                                                    |
| role_id          | Integer                                                                                   |
| project_id       | Integer                                                                                   |
| project_group_id | Integer                                                                                   |
| department_id    | Integer                                                                                   |
| team_ids         | List of [teamId](teams.md): Integer                                                       |
| skills           | List of objects ([skillId](skills.md): Integer, [skillLevelId](skill_levels.md): Integer) |

Example request:

```json
{
  "name": "Awesome",
  "role_id": 15,
  "project_id": 2817,
  "department_id": 42,
  "team_ids": [
    1,
    2
  ],
  "skills": [
    {
      "skillId": 123,
      "skillLevelId": 25
    },
    {
      "skillId": 207,
      "skillLevelId": 26
    }
  ],
  "created_by": 34,
  "updated_by": 34,
  "created_at": "2023-03-02T13:33:20+01:00",
  "updated_at": "2023-03-02T13:34:04+01:00"
}
```

## Update skill

* `PUT /placeholders/{placeholderId}` - Updates a placeholder.

| Request fields   | Description/format                                                                        |
|------------------|-------------------------------------------------------------------------------------------|
| name             | String                                                                                    |
| role_id          | Integer                                                                                   |
| project_id       | Integer                                                                                   |
| project_group_id | Integer                                                                                   |
| department_id    | Integer                                                                                   |
| team_ids         | List of [teamId](teams.md): Integer                                                       |
| skills           | List of objects ([skillId](skills.md): Integer, [skillLevelId](skill_levels.md): Integer) |

Example request:

```json
{
  "name": "Awesome",
  "role_id": 15,
  "project_id": 2817,
  "department_id": 42,
  "team_ids": [
    1,
    2
  ],
  "skills": [
    {
      "skillId": 123,
      "skillLevelId": 25
    },
    {
      "skillId": 207,
      "skillLevelId": 26
    }
  ],
  "created_by": 34,
  "updated_by": 34,
  "created_at": "2023-03-02T13:33:20+01:00",
  "updated_at": "2023-03-02T13:34:04+01:00"
}
```

## Delete placeholder

* `DELETE /placeholders/{placeholderId}` - Deletes a placeholder and all its allocations.

## Utilization for single placeholder

- `GET /placeholders/{placeholderId}/utilization?start_date=YYYYMMDD&end_date=YYYYMMDD` - Returns a placeholder's
  utilization data for the given timespan. Both `start_date` and `end_date` are required and inclusive.

### Sample JSON request

GET https://api.forecast.it/api/v1/placeholders/988/utilization?start_date=20230309&end_date=20230310

| Response fields                  | Description/format                     |
|----------------------------------|----------------------------------------|
| placeholderId                    | Integer                                |
| plannedNonBillableProjectMinutes | Integer                                |
| plannedBillableProjectMinutes    | Integer                                |
| dates                            | Daily breakdown of utilization numbers |

### Sample JSON response

```json
{
  "placeholderId": "988",
  "plannedNonBillableProjectMinutes": 960,
  "plannedBillableProjectMinutes": 0,
  "dates": [
    {
      "date": "2023-03-09",
      "plannedNonBillableProjectMinutes": 480,
      "plannedBillableProjectMinutes": 0
    },
    {
      "date": "2023-03-10",
      "plannedNonBillableProjectMinutes": 480,
      "plannedBillableProjectMinutes": 0
    }
  ]
}
```

## Utilization for all placeholders

- `GET /placeholders/utilization?start_date=YYYYMMDD&end_date=YYYYMMDD` - Returns all placeholder's
  utilization data for the given timespan. Both `start_date` and `end_date` are required and inclusive.

### Sample JSON request

GET https://api.forecast.it/api/v1/placeholders/utilization?start_date=20230309&end_date=20230310

| Response fields                  | Description/format                     |
|----------------------------------|----------------------------------------|
| placeholderId                    | Integer                                |
| plannedNonBillableProjectMinutes | Integer                                |
| plannedBillableProjectMinutes    | Integer                                |
| dates                            | Daily breakdown of utilization numbers |

### Sample JSON response

```json
[
  {
    "placeholderId": "988",
    "plannedNonBillableProjectMinutes": 960,
    "plannedBillableProjectMinutes": 0,
    "dates": [
      {
        "date": "2023-03-09",
        "plannedNonBillableProjectMinutes": 480,
        "plannedBillableProjectMinutes": 0
      },
      {
        "date": "2023-03-10",
        "plannedNonBillableProjectMinutes": 480,
        "plannedBillableProjectMinutes": 0
      }
    ]
  }, ...
]
```

## Utilization for specific placeholders

- `GET /placeholders/utilization?start_date=YYYYMMDD&end_date=YYYYMMDD&placeholderId={placeholderId}&placeholderId=placeholderId}` - Returns all placeholder's
  utilization data for the given timespan. Both `start_date` and `end_date` are required and inclusive.

### Sample JSON request

GET https://api.forecast.it/api/v1/placeholders/utilization?start_date=20230309&end_date=20230310&placeholderId=374&placeholderId=375

| Response fields                  | Description/format                     |
|----------------------------------|----------------------------------------|
| placeholderId                    | Integer                                |
| plannedNonBillableProjectMinutes | Integer                                |
| plannedBillableProjectMinutes    | Integer                                |
| dates                            | Daily breakdown of utilization numbers |

### Sample JSON response

```json
[
  {
    "placeholderId": "374",
    "plannedNonBillableProjectMinutes": 960,
    "plannedBillableProjectMinutes": 0,
    "dates": [
      {
        "date": "2023-03-09",
        "plannedNonBillableProjectMinutes": 480,
        "plannedBillableProjectMinutes": 0
      },
      {
        "date": "2023-03-10",
        "plannedNonBillableProjectMinutes": 480,
        "plannedBillableProjectMinutes": 0
      }
    ]
  }, ...
]
```
