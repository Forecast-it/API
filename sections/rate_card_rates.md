# Rate card rates

## Get rate card rates

* `GET /rate_cards/{rate_cardId}/rates` - Returns all rates for a rate card.

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
      "id":1,
      "rate":100.0,
      "role":1,
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:561Z",
      "updated_at":"2017-01-14T18:47:581Z"
   }, ...
]
```

## Get rate card rate

* `GET /rate_cards/{rate_cardId}/rates/{roleId}` - Returns a specific rate card rate for a role.

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
   "rate":100.0,
   "role":1,
   "created_by":1,
   "updated_by":1,
   "created_at":"2017-01-14T18:46:561Z",
   "updated_at":"2017-01-14T18:47:581Z"
}
```

## Update rate card rate

* `PUT /rate_cards/{rate_cardId}/rates/{roleId}` - Updates a rate card. Returns the same object as getting a single rate card.

|Request fields | Description/format|
|------------ | -------------|
|rate | String|

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