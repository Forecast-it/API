# Baseline Expenses

## Get all baseline expenses in a project

- `GET /projects/{projectId}/baseline_expenses` - Returns all baseline expenses for a given project.

| Response fields         | Description/format                         |
| ----------------------- | ------------------------------------------ |
| id                      | Integer                                    |
| project                 | Integer, ID of project                     |
| milestone               | Integer, ID of milestone                   |
| expense_category        | Integer, ID of expense category            |
| expense_cost            | Double                                     |
| expense_revenue         | Double                                     |
| created_by              | Integer, ID of person                      |
| updated_by              | Integer, ID of person                      |
| created_at              | Date                                       |
| updated_at              | Date                                       |

### Sample JSON response

```javascript
[
   {
     "id": 1,
     "project": 1,
     "phase": 2,
     "expense_category": 1,
     "expense_cost": 123.45,
     "expense_revenue": 234.56,
     "created_by":1,
     "updated_by":1,
     "created_at":"2020-01-01T18:46:56Z",
     "updated_at":"2020-01-01T18:47:58Z"
    }, ...
]
```

## Get baseline expenses for milestone

- `GET /projects/{projectId}/milestones/{milestoneId}/baseline_expenses` - Returns all baseline expenses for a given milestone.

| Response fields         | Description/format                         |
| ----------------------- | ------------------------------------------ |
| id                      | Integer                                    |
| project                 | Integer, ID of project                     |
| milestone               | Integer, ID of milestone                   |
| expense_category        | Integer, ID of expense category            |
| expense_cost            | Double                                     |
| expense_revenue         | Double                                     |
| created_by              | Integer, ID of person                      |
| updated_by              | Integer, ID of person                      |
| created_at              | Date                                       |
| updated_at              | Date                                       |

### Sample JSON response

```javascript
[
   {
      "id": 1,
      "project": 1,
      "phase": 1,
      "expense_category": 1,
      "expense_cost": 123.45,
      "expense_revenue": 234.56,
      "created_by":1,
      "updated_by":1,
      "created_at":"2020-01-01T18:46:56Z",
      "updated_at":"2020-01-01T18:47:58Z"
   }, ...
]
```

## Get baseline expense

- `GET /projects/{projectId}/milestones/{milestoneId}/baseline_expenses/{baselineExpenseId}` - Returns a specific baseline expense.

| Response fields         | Description/format                         |
| ----------------------- | ------------------------------------------ |
| id                      | Integer                                    |
| project                 | Integer, ID of project                     |
| milestone               | Integer, ID of milestone                   |
| expense_category        | Integer, ID of expense category            |
| expense_cost            | Double                                     |
| expense_revenue         | Double                                     |
| created_by              | Integer, ID of person                      |
| updated_by              | Integer, ID of person                      |
| created_at              | Date                                       |
| updated_at              | Date                                       |

### Sample JSON response

```javascript
[
   {
      "id": 1,
      "project": 1,
      "phase": 1,
      "expense_category": 1,
      "expense_cost": 123.45,
      "expense_revenue": 234.56,
      "created_by":1,
      "updated_by":1,
      "created_at":"2020-01-01T18:46:56Z",
      "updated_at":"2020-01-01T18:47:58Z"
   }, ...
]
```

## Create baseline expense

-  `POST /projects/{projectId}/milestones/{milestoneId}/baseline_expenses` - Creates a new baseline expense. Returns the same object as getting a single baseline expense.

| Request fields          | Description/format                                    |
| ----------------------- | ----------------------------------------------------- |
| expense_category        | (Required) Integer, ID of expense category            |
| expense_cost            | (Required) Double                                     |
| expense_revenue         | (Required) Double                                     |

### Sample JSON request

POST https://api.forecast.it/api/v1/projects/1/milestones/1/baselines_expenses

```javascript
{
     "expense_category": 1,
     "expense_cost": 123.45,
     "expense_revenue": 234.56
}
```

When creating a baseline expense, the response may contain a baseline_correction_error. 
This indicates that the values you sent do not fit within the baseline, and have been adjusted accordingly.

## Update baseline expense

-  `PUT /projects/{projectId}/milestones/{milestoneId}/baseline_expenses/{baselineExpenseId}` - Updates a baseline expense. Returns the same object as getting a single baseline expense.

| Request fields   | Description/format                         |
| ---------------- | ------------------------------------------ |
| expense_cost     | Double                                     |
| expense_revenue  | Double                                     |

### Sample JSON request

PUT https://api.forecast.it/api/v1/projects/1/milestones/1/baseline_expenses/1

```javascript
{
   "expense_cost": 123.45,
   "expense_revenue": 234.56
}
```

When updating a baseline expense, the response may contain a baseline_correction_error. 
This indicates that the values you sent do not fit within the baseline, and have been adjusted accordingly.

## Delete baseline expense

-  `DELETE /projects/{projectId}/milestones/{milestoneId}/baseline_expenses/{baselineExpenseId}` - Deletes a baseline expense.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/projects/1/milestones/1/baseline_expenses/1