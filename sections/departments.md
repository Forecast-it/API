# Departments

## Get departments

* `GET /departments` - Returns all departments.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|name | String|

### Sample JSON response
```javascript
[
   {
      "id":1,
      "name":"Development",
   }, ...
]
```

## Get department

* `GET /departments/{departmentId}` - Returns a specific department.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|name | String|

### Sample JSON response
```javascript
{
   "id":1,
   "name":"Development",
}
```