# Invoices

## Get Invoices

-   `GET /invoices` - Returns all invoices across projects.

### Invoice

| Response fields    | Description/format                                       |
| ------------------ | -------------------------------------------------------- |
| id                 | Integer                                                  |
| company_invoice_id | Integer                                                  |
| project_id         | Integer, ID of the project                               |
| name               | String                                                   |
| currency           | String                                                   |
| client_id          | Integer, ID of client                                    |
| invoice_reference  | String                                                   |
| invoice_type       | String (DEPOSIT, FIXED_PRICE, TIME_AND_MATERIAL, MANUAL) |
| created_date       | Date                                                     |
| due_date           | Date                                                     |
| notes              | String                                                   |
| status             | String (DRAFT, APPROVED, SENT)                           |
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
| project_id      | Integer, ID of project     |
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
| date            | Date                       |
| created_by      | Integer, ID of person      |
| updated_by      | Integer, ID of person      |
| created_at      | Date                       |
| updated_at      | Date                       |

### Sample JSON response

```json
[
    {
        "id": 80,
        "company_invoice_id": 90,
        "project_id": 4,
        "name": "Invoice for Client 12",
        "invoice_reference": "INV-90",
        "invoice_type": "FIXED_PRICE",
        "created_date": "2020-09-05",
        "due_date": "2020-10-12",
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
            }
        ],
        "payments": [
            {
                "id": 2,
                "invoice_id": 80,
                "notes": "payment for december",
                "amount": 150,
                "date": "2020-12-05",
                "created_by": 97,
                "created_at": "2019-10-02T09:18:02Z"
            }
        ],
        "created_by": 97,
        "created_at": "2019-10-01T11:21:36Z"
    }
]
```
## Get Invoices with status

-   `GET /invoices/status/{invoiceStatus}` - Returns all invoices with the given status. invoiceStatus can be DRAFT, APPROVED or SENT

returns the same list of invoices with entries and payments as "Get Invoices" see above for details

## Create invoice

-   `POST /invoices` - Creates a new invoice. Returns the same object as getting a single invoice. This invoice can be
    cross-projects, by specifying the project_id on Entry level. All projects most belong to the same client_id, which
    is defined on the Invoice. 

### Invoice

| Request fields    | Description/format                                       |
| ----------------- | -------------------------------------------------------- |
| name              | String                                                   |
| currency          | String (Defaults to company currency)                    |
| client_id         | Integer, ID of client                                    |
| invoice_reference | String (Default INV-{Invoice ID})                        |
| created_date      | Date                                                     |
| due_date          | Date                                                     |
| notes             | String                                                   |
| status            | String (DRAFT, APPROVED, SENT), (default DRAFT)          |
| entries           | List<Entries>, List of entries                           |

### Entries

| Request fields | Description/format     |
| -------------- | ---------------------- |
| name           | String                 |
| project_id     | Integer, ID of project |
| quantity       | Integer                |
| unit_price     | Double                 |
| discount       | Double                 |
| tax            | Double                 |
| description    | String                 |

### Sample JSON request

POST https://api.forecast.it/api/v1/projects/123/invoices

```json
{
    "name": "Invoice for the Queen",
    "invoice_reference": "INV-156",
    "invoice_type": "FIXED_PRICE",
    "created_date": "2020-09-05",
    "due_date": "2020-10-12",
    "status": "DRAFT",
    "entries": [
        {
            "name": "Time worked on Task 10",
            "quantity": 2,
            "unit_price": 12.5,
            "discount": 0,
            "tax": 0
        }
    ]
}
```

## Get Invoices for a project

-   `GET /projects/{projectId}/invoices` - Returns all invoices of a specific project.

### Invoice

| Response fields    | Description/format                                       |
| ------------------ | -------------------------------------------------------- |
| id                 | Integer                                                  |
| company_invoice_id | Integer                                                  |
| project_id         | Integer, ID of the project                               |
| name               | String                                                   |
| currency           | String                                                   |
| client_id          | Integer, ID of client                                    |
| invoice_reference  | String                                                   |
| invoice_type       | String (DEPOSIT, FIXED_PRICE, TIME_AND_MATERIAL, MANUAL) |
| created_date       | Date                                                     |
| due_date           | Date                                                     |
| notes              | String                                                   |
| status             | String (DRAFT, APPROVED, SENT)                           |
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
| project_id      | Integer, ID of project     |
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
| date            | Date                       |
| created_by      | Integer, ID of person      |
| updated_by      | Integer, ID of person      |
| created_at      | Date                       |
| updated_at      | Date                       |

### Sample JSON response

```json
[
    {
        "id": 80,
        "company_invoice_id": 90,
        "project_id": 4,
        "name": "Invoice for Client 12",
        "invoice_reference": "INV-90",
        "invoice_type": "FIXED_PRICE",
        "created_date": "2020-09-05",
        "due_date": "2020-10-12",
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
            }
        ],
        "payments": [
            {
                "id": 2,
                "invoice_id": 80,
                "notes": "payment for december",
                "amount": 150,
                "date": "2020-12-05",
                "created_by": 97,
                "created_at": "2019-10-02T09:18:02Z"
            }
        ],
        "created_by": 97,
        "created_at": "2019-10-01T11:21:36Z"
    }
]
```

## Get Invoice

-   `GET /invoices/{invoiceId}` - Returns a specific invoice.

### Invoice

| Response fields    | Description/format                                       |
| ------------------ | -------------------------------------------------------- |
| id                 | Integer                                                  |
| company_invoice_id | Integer                                                  |
| project_id         | Integer, ID of the project                               |
| name               | String                                                   |
| currency           | String                                                   |
| client_id          | Integer, ID of client                                    |
| invoice_reference  | String                                                   |
| invoice_type       | String (DEPOSIT, FIXED_PRICE, TIME_AND_MATERIAL, MANUAL) |
| created_date       | Date                                                     |
| due_date           | Date                                                     |
| notes              | String                                                   |
| status             | String (DRAFT, APPROVED, SENT)                           |
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
| project_id      | Integer, ID of project     |
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
| date            | Date                       |
| created_by      | Integer, ID of person      |
| updated_by      | Integer, ID of person      |
| created_at      | Date                       |
| updated_at      | Date                       |

### Sample JSON response

```json
   {
        "id": 123,
        "company_invoice_id": 90,
        "project_id": 4,
        "name": "Invoice for Client 12",
        "invoice_reference": "INV-90",
        "invoice_type": "FIXED_PRICE",
        "created_date": "2020-09-05",
        "due_date": "2020-10-12",
        "status": "SENT",
        "entries": [
             {
                "id": 1,
                "invoice_id": 123,
                "name": "Time worked on Task 2",
                "quantity": 2,
                "unit_price": 12.5,
                "discount": 0,
                "tax": 0,
                "description": "need to be paid"
            }
        ],
        "payments": [
            {
                "id": 1,
                "invoice_id": 123,
                "notes": "payment for december",
                "amount": 150,
                "date": "2020-12-05",
                "created_by": 97,
                "created_at": "2019-10-02T09:18:02Z"
            }
        ],
        "created_by": 97,
        "created_at": "2019-10-01T11:21:36Z"
    }

```

## Create invoice

-   `POST /projects/{projectId}/invoices` - Creates a new invoice for a specific project. Returns the same object as getting a single invoice.

### Invoice

| Request fields    | Description/format                                       |
| ----------------- | -------------------------------------------------------- |
| name              | String                                                   |
| currency          | String (Defaults to company currency)                    |
| client_id         | Integer, ID of client                                    |
| invoice_reference | String (Default INV-{Invoice ID})                        |
| invoice_type      | String (DEPOSIT, FIXED_PRICE, TIME_AND_MATERIAL, MANUAL) |
| created_date      | Date                                                     |
| due_date          | Date                                                     |
| notes             | String                                                   |
| status            | String (DRAFT, APPROVED, SENT), (default DRAFT)          |
| entries           | List<Entries>, List of entries                           |

### Entries

| Request fields | Description/format     |
| -------------- | ---------------------- |
| name           | String                 |
| project_id     | Integer, ID of project |
| quantity       | Integer                |
| unit_price     | Double                 |
| discount       | Double                 |
| tax            | Double                 |
| description    | String                 |

### Sample JSON request

POST https://api.forecast.it/api/v1/projects/123/invoices

```json
{
    "name": "Invoice for the Queen",
    "invoice_reference": "INV-156",
    "invoice_type": "FIXED_PRICE",
    "created_date": "2020-09-05",
    "due_date": "2020-10-12",
    "status": "DRAFT",
    "entries": [
        {
            "name": "Time worked on Task 10",
            "quantity": 2,
            "unit_price": 12.5,
            "discount": 0,
            "tax": 0
        }
    ]
}
```

## Update invoice

-   `PUT /invoices/{invoiceId}` - Updates a specific invoice. Returns the same object as getting a single invoice.

### Invoice

| Request fields    | Description/format                                       |
| ----------------- | -------------------------------------------------------- |
| name              | String                                                   |
| currency          | String                                                   |
| client_id         | Integer, ID of client                                    |
| invoice_reference | String (Default INV-{Invoice ID})                        |
| invoice_type      | String (DEPOSIT, FIXED_PRICE, TIME_AND_MATERIAL, MANUAL) |
| created_date      | Date                                                     |
| due_date          | Date                                                     |
| notes             | String                                                   |
| status            | String (DRAFT, APPROVED, SENT), (default DRAFT)          |
| entries           | List<Entries>, List of entries                           |
| payments          | List<Payements>, List of payments                        |

### Entries

-   If the entry id is specified then this entry will be updated (or an error occure if it does not exist) else a new entry will be created.

| Request fields | Description/format       |
| -------------- | ------------------------ |
| id             | Integer, ID of the entry |
| name           | String                   |
| project_id     | Integer, ID of project   |
| quantity       | Integer                  |
| unit_price     | Double                   |
| discount       | Double                   |
| tax            | Double                   |
| description    | String                   |

### Payments

-   If the payment id is specified then this payment will be updated (or an error occure if it does not exist) else a new payment will be created.

| Request fields | Description/format         |
| -------------- | -------------------------- |
| id             | Integer, ID of the payment |
| notes          | String                     |
| amount         | Double                     |
| date           | Date                       |

### Sample JSON request

PUT https://api.forecast.it/api/v1/invoices/123

```json
{
    "name": "Invoice of the month",
    "invoice_reference": "INV-90",
    "invoice_type": "FIXED_PRICE",
    "created_date": "2020-09-05",
    "due_date": "2020-10-12",
    "status": "DRAFT",
    "entries": [
        {
            "id": 214,
            "name": "interesting entry",
            "quantity": 2,
            "discount": 0,
            "tax": 0,
            "unit_price": 100.00
        }
    ],
    "payments": [
        {
            "id": 6,
            "notes": "awesome payment",
            "amount": 1500,
            "date": "2020-12-05"
        }
    ]
}
```

## Delete Invoice

-   `DELETE /invoices/{invoiceId}` - Deletes a specific invoice and its entries and payments if there are any.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/invoices/123

# Invoice Entries

## Create Invoice entry

-   `POST /invoices/{invoiceId}/invoice_entries` - Creates a new invoice entry for a specific invoice. Returns the newly created invoice entry.

| Request fields | Description/format     |
| -------------- | ---------------------- |
| name           | String, Required       |
| project_id     | Integer, ID of project |
| quantity       | Integer, Required      |
| unit_price     | Double, Required       |
| discount       | Double                 |
| tax            | Double                 |
| description    | String                 |

### Sample JSON request

POST https://api.forecast.it/api/v1/invoices/84/invoice_entries

```json
{
    "name": "2 hours registered",
    "quantity": 2,
    "unit_price": 12.5,
    "discount": 0,
    "tax": 0,
    "description": "Worked on the thing"
}
```

## Update invoice entry

-   `PUT /invoice_entries/{invoiceEntryId}` - Updates a specific invoice entry. Returns the updated invoice entry.

| Request fields | Description/format     |
| -------------- | ---------------------- |
| name           | String                 |
| project_id     | Integer, ID of project |
| quantity       | Integer                |
| unit_price     | Double                 |
| discount       | Double                 |
| tax            | Double                 |
| description    | String                 |

### Sample JSON request

PUT https://api.forecast.it/api/v1/invoice_entries/123

```json
{
    "name": "New name",
    "quantity": 2,
    "unit_price": 12.5,
    "discount": 0,
    "tax": 0,
    "description": "Worked on the thing"
}
```

## Delete Invoice Entry

-   `DELETE /invoice_entries/{invoiceEntryId}` - Deletes a specific invoice entry.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/invoice_entries/123

# Invoice Payments

## Create Invoice payment

-   `POST /invoices/{invoiceId}/invoice_payments` - Creates a new invoice payment for a specific invoice. Returns the newly created invoice payment.

| Request fields | Description/format |
| -------------- | ------------------ |
| notes          | String             |
| amount         | Integer            |
| date           | Date               |

### Sample JSON request

POST https://api.forecast.it/api/v1/invoices/80/invoice_payments

```json
{
    "notes": "the payment",
    "amount": 150,
    "date": "2020-12-05"
}
```

## Update Invoice Payment

-   `PUT /invoice_payments/{invoicePaymentId}` - Updates a specific invoice payment. Returns the updated invoice payment.

| Request fields | Description/format |
| -------------- | ------------------ |
| notes          | String             |
| amount         | Integer            |
| date           | Date               |

### Sample JSON request

PUT https://api.forecast.it/api/v1/invoice_payments/123

```json
{
    "notes": "the payment",
    "amount": 150,
    "date": "2020-12-05"
}
```

## Delete Invoice Payment

-   `DELETE /invoice_payments/{invoicePaymentId}` - Deletes a specific invoice payment.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/invoice_payments/123
