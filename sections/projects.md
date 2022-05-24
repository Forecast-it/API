# Projects

## Get projects

- `GET /projects` - Returns all projects.

| Response fields              | Description/format                                               |
| ---------------------------- | ---------------------------------------------------------------- |
| id                           | Integer                                                          |
| company_project_id           | Integer                                                          |
| name                         | String                                                           |
| connected_project            | Integer, ID of connected project                                 |
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
| card_levels                  | Integer, deprecated. Use 'task_levels' instead                   |
| task_levels                  | Integer (1 or 2)                                                 |
| client                       | Integer, ID of client                                            |
| rate_card                    | Integer, ID of rate card                                         |
| remaining_auto_calculated    | Boolean                                                          |
| use_project_allocations      | Boolean                                                          |
| use_baseline                 | Boolean                                                          |
| baseline_win_chance          | Double (Between 0.0 and 1.0)                                     |
| baseline_target              | Double (Same as budget if budget_type = FIXED_PRICE)             |
| labels                       | List<Integer>, List ID of labels                                 |
| external_refs                | List of references to other systems                              |
| default_period_periodicity   | String (DAILY, WEEKLY, MONTHLY)                                  |
| default_period_length        | Integer                                                          |
| default_period_budget_type   | String (FIXED_HOURS, FIXED_PRICE, TIME_AND_MATERIALS)            |
| default_period_hours_amount  | Double                                                           |
| default_period_price_amount  | Double                                                           |
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
      "budget_type": "RETAINER",
      "billable": true,
      "use_sprints": true,
      "sprint_length": 14,
      "start_date": "2017-01-01",
      "end_date": "2018-01-01",
      "task_levels": 1,
      "client": 1,
      "rate_card": 1,
      "remaining_auto_calculated": false,
      "use_project_allocations": true,
      "use_baseline": true,
      "baseline_win_chance": 0.95,
      "baseline_target": 1234.56,
      "labels": [1,2],
      "external_refs": [],
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z",
      "default_period_periodicity": "DAILY",
      "default_period_length": 1,
      "default_period_budget_type": "FIXED_PRICE",
      "default_period_hours_amount": 1,
      "default_period_price_amount": 1
   }, ...
]
```

## Get project

- `GET /projects/{projectId}` - Returns a specific project.

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
| card_levels                  | Integer, deprecated. Use 'task_levels' instead                   |
| task_levels                  | Integer (1 or 2)                                                 |
| client                       | Integer, ID of client                                            |
| rate_card                    | Integer, ID of rate card                                         |
| remaining_auto_calculated    | Boolean                                                          |
| use_project_allocations      | Boolean                                                          |
| use_baseline                 | Boolean                                                          |
| baseline_win_chance          | Double (Between 0.0 and 1.0)                                     |
| baseline_target              | Double (Same as budget if budget_type = FIXED_PRICE)             |
| labels                       | List<Integer>, List ID of labels                                 |
| external_refs                | List of references to other systems                              |
| default_period_periodicity   | String (DAILY, WEEKLY, MONTHLY)                                  |
| default_period_length        | Integer                                                          |
| default_period_budget_type   | String (FIXED_HOURS, FIXED_PRICE, TIME_AND_MATERIALS)            |
| default_period_hours_amount  | Double                                                           |
| default_period_price_amount  | Double                                                           |
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
   "task_levels": 1,
   "client": 1,
   "rate_card": 1,
   "remaining_auto_calculated": false,
   "use_project_allocations": true,
   "use_baseline": true,
   "baseline_win_chance": 0.95,
   "baseline_target": 1234.56,
   "labels": [1,2],
   "external_refs": [],
   "created_by":1,
   "updated_by":1,
   "created_at":"2017-01-14T18:46:56Z",
   "updated_at":"2017-01-14T18:47:58Z",
   "default_period_periodicity": "DAILY",
   "default_period_length": 1,
   "default_period_budget_type": "FIXED_PRICE",
   "default_period_hours_amount": 1,
   "default_period_price_amount": 1
}
```

## Get project by company project id

- `GET /projects/company_project_id/{companyProjectId}` - Returns a specific project.

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
| card_levels                  | Integer, deprecated. Use 'task_levels' instead                   |
| task_levels                  | Integer (1 or 2)                                                 |
| client                       | Integer, ID of client                                            |
| rate_card                    | Integer, ID of rate card                                         |
| remaining_auto_calculated    | Boolean                                                          |
| use_project_allocations      | Boolean                                                          |
| use_baseline                 | Boolean                                                          |
| baseline_win_chance          | Double (Between 0.0 and 1.0)                                     |
| baseline_target              | Double (Same as budget if budget_type = FIXED_PRICE)             |
| labels                       | List<Integer>, List ID of labels                                 |
| external_refs                | List of references to other systems                              |
| default_period_periodicity   | String (DAILY, WEEKLY, MONTHLY)                                  |
| default_period_length        | Integer                                                          |
| default_period_budget_type   | String (FIXED_HOURS, FIXED_PRICE, TIME_AND_MATERIALS)            |
| default_period_hours_amount  | Double                                                           |
| default_period_price_amount  | Double                                                           |
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
   "task_levels": 1,
   "client": 1,
   "rate_card": 1,
   "remaining_auto_calculated": false,
   "use_project_allocations": true,
   "use_baseline": true,
   "baseline_win_chance": 0.95,
   "baseline_target": 1234.56,
   "labels": [1,2],
   "external_refs": [],
   "created_by":1,
   "updated_by":1,
   "created_at":"2017-01-14T18:46:56Z",
   "updated_at":"2017-01-14T18:47:58Z",
   "default_period_periodicity": "DAILY",
   "default_period_length": 1,
   "default_period_budget_type": "FIXED_PRICE",
   "default_period_hours_amount": 1,
   "default_period_price_amount": 1
}
```

## Create project

- `POST /projects` - Creates a new project. Returns the same object as getting a single project.

| Request fields               | Description/format                                                                                |
| ---------------------------- | ------------------------------------------------------------------------------------------------- |
| name                         | String                                                                                            |
| stage                        | String (PLANNING, RUNNING, HALTED, DONE) (Defaults to PLANNING)                                   |
| status                       | String (GREEN, YELLOW, RED) (Defaults to GREEN)                                                   |
| status_description           | String                                                                                            |
| description                  | String                                                                                            |
| estimation_units             | String (HOURS, POINTS) (Defaults to HOURS)                                                        |
| minutes_per_estimation_point | Integer (Defaults to 60)                                                                          |
| budget                       | Double (Should only be set with budget_type: FIXED_PRICE)                                         |
| billable                     | Boolean (Defaults to true) (Deprecated)                                                           |
| budget_type                  | String (FIXED_PRICE, NON_BILLABLE, TIME_AND_MATERIALS, RETAINER) (Defaults to TIME_AND_MATERIALS) |
| use_sprints                  | Boolean (Defaults to false)                                                                       |
| sprint_length                | Integer (Defaults to 14)                                                                          |
| start_date                   | Date                                                                                              |
| end_date                     | Date                                                                                              |
| card_levels                  | Integer, deprecated. Use 'task_levels' instead                                                    |
| task_levels                  | Integer (1 or 2) (Defaults to 1)                                                                  |
| client                       | Integer, ID of client                                                                             |
| rate_card                    | Integer, ID of rate card                                                                          |
| remaining_auto_calculated    | Boolean (Defaults to true)                                                                        |
| use_project_allocations      | Boolean, deprecated. Uses company setting instead.                                                |
| use_baseline                 | Boolean (Defaults to false)                                                                       |
| baseline_target              | Double (Minimum 0.0, Should not be set with budget_type: FIXED_PRICE)                             |
| baseline_win_chance          | Double (Between 0.0 and 1.0) (Defaults to 1.0)                                                    |
| labels                       | List<Integer>, List ID of labels                                                                  |
| default_period_periodicity   | String (DAILY, WEEKLY, MONTHLY)                                                                   |
| default_period_length        | Integer                                                                                           |
| default_period_budget_type   | String (FIXED_HOURS, FIXED_PRICE, TIME_AND_MATERIALS)                                             |
| default_period_hours_amount  | Double                                                                                            |
| default_period_price_amount  | Double                                                                                            |

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
   "budget_type": "FIXED_PRICE",
   "use_sprints":true,
   "sprint_length":14,
   "use_baseline":true,
   "baseline_win_chance":0.95
}
```

## Update project

- `PUT /projects/{projectId}` - Updates a project. Returns the same object as getting a single project.

| Request fields               | Description/format                                                    |
| ---------------------------- | --------------------------------------------------------------------- |
| name                         | String                                                                |
| connected_project            | Integer, ID of connected project                                      |
| stage                        | String (PLANNING, RUNNING, HALTED, DONE)                              |
| status                       | String (GREEN, YELLOW, RED)                                           |
| status_description           | String                                                                |
| description                  | String                                                                |
| estimation_units             | String (HOURS, POINTS)                                                |
| minutes_per_estimation_point | Integer                                                               |
| budget                       | Double (Should only be set with budget_type: FIXED_PRICE)             |
| billable                     | Boolean (Deprecated)                                                  |
| budget_type                  | String (FIXED_PRICE, NON_BILLABLE, TIME_AND_MATERIALS, RETAINER)      |
| use_sprints                  | Boolean                                                               |
| sprint_length                | Integer                                                               |
| remaining_auto_calculated    | Boolean                                                               |
| start_date                   | Date                                                                  |
| end_date                     | Date                                                                  |
| card_levels                  | Integer, deprecated. Use 'task_levels' instead                        |
| task_levels                  | Integer (1 or 2)                                                      |
| client                       | Integer, ID of client                                                 |
| rate_card                    | Integer, ID of rate card                                              |
| use_project_allocations      | Boolean, deprecated. Uses company setting instead.                    |
| use_baseline                 | Boolean                                                               |
| baseline_win_chance          | Double (Between 0.0 and 1.0)                                          |
| baseline_target              | Double (Minimum 0.0, Should not be set with budget_type: FIXED_PRICE) |
| labels                       | List<Integer>, List ID of labels                                      |
| default_period_periodicity   | String (DAILY, WEEKLY, MONTHLY)                                       |
| default_period_length        | Integer                                                               |
| default_period_budget_type   | String (FIXED_HOURS, FIXED_PRICE, TIME_AND_MATERIALS)                 |
| default_period_hours_amount  | Double                                                                |
| default_period_price_amount  | Double                                                                |

### Sample JSON request

PUT https://api.forecast.it/api/v1/projects/1

```javascript
{
   "stage":"RUNNING",
   "labels":[12, 13]
}
```

## Duplicate project

- `POST /projects/duplicate/{projectId}` - Creates a duplicate of the given project. Returns the new project.

| Request fields            | Description/format                                                                              |
| ------------------------- | ----------------------------------------------------------------------------------------------- |
| name                      | String                                                                                          |
| start_date                | Date (Changing the dates of a duplicated project will move tasks and phases accordingly)        |
| end_date                  | Date (Changing the dates of a duplicated project will move tasks and phases accordingly)        |
| client                    | Integer, ID of client                                                                           |
| duplicate_color           | Boolean (Defaults to true). Determines if the project color should be duplicated                |
| duplicate_expenses        | Boolean (Defaults to true). Determines if expenses attached to the project should be duplicated |
| duplicate_phases          | Boolean (Defaults to true). Determines if phases on the project should be duplicated            |
| duplicate_settings        | Boolean (Defaults to true). Determines if settings on the project should be duplicated          |
| duplicate_project_persons | Boolean (Defaults to true). Determines if persons assigned to the project should be duplicated  |
| duplicate_tasks           | Boolean (Defaults to true). Determines if tasks on the project should be duplicated             |

### Sample JSON request

POST https://api.forecast.it/api/v1/projects/duplicate/1

```javascript
{
   "name":"Duplicated Project",
   "client": 1,
   "start_date": "2021-08-14",
   "duplicate_color": false,
   "duplicate_expenses": false
}
```

## Delete project

- `DELETE /projects/{projectId}` - Deletes a project.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/projects/1

## Get project statuses

- `GET /projects/{projectId}/statuses` - Returns the entire status history of a specific project.

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

- `GET /projects/{projectId}/financials` - Returns all financial data for the project, broken down to milestone and role level.
- `GET /projects/{projectId}/financials?start_date=YYYYMMDD&end_date=YYYYMMDD` - Returns all financial data for the project between `start_date` and `end_date`, broken down to milestone and role level.

Some data in the response is broken down on the individual milestones of the project in arrays called `milestone_breakdown`. Each of these milestones can be further broken down on the individual roles in arrays called `role_breakdown`.

Milestone and role objects with id zero represent data with no milestone or role.

### Sample JSON request

GET https://api.forecast.it/api/v1/projects/1/financials

| Response fields                                    | Description/format                                                                                           |
| -------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| project_id                                         | Integer                                                                                                      |
| progress                                           | Object                                                                                                       |
| &nbsp;&nbsp;↳ period_value                         | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;↳ total_value                          | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ milestone_breakdown                  | Array, The same values broken down on the project milestones                                                 |
| fixed_price                                        | Object                                                                                                       |
| &nbsp;&nbsp;↳ revenue                              | Double, The fixed price of the project                                                                       |
| &nbsp;&nbsp;↳ cost                                 | Double, The forecasted cost of the project                                                                   |
| &nbsp;&nbsp;↳ profit                               | Double, The fixed price minus the forecasted cost of the project                                             |
| &nbsp;&nbsp;↳ margin                               | Double, The profit as a percentage of the revenue                                                            |
| actual_price                                       | Object                                                                                                       |
| &nbsp;&nbsp;↳ revenue                              | Object, All billable time entries multiplied with their rate, plus price on all actual billable expenses     |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ cost                                 | Object, All time entries multiplied by their internal cost, plus cost on all actual expenses                 |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ profit                               | Object, The actual revenue minus actual cost                                                                 |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ margin                               | Object, The profit as a percentage of the revenue                                                            |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ milestone_breakdown                  | Array, The same values broken down on the project milestones                                                 |
| plan_price                                         | Object                                                                                                       |
| &nbsp;&nbsp;↳ revenue                              | Object, All billable estimated hours multiplied by their rate, plus price on all planned billable expenses   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ cost                                 | Object, Total estimated hours multiplid by their internal cost, plus cost on all planned expenses            |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ profit                               | Object, The Planned revenue minus planned cost                                                               |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ margin                               | Object, The profit as a percentage of the revenue                                                            |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ milestone_breakdown                  | Array, The same values broken down on the project milestones                                                 |
| remaining_price                                    | Object                                                                                                       |
| &nbsp;&nbsp;↳ revenue                              | Object, The remaining billable hours multiplied by their rate, plus price on all remaining billable expenses |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ cost                                 | Object, All remaining hours multiplied by their internal cost, plus cost on all remaining expenses           |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ profit                               | Object, The remaining revenue minus remaining cost                                                           |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ margin                               | Object, The profit as a percentage of the revenue                                                            |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ milestone_breakdown                  | Array, The same values broken down on the project milestones                                                 |
| forecast_price                                     | Object                                                                                                       |
| &nbsp;&nbsp;↳ revenue                              | Object, The actual revenue plus the remaining revenue                                                        |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ cost                                 | Object, The actual cost plus the remaining cost                                                              |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ profit                               | Object, The forecasted revenue minus the forecasted cost                                                     |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ margin                               | Object, The profit as a percentage of the revenue                                                            |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ milestone_breakdown                  | Array, The same values broken down on the project milestones                                                 |
| actual_variance_to_plan_price                      | Object, Variance is the difference between the estimated or expected plan and the actual or projected result |
| &nbsp;&nbsp;↳ revenue                              | Object, The actual revenue minus the planned revenue                                                         |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ cost                                 | Object, The actual cost minus the planned cost                                                               |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ profit                               | Object, The actual variance revenue minus the actual variance cost                                           |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ margin                               | Object, The profit as a percentage of the revenue                                                            |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ milestone_breakdown                  | Array, The same values broken down on the project milestones                                                 |
| forecast_variance_to_plan_price                    | Object, Variance is the difference between the estimated or expected plan and the actual or projected result |
| &nbsp;&nbsp;↳ revenue                              | Object, The forecasted revenue minus the planned revenue                                                     |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ cost                                 | Object, The forecasted cost minus the planned cost                                                           |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ profit                               | Object, The forecasted variance revenue minus the forecasted variance cost                                   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ margin                               | Object, The profit as a percentage of the revenue                                                            |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ milestone_breakdown                  | Array, The same values broken down on the project milestones                                                 |
| company_financials                                 | Object                                                                                                       |
| &nbsp;&nbsp;↳ revenue                              | Double, All fixed price revenue plus all forecasted revenue (only on T&M)                                    |
| &nbsp;&nbsp;↳ cost                                 | Double, All fixed price costs plus all forecasted costs (T&M)                                                |
| &nbsp;&nbsp;↳ profit                               | Double, Revenue minus cost                                                                                   |
| &nbsp;&nbsp;↳ margin                               | Double, The profit as a percentage of the revenue                                                            |
| registered_hours                                   | Object, All time entries                                                                                     |
| &nbsp;&nbsp;↳ period_value                         | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;↳ total_value                          | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ milestone_breakdown                  | Array, The same values broken down on the project milestones                                                 |
| remaining_hours                                    | Object, All remaining hours                                                                                  |
| &nbsp;&nbsp;↳ period_value                         | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;↳ total_value                          | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ milestone_breakdown                  | Array, The same values broken down on the project milestones                                                 |
| forecast_hours                                     | Object, Registered plus remaining hours                                                                      |
| &nbsp;&nbsp;↳ period_value                         | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;↳ total_value                          | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ milestone_breakdown                  | Array, The same values broken down on the project milestones                                                 |
| estimated_hours                                    | Object                                                                                                       |
| &nbsp;&nbsp;↳ approved                             | Object, Values of only the approved tasks in the project                                                     |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ all                                  | Object, Values of all tasks in the project                                                                   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, The total value for the project                                                                      |
| low_hours                                          | Object                                                                                                       |
| &nbsp;&nbsp;↳ approved                             | Object, Values of only the approved tasks in the project                                                     |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ all                                  | Object, Values of all tasks in the project                                                                   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, The total value for the project                                                                      |
| high_hours                                         | Object                                                                                                       |
| &nbsp;&nbsp;↳ approved                             | Object, Values of only the approved tasks in the project                                                     |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ all                                  | Object, Values of all tasks in the project                                                                   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, The total value for the project                                                                      |
| allocation                                         | Object                                                                                                       |
| &nbsp;&nbsp;↳ period_value                         | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;↳ total_value                          | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ milestone_breakdown                  | Array, The same values broken down on the project milestones                                                 |
| invoice                                            | Object                                                                                                       |
| &nbsp;&nbsp;↳ invoiced_price                       | Object                                                                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ invoiced_on_fixed_price              | Object, The invoiced price as a percentage of the fixed price                                                |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, The total value for the project                                                                      |
| &nbsp;&nbsp;↳ invoiced_paid                        | Object                                                                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ period_value | Double, The value for the selected period                                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ total_value  | Double, The total value for the project                                                                      |

## Get project baseline

- `GET /projects/{projectId}/baseline` - Returns all baseline data for the project, including aggregations of phases, roles and expenses.

### Sample JSON request

GET https://api.forecast.it/api/v1/projects/1/baseline

| Response fields                                                   | Description/format                                                                                  |
| ----------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| project_id                                                        | Integer                                                                                             |
| baseline_target                                                   | Double, The set revenue target for the baseline.                                                    |
| baseline_win_chance                                               | Double, The set win chance for the baseline.                                                        |
| baseline_minutes                                                  | Integer, The total sum of minutes allocated to roles belonging to the baseline project.             |
| baseline_price                                                    | Double, The total sum of revenue from roles and expenses belonging to the baseline project.         |
| baseline_cost                                                     | Double, The total sum of cost from roles and expenses belonging to the baseline project.            |
| baseline_profit                                                   | Double, The total sum of profit from roles and expenses belonging to the baseline project.          |
| phase_baselines                                                   | Array, The baseline phases attached to the baseline project.                                        |
| &nbsp;&nbsp;↳ phase_id                                            | Integer                                                                                             |
| &nbsp;&nbsp;↳ phase_baseline_minutes                              | Integer, The total sum of minutes allocated to roles belonging to the baseline phase.               |
| &nbsp;&nbsp;↳ phase_baseline_price                                | Double, The total sum of revenue from roles and expenses belonging to the baseline phase.           |
| &nbsp;&nbsp;↳ phase_baseline_cost                                 | Double, The total sum of cost from roles and expenses belonging to the baseline phase.              |
| &nbsp;&nbsp;↳ phase_baseline_profit                               | Double, The total sum of profit from roles and expenses belonging to the baseline phase.            |
| &nbsp;&nbsp;↳ phase_baseline_roles                                | Array, The baseline roles attached to the baseline phase.                                           |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ role_id                     | Integer                                                                                             |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ role_baseline_minutes       | Integer, The minutes allocated to the baseline role.                                                |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ role_baseline_price         | Double, The revenue calculated from the minutes allocated and the hourly rate of the baseline role. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ role_baseline_rate_per_hour | Double, The hourly rate for the baseline role.                                                      |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ role_baseline_cost          | Double, The cost calculated from the minutes allocated and the hourly cost of the baseline role.    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ role_baseline_cost_per_hour | Double, The hourly cost of the baseline role.                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ role_baseline_profit        | Double, The profit calculated from the cost and the revenue of the baseline role.                   |
| &nbsp;&nbsp;↳ phase_baseline_expenses                             | Array, The baseline expenses attached to the baseline phase.                                        |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ expense_category_id         | Integer                                                                                             |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ expense_baseline_cost       | Double, The set cost of the baseline expense.                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ expense_baseline_markup     | Double, The set markup of the baseline expense.                                                     |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ expense_baseline_revenue    | Double, The set revenue of the baseline expense.                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↳ expense_baseline_profit     | Double, The profit calculated from the cost and the revenue of the baseline expense.                |
