# Expense categories

## Get expense categories

* `GET /expense_categories` - Returns all expense categories.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|name | String|
|disabled | Boolean|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
[
   {
      "id":1,
      "name":"Other",
      "disabled": false,
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z"
   }, ...
]
```

## Get expense category

* `GET /expense_categories/{expenseCategoryId}` - Returns a specific expense category.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|name | String|
|disabled | Boolean|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
{
  "id":1,
  "name":"Other",
  "disabled": false,
  "created_by":1,
  "updated_by":1,
  "created_at":"2017-01-14T18:46:56Z",
  "updated_at":"2017-01-14T18:47:58Z"
}
```


## Create expense category

* `POST /expense_categories` - Creates a new expense category. Returns the created expense category.

| Request fields | Description/format   |
|--------------- | ---------------------|
| name           | (Required) String    |
| disabled       | Boolean              |

### Sample JSON request
POST https://api.forecast.it/api/v1/expense_categories

```javascript
{
   "name":"Transportation",
   "disabled": false
}
```

## Update expense category

* `PUT /expense_categories/{expenseCategoryId}` - Updates an expense category. Returns the updated expense category.

| Request fields | Description/format |
|--------------- | -------------------|
| name           | String             |
| disabled       | Boolean            |

### Sample JSON request
PUT https://api.forecast.it/api/v1/expense_categories/1

```javascript
{
    "name": "Utilities"
}
```

## Delete expense category

* `DELETE /expense_categories/{expenseCategoryId}` - Deletes an expense category.

### Sample JSON request
DELETE https://api.forecast.it/api/v1/expense_categories/1