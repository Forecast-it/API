# Connected Projects

## Get connected projects

* `GET /connected_projects` - Returns all connected projects.

| Response fields              | Description/format     |
| ---------------------------- | ---------------------- |
| id                           | Integer                |
| company_connected_project_id | Integer                |
| name                         | String                 |
| color                        | String                 |
| estimation_units             | String (HOURS, POINTS) |
| use_sprints                  | Boolean                |
| sprint_length                | Integer                |
| minutes_per_estimation_point | Integer                |
| created_by                   | Integer, ID of person  |
| updated_by                   | Integer, ID of person  |
| created_at                   | Date                   |
| updated_at                   | Date                   |

### Sample JSON response

```javascript
[
   {
      "id":1,
      "company_connected_project_id":1,
      "name":"Website connected project",
      "color": "#E3E190",
      "estimation_units": "POINTS",
      "use_sprints": true,
      "sprint_length": 7,
      "minutes_per_estimation_point": 480,
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z"
   }, ...
]
```

## Get connected project

* `GET /connected_projects/{connectedProjectId}` - Returns a specific connected project.

| Response fields              | Description/format     |
| ---------------------------- | ---------------------- |
| id                           | Integer                |
| company_connected_project_id | Integer                |
| name                         | String                 |
| color                        | String                 |
| estimation_units             | String (HOURS, POINTS) |
| use_sprints                  | Boolean                |
| sprint_length                | Integer                |
| minutes_per_estimation_point | Integer                |
| created_by                   | Integer, ID of person  |
| updated_by                   | Integer, ID of person  |
| created_at                   | Date                   |
| updated_at                   | Date                   |

### Sample JSON response

```javascript
{
     "id":1,
     "company_connected_project_id":1,
     "name":"Website connected project",
     "color": "#E3E190",
     "estimation_units": "POINTS",
     "use_sprints": true,
     "sprint_length": 7,
     "minutes_per_estimation_point": 480,
     "created_by":1,
     "updated_by":1,
     "created_at":"2017-01-14T18:46:56Z",
     "updated_at":"2017-01-14T18:47:58Z"
}
```

## Create connected project

* `POST /connected_projects` - Creates a new connected project. Returns the same object as getting a single project.

| Request fields               | Description/format                                                     |
| ---------------------------- | ---------------------------------------------------------------------- |
| name                         | String                                                                 |
| color                        | String                                                                 |
| estimation_units             | String (HOURS, POINTS) (Default is inherited from one of the projects) |
| use_sprints                  | Boolean (If any of the projects uses sprints default is set to true)   |
| sprint_length                | Integer (Default is nherited from one of the projects)                 |
| projects                     | (Requried not empty array) Array, IDs of projects                      |
| minutes_per_estimation_point | Integer (Default is inherited from one of the projects)                |

### Sample JSON request

POST https://api.forecast.it/api/v1/connected_projects

```javascript
{
   "name":"Website project",
   "color": "#E3E190",
   "estimation_units": "POINTS",
   "use_sprints": true,
   "sprint_length": 7,
   "projects": [1,2,3],
   "minutes_per_estimation_point": 480
}
```

## Update connected project

* `PUT /connected_projects/{connectedProjectId}` - Updates a connected project. Returns the same object as getting a single project.

| Request fields               | Description/format     |
| ---------------------------- | ---------------------- |
| name                         | String                 |
| color                        | String                 |
| estimation_units             | String (HOURS, POINTS) |
| use_sprints                  | Boolean                |
| sprint_length                | Integer                |
| minutes_per_estimation_point | Integer                |

### Sample JSON request

PUT https://api.forecast.it/api/v1/connected_projects/1

```javascript
{
   "name":"Website project",
   "color": "#E3E190",
   "estimation_units": "POINTS",
   "use_sprints": true,
   "sprint_length": 7,
   "minutes_per_estimation_point": 480
}
```

## Delete connected project

* `DELETE /connected_projects/{connectedProjectId}` - Deletes a connected project. Does not delete projects in the connected project

### Sample JSON request

DELETE https://api.forecast.it/api/v1/connected_projects/1
