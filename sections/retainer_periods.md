# Retainer periods

## Get retainer periods by IDs

- `GET /retainer_periods` - Returns retainer periods with IDs specified by the `ids` query parameter, including aggregated rollover to and from each period.

This endpoint will not return any data in the absence of the `ids` query parameter.

### Sample JSON request

GET https://api.forecast.it/api/v1/retainer_periods?ids=1,2,3

Returns array of: 

| Response fields                        | Description                                                                                                                                                                                                                                  | Format   |
| -------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- |
| created_at                             | The date and time when the period was created.                                                                                                                                                                                               | String   |
| created_by                             | The ID of the user who created the period.                                                                                                                                                                                                   | Integer  |
| end_day                                | The day of the month of the period end date.                                                                                                                                                                                                 | Integer  |
| end_month                              | The month of the period end date.                                                                                                                                                                                                            | Integer  |
| end_year                               | The year of the period end date.                                                                                                                                                                                                             | Integer  |
| id                                     | The period ID.                                                                                                                                                                                                                               | Integer  |
| invoice_id                             | The ID of the invoice associated with the period.                                                                                                                                                                                            | Integer  |
| name                                   | The period name.                                                                                                                                                                                                                             | String   |
| retainer_budget_type                   | The budget type of the retainer.                                                                                                                                                                                                             | String   |
| period_target_hours                    | The period target in hours (for Fixed Hours and Time & Materials retainers).                                                                                                                                                                 | Integer  |
| period_length                          | The length of the period in days.                                                                                                                                                                                                            | Integer  |
| period_locked                          | Whether the period is locked.                                                                                                                                                                                                                | Boolean  |
| retainer_billing_period                | The billing period of the retainer (e.g., monthly, weekly).                                                                                                                                                                                  | String   |
| period_target_price                    | The period target price (for Fixed Price retainers).                                                                                                                                                                                         | Double   |
| project_id                             | The ID of the associated project.                                                                                                                                                                                                            | Integer  |
| start_day                              | The day of the month of the period start date.                                                                                                                                                                                               | Integer  |
| start_month                            | The month of the period start date.                                                                                                                                                                                                          | Integer  |
| start_year                             | The year of the period start date.                                                                                                                                                                                                           | Integer  |
| updated_at                             | The date on which the period was last updated.                                                                                                                                                                                               | DateTime |
| updated_by                             | The user who last updated the object.                                                                                                                                                                                                        | String   |
| period_rollover_hours                  | The net amount of rollover hours to and from the period, including the fixing of conflicted time (registered after a period is locked). Applicable for Fixed Hours retainers.                                                                 | Double   |
| period_rollover_price                  | The net amount of rollover price to and from the period, including the fixing of conflicted time (registered after a period is locked). Applicable for Fixed Price retainers.                                                                 | Double   |
| estimated_billable_hours               | Estimated billable time for the period, either from billable task estimates or resource allocations, depending on project financial settings.                                                                                                 | Double   |
| actual_billable_hours                  | Actual billable time for the period, either from billable time registered or past resource allocations, depending on project financial settings. Conflicted time (registered after a period is locked) is not included.                       | Double   |
| remaining_work_billable_hours          | Remaining work billable time for the period, either from time remaining on unfinished billable tasks or future resource allocations, depending on project financial settings.                                                                 | Double   |
| projected_total_billable_hours         | Projected total billable time for the period when work is completed (actual billable hours plus remaining work billable hours).                                                                                                               | Double   |
| estimated_billable_value_of_service    | The amount that would be charged in Time & Materials for the period, based on estimated billable time. Estimated time is either from task estimates or resource allocations, depending on project financial settings. Expenses can be included or excluded.                           | Double   |
| actual_billable_value_of_service       | The amount that would be charged in Time & Materials for the period, based on actual time. Actual time is from time registrations or past resource allocations, depending on project financial settings. Expenses can be included or excluded. Conflicted time (registered after a period is locked) is not included. | Double   |
| remaining_work_billable_value_of_service | The amount that would be charged in Time & Materials for the period, based on remaining work time. Remaining work time is from time remaining on unfinished billable tasks or future resource allocations, depending on project financial settings. Expenses can be included or excluded.  | Double   |
| projected_total_billable_value_of_service | Projected amount for the period that would be charged in Time & Materials when work is completed (actual billable value of service plus remaining work billable value of service). Expenses can be included or excluded.                      | Double   |

## Get retainer period by ID

- `GET /retainer_periods/{periodId}` - Returns retainer period with ID periodId

### Sample JSON request

GET https://api.forecast.it/api/v1/retainer_periods/{periodId}

| Response fields                        | Description                                                                                                                                                                                                                                  | Format   |
| -------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- |
| created_at                             | The date and time when the period was created.                                                                                                                                                                                               | String   |
| created_by                             | The ID of the user who created the period.                                                                                                                                                                                                   | Integer  |
| end_day                                | The day of the month of the period end date.                                                                                                                                                                                                 | Integer  |
| end_month                              | The month of the period end date.                                                                                                                                                                                                            | Integer  |
| end_year                               | The year of the period end date.                                                                                                                                                                                                             | Integer  |
| invoice_id                             | The ID of the invoice associated with the period.                                                                                                                                                                                            | Integer  |
| name                                   | The period name.                                                                                                                                                                                                                             | String   |
| retainer_budget_type                   | The budget type of the retainer.                                                                                                                                                                                                             | String   |
| period_target_hours                    | The period target in hours (for Fixed Hours and Time & Materials retainers).                                                                                                                                                                 | Integer  |
| period_length                          | The length of the period in days.                                                                                                                                                                                                            | Integer  |
| period_locked                          | Whether the period is locked.                                                                                                                                                                                                                | Boolean  |
| retainer_billing_period                | The billing period of the retainer (e.g., monthly, weekly).                                                                                                                                                                                  | String   |
| period_target_price                    | The period target price (for Fixed Price retainers).                                                                                                                                                                                         | Double   |
| project_id                             | The ID of the associated project.                                                                                                                                                                                                            | Integer  |
| start_day                              | The day of the month of the period start date.                                                                                                                                                                                               | Integer  |
| start_month                            | The month of the period start date.                                                                                                                                                                                                          | Integer  |
| start_year                             | The year of the period start date.                                                                                                                                                                                                           | Integer  |
| updated_at                             | The date on which the period was last updated.                                                                                                                                                                                               | DateTime |
| updated_by                             | The user who last updated the object.                                                                                                                                                                                                        | String   |
| period_rollover_hours                  | The net amount of rollover hours to and from the period, including the fixing of conflicted time (registered after a period is locked). Applicable for Fixed Hours retainers.                                                                 | Double   |
| period_rollover_price                  | The net amount of rollover price to and from the period, including the fixing of conflicted time (registered after a period is locked). Applicable for Fixed Price retainers.                                                                 | Double   |
| estimated_billable_hours               | Estimated billable time for the period, either from billable task estimates or resource allocations, depending on project financial settings.                                                                                                 | Double   |
| actual_billable_hours                  | Actual billable time for the period, either from billable time registered or past resource allocations, depending on project financial settings. Conflicted time (registered after a period is locked) is not included.                       | Double   |
| remaining_work_billable_hours          | Remaining work billable time for the period, either from time remaining on unfinished billable tasks or future resource allocations, depending on project financial settings.                                                                 | Double   |
| projected_total_billable_hours         | Projected total billable time for the period when work is completed (actual billable hours plus remaining work billable hours).                                                                                                               | Double   |
| estimated_billable_value_of_service    | The amount that would be charged in Time & Materials for the period, based on estimated billable time. Estimated time is either from task estimates or resource allocations, depending on project financial settings. Expenses can be included or excluded.                           | Double   |
| actual_billable_value_of_service       | The amount that would be charged in Time & Materials for the period, based on actual time. Actual time is from time registrations or past resource allocations, depending on project financial settings. Expenses can be included or excluded. Conflicted time (registered after a period is locked) is not included. | Double   |
| remaining_work_billable_value_of_service | The amount that would be charged in Time & Materials for the period, based on remaining work time. Remaining work time is from time remaining on unfinished billable tasks or future resource allocations, depending on project financial settings. Expenses can be included or excluded.  | Double   |
| projected_total_billable_value_of_service | Projected amount for the period that would be charged in Time & Materials when work is completed (actual billable value of service plus remaining work billable value of service). Expenses can be included or excluded.                      | Double   |



