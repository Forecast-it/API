# Clients

## Get clients

* `GET /clients` - Returns all clients.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|name | String|
|street | String|
|zip | String|
|city | String|
|country | String|
|vat_number | String|
|notes | String|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
[
   {
      "id":1,
      "name":"John Dow Inc.",
      "street":"Broadway 1",
      "zip":"90210",
      "city":"Los Angeles",
      "country":"United States",
      "vat_number":null,
      "notes":"Very important client",
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z"
   }, ...
]
```

## Get client

* `GET /clients/{clientId}` - Returns a specific client.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|name | String|
|street | String|
|zip | String|
|city | String|
|country | String|
|vat_number | String|
|notes | String|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
{
   "id":1,
   "name":"John Dow Inc.",
   "street":"Broadway 1",
   "zip":"90210",
   "city":"Los Angeles",
   "country":"United States",
   "vat_number":null,
   "notes":"Very important client",
   "created_by":1,
   "updated_by":1,
   "created_at":"2017-01-14T18:46:56Z",
   "updated_at":"2017-01-14T18:47:58Z"
}
```

## Create client

* `POST /clients` - Creates a new client. Returns the same object as getting a single client.

|Request fields | Description/format|
|------------ | -------------|
|name | (Required) String|
|street | String|
|zip | String|
|city | String|
|country | String|
|vat_number | String|
|notes | String|

### Sample JSON request
POST https://api.forecast.it/api/v1/clients

```javascript
{
   "name":"John Dow Inc.",
   "street":"Broadway 1",
   "zip":"90210",
   "city":"Los Angeles",
   "country":"United States",
   "vat_number":null,
   "notes":"Very important client"
}
```

## Update client

* `PUT /clients/{clientId}` - Updates a client. Returns the same object as getting a single client.

|Request fields | Description/format|
|------------ | -------------|
|name | String|
|street | String|
|zip | String|
|city | String|
|country | String|
|vat_number | String|
|notes | String|

### Sample JSON request
PUT https://api.forecast.it/api/v1/clients/1

```javascript
{
   "name":"Jane Doen Inc.",
   "street":"Sesame Street 42"
}
```

## Delete client

* `DELETE /clients/{clientId}` - Deletes a client.

### Sample JSON request
DELETE https://api.forecast.it/api/v1/clients/1