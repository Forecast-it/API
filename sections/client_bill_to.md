# ClientBillTos

## Get ClientBillTo

* `GET /client_bill_tos` - Returns all client bill tos

| Response fields | Description/format   |
|-----------------|----------------------|
| id              | Integer              |
| client_id       | Integer              |
| bill_from_id      | Integer              |
| bill_to_id      | Integer              |
| created_by      | Integer, ID of person |
| updated_by      | Integer, ID of person |
| created_at      | Date                 |
| updated_at      | Date                 |

### Sample JSON response
```json
[
  {
    "id": 1,
    "client_id": 2,
    "bill_from_id": 2,
    "bill_to_id": 3,
    "created_by": 1,
    "updated_by": 1,
    "created_at": "2020-01-14T18:46:56Z",
    "updated_at": "2020-01-14T18:47:58Z"
  },
  {
    "id": 2,
    "client_id": 1,
    "bill_from_id": 2,
    "bill_to_id": 3,
    "created_by": 1,
    "updated_by": 1,
    "created_at": "2020-01-14T18:46:56Z",
    "updated_at": "2020-01-14T18:47:58Z"
  }
]
```

* `GET /client_bill_tos?client_id={clientId}&client_id={clientId}` - Returns all client bill tos for given client ids.

| Response fields | Description/format   |
|-----------------|----------------------|
| id              | Integer              |
| client_id       | Integer              |
| bill_from_id      | Integer              |
| bill_to_id      | Integer              |
| created_by      | Integer, ID of person |
| updated_by      | Integer, ID of person |
| created_at      | Date                 |
| updated_at      | Date                 |

### Sample JSON response
```json
[
  {
    "id": 1,
    "client_id": 2,
    "bill_from_id": 2,
    "bill_to_id": 3,
    "created_by": 1,
    "updated_by": 1,
    "created_at": "2020-01-14T18:46:56Z",
    "updated_at": "2020-01-14T18:47:58Z"
  },
  {
    "id": 3,
    "client_id": 2,
    "bill_from_id": 2,
    "bill_to_id": 3,
    "created_by": 1,
    "updated_by": 1,
    "created_at": "2020-01-14T18:46:56Z",
    "updated_at": "2020-01-14T18:47:58Z"
  }
]
```

## Create ClientBillTo

* `POST /client_bill_tos` - Creates a new client bill to entry.


|Request fields | Description/format       |
|------------ |--------------------------|
|bill_from_id | Integer, id of bill_from |
|bill_to_id | Integer, id of bill_to   |
|client_id | Integer, id of client         |

### Sample JSON request
POST https://api.forecast.it/api/v1/client_bill_tos

```json
{
   "bill_from_id": 2,
   "bill_to_id": 3,
   "client_id": 2
}
```

| Response fields | Description/format   |
|-----------------|----------------------|
| id              | Integer              |
| client_id       | Integer              |
| bill_from_id      | Integer              |
| bill_to_id      | Integer              |
| created_by      | Integer, ID of person |
| updated_by      | Integer, ID of person |
| created_at      | Date                 |
| updated_at      | Date                 |

### Sample JSON response
```json
{
    "id": 1,
    "client_id": 2,
    "bill_from_id": 2,
    "bill_to_id": 3,
    "created_by": 1,
    "updated_by": 1,
    "created_at": "2020-01-14T18:46:56Z",
    "updated_at": "2020-01-14T18:47:58Z"
}
```

## Delete ClientBillTo

* `DELETE /client_bill_tos/{clientBillToId}` - Deletes a client bill to.

### Sample JSON request
DELETE https://api.forecast.it/api/v1/client_bill_tos/1
