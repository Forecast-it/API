# Roles

## Get roles

* `GET /roles` - Returns all roles.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|name | String|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
[
   {
      "id":1,
      "name":"Developer",
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z"
   }, ...
]
```

## Get role

* `GET /roles/{roleId}` - Returns a specific role.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|name | String|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
{
   "id":1,
   "name":"Developer",
   "created_by":1,
   "updated_by":1,
   "created_at":"2017-01-14T18:46:56Z",
   "updated_at":"2017-01-14T18:47:58Z"
}
```

## Create role

* `POST /roles` - Creates a new role. Returns the same object as getting a single role.

|Request fields | Description/format|
|------------ | -------------|
|name | (Required) String|

### Sample JSON request
POST https://api.forecast.it/api/v1/roles

```javascript
{
   "name":"Tester",
}
```

## Update role

* `PUT /roles/{roleId}` - Updates a role. Returns the same object as getting a single role.

|Request fields | Description/format|
|------------ | -------------|
|name | String|

### Sample JSON request
PUT https://api.forecast.it/api/v1/roles/1

```javascript
{
   "name":"Project Manager",
}
```

## Delete role

* `DELETE /roles/{roleId}` - Deletes a role.

### Sample JSON request
DELETE https://api.forecast.it/api/v1/roles/1