# Label Categories

## Get label categories

* `GET /label_categories` - Returns all label categories.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|name | String|
|allowOnTasks | Boolean|
|allowOnProjects | Boolean|
|allowOnPeople | Boolean|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
[
    {
        "id":1,
        "name":"Programming",
        "allowOnTasks": true,
        "allowOnProjects": false,
        "allowOnPeople": false,
        "created_by":1,
        "updated_by":1,
        "created_at":"2020-01-14T18:46:56Z",
        "updated_at":"2020-01-14T18:47:58Z"
    }, ...
]
```

## Get label category

* `GET /label_categories/{labelCategoryId}` - Returns a specific label category.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|name | String|
|allowOnTasks | Boolean|
|allowOnProjects | Boolean|
|allowOnPeople | Boolean|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
{
    "id":1,
    "name":"Programming",
    "allowOnTasks": true,
    "allowOnProjects": false,
    "allowOnPeople": false,
    "created_by":1,
    "updated_by":1,
    "created_at":"2020-01-14T18:46:56Z",
    "updated_at":"2020-01-14T18:47:58Z"
}
```

## Create label category

* `POST /label_categories` - Creates a new label category. Returns the same object as getting a single label category.

|Request fields | Description/format|
|------------ | -------------|
|name | (Required) String|
|allowOnTasks | (Required) Boolean|
|allowOnProjects | (Required) Boolean|
|allowOnPeople | (Required) Boolean|

### Sample JSON request
POST https://api.forecast.it/api/v1/label_categories

```javascript
{
   "name":"Programming",
    "allowOnTasks": true,
    "allowOnProjects": false,
    "allowOnPeople": false
}
```

## Update label category

* `PUT /label_categories/{labelCategoryId}` - Updates a label category. Returns the same object as getting a single label category.

|Request fields | Description/format|
|------------ | -------------|
|name | String|
|allowOnTasks | Boolean|
|allowOnProjects | Boolean|
|allowOnPeople | Boolean|

### Sample JSON request
PUT https://api.forecast.it/api/v1/label_categories/1

```javascript
{
    "name":"Programming",
    "allowOnTasks": true,
    "allowOnProjects": false,
    "allowOnPeople": false
}
```

## Delete label category

* `DELETE /label_categories/{labelCategoryId}` - Deletes a label category.

### Sample JSON request
DELETE https://api.forecast.it/api/v1/label_categories/1