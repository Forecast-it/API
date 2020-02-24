# Projects

## Get projects

-  `GET /projects` - Returns all projects.

| Response fields              | Description/format                                               |
| ---------------------------- | ---------------------------------------------------------------- |
| id                           | Integer                                                          |
| company_project_id           | Integer                                                          |
| name                         | String                                                           |
| connected_project            | Integer, ID of connected project                                 |
| stage                        | String (PLANNING, RUNNING, HALTED, DONE)                         |
| status_color                 | String (GREEN, YELLOW, RED)                                      |
| status_description           | String                                                           |
| description                  | String                                                           |
| color                        | String                                                           |
| estimation_units             | String (HOURS, POINTS)                                           |
| minutes_per_estimation_point | Integer                                                          |
| budget                       | Double                                                           |
| billable                     | Boolean (Deprecated)                                             |
| budget_type                  | String (FIXED_PRICE, NON_BILLABLE, TIME_AND_MATERIALS, RETAINER) |
| use_sprints                  | Boolean                                                          |
| sprint_length                | Integer                                                          |
| start_date                   | Date                                                             |
| end_date                     | Date                                                             |
| card_levels                  | Integer (1 or 2)                                                 |
| client                       | Integer, ID of client                                            |
| rate_card                    | Integer, ID of rate card                                         |
| remaining_auto_calculated    | Boolean                                                          |
| use_project_allocations      | Boolean                                                          |
| labels                       | List<Integer>, List ID of labels                                 |
| external_refs                | List of references to other systems                              |
| created_by                   | Integer, ID of person                                            |
| updated_by                   | Integer, ID of person                                            |
| created_at                   | Date                                                             |
| updated_at                   | Date                                                             |

### Sample JSON response

```javascript
[
   {
      "id":1,
      "company_project_id":1,
      "name":"Website project",
      "stage":"PLANNING",
      "status": "GREEN",
      "status_description": "",
      "description": "",
      "color": "#FF7C75",
      "estimation_units": "HOURS",
      "minutes_per_estimation_point": 480,
      "budget": 1234.56,
      "billable": true,
      "use_sprints": true,
      "sprint_length": 14,
      "start_date": "2017-01-01",
      "end_date": "2018-01-01",
      "card_levels": 1,
      "client": 1,
      "rate_card": 1,
      "remaining_auto_calculated": false,
      "use_project_allocations": true,
      "labels": [1,2],
      "external_refs": [],
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z"
   }, ...
]
```

## Get project

-  `GET /projects/{projectId}` - Returns a specific project.

| Response fields              | Description/format                                               |
| ---------------------------- | ---------------------------------------------------------------- |
| id                           | Integer                                                          |
| company_project_id           | Integer                                                          |
| connected_project            | Integer, ID of connected project                                 |
| name                         | String                                                           |
| stage                        | String (PLANNING, RUNNING, HALTED, DONE)                         |
| status                       | String (GREEN, YELLOW, RED)                                      |
| status_description           | String                                                           |
| description                  | String                                                           |
| color                        | String                                                           |
| estimation_units             | String (HOURS, POINTS)                                           |
| minutes_per_estimation_point | Integer                                                          |
| budget                       | Double                                                           |
| billable                     | Boolean (Deprecated)                                             |
| budget_type                  | String (FIXED_PRICE, NON_BILLABLE, TIME_AND_MATERIALS, RETAINER) |
| use_sprints                  | Boolean                                                          |
| sprint_length                | Integer                                                          |
| start_date                   | Date                                                             |
| end_date                     | Date                                                             |
| card_levels                  | Integer (1 or 2)                                                 |
| client                       | Integer, ID of client                                            |
| rate_card                    | Integer, ID of rate card                                         |
| remaining_auto_calculated    | Boolean                                                          |
| use_project_allocations      | Boolean                                                          |
| labels                       | List<Integer>, List ID of labels                                 |
| external_refs                | List of references to other systems                              |
| created_by                   | Integer, ID of person                                            |
| updated_by                   | Integer, ID of person                                            |
| created_at                   | Date                                                             |
| updated_at                   | Date                                                             |

### Sample JSON response

```javascript
{
   "id":1,
   "company_project_id":1,
   "name":"Website project",
   "stage":"PLANNING",
   "status": "GREEN",
   "status_description": "",
   "description": "",
   "color": "#FF7C75",
   "estimation_units": "HOURS",
   "minutes_per_estimation_point": 480,
   "budget": 1234.56,
   "billable": true,
   "use_sprints": true,
   "sprint_length": 14,
   "start_date": "2017-01-01",
   "end_date": "2018-01-01",
   "card_levels": 1,
   "client": 1,
   "rate_card": 1,
   "remaining_auto_calculated": false,
   "use_project_allocations": true,
   "labels": [1,2],
   "external_refs": [],
   "created_by":1,
   "updated_by":1,
   "created_at":"2017-01-14T18:46:56Z",
   "updated_at":"2017-01-14T18:47:58Z"
}
```

## Create project

-  `POST /projects` - Creates a new project. Returns the same object as getting a single project.

| Request fields               | Description/format                                                                                |
| ---------------------------- | ------------------------------------------------------------------------------------------------- |
| name                         | String                                                                                            |
| stage                        | String (PLANNING, RUNNING, HALTED, DONE) (Defaults to PLANNING)                                   |
| status                       | String (GREEN, YELLOW, RED) (Defaults to GREEN)                                                   |
| status_description           | String                                                                                            |
| description                  | String                                                                                            |
| estimation_units             | String (HOURS, POINTS) (Defaults to HOURS)                                                        |
| minutes_per_estimation_point | Integer (Defaults to 60)                                                                          |
| budget                       | Double                                                                                            |
| billable                     | Boolean (Defaults to true) (Deprecated)                                                           |
| budget_type                  | String (FIXED_PRICE, NON_BILLABLE, TIME_AND_MATERIALS, RETAINER) (Defaults to TIME_AND_MATERIALS) |
| use_sprints                  | Boolean (Defaults to false)                                                                       |
| sprint_length                | Integer (Defaults to 14)                                                                          |
| start_date                   | Date                                                                                              |
| end_date                     | Date                                                                                              |
| card_levels                  | Integer (1 or 2) (Defaults to 1)                                                                  |
| client                       | Integer, ID of client                                                                             |
| rate_card                    | Integer, ID of rate card                                                                          |
| remaining_auto_calculated    | Boolean (Defaults to true)                                                                        |
| use_project_allocations      | Boolean (Defaults to false)                                                                       |
| labels                       | List<Integer>, List ID of labels                                                                  |

### Sample JSON request

POST https://api.forecast.it/api/v1/projects

```javascript
{
   "name":"Website project",
   "stage":"PLANNING",
   "status":"GREEN",
   "estimation_units":"HOURS",
   "budget":1000,
   "billable":true,
   "use_sprints":true,
   "sprint_length":14
}
```

## Update project

-  `PUT /projects/{projectId}` - Updates a project. Returns the same object as getting a single project.

| Request fields               | Description/format                                               |
| ---------------------------- | ---------------------------------------------------------------- |
| name                         | String                                                           |
| connected_project            | Integer, ID of connected project                                 |
| stage                        | String (PLANNING, RUNNING, HALTED, DONE)                         |
| status                       | String (GREEN, YELLOW, RED)                                      |
| status_description           | String                                                           |
| description                  | String                                                           |
| estimation_units             | String (HOURS, POINTS)                                           |
| minutes_per_estimation_point | Integer                                                          |
| budget                       | Double                                                           |
| billable                     | Boolean (Deprecated)                                             |
| budget_type                  | String (FIXED_PRICE, NON_BILLABLE, TIME_AND_MATERIALS, RETAINER) |
| use_sprints                  | Boolean                                                          |
| sprint_length                | Integer                                                          |
| remaining_auto_calculated    | Boolean                                                          |
| start_date                   | Date                                                             |
| end_date                     | Date                                                             |
| card_levels                  | Integer (1 or 2)                                                 |
| client                       | Integer, ID of client                                            |
| rate_card                    | Integer, ID of rate card                                         |
| use_project_allocations      | Boolean                                                          |
| labels                       | List<Integer>, List ID of labels                                 |

### Sample JSON request

PUT https://api.forecast.it/api/v1/projects/1

```javascript
{
   "stage":"RUNNING",
}
```

## Delete project

-  `DELETE /projects/{projectId}` - Deletes a project.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/projects/1

## Get project statuses

-  `GET /projects/{projectId}/statuses` - Returns the entire status history of a specific project.

### Sample JSON request

GET https://api.forecast.it/api/v1/projects/1/statuses

### Sample JSON response

```javascript
[
   {
      "status_description": "<div>Sample description</div>",
      "status": "GREEN",
      "created_at":"2019-01-04T12:00:00Z",
      "created_by":1
   }, ...
]
```

## Get project financials

-  `GET /projects/{projectId}/financials` - Returns all financial data for the project, broken down to milestone and role level.

Some data in the response is broken down on the individual milestones of the project in arrays called `milestone_breakdown`. Each of these milestones can be further broken down on the individual roles in arrays called `role_breakdown`.

Milestone and role objects with id zero represent data with no milestone or role.

### Sample JSON request

GET https://api.forecast.it/api/v1/projects/1/financials

| Response fields                                    | Description/format                                           |
| -------------------------------------------------- | ------------------------------------------------------------ |
| project_id                                         | Integer                                                      |
| progress                                           | Object                                                       |
| &nbsp;&nbsp;↳ period_value                         | Double, the value for the selected period                    |
| &nbsp;&nbsp;↳ total_value                          | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ milestone_breakdown                  | Array, the same values broken down on the project milestones |
| fixed_price                                        | Object                                                       |
| &nbsp;&nbsp;↳ revenue                              | Double                                                       |
| &nbsp;&nbsp;↳ cost                                 | Double                                                       |
| &nbsp;&nbsp;↳ profit                               | Double                                                       |
| &nbsp;&nbsp;↳ margin                               | Double                                                       |
| actual_price                                       | Object                                                       |
| &nbsp;&nbsp;↳ revenue                              | Object                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ cost                                 | Object                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ profit                               | Object                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ margin                               | Object                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ milestone_breakdown                  | Array, the same values broken down on the project milestones |
| plan_price                                         | Object                                                       |
| &nbsp;&nbsp;↳ revenue                              | Object                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ cost                                 | Object                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ profit                               | Object                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ margin                               | Object                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ milestone_breakdown                  | Array, the same values broken down on the project milestones |
| remaining_price                                    | Object                                                       |
| &nbsp;&nbsp;↳ revenue                              | Object                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ cost                                 | Object                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ profit                               | Object                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ margin                               | Object                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ milestone_breakdown                  | Array, the same values broken down on the project milestones |
| forecast_price                                     | Object                                                       |
| &nbsp;&nbsp;↳ revenue                              | Object                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ cost                                 | Object                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ profit                               | Object                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ margin                               | Object                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ milestone_breakdown                  | Array, the same values broken down on the project milestones |
| actual_variance_to_plan_price                      | Object                                                       |
| &nbsp;&nbsp;↳ revenue                              | Object                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ cost                                 | Object                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ profit                               | Object                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ margin                               | Object                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ milestone_breakdown                  | Array, the same values broken down on the project milestones |
| forecast_variance_to_plan_price                    | Object                                                       |
| &nbsp;&nbsp;↳ revenue                              | Object                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ cost                                 | Object                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ profit                               | Object                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ margin                               | Object                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ milestone_breakdown                  | Array, the same values broken down on the project milestones |
| company_financials                                 | Object                                                       |
| &nbsp;&nbsp;↳ revenue                              | Double                                                       |
| &nbsp;&nbsp;↳ cost                                 | Double                                                       |
| &nbsp;&nbsp;↳ profit                               | Double                                                       |
| &nbsp;&nbsp;↳ margin                               | Double                                                       |
| registered_hours                                   | Object                                                       |
| &nbsp;&nbsp;↳ period_value                         | Double, the value for the selected period                    |
| &nbsp;&nbsp;↳ total_value                          | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ milestone_breakdown                  | Array, the same values broken down on the project milestones |
| remaining_hours                                    | Object                                                       |
| &nbsp;&nbsp;↳ period_value                         | Double, the value for the selected period                    |
| &nbsp;&nbsp;↳ total_value                          | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ milestone_breakdown                  | Array, the same values broken down on the project milestones |
| forecast_hours                                     | Object                                                       |
| &nbsp;&nbsp;↳ period_value                         | Double, the value for the selected period                    |
| &nbsp;&nbsp;↳ total_value                          | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ milestone_breakdown                  | Array, the same values broken down on the project milestones |
| estimated_hours                                    | Object                                                       |
| &nbsp;&nbsp;↳ approved                             | Object, values of only the approved tasks in the project     |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ all                                  | Object, values of all tasks in the project                   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| low_hours                                          | Object                                                       |
| &nbsp;&nbsp;↳ approved                             | Object, values of only the approved tasks in the project     |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ all                                  | Object, values of all tasks in the project                   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| high_hours                                         | Object                                                       |
| &nbsp;&nbsp;↳ approved                             | Object, values of only the approved tasks in the project     |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ all                                  | Object, values of all tasks in the project                   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| allocation                                         | Object                                                       |
| &nbsp;&nbsp;↳ period_value                         | Double, the value for the selected period                    |
| &nbsp;&nbsp;↳ total_value                          | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ milestone_breakdown                  | Array, the same values broken down on the project milestones |
| invoice                                            | Object                                                       |
| &nbsp;&nbsp;↳ invoiced_price                       | Object                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ invoiced_hours                       | Object                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ invoiced_on_fixed_price              | Object                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ invoiced_paid                        | Object                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
| &nbsp;&nbsp;↳ un_invoiced                          | Object                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, the value for the selected period                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, the total value for the project                      |
