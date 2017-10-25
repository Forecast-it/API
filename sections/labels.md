# Labels

## Get labels

* `GET /labels` - Returns all labels.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|name | String|
|color | String|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
[
   {
      "id":1,
      "name":"Java",
      "color":"#392664",
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:561Z",
      "updated_at":"2017-01-14T18:47:581Z"
   }, ...
]
```

## Get label

* `GET /labels/{labelId}` - Returns a specific label.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|name | String|
|color | String|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
{
   "id":1,
   "name":"Java",
   "color":"#392664",
   "created_by":1,
   "updated_by":1,
   "created_at":"2017-01-14T18:46:561Z",
   "updated_at":"2017-01-14T18:47:581Z"
}
```

## Create label

* `POST /labels` - Creates a new label. Returns the same object as getting a single label.

|Request fields | Description/format|
|------------ | -------------|
|name | (Required) String|
|color | String|

### Sample JSON request
POST https://api.forecast.it/api/v1/labels

```javascript
{
   "name":"Design",
   "color":"#392664"
}
```

## Update label

* `PUT /labels/{labelId}` - Updates a label. Returns the same object as getting a single label.

|Request fields | Description/format|
|------------ | -------------|
|name | String|
|color | String|

### Sample JSON request
PUT https://api.forecast.it/api/v1/labels/1

```javascript
{
   "name":"Design"
}
```

## Delete label

* `DELETE /labels/{labelId}` - Deletes a label.

### Sample JSON request
DELETE https://api.forecast.it/api/v1/labels/1