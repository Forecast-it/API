# BillTos

## Get BillTo

* `GET /bill_tos` - Returns all bill tos

| Response fields | Description/format    |
|-----------------|-----------------------|
| id              | Integer               |
| name            | String                |
| address         | String                |
| tax_id          | String                |
| external_id     | String                |
| bill_from_id    | Integer               |
| created_by      | Integer, ID of person |
| updated_by      | Integer, ID of person |
| created_at      | Date                  |
| updated_at      | Date                  |

### Sample JSON response
```json
{
    "id": 1,
    "name": "Bill's Windsurf Shop",
    "address": "12 Ocean Dr. Half Moon Bay 94213 CA",
    "tax_id": "8559545",
    "external_id": "f0747n0b-c3a5-4039-af39-7bca06881858",
    "bill_from_id": 2,
    "created_by": 1,
    "updated_by": 1,
    "created_at": "2020-01-14T18:46:56Z",
    "updated_at": "2020-01-14T18:47:58Z"
}
```

* `GET /bill_tos?id={billToId}&id={billToId}` - Returns all bill tos for given bill to ids.

| Response fields | Description/format    |
|-----------------|-----------------------|
| id              | Integer               |
| name            | String                |
| address         | String                |
| tax_id          | String                |
| external_id     | String                |
| bill_from_id    | Integer               |
| created_by      | Integer, ID of person |
| updated_by      | Integer, ID of person |
| created_at      | Date                  |
| updated_at      | Date                  |

### Sample JSON response
```json
[
  {
    "id": 1,
    "name": "Bill's Windsurf Shop",
    "address": "12 Ocean Dr. Half Moon Bay 94213 CA",
    "tax_id": "8559545",
    "external_id": "f0747n0b-c3a5-4039-af39-7bca06881858",
    "bill_from_id": 2,
    "created_by": 1,
    "updated_by": 1,
    "created_at": "2023-01-14T18:46:56Z",
    "updated_at": "2023-01-14T18:47:58Z"
  },
  {
    "id": 2,
    "name": "Wedding Planning by Whitney",
    "address": "135 Broadway Menlo Park 94304 CA",
    "tax_id": null,
    "external_id": "90882359-d8f1-4399-ab95-8cc8fb11a553",
    "bill_from_id": 2,
    "created_by": 1,
    "updated_by": 1,
    "created_at": "2023-02-14T18:46:56Z",
    "updated_at": "2023-02-14T18:47:58Z"
  }
]
```

* `GET /bill_tos?bill_from_id={billFromId}&bill_from_id={billFromId}` - Returns all bill tos for given bill from ids.

| Response fields | Description/format    |
|-----------------|-----------------------|
| id              | Integer               |
| name            | String                |
| address         | String                |
| tax_id          | String                |
| external_id     | String                |
| bill_from_id    | Integer               |
| created_by      | Integer, ID of person |
| updated_by      | Integer, ID of person |
| created_at      | Date                  |
| updated_at      | Date                  |

### Sample JSON response
```json
[
  {
    "id": 1,
    "name": "Bill's Windsurf Shop",
    "address": "12 Ocean Dr. Half Moon Bay 94213 CA",
    "tax_id": "8559545",
    "external_id": "f0747n0b-c3a5-4039-af39-7bca06881858",
    "bill_from_id": 2,
    "created_by": 1,
    "updated_by": 1,
    "created_at": "2023-01-14T18:46:56Z",
    "updated_at": "2023-01-14T18:47:58Z"
  },
  {
    "id": 3,
    "name": "Video Games by Dan",
    "address": "202 Main St. Tucson 85704 AZ",
    "tax_id": null,
    "external_id": "21731893-d8f1-4399-ab95-8cc8fb11a553",
    "bill_from_id": 3,
    "created_by": 1,
    "updated_by": 1,
    "created_at": "2023-02-14T18:46:56Z",
    "updated_at": "2023-02-14T18:47:58Z"
  }
]
```