# Allocations

## Get allocations

* `GET /allocations` - Returns all allocations.

| Response fields   | Description/format                   |
| ----------------- | ------------------------------------ |
| id                | Integer                              |
| project           | Integer, ID of project               |
| non_project_time  | Integer, ID of non project time      |
| connected_project | Integer, ID of connected project     |
| person            | Integer, ID of person                |
| start_date        | Date                                 |
| end_date          | Date                                 |
| monday            | Integer, allocation hours in minutes |
| tuesday           | Integer, allocation hours in minutes |
| wednesday         | Integer, allocation hours in minutes |
| thursday          | Integer, allocation hours in minutes |
| friday            | Integer, allocation hours in minutes |
| saturday          | Integer, allocation hours in minutes |
| sunday            | Integer, allocation hours in minutes |
| notes             | String                               |
| created_by        | Integer, ID of person                |
| updated_by        | Integer, ID of person                |
| created_at        | Date                                 |
| updated_at        | Date                                 |

### Sample JSON response

```javascript
[
   {
      "id":1,
      "project":1,
      "non_project_time":null,
      "connected_project": null,
      "person":1,
      "start_date":"2017-01-14",
      "end_date":"2018-02-14",
      "monday":480,
      "tuesday":480,
      "wednesday":480,
      "thursday":480,
      "friday":480,
      "saturday":0,
      "sunday":0,
      "notes":"Very important client",
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z"
   }, ...
]
```

## Get allocation

* `GET /allocations/{allocationId}` - Returns a specific allocation.

| Response fields   | Description/format                   |
| ----------------- | ------------------------------------ |
| id                | Integer                              |
| project           | Integer, ID of project               |
| non_project_time  | Integer, ID of non project time      |
| connected_project | Integer, ID of connected project     |
| person            | Integer, ID of person                |
| start_date        | Date                                 |
| end_date          | Date                                 |
| monday            | Integer, allocation hours in minutes |
| tuesday           | Integer, allocation hours in minutes |
| wednesday         | Integer, allocation hours in minutes |
| thursday          | Integer, allocation hours in minutes |
| friday            | Integer, allocation hours in minutes |
| saturday          | Integer, allocation hours in minutes |
| sunday            | Integer, allocation hours in minutes |
| notes             | String                               |
| created_by        | Integer, ID of person                |
| updated_by        | Integer, ID of person                |
| created_at        | Date                                 |
| updated_at        | Date                                 |

### Sample JSON response

```javascript
{
   "id":1,
   "project":1,
   "non_project_time":null,
   "connected_project": null,
   "person":1,
   "start_date":"2017-01-14",
   "end_date":"2018-02-14",
   "monday":480,
   "tuesday":480,
   "wednesday":480,
   "thursday":480,
   "friday":480,
   "saturday":0,
   "sunday":0,
   "notes":"Very important client",
   "created_by":1,
   "updated_by":1,
   "created_at":"2017-01-14T18:46:56Z",
   "updated_at":"2017-01-14T18:47:58Z"
}
```

## Create allocation

* `POST /allocations` - Creates a new allocation. Returns the same object as getting a single allocation.

| Request fields    | Description/format                                                       |
| ----------------- | ------------------------------------------------------------------------ |
| project           | (Required\*) Integer, ID of project                                      |
| non_project_time  | (Required\*) Integer, ID of non project time                             |
| connected_project | (Required\*) Integer, ID of connected project                            |
| person            | (Required) Integer, ID of person                                         |
| start_date        | (Required) Date                                                          |
| end_date          | (Required) Date                                                          |
| monday            | Integer, allocation hours in minutes (Defaults to persons working hours) |
| tuesday           | Integer, allocation hours in minutes (Defaults to persons working hours) |
| wednesday         | Integer, allocation hours in minutes (Defaults to persons working hours) |
| thursday          | Integer, allocation hours in minutes (Defaults to persons working hours) |
| friday            | Integer, allocation hours in minutes (Defaults to persons working hours) |
| saturday          | Integer, allocation hours in minutes (Defaults to persons working hours) |
| sunday            | Integer, allocation hours in minutes (Defaults to persons working hours) |
| notes             | String                                                                   |

\* Either a project, connected_project or non_project_time must be supplied

### Sample JSON request

POST https://api.forecast.it/api/v1/allocations

```javascript
{
   "project":1,
   "person":1,
   "start_date":"2017-01-14",
   "end_date":"2018-02-14"
}
```

## Update allocation

* `PUT /allocations/{allocationId}` - Updates an allocation. Returns the same object as getting a single allocation.

| Request fields    | Description/format                   |
| ----------------- | ------------------------------------ |
| project           | Integer, ID of project               |
| non_project_time  | Integer, ID of non project time      |
| connected_project | Integer, ID of connected project     |
| person            | Integer, ID of person                |
| start_date        | Date                                 |
| end_date          | Date                                 |
| monday            | Integer, allocation hours in minutes |
| tuesday           | Integer, allocation hours in minutes |
| wednesday         | Integer, allocation hours in minutes |
| thursday          | Integer, allocation hours in minutes |
| friday            | Integer, allocation hours in minutes |
| saturday          | Integer, allocation hours in minutes |
| sunday            | Integer, allocation hours in minutes |
| notes             | String                               |

### Sample JSON request

PUT https://api.forecast.it/api/v1/allocations/1

```javascript
{
   "start_date":"2017-01-14",
   "end_date":"2018-02-14"
}
```

## Delete allocation

* `DELETE /allocations/{allocationId}` - Deletes a allocation.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/allocations/1
