# Rate cards

## Get rate cards

-  `GET /rate_cards` - Returns all rate cards.

| Response fields | Description/format    |
| --------------- | --------------------- |
| id              | Integer               |
| name            | String                |
| default_rate    | Decimal               |
| created_by      | Integer, ID of person |
| updated_by      | Integer, ID of person |
| created_at      | Date                  |
| updated_at      | Date                  |

### Sample JSON response

```javascript
[
   {
      "id":1,
      "name":"High end rates 2017",
      "default_rate":200.0,
      "currency":"USD",
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z"
   }, ...
]
```

## Get rate card

-  `GET /rate_cards/{rate_cardId}` - Returns a specific rate card.

| Response fields | Description/format    |
| --------------- | --------------------- |
| id              | Integer               |
| name            | String                |
| default_rate    | Decimal               |
| created_by      | Integer, ID of person |
| updated_by      | Integer, ID of person |
| created_at      | Date                  |
| updated_at      | Date                  |

### Sample JSON response

```javascript
{
   "id":1,
   "name":"High end rates 2017",
   "default_rate":200.0,
   "currency":"USD",
   "created_by":1,
   "updated_by":1,
   "created_at":"2017-01-14T18:46:56Z",
   "updated_at":"2017-01-14T18:47:58Z"
}
```

## Create rate card

-  `POST /rate_cards` - Creates a new rate card. Returns the same object as getting a single rate card.

| Request fields | Description/format |
| -------------- | ------------------ |
| name           | (Required) String  |
| default_rate   | Decimal            |

### Sample JSON request

POST https://api.forecast.it/api/v1/rate_cards

```javascript
{
   "name":"Low end rates 2017",
   "default_rate":150.0,
}
```

## Update rate card

-  `PUT /rate_cards/{rate_cardId}` - Updates a rate card. Returns the same object as getting a single rate card.

| Request fields | Description/format |
| -------------- | ------------------ |
| name           | String             |
| default_rate   | Decimal            |

### Sample JSON request

PUT https://api.forecast.it/api/v1/rate_cards/1

```javascript
{
   "name":"High end rates 2017-2018",
}
```

## Delete rate card

-  `DELETE /rate_cards/{rate_cardId}` - Deletes a rate card.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/rate_cards/1
