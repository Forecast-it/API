# Financial Numbers 

## Get financial numbers

- `POST /v2/getFinancialNumbers` - Gets financial numbers.

| Request fields | Description/format                                                                                                |
| -------------- | ----------------------------------------------------------------------------------------------------------------- |
| startDate      | Date. ISO 8601. Required if 'endDate' is present.                                                                 |
| endDate        | Date. ISO 8601. Required if 'startDate' is present.                                                                |
| groupBy        | Array of strings. Accepted values: 'PROJECT', 'YEAR', 'MONTH', 'DAY', 'PHASE', 'ROLE', 'EXPENSE_CATEGORY', 'TASK' |
| filters        | Array of [Filters](financial_filter.md)                                                                           |

### Sample JSON request

POST https://api.forecast.it/api/v2/getFinancialNumbers

```javascript
{
  "startDate": "2020-01-01",
  "endDate": "2020-12-31",
  "groupBy": ["ROLE"],
  "filters": [{
      "field": "PROJECT",
      "operator": "IS"
      "value": 10042
    }]
}
```

| Response fields                                 | Description/format              |
| ----------------------------------------------- | ------------------------------- |
| yearGrouping                                    | String (when grouping by year)  |
| yearMonthGrouping                               | String (when grouping by month) |
| revenueRecognition                              | Object                          |
| &nbsp;&nbsp;↳ totalRevenueRecognition           | Amount (Double)                 |
| &nbsp;&nbsp;↳ revenueRecogitionLocked           | Amount (Double)                 |
| &nbsp;&nbsp;↳ revenueRecognitionUnlocked        | Amount (Double)                 |
| &nbsp;&nbsp;↳ percentageComplete                | Percentage (Decimal)            |
| &nbsp;&nbsp;↳ varianceWithBudget                | Amount (Double)                 |
| &nbsp;&nbsp;↳ profitAtCompletion                | Amount (Double)                 |
| &nbsp;&nbsp;↳ tasksWithForecastTimeInThePast    | Amount (Double)                 |
| baseline                                        | Object                          |
| &nbsp;&nbsp;↳ billableTimeAndExpenses           | Amount (Double)                 |
| &nbsp;&nbsp;↳ cost                              | Amount (Double)                 |
| &nbsp;&nbsp;↳ profit                            | Amount (Double)                 |
| &nbsp;&nbsp;↳ margin                            | Percentage (Decimal)            |
| planned                                         | Object                          |
| &nbsp;&nbsp;↳ billableTimeAndExpenses           | Amount (Double)                 |
| &nbsp;&nbsp;↳ nonbillableTimeAndExpenses        | Amount (Double)                 |
| &nbsp;&nbsp;↳ cost                              | Amount (Double)                 |
| &nbsp;&nbsp;↳ profit                            | Amount (Double)                 |
| &nbsp;&nbsp;↳ margin                            | Percentage (Decimal)            |
| actual                                          | Object                          |
| &nbsp;&nbsp;↳ billableTimeAndExpenses           | Amount (Double)                 |
| &nbsp;&nbsp;↳ nonbillableTimeAndExpenses        | Amount (Double)                 |
| &nbsp;&nbsp;↳ cost                              | Amount (Double)                 |
| &nbsp;&nbsp;↳ profit                            | Amount (Double)                 |
| &nbsp;&nbsp;↳ margin                            | Percentage (Decimal)            |
| forecastToComplete                              | Object                          |
| &nbsp;&nbsp;↳ billableTimeAndExpenses           | Amount (Double)                 |
| &nbsp;&nbsp;↳ nonbillableTimeAndExpenses        | Amount (Double)                 |
| &nbsp;&nbsp;↳ cost                              | Amount (Double)                 |
| &nbsp;&nbsp;↳ profit                            | Amount (Double)                 |
| &nbsp;&nbsp;↳ margin                            | Percentage (Decimal)            |
| totalAtCompletion                               | Object                          |
| &nbsp;&nbsp;↳ billableTimeAndExpenses           | Amount (Double)                 |
| &nbsp;&nbsp;↳ nonbillableTimeAndExpenses        | Amount (Double)                 |
| &nbsp;&nbsp;↳ cost                              | Amount (Double)                 |
| &nbsp;&nbsp;↳ profit                            | Amount (Double)                 |
| &nbsp;&nbsp;↳ margin                            | Percentage (Decimal)            |
| baselineVsActual                                | Object                          |
| &nbsp;&nbsp;↳ billableTimeAndExpenses           | Amount (Double)                 |
| &nbsp;&nbsp;↳ cost                              | Amount (Double)                 |
| &nbsp;&nbsp;↳ profit                            | Amount (Double)                 |
| baselineVsTotalAtCompletion                     | Object                          |
| &nbsp;&nbsp;↳ billableTimeAndExpenses           | Amount (Double)                 |
| &nbsp;&nbsp;↳ cost                              | Amount (Double)                 |
| &nbsp;&nbsp;↳ profit                            | Amount (Double)                 |
| plannedVsActual                                 | Object                          |
| &nbsp;&nbsp;↳ billableTimeAndExpenses           | Amount (Double)                 |
| &nbsp;&nbsp;↳ cost                              | Amount (Double)                 |
| &nbsp;&nbsp;↳ profit                            | Amount (Double)                 |
| plannedVsTotalAtCompletion                      | Object                          |
| &nbsp;&nbsp;↳ billableTimeAndExpenses           | Amount (Double)                 |
| &nbsp;&nbsp;↳ cost                              | Amount (Double)                 |
| &nbsp;&nbsp;↳ profit                            | Amount (Double)                 |
| timeInMinutes                                   | Object                          |
| &nbsp;&nbsp;↳ actualTimeRegisteredToDate        | Minutes (Integer)               |
| &nbsp;&nbsp;↳ forecastTimeToComplete            | Minutes (Integer)               |
| &nbsp;&nbsp;↳ totalTimeAtCompletion             | Minutes (Integer)               |
| &nbsp;&nbsp;↳ scopeApprovedTime                 | Minutes (Integer)               |
| &nbsp;&nbsp;↳ scopeTotalTime                    | Minutes (Integer)               |
| &nbsp;&nbsp;↳ totalAllocation                   | Minutes (Integer)               |
| &nbsp;&nbsp;↳ baselineTotalMinutes              | Minutes (Integer)               |
| &nbsp;&nbsp;↳ baselineVsRegisteredMinutes       | Minutes (Integer)               |
| &nbsp;&nbsp;↳ baselineVsForecastMinutes         | Minutes (Integer)               |
| &nbsp;&nbsp;↳ registeredVsScopeApprovedMinutes  | Minutes (Integer)               |
| &nbsp;&nbsp;↳ forecastVsScopeApprovedMinutes    | Minutes (Integer)               |
| invoices                                        | Object                          |
| &nbsp;&nbsp;↳ invoicedTotal                     | Amount (Double)                 |
| &nbsp;&nbsp;↳ uninvoicedTotal                   | Amount (Double)                 |
| &nbsp;&nbsp;↳ paid                              | Amount (Double)                 |
| &nbsp;&nbsp;↳ invoicedVsBillableTimeAndExpenses | Amount (Double)                 |
| retainerPeriodTarget                            | Object                          |
| &nbsp;&nbsp;↳ minutes                           | Minutes (Integer)               |
| &nbsp;&nbsp;↳ price                             | Amount (Double)                 |

`Deprecated response from version 1 (/v1/getFinancialNumbers) ` - Please use v2
 
| Response fields       | Description/format                                                                                   |
| --------------------- | ---------------------------------------------------------------------------------------------------- |
| actualRevenue         | Number. All billable Time Registrations x Rate + Actual Billable Expenses                            |
| actualCost            | Number. All Time Registrations x Internal costs + Actual costs on all Expenses                       |
| actualProfit          | Number. Actual Revenue - Actual costs                                                                |
| actualMargin          | Number. Actual Profit / Actual Revenue X 100                                                         |
| plannedRevenue        | Number. All billable estimated hours x Rate + Price on all planned billable expenses                 |
| plannedCost           | Number. Total Estimated hours x Internal costs + Planned costs on all Expenses                       |
| plannedProfit         | Number. Planned Revenue - Planned costs                                                              |
| plannedMargin         | Number. Planned Profit / Planned Revenue X 100                                                       |
| remainingRevenue      | Number. All remaining billable hours x Rate + Price on all remaining billable Expenses               |
| remainingCost         | Number. All remaining hours x Internal costs + Remaining Planned costs on Expenses                   |
| remainingProfit       | Number. Remaining Revenue - Remaining costs                                                          |
| remainingMargin       | Number. Remaining Profit / Remaining Revenue X 100                                                   |
| forecastRevenue       | Number. Actual Revenue + Remaining Revenue                                                           |
| forecastCost          | Number. Actual costs + Remaining costs                                                               |
| forecastProfit        | Number. Forecasted Revenue - Forecasted costs                                                        |
| forecastMargin        | Number. Estimated profit / Forecasted Revenue X 100                                                  |
| registeredMinutes     | Number. Sum of time registrations on projects/tasks on project.                                      |
| remainingMinutes      | Number. Sum of remaining minutes                                                                     |
| forecastMinutes       | Number. Sum of registered + remaining minutes                                                        |
| scopeApprovedMinutes  | Number. Sum of estimate of approved tasks in minutes                                                 |
| scopeTotalMinutes     | Number. Sum of estimate of all tasks in minutes                                                      |
| allocationMinutes     | Number. Sum of project allocations. Rounded to nearest whole minute                                  |
| invoiced              | Number. Total invoiced (not draft)                                                                   |
| unInvoicedTotal       | Number. Sum of the price of all uninvoiced time registrations + the sum of all un invoiced expenses. |
| paid                  | Number. Total invoice paid                                                                           |
| baselineRevenue       | Number.                                                                                              |
| baselineCost          | Number.                                                                                              |
| baselineProfit        | Number.                                                                                              |
| baselineMargin        | Number.                                                                                              |
| baselineMinutes       | Number. Baseline minutes. Rounded to nearest whole minute                                            |
| actualVsPlanRevenue   | Number. Actual vs planned revenue                                                                    |
| actualVsPlanCost      | Number. Actual vs planned cost                                                                       |
| actualVsPlanProfit    | Number. Actual vs planned profit                                                                     |
| forecastVsPlanRevenue | Number. Forecasted vs planned revenue                                                                |
| forecastVsPlanCost    | Number. Forecasted vs planned cost                                                                   |
| forecastVsPlanProfit  | Number. Forecasted vs planned profit                                                                 |
