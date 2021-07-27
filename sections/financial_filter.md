# Financial Filter

This is a filter object used by the [getFinancialNumbers](financials.md) endpoint.

| Fields         | Description/format                                                                                                                                                                                       |
| ---------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| field    | String. Required. Accepted values: 'PROJECT_STATUS', 'PROJECT_STAGE', 'ROLE', 'PHASE', 'TASK', 'PROJECT_BUDGET_TYPE', 'PROJECT_OWNER', 'CONTACT', 'LABELS', 'CLIENT', 'RATE_CARD', 'PROJECT', 'DEADLINE' |
| operator | String. Required (unless 'field' is 'DEADLINE'). Accepted values: 'IS', 'IS_NOT', 'GREATER', 'GREATER_OR_EQUAL', 'LESS', 'LESS_OR_EQUAL', 'IN', 'NOT_IN'                                                 |
| value    | The format of 'value' depends on the values of the 'field' and 'operator' fields.<br>If 'operator' is 'IN' or 'NOT_IN', then 'value' needs to be an array of strings or integers.<br>Otherwise 'value' needs to be a single string or integer.<br>For accepted values, see below. |

The accepted values for the 'value' field depend on the value of 'field'.<br>
| Value of 'field' | Accepted values for the 'value' field |
| ---------------- | ------------------------------------- |
| PROJECT_STATUS | 'GREEN', 'YELLOW', 'RED' |
| PROJECT_STAGE | 'OPPORTUNITY', 'PLANNING', 'RUNNING', 'HALTED', 'DONE' |
| PROJECT_BUDGET_TYPE | 'FIXED_PRICE', 'TIME_AND_MATERIALS', 'NON_BILLABLE', 'RETAINER' |
| DEADLINE | 'overdue', 'today', 'this_week', 'within_five_days', 'within_seven_days', 'next_week', 'this_month', 'within_thirty_days', 'next_month', 'future', 'past', 'no_dates' |
| All others | Integer |

## Examples

```javascript
{
    "field": "PROJECT",
    "operator": "IS"
    "value": 10042
}
```
```javascript
{
    "field": "PROJECT_STAGE",
    "operator": "IN"
    "value": ["PLANNING", "RUNNING", "HALTED"]
}
```
```javascript
{
    "field": "DEADLINE",
    "value": "overdue"
}
```
