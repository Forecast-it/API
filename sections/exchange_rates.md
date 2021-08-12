# Exchange rates

## Get exchange rates

-  `GET /exchange_rates` - Returns all exchange rates.

| Response fields | Description/format    |
| --------------- | --------------------- |
| currency        | String                |
| rate            | Decimal               |

### Sample JSON response

Get https://api.forecast.it/api/v1/exchange_rates

```javascript
[
   {
      "currency": "EUR",
      "rate": 6.5
   }, ...
]
```

## Get exchange rate

-  `GET /exchange_rates/{currency}` - Returns a specific exchange rate.

| Response fields | Description/format    |
| --------------- | --------------------- |
| currency        | String                |
| rate            | Decimal               |

### Sample JSON response

Get https://api.forecast.it/api/v1/exchange_rates/EUR

```javascript
{
   "currency": "EUR",
   "rate": 6.5
}
```

## Create exchange rate

-  `POST /exchange_rates` - Creates a new exchange rate. Returns the same object as getting a single exchange rate.

| Response fields | Description/format    |
| --------------- | --------------------- |
| currency        | String                |
| rate            | Decimal               |

### Sample JSON request

POST https://api.forecast.it/api/v1/exchange_rates

```javascript
{
   "currency": "EUR",
   "rate": 6.5
}
```

## Update exchange rate

-  `PUT /exchange_rates/{currency}` - Updates an exchange rate. Returns the same object as getting a single exchange rate.

| Response fields | Description/format    |
| --------------- | --------------------- |
| currency        | String                |
| rate            | Decimal               |

### Sample JSON request

PUT https://api.forecast.it/api/v1/exchange_rates

```javascript
{
   "currency": "EUR",
   "rate": 6.3
}
```

## Delete exchange rate

-  `DELETE /exchange_rates/{currency}` - Deletes an exchange rate.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/exchange_rates/EUR
