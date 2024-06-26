# Retainer periods

## Get retainer periods by IDs

- `GET /retainer_periods` - Returns retainer periods with IDs specified by the `ids` query parameter, including aggregated rollover to and from each period.

This endpoint will not return any data in the absence of the `ids` query parameter.

### Sample JSON request

GET https://api.forecast.it/api/v1/retainer_periods/ids=1,2,3

Returns array of: 

| Response fields                                                   | Description/format                                                                                   |
| ----------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| created_at                                                        | String, The date and time when the object was created.                                               |
| created_by                                                        | Integer, The ID of the user who created the object.                                                  |
| end_day                                                           | Integer, The day the period ends.                                                                    |
| end_month                                                         | Integer, The month the period ends.                                                                  |
| end_year                                                          | Integer, The year the period ends.                                                                   |
| id                                                                | Integer, The period ID.                                                                              |
| invoice_id                                                        | Integer, The ID of the associated invoice.                                                           |
| name                                                              | String, The period name.                                                                             |
| period_budget_type                                                | String, The type of budget for the period.                                                           |
| period_hours_amount                                               | Integer, The period target in hours (for fixed hours retainers).                                     |
| period_length                                                     | Integer, The length of the period in days.                                                           |
| period_locked                                                     | Boolean, Whether the period is locked.                                                               |
| period_periodicity                                                | String, The periodicity of the period (e.g., monthly, weekly).                                       |
| period_price_amount                                               | Double, The period target price (for fixed price retainers).                                         |
| project_id                                                        | Integer, The ID of the associated project.                                                           |
| start_day                                                         | Integer, The day the period starts.                                                                  |
| start_month                                                       | Integer, The month the period starts.                                                                |
| start_year                                                        | Integer, The year the period starts.                                                                 |
| updated_at                                                        | DateTime, The date on which the period was last updated.                                             |
| updated_by                                                        | String, The user who last updated the object.                                                        |

## Get retainer period by ID

- `GET /retainer_periods/{periodId}` - Returns retainer period with ID periodId

### Sample JSON request

GET https://api.forecast.it/api/v1/retainer_periods/{periodId}

| Response fields                                                   | Description/format                                                                                   |
| ----------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| created_at                                                        | String, The date and time when the object was created.                                               |
| created_by                                                        | Integer, The ID of the user who created the object.                                                  |
| end_day                                                           | Integer, The day the period ends.                                                                    |
| end_month                                                         | Integer, The month the period ends.                                                                  |
| end_year                                                          | Integer, The year the period ends.                                                                   |
| id                                                                | Integer, The period ID.                                                                              |
| invoice_id                                                        | Integer, The ID of the associated invoice.                                                           |
| name                                                              | String, The period name.                                                                             |
| period_budget_type                                                | String, The type of budget for the period.                                                           |
| period_hours_amount                                               | Integer, The period target in hours (for fixed hours retainers).                                     |
| period_length                                                     | Integer, The length of the period in days.                                                           |
| period_locked                                                     | Boolean, Whether the period is locked.                                                               |
| period_periodicity                                                | String, The periodicity of the period (e.g., monthly, weekly).                                       |
| period_price_amount                                               | Double, The period target price (for fixed price retainers).                                         |
| project_id                                                        | Integer, The ID of the associated project.                                                           |
| start_day                                                         | Integer, The day the period starts.                                                                  |
| start_month                                                       | Integer, The month the period starts.                                                                |
| start_year                                                        | Integer, The year the period starts.                                                                 |
| updated_at                                                        | DateTime, The date on which the period was last updated.                                             |
| updated_by                                                        | String, The user who last updated the object.                                                        |
