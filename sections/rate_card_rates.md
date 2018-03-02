# Rate card rates

## Get rate card rates

* `GET /rate_cards/{rate_cardId}/rates` - Returns all rates for a rate card. All roles might not be present. When a role is not present, the default rate of the rate card is used.

|Response fields | Description/format|
|------------ | -------------|
|role | Integer, ID of the role|
|rate | Decimal|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
[
   {
      "role":1,
      "rate":100.0,
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z"
   }, ...
]
```

## Get rate card rate

* `GET /rate_cards/{rate_cardId}/rates/{roleId}` - Returns a specific rate card rate for a role. This will return a 404 error if the role does not have a rate.

|Response fields | Description/format|
|------------ | -------------|
|role | Integer, ID of the role|
|rate | Decimal|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
{
   "role":1,
   "rate":100.0,
   "created_by":1,
   "updated_by":1,
   "created_at":"2017-01-14T18:46:56Z",
   "updated_at":"2017-01-14T18:47:58Z"
}
```

## Update rate card rate

* `PUT /rate_cards/{rate_cardId}/rates/{roleId}` - Updates a rate card rate. Returns the same object as getting a single rate card rate.

|Request fields | Description/format|
|------------ | -------------|
|rate | Decimal|

### Sample JSON request
PUT https://api.forecast.it/api/v1/rate_cards/1/rates/1

```javascript
{
   "rate":120.0
}
```

## Delete rate card rate

* `DELETE /rate_cards/{rate_cardId}/rates/{roleId}` - Deletes a rate card rate.

### Sample JSON request
DELETE https://api.forecast.it/api/v1/rate_cards/1/rates/1