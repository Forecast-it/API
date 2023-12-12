# ProjectBillTos

## Create ProjectBillTo

* `POST /project_bill_tos` - Creates a new project bill to entry.


| Request fields | Description/format            |
|----------------|-------------------------------|
| bill_from_id   | Integer, id of bill_from      |
| bill_to_id     | Integer, id of bill_to        |
| project_id     | Integer, id of project        |
| client_bill_to_id    | Integer, id of client_bill_to |
| client_id      | Integer, id of client         |

### Sample JSON request
POST https://api.forecast.it/api/v1/client_bill_tos

```json
{
    "bill_from_id": 2,
    "bill_to_id": 3,
    "project_id": 5,
    "client_bill_to_id": 4,
    "client_id": 2
}
```

| Response fields | Description/format   |
|-----------------|----------------------|
| id              | Integer              |
| bill_from_id    | Integer              |
| bill_to_id      | Integer              |
| project_id      | Integer              |
| client_bill_to_id      | Integer              |
| client_id       | Integer              |
| created_by      | Integer, ID of person |
| updated_by      | Integer, ID of person |
| created_at      | Date                 |
| updated_at      | Date                 |

### Sample JSON response
```json
{
    "id": 1,
    "bill_from_id": 2,
    "bill_to_id": 3,
    "project_id": 5,
    "client_bill_to_id": 4,
    "client_id": 2,
    "created_by": 1,
    "updated_by": 1,
    "created_at": "2020-01-14T18:46:56Z",
    "updated_at": "2020-01-14T18:47:58Z"
}
```

## Delete ProjectBillTo

* `DELETE /project_bill_tos/{projectBillToId}` - Deletes a project bill to.

### Sample JSON request
DELETE https://api.forecast.it/api/v1/project_bill_tos/1
