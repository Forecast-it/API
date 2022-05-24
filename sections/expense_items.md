# Expense items

## Get company expense items

- `GET /expense_items` - Returns all expense items of the company.

| Response fields     | Description/format              |
| ------------------- | ------------------------------- |
| id                  | Integer                         |
| project_id          | Integer                         |
| name                | String                          |
| expense_date        | Date                            |
| cost                | Decimal                         |
| price               | Decimal                         |
| quantity            | Decimal                         |
| approved            | Boolean                         |
| billable            | Boolean                         |
| notes               | String                          |
| person_id           | Integer, ID of person           |
| expense_category    | Integer, ID of expense category |
| created_by          | Integer, ID of person           |
| updated_by          | Integer, ID of person           |
| created_at          | Date                            |
| updated_at          | Date                            |
| phase_id            | Integer, ID of phase            |
| part_of_fixed_price | Boolean                         |

### Sample JSON response

```javascript
[
   {
      "id":1,
      "project_id":2,
      "name":"Servers",
      "expense_date": "2017-01-01",
      "cost": 150,
      "price": 200,
      "quantity": 1,
      "approved": true,
      "billable": true,
      "notes": "Notes about servers expense",
      "person_id": 1,
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z",
      "phase_id": 1,
      "part_of_fixed_price": true
   }, ...
]
```

## Get project expense items

- `GET /projects/{projectId}/expense_items` - Returns all expense items of the project.

| Response fields     | Description/format              |
| ------------------- | ------------------------------- |
| id                  | Integer                         |
| name                | String                          |
| expense_date        | Date                            |
| cost                | Decimal                         |
| price               | Decimal                         |
| quantity            | Decimal                         |
| approved            | Boolean                         |
| billable            | Boolean                         |
| notes               | String                          |
| person_id           | Integer, ID of person           |
| expense_category    | Integer, ID of expense category |
| created_by          | Integer, ID of person           |
| updated_by          | Integer, ID of person           |
| created_at          | Date                            |
| updated_at          | Date                            |
| phase_id            | Integer, ID of phase            |
| part_of_fixed_price | Boolean                         |

### Sample JSON response

```javascript
[
   {
      "id":1,
      "name":"Servers",
      "expense_date": "2017-01-01",
      "cost": 150,
      "price": 200,
      "quantity": 1,
      "approved": true,
      "billable": true,
      "notes": "Notes about servers expense",
      "person_id": 1,
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z",
      "phase_id": 1,
      "part_of_fixed_price": true
   }, ...
]
```

## Get expense item

- `GET /expense_items/{expense_itemId}` - Returns a specific expense item.

| Response fields     | Description/format              |
| ------------------- | ------------------------------- |
| id                  | Integer                         |
| project_id          | Integer                         |
| name                | String                          |
| expense_date        | Date                            |
| cost                | Decimal                         |
| price               | Decimal                         |
| quantity            | Decimal                         |
| approved            | Boolean                         |
| billable            | Boolean                         |
| notes               | String                          |
| person_id           | Integer, ID of person           |
| expense_category    | Integer, ID of expense category |
| created_by          | Integer, ID of person           |
| updated_by          | Integer, ID of person           |
| created_at          | Date                            |
| updated_at          | Date                            |
| phase_id            | Integer, ID of phase            |
| part_of_fixed_price | Boolean                         |

### Sample JSON response

```javascript
{
   "id":1,
   "project_id":2,
   "name":"Servers",
   "expense_date": "2017-01-01",
   "cost": 150,
   "price": 200,
   "quantity": 1,
   "approved": true,
   "billable": true,
   "notes": "Notes about servers expense",
   "person_id": 1,
   "created_by":1,
   "updated_by":1,
   "created_at":"2017-01-14T18:46:56Z",
   "updated_at":"2017-01-14T18:47:58Z",
   "phase_id": 1,
   "part_of_fixed_price": true
}
```

## Get expense item in a project

- `GET /projects/{projectId}/expense_items/{expense_itemId}` - Returns a specific expense item in a project.

| Response fields     | Description/format              |
| ------------------- | ------------------------------- |
| id                  | Integer                         |
| name                | String                          |
| expense_date        | Date                            |
| cost                | Decimal                         |
| price               | Decimal                         |
| quantity            | Decimal                         |
| approved            | Boolean                         |
| billable            | Boolean                         |
| notes               | String                          |
| person_id           | Integer, ID of person           |
| expense_category    | Integer, ID of expense category |
| created_by          | Integer, ID of person           |
| updated_by          | Integer, ID of person           |
| created_at          | Date                            |
| updated_at          | Date                            |
| phase_id            | Integer, ID of phase            |
| part_of_fixed_price | Boolean                         |

### Sample JSON response

```javascript
{
   "id":1,
   "name":"Servers",
   "expense_date": "2017-01-01",
   "cost": 150,
   "price": 200,
   "quantity": 1,
   "approved": true,
   "billable": true,
   "notes": "Notes about servers expense",
   "person_id": 1,
   "created_by":1,
   "updated_by":1,
   "created_at":"2017-01-14T18:46:56Z",
   "updated_at":"2017-01-14T18:47:58Z",
   "phase_id": 1,
   "part_of_fixed_price": true
}
```

## Create expense item

- `POST /projects/{projectId}/expense_items` - Creates a new expense item. Returns the same object as getting a single expense item.

| Request fields      | Description/format                                                                                                               |
| ------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| name                | (Required) String                                                                                                                |
| expense_date        | Date                                                                                                                             |
| cost                | (Required) Decimal                                                                                                               |
| price               | Decimal                                                                                                                          |
| quantity            | Decimal (defaults to 1)                                                                                                          |
| approved            | Boolean (Defaults to false)                                                                                                      |
| billable            | Boolean (Cannot be set to true if project on which expense item is added is not billable, defaults to true on billable projects) |
| notes               | String                                                                                                                           |
| person_id           | Integer, ID of person                                                                                                            |
| expense_category    | (Required) Integer, ID of expense category                                                                                       |
| phase_id            | Integer, ID of phase                                                                                                             |
| part_of_fixed_price | Boolean (Can only be set on retainer projects with fixed price)                                                                  |

### Sample JSON request

POST https://api.forecast.it/api/v1/projects/1/expense_items

```json
{
  "name": "Licenses",
  "cost": 150,
  "price": 200,
  "billable": true,
  "expense_category": 1
}
```

## Update expense item

- `PUT /projects/{projectId}/expense_items/{expense_itemId}` - Updates an expense item. Returns the same object as getting a single expense item.

| Request fields      | Description/format                                                                         |
| ------------------- | ------------------------------------------------------------------------------------------ |
| name                | String                                                                                     |
| expense_date        | Date                                                                                       |
| cost                | Decimal                                                                                    |
| price               | Decimal                                                                                    |
| quantity            | Decimal                                                                                    |
| approved            | Boolean                                                                                    |
| billable            | Boolean (Cannnot be set to true if project on which expense item is added is not billable) |
| notes               | String                                                                                     |
| person_id           | Integer, Id of person                                                                      |
| expense_category    | Integer, ID of expense category                                                            |
| phase_id            | Integer, ID of phase                                                                       |
| part_of_fixed_price | Boolean (Can only be set on retainer projects with fixed price)                            |

### Sample JSON request

PUT https://api.forecast.it/api/v1/projects/1/expense_items/1

```javascript
{
   "cost":200,
   "price": 200,
   "billable": true
}
```

## Delete expense item

- `DELETE /projects/{projectId}/expense_items/{expense_itemId}` - Deletes an expense item.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/projects/1/expense_items/1
