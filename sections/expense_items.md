# Expense items

## Get expense items

* `GET /projects/{projectId}/expense_items` - Returns all expense items of the project.

| Response fields | Description/format    |
| --------------- | --------------------- |
| id              | Integer               |
| name            | String                |
| expense_date    | Date                  |
| cost            | Decimal               |
| price           | Decimal               |
| quantity        | Integer               |
| approved        | Boolean               |
| billable        | Boolean               |
| notes           | String                |
| person_id       | Integer, Id of person |
| created_by      | Integer, ID of person |
| updated_by      | Integer, ID of person |
| created_at      | Date                  |
| updated_at      | Date                  |

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
      "updated_at":"2017-01-14T18:47:58Z"
   }, ...
]
```

## Get expense item

* `GET /projects/{projectId}/expense_items/{expense_itemId}` - Returns a specific expense item.

| Response fields | Description/format    |
| --------------- | --------------------- |
| id              | Integer               |
| name            | String                |
| expense_date    | Date                  |
| cost            | Decimal               |
| price           | Decimal               |
| quantity        | Integer               |
| approved        | Boolean               |
| billable        | Boolean               |
| notes           | String                |
| person_id       | Integer, Id of person |
| created_by      | Integer, ID of person |
| updated_by      | Integer, ID of person |
| created_at      | Date                  |
| updated_at      | Date                  |

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
   "updated_at":"2017-01-14T18:47:58Z"
}
```

## Create expense item

* `POST /projects/{projectId}/expense_items` - Creates a new expense item. Returns the same object as getting a single expense item.

| Request fields | Description/format                                                                                                                |
| -------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| name           | (Required) String                                                                                                                 |
| expense_date   | Date                                                                                                                              |
| cost           | (Required) Decimal                                                                                                                |
| price          | Decimal                                                                                                                           |
| quantity       | Integer (min 1, defaults to 1)                                                                                                    |
| approved       | Boolean (Defaults to true)                                                                                                        |
| billable       | Boolean (Cannnot be set to true if project on which expense item is added is not billable, defaults to true on billable projects) |
| notes          | String                                                                                                                            |
| person_id      | Integer, Id of person                                                                                                             |

### Sample JSON request

POST https://api.forecast.it/api/v1/projects/1/expense_items

```javascript
{
   "name":"Licenses",
   "cost": 150,
   "price": 200,
   "billable": true,
}
```

## Update expense item

* `PUT /projects/{projectId}/expense_items/{expense_itemId}` - Updates an expense item. Returns the same object as getting a single expense item.

| Request fields | Description/format                                                                         |
| -------------- | ------------------------------------------------------------------------------------------ |
| name           | String                                                                                     |
| expense_date   | Date                                                                                       |
| cost           | Decimal                                                                                    |
| price          | Decimal                                                                                    |
| quantity       | Integer (min 1)                                                                            |
| approved       | Boolean                                                                                    |
| billable       | Boolean (Cannnot be set to true if project on which expense item is added is not billable) |
| notes          | String                                                                                     |
| person_id      | Integer, Id of person                                                                      |

### Sample JSON request

PUT https://api.forecast.it/api/v1/projects/1/expense_items/1

```javascript
{
   "cost":200,
   "price": 200,
   "billable": true,
}
```

## Delete expense item

* `DELETE /projects/{projectId}/expense_items/{expense_itemId}` - Deletes an expense item.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/projects/1/expense_items/1
