# Placeholder Allocations

## Get all placeholder allocations

* `GET /placeholder_allocations` - Returns all placeholder allocations.

| Response fields | Description/format                   |
|-----------------|--------------------------------------|
| id              | Integer                              |
| placeholder_id  | Integer, ID of placeholder           |
| start_date      | Date                                 |
| end_date        | Date                                 |
| monday          | Integer, allocation hours in minutes |
| tuesday         | Integer, allocation hours in minutes |
| wednesday       | Integer, allocation hours in minutes |
| thursday        | Integer, allocation hours in minutes |
| friday          | Integer, allocation hours in minutes |
| saturday        | Integer, allocation hours in minutes |
| sunday          | Integer, allocation hours in minutes |
| notes           | String                               |
| created_by      | Integer, ID of person                |
| updated_by      | Integer, ID of person                |
| created_at      | Date                                 |
| updated_at      | Date                                 |

### Sample JSON response

```json
[
  {
    "id": 5390,
    "placeholder_id": 988,
    "start_date": "2021-12-07",
    "end_date": "2022-01-27",
    "monday": 480,
    "tuesday": 480,
    "wednesday": 480,
    "thursday": 480,
    "friday": 480,
    "saturday": 0,
    "sunday": 0,
    "notes": null,
    "created_by": 1,
    "updated_by": 1,
    "created_at": "2023-02-27T15:52:08+01:00",
    "updated_at": "2023-02-27T15:52:08+01:00"
  },
  ...
]
```

## Get all placeholder allocations for placeholder

* `GET /placeholders/{placeholderId}/placeholder_allocations` - Returns all placeholder allocations for a placeholder.

| Response fields | Description/format                   |
|-----------------|--------------------------------------|
| id              | Integer                              |
| placeholder_id  | Integer, ID of placeholder           |
| start_date      | Date                                 |
| end_date        | Date                                 |
| monday          | Integer, allocation hours in minutes |
| tuesday         | Integer, allocation hours in minutes |
| wednesday       | Integer, allocation hours in minutes |
| thursday        | Integer, allocation hours in minutes |
| friday          | Integer, allocation hours in minutes |
| saturday        | Integer, allocation hours in minutes |
| sunday          | Integer, allocation hours in minutes |
| notes           | String                               |
| created_by      | Integer, ID of person                |
| updated_by      | Integer, ID of person                |
| created_at      | Date                                 |
| updated_at      | Date                                 |

### Sample JSON response

```json
[
  {
    "id": 5390,
    "placeholder_id": 988,
    "start_date": "2021-12-07",
    "end_date": "2022-01-27",
    "monday": 480,
    "tuesday": 480,
    "wednesday": 480,
    "thursday": 480,
    "friday": 480,
    "saturday": 0,
    "sunday": 0,
    "notes": null,
    "created_by": 1,
    "updated_by": 1,
    "created_at": "2023-02-27T15:52:08+01:00",
    "updated_at": "2023-02-27T15:52:08+01:00"
  },
  ...
]
```

## Get all placeholder allocations for a project

* `GET /projects/{projectId}/placeholder_allocations` - Returns all placeholder allocations for a project.

| Response fields | Description/format                   |
|-----------------|--------------------------------------|
| id              | Integer                              |
| placeholder_id  | Integer, ID of placeholder           |
| start_date      | Date                                 |
| end_date        | Date                                 |
| monday          | Integer, allocation hours in minutes |
| tuesday         | Integer, allocation hours in minutes |
| wednesday       | Integer, allocation hours in minutes |
| thursday        | Integer, allocation hours in minutes |
| friday          | Integer, allocation hours in minutes |
| saturday        | Integer, allocation hours in minutes |
| sunday          | Integer, allocation hours in minutes |
| notes           | String                               |
| created_by      | Integer, ID of person                |
| updated_by      | Integer, ID of person                |
| created_at      | Date                                 |
| updated_at      | Date                                 |

### Sample JSON response

```json
[
  {
    "id": 5390,
    "placeholder_id": 988,
    "start_date": "2021-12-07",
    "end_date": "2022-01-27",
    "monday": 480,
    "tuesday": 480,
    "wednesday": 480,
    "thursday": 480,
    "friday": 480,
    "saturday": 0,
    "sunday": 0,
    "notes": null,
    "created_by": 1,
    "updated_by": 1,
    "created_at": "2023-02-27T15:52:08+01:00",
    "updated_at": "2023-02-27T15:52:08+01:00"
  },
  ...
]
```

## Get all placeholder allocations for a connected project

* `GET /connected_projects/{connectedProjectId}/placeholder_allocations` - Returns all placeholder allocations for a
  connected project.

| Response fields | Description/format                   |
|-----------------|--------------------------------------|
| id              | Integer                              |
| placeholder_id  | Integer, ID of placeholder           |
| start_date      | Date                                 |
| end_date        | Date                                 |
| monday          | Integer, allocation hours in minutes |
| tuesday         | Integer, allocation hours in minutes |
| wednesday       | Integer, allocation hours in minutes |
| thursday        | Integer, allocation hours in minutes |
| friday          | Integer, allocation hours in minutes |
| saturday        | Integer, allocation hours in minutes |
| sunday          | Integer, allocation hours in minutes |
| notes           | String                               |
| created_by      | Integer, ID of person                |
| updated_by      | Integer, ID of person                |
| created_at      | Date                                 |
| updated_at      | Date                                 |

### Sample JSON response

```json
[
  {
    "id": 5390,
    "placeholder_id": 988,
    "start_date": "2021-12-07",
    "end_date": "2022-01-27",
    "monday": 480,
    "tuesday": 480,
    "wednesday": 480,
    "thursday": 480,
    "friday": 480,
    "saturday": 0,
    "sunday": 0,
    "notes": null,
    "created_by": 1,
    "updated_by": 1,
    "created_at": "2023-02-27T15:52:08+01:00",
    "updated_at": "2023-02-27T15:52:08+01:00"
  },
  ...
]
```

## Get a placeholder allocation

* `GET /placeholder_allocations/{placeholderAllocationId}` - Returns a placeholder allocation.

| Response fields | Description/format                   |
|-----------------|--------------------------------------|
| id              | Integer                              |
| placeholder_id  | Integer, ID of placeholder           |
| start_date      | Date                                 |
| end_date        | Date                                 |
| monday          | Integer, allocation hours in minutes |
| tuesday         | Integer, allocation hours in minutes |
| wednesday       | Integer, allocation hours in minutes |
| thursday        | Integer, allocation hours in minutes |
| friday          | Integer, allocation hours in minutes |
| saturday        | Integer, allocation hours in minutes |
| sunday          | Integer, allocation hours in minutes |
| notes           | String                               |
| created_by      | Integer, ID of person                |
| updated_by      | Integer, ID of person                |
| created_at      | Date                                 |
| updated_at      | Date                                 |

### Sample JSON response

```json
{
  "id": 5390,
  "placeholder_id": 988,
  "start_date": "2021-12-07",
  "end_date": "2022-01-27",
  "monday": 480,
  "tuesday": 480,
  "wednesday": 480,
  "thursday": 480,
  "friday": 480,
  "saturday": 0,
  "sunday": 0,
  "notes": null,
  "created_by": 1,
  "updated_by": 1,
  "created_at": "2023-02-27T15:52:08+01:00",
  "updated_at": "2023-02-27T15:52:08+01:00"
}

```

## Create placeholder allocation

* `POST /placeholder_allocations` - Creates a new placeholder allocation. Returns the same object as getting a single
  allocation.

| Request fields | Description/format                   |
|----------------|--------------------------------------|
| placeholder_id | Integer, ID of placeholder           |
| start_date     | Date                                 |
| end_date       | Date                                 |
| monday         | Integer, allocation hours in minutes |
| tuesday        | Integer, allocation hours in minutes |
| wednesday      | Integer, allocation hours in minutes |
| thursday       | Integer, allocation hours in minutes |
| friday         | Integer, allocation hours in minutes |
| saturday       | Integer, allocation hours in minutes |
| sunday         | Integer, allocation hours in minutes |
| notes          | String                               |

```json
{
  "placeholder_id": 988,
  "start_date": "2023-01-01",
  "end_date": "2023-04-01",
  "monday": 480,
  "tuesday": 480,
  "wednesday": 480,
  "thursday": 480,
  "friday": 480,
  "saturday": 0,
  "sunday": 0,
  "notes": "Created through API"
}
```

## Update placeholder allocation


* `PUT /placeholder_allocations/{placeholderAllocationId}` - Updated a placeholder allocation. Returns the same object as getting a single
  allocation.

| Request fields | Description/format                   |
|----------------|--------------------------------------|
| placeholder_id | Integer, ID of placeholder           |
| start_date     | Date                                 |
| end_date       | Date                                 |
| monday         | Integer, allocation hours in minutes |
| tuesday        | Integer, allocation hours in minutes |
| wednesday      | Integer, allocation hours in minutes |
| thursday       | Integer, allocation hours in minutes |
| friday         | Integer, allocation hours in minutes |
| saturday       | Integer, allocation hours in minutes |
| sunday         | Integer, allocation hours in minutes |
| notes          | String                               |

```json
{
  "placeholder_id": 988,
  "start_date": "2023-01-01",
  "end_date": "2023-04-01",
  "monday": 480,
  "tuesday": 480,
  "wednesday": 480,
  "thursday": 480,
  "friday": 480,
  "saturday": 0,
  "sunday": 0,
  "notes": "Created through API"
}
```

## Delete placeholder allocation

* `DELETE /placeholder_allocations/{placeholderAllocationId}` - Deletes a placeholder allocation.
