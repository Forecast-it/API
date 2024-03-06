# BillFroms

## Get BillFrom

* `GET /bill_froms` - Returns all bill froms

| Response fields | Description/format    |
|-----------------|-----------------------|
| id              | Integer               |
| name            | String                |
| integration               | String                |
| external_id     | String                |
| created_by      | Integer, ID of person |
| updated_by      | Integer, ID of person |
| created_at      | Date                  |
| updated_at      | Date                  |

### Sample JSON response
```json
{
    "id": 1,
    "name": "Example Xero Organisation",
    "integration": "XERO",
    "external_id": "f0747n0b-c3a5-4039-af39-7bca06881858",
    "created_by": 1,
    "updated_by": 1,
    "created_at": "2020-01-14T18:46:56Z",
    "updated_at": "2020-01-14T18:47:58Z"
}
```

* `GET /bill_froms?id={billFromId}&id={billFromId}` - Returns all bill froms for given bill from ids.

| Response fields | Description/format    |
|-----------------|-----------------------|
| id              | Integer               |
| name            | String                |
| integration               | String                |
| external_id     | String                |
| created_by      | Integer, ID of person |
| updated_by      | Integer, ID of person |
| created_at      | Date                  |
| updated_at      | Date                  |

### Sample JSON response
```json
[
  {
    "id": 1,
    "name": "Example Xero Organisation",
    "integration": "XERO",
    "external_id": "f0747n0b-c3a5-4039-af39-7bca06881858",
    "created_by": 1,
    "updated_by": 1,
    "created_at": "2020-01-14T18:46:56Z",
    "updated_at": "2020-01-14T18:47:58Z"
  },
  {
    "id": 2,
    "name": "Example QuickBooks Organisation",
    "integration": "QUICKBOOKS",
    "external_id": "f0747n0b-c3a5-4039-af39-7bca06881858",
    "created_by": 1,
    "updated_by": 1,
    "created_at": "2020-01-14T18:46:56Z",
    "updated_at": "2020-01-14T18:47:58Z"
  }
]
```

* `GET /bill_froms?integration={integration}&integration={integration}` - Returns all bill froms for given integration.

| Response fields | Description/format    |
|-----------------|-----------------------|
| id              | Integer               |
| name            | String                |
| integration               | String                |
| external_id     | String                |
| created_by      | Integer, ID of person |
| updated_by      | Integer, ID of person |
| created_at      | Date                  |
| updated_at      | Date                  |

### Sample JSON response
```json
[
  {
    "id": 1,
    "name": "Example Xero Organisation",
    "integration": "XERO",
    "external_id": "f0747n0b-c3a5-4039-af39-7bca06881858",
    "created_by": 1,
    "updated_by": 1,
    "created_at": "2020-01-14T18:46:56Z",
    "updated_at": "2020-01-14T18:47:58Z"
  },
  {
    "id": 3,
    "name": "Another Example Xero Organisation",
    "integration": "XERO",
    "external_id": "f0747n0b-c3a5-4039-af39-7bca06881858",
    "created_by": 1,
    "updated_by": 1,
    "created_at": "2020-01-14T18:46:56Z",
    "updated_at": "2020-01-14T18:47:58Z"
  }
]
```