# Invoices

## Get Invoices

- `GET /projects/{projectId}/invoices` - Returns all invoices of a specific project.

### Invoice

| Response fields    | Description/format                                       |
| ------------------ | -------------------------------------------------------- |
| id                 | Integer                                                  |
| company_invoice_id | Integer                                                  |
| project_id         | Integer, ID of the project                               |
| name               | String                                                   |
| invoice_reference  | String                                                   |
| invoice_type       | String (DEPOSIT, FIXED_PRICE, TIME_AND_MATERIAL, MANUAL) |
| created_day        | Integer                                                  |
| created_month      | Integer                                                  |
| created_year       | Integer                                                  |
| due_day            | Integer                                                  |
| due_month          | Integer                                                  |
| due_year           | Integer                                                  |
| notes              | String                                                   |
| status             | String (DRAFT, APPROVED, SENT)                          |
| entries            | List<Entries>, List of entries                           |
| payments           | List<Payments>, List of payments                         |
| created_by         | Integer, ID of person                                    |
| updated_by         | Integer, ID of person                                    |
| created_at         | Date                                                     |
| updated_at         | Date                                                     |

### Entries

| Response fields | Description/format         |
| --------------- | -------------------------- |
| id              | Integer                    |
| invoice_id      | Integer, ID of the Invoice |
| name            | String                     |
| quantity        | Integer                    |
| unit_price      | Double                     |
| discount        | Double                     |
| tax             | Double                     |
| description     | String                     |
| created_by      | Integer, ID of person      |
| updated_by      | Integer, ID of person      |
| created_at      | Date                       |
| updated_at      | Date                       |

### Payments

| Response fields | Description/format         |
| --------------- | -------------------------- |
| id              | Integer                    |
| invoice_id      | Integer, ID of the Invoice |
| notes           | String                     |
| amount          | Double                     |
| day             | Integer                    |
| month           | Integer                    |
| year            | Integer                    |
| created_by      | Integer, ID of person      |
| updated_by      | Integer, ID of person      |
| created_at      | Date                       |
| updated_at      | Date                       |

### Sample JSON response

```javascript
[
    {
        "id": 58,
        "company_invoice_id": 90,
        "project_id": 4,
        "name": "Invoice for Client 12",
        "invoice_reference": "INV-90",
        "invoice_type": "FIXED_PRICE",
        "created_day": 5,
        "created_month": 9,
        "created_year": 2019,
        "due_day": 12,
        "due_month": 10,
        "due_year": 2019,
        "status": "SENT",
        "entries": [
             {
                "id": 134,
                "invoice_id": 80,
                "name": "Time worked on Task 2",
                "quantity": 2,
                "unit_price": 12.5,
                "discount": 0,
                "tax": 0,
                "description": "need to be paid"
            }, ...
        ],
        "payments": [
            {
                "id": 2,
                "invoice_id": 80,
                "notes": "payment for december",
                "amount": 150,
                "day": 5,
                "month": 12,
                "year": 2019,
                "created_by": 97,
                "created_at": "2019-10-02T09:18:02Z"
            }, ...
        ],
        "created_by": 97,
        "created_at": "2019-10-01T11:21:36Z"
    }, ...
]
```