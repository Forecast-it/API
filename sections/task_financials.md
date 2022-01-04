# Task Financials

## Get financials for task

* `/tasks/{taskId}/financials` - Return financial numbers for specific task

| Response fields        | Description/format                                                                     |
|------------------------|----------------------------------------------------------------------------------------|
| task_id                | Integer. Task ID                                                                       |
| actual_revenue         | Number. All billable Time Registrations x Rate + Actual Billable Expenses              |
| actual_cost            | Number. All Time Registrations x Internal costs + Actual costs on all Expenses         |
| actual_profit          | Number. Actual Revenue - Actual costs                                                  |
| actual_margin          | Number. Actual Profit / Actual Revenue X 100                                           |
| planned_revenue        | Number. All billable estimated hours x Rate + Price on all planned billable expenses   |
| planned_cost           | Number. Total Estimated hours x Internal costs + Planned costs on all Expenses         |
| planned_profit         | Number. Planned Revenue - Planned costs                                                |
| planned_margin         | Number. Planned Profit / Planned Revenue X 100                                         |
| remaining_revenue      | Number. All remaining billable hours x Rate + Price on all remaining billable Expenses |
| remaining_cost         | Number. All remaining hours x Internal costs + Remaining Planned costs on Expenses     |
| remaining_profit       | Number. Remaining Revenue - Remaining costs                                            |
| remaining_margin       | Number. Remaining Profit / Remaining Revenue X 100                                     |
| forecast_revenue       | Number. Actual Revenue + Remaining Revenue                                             |
| forecast_cost          | Number. Actual costs + Remaining costs                                                 |
| forecast_profit        | Number. Forecasted Revenue - Forecasted costs                                          |
| forecast_margin        | Number. Estimated profit / Forecasted Revenue X 100                                    |
| registered_minutes     | Number. Time registrations                                                             |
| remaining_minutes      | Number. Remaining minutes                                                              |
| forecast_minutes       | Number. Registered + remaining minutes                                                 |
| scope_approved_minutes | Number. Estimate of approved task in minutes                                           |
| scope_total_minutes    | Number. Estimate of task in minutes                                                    |

### Sample JSON response
```json
{
    "task_id": 465,
    "actual_revenue": 1181.931883776,
    "actual_cost": 700,
    "actual_profit": 481.93188377599995,
    "actual_margin": 0.40774928774773267,
    "planned_revenue": 225.129882624,
    "planned_cost": 291.25,
    "planned_profit": -66.120117376,
    "planned_margin": -0.2936976495760463,
    "remaining_revenue": 0,
    "remaining_cost": 0,
    "remaining_profit": 0,
    "remaining_margin": 0,
    "forecast_revenue": 1181.931883776,
    "forecast_cost": 700,
    "forecast_profit": 481.93188377599995,
    "forecast_margin": 0.40774928774773267,
    "registered_minutes": 420,
    "remaining_minutes": 0,
    "forecast_minutes": 420,
    "scope_approved_minutes": 120,
    "scope_total_minutes": 120
}
```

## Get financials for all tasks in a project

* `/projects/{projectId}/tasks/financials` - Return list of financial numbers for each task in the specific project

| Response fields        | Description/format                                                                     |
|------------------------|----------------------------------------------------------------------------------------|
| task_id                | Integer. Task ID                                                                       |
| actual_revenue         | Number. All billable Time Registrations x Rate + Actual Billable Expenses              |
| actual_cost            | Number. All Time Registrations x Internal costs + Actual costs on all Expenses         |
| actual_profit          | Number. Actual Revenue - Actual costs                                                  |
| actual_margin          | Number. Actual Profit / Actual Revenue X 100                                           |
| planned_revenue        | Number. All billable estimated hours x Rate + Price on all planned billable expenses   |
| planned_cost           | Number. Total Estimated hours x Internal costs + Planned costs on all Expenses         |
| planned_profit         | Number. Planned Revenue - Planned costs                                                |
| planned_margin         | Number. Planned Profit / Planned Revenue X 100                                         |
| remaining_revenue      | Number. All remaining billable hours x Rate + Price on all remaining billable Expenses |
| remaining_cost         | Number. All remaining hours x Internal costs + Remaining Planned costs on Expenses     |
| remaining_profit       | Number. Remaining Revenue - Remaining costs                                            |
| remaining_margin       | Number. Remaining Profit / Remaining Revenue X 100                                     |
| forecast_revenue       | Number. Actual Revenue + Remaining Revenue                                             |
| forecast_cost          | Number. Actual costs + Remaining costs                                                 |
| forecast_profit        | Number. Forecasted Revenue - Forecasted costs                                          |
| forecast_margin        | Number. Estimated profit / Forecasted Revenue X 100                                    |
| registered_minutes     | Number. Time registrations                                                             |
| remaining_minutes      | Number. Remaining minutes                                                              |
| forecast_minutes       | Number. Registered + remaining minutes                                                 |
| scope_approved_minutes | Number. Estimate of approved task in minutes                                           |
| scope_total_minutes    | Number. Estimate of task in minutes                                                    |

### Sample JSON response
```json
[
  {
    "task_id": 464,
    "actual_revenue": 844.23705984,
    "actual_cost": 500,
    "actual_profit": 344.23705984000003,
    "actual_margin": 0.4077492877477327,
    "planned_revenue": 225.129882624,
    "planned_cost": 291.25,
    "planned_profit": -66.120117376,
    "planned_margin": -0.2936976495760463,
    "remaining_revenue": 0,
    "remaining_cost": 0,
    "remaining_profit": 0,
    "remaining_margin": 0,
    "forecast_revenue": 844.23705984,
    "forecast_cost": 500,
    "forecast_profit": 344.23705984000003,
    "forecast_margin": 0.4077492877477327,
    "registered_minutes": 300,
    "remaining_minutes": 0,
    "forecast_minutes": 300,
    "scope_approved_minutes": 120,
    "scope_total_minutes": 120
  },
  ...
]
```
