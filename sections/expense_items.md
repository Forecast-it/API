# Expense items

## Get expense items

* `GET /projects/{projectId}/expense_items` - Returns all expense items of the project.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|name | String|
|minimum | Integer|
|maximum | Integer|
|spent | Integer|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
[
   {
      "id":1,
      "name":"Servers",
      "minimum":2000,
      "maximum":3000,
      "spent":500,
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z"
   }, ...
]
```

## Get expense item

* `GET /projects/{projectId}/expense_items/{expense_itemId}` - Returns a specific expense item.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|name | String|
|minimum | Integer|
|maximum | Integer|
|spent | Integer|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
{
   "id":1,
   "name":"Servers",
   "minimum":2000,
   "maximum":3000,
   "spent":500,
   "created_by":1,
   "updated_by":1,
   "created_at":"2017-01-14T18:46:56Z",
   "updated_at":"2017-01-14T18:47:58Z"
}
```

## Create expense item

* `POST /projects/{projectId}/expense_items` - Creates a new expense item. Returns the same object as getting a single expense item.

|Request fields | Description/format|
|------------ | -------------|
|name | (Required) String|
|minimum | (Required) Integer|
|maximum | (Required) Integer|
|spent | Integer|

### Sample JSON request
POST https://api.forecast.it/api/v1/projects/1/expense_items

```javascript
{
   "name":"Licenses",
   "minimum":100,
   "maximum":600
}
```

## Update expense item

* `PUT /projects/{projectId}/expense_items/{expense_itemId}` - Updates an expense item. Returns the same object as getting a single expense item.

|Request fields | Description/format|
|------------ | -------------|
|name | (Required) String|
|minimum | (Required) Integer|
|maximum | (Required) Integer|
|spent | Integer|

### Sample JSON request
PUT https://api.forecast.it/api/v1/projects/1/expense_items/1

```javascript
{
   "spent":200,
}
```

## Delete expense item

* `DELETE /projects/{projectId}/expense_items/{expense_itemId}` - Deletes an expense item.

### Sample JSON request
DELETE https://api.forecast.it/api/v1/projects/1/expense_items/1