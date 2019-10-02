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

## Get Invoice

- `GET /invoices/{invoiceId}` - Returns a specific invoice.

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
    }

```

## Create invoice

- `POST /projects/{projectId}/invoices` - Creates a new invoice for a specific project. Returns the same object as getting a single invoice.

### Invoice

| Request fields    | Description/format                                       |
| ----------------- | -------------------------------------------------------- |
| name              | String                                                   |
| invoice_reference | String (Default INV-{Invoice ID})                        |
| invoice_type      | String (DEPOSIT, FIXED_PRICE, TIME_AND_MATERIAL, MANUAL) |
| created_day       | Integer                                                  |
| created_month     | Integer                                                  |
| created_year      | Integer                                                  |
| due_day           | Integer                                                  |
| due_month         | Integer                                                  |
| due_year          | Integer                                                  |
| notes             | String                                                   |
| status            | String (DRAFT, APPROVED, SENT), (default DRAFT)          |
| entries           | List<Entries>, List of entries                           |

### Entries

| Request fields | Description/format         |
| -------------- | -------------------------- |
| invoice_id     | Integer, ID of the Invoice |
| name           | String                     |
| quantity       | Integer                    |
| unit_price     | Double                     |
| discount       | Double                     |
| tax            | Double                     |
| description    | String                     |

### Sample JSON request

POST https://api.forecast.it/api/v1/projects/4/invoices

```javascript
{
    "id": 139,
    "company_invoice_id": 156,
    "project_id": 4,
    "name": "Invoice for the Queen",
    "invoice_reference": "INV-156",
    "invoice_type": "FIXED_PRICE",
    "created_day": 5,
    "created_month": 9,
    "created_year": 2019,
    "due_day": 12,
    "due_month": 10,
    "due_year": 2019,
    "status": "DRAFT",
    "entries": [
        {
            "id": 134,
            "invoice_id": 80,
            "name": "Time worked on Task 10",
            "quantity": 2,
            "unit_price": 12.5,
            "discount": 0,
            "tax": 0,
        }
    ], ...
    "created_by": 97,
    "created_at": "2019-10-02T15:48:19Z"
}
```

## Update invoice

- `PUT /invoices/{invoiceId}` - Updates a specific invoice. Returns the same object as getting a single invoice.

### Invoice

| Request fields    | Description/format                                       |
| ----------------- | -------------------------------------------------------- |
| name              | String                                                   |
| invoice_reference | String (Default INV-{Invoice ID})                        |
| invoice_type      | String (DEPOSIT, FIXED_PRICE, TIME_AND_MATERIAL, MANUAL) |
| created_day       | Integer                                                  |
| created_month     | Integer                                                  |
| created_year      | Integer                                                  |
| due_day           | Integer                                                  |
| due_month         | Integer                                                  |
| due_year          | Integer                                                  |
| notes             | String                                                   |
| status            | String (DRAFT, APPROVED, SENT), (default DRAFT)          |
| entries           | List<Entries>, List of entries                           |
| payments          | List<Payements>, List of payments                        |

### Entries

- If the entry id is specified then this entry will be updated (or an error occure if it does not exist) else a new entry will be created.

| Request fields | Description/format         |
| -------------- | -------------------------- |
| id             | Integer, ID of the entry   |
| invoice_id     | Integer, ID of the Invoice |
| name           | String                     |
| quantity       | Integer                    |
| unit_price     | Double                     |
| discount       | Double                     |
| tax            | Double                     |
| description    | String                     |

### Payments

- If the payment id is specified then this payment will be updated (or an error occure if it does not exist) else a new payment will be created.

| Response fields | Description/format         |
| --------------- | -------------------------- |
| id              | Integer                    |
| invoice_id      | Integer, ID of the Invoice |
| notes           | String                     |
| amount          | Double                     |
| day             | Integer                    |
| month           | Integer                    |
| year            | Integer                    |

### Sample JSON request

PUT https://api.forecast.it/api/v1/invoices/58

```javascript
{
    "id": 58,
    "company_invoice_id": 90,
    "project_id": 4,
    "name": "Invoice of the month",
    "invoice_reference": "INV-90",
    "invoice_type": "FIXED_PRICE",
    "created_day": 15,
    "created_month": 12,
    "created_year": 2020,
    "due_day": 16,
    "due_month": 12,
    "due_year": 2020,
    "status": "DRAFT",
    "entries": [
        {
            "id": 214,
            "name": "entry 3",
            "quantity": 2,
            "discount": 0,
            "tax": 0
        },...
    ],
    "payments": [
        {
            "id": 6,
            "invoice_id": 58,
            "notes": "awesome payment",
            "amount": 1500,
            "day": 5,
            "month": 12,
            "year": 2019,
            "created_by": 97,
            "created_at": "2019-10-02T16:44:33Z"
        },...
    ],
    "created_by": 97,
    "created_at": "2019-10-01T11:21:36Z"
}
```

## Delete Invoice

- `DELETE /invoices/{invoiceId}` - Deletes a specific invoice and its entries and payments if there are.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/invoices/1

# Invoice Entries

## Create Invoice entry

- `POST /invoices/{invoiceId}/invoice_entries` - Creates a new invoice entry for a specific invoice. Returns the newly created invoice entry.

| Request fields | Description/format         |
| -------------- | -------------------------- |
| project_id     | Integer, ID of the porject |
| name           | String                     |
| quantity       | Integer                    |
| unit_price     | Double                     |
| discount       | Double                     |
| tax            | Double                     |
| description    | String                     |

### Sample JSON request

POST https://api.forecast.it/api/v1/invoices/84/invoice_entries

```javascript
{
    "id": 134,
    "invoice_id": 84,
    "name": "2 hours registered",
    "quantity": 2,
    "unit_price": 12.5,
    "discount": 0,
    "tax": 0
}
```

## Update invoice entry

- `PUT /invoice_entries/{invoiceEntryId}` - Updates a specific invoice entry. Returns the updated invoice entry.

| Request fields | Description/format         |
| -------------- | -------------------------- |
| invoice_id     | Integer, ID of the Invoice |
| name           | String                     |
| quantity       | Integer                    |
| unit_price     | Double                     |
| discount       | Double                     |
| tax            | Double                     |
| description    | String                     |

### Sample JSON request

PUT https://api.forecast.it/api/v1/invoice_entries/221

```javascript
{
    "id": 221,
    "invoice_id": 59,
    "name": "New name",
    "quantity": 2,
    "unit_price": 12.5,
    "discount": 0,
    "tax": 0
}
```

## Delete Invoice Entry

- `DELETE /invoice_entries/{invoiceEntryId}` - Deletes a specific invoice entry.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/invoice_entries/1

# Invoice Payments

## Create Invoice payment

- `POST /invoices/{invoiceId}/invoice_payments` - Creates a new invoice payment for a specific invoice. Returns the newly created invoice payment.

| Request fields | Description/format |
| -------------- | ------------------ |
| notes          | String             |
| amount         | Integer            |
| year           | Integer            |
| month          | Integer            |
| day            | Integer            |

### Sample JSON request

POST https://api.forecast.it/api/v1/invoices/80/invoice_payments

```javascript
{
    "id": 7,
    "invoice_id": 80,
    "notes": "the payment",
    "amount": 150,
    "day": 5,
    "month": 12,
    "year": 2019,
    "created_by": 97,
    "created_at": "2019-10-02T17:28:29Z"
}
```

## Update Invoice Payment

- `PUT /invoice_payments/{invoicePaymentId}` - Updates a specific invoice payment. Returns the updated invoice payment.

| Request fields | Description/format |
| -------------- | ------------------ |
| notes          | String             |
| amount         | Integer            |
| year           | Integer            |
| month          | Integer            |
| day            | Integer            |


### Sample JSON request

PUT https://api.forecast.it/api/v1/invoice_payments/7

```javascript
{
    "id": 7,
    "invoice_id": 80,
    "notes": "the payment",
    "amount": 150,
    "day": 5,
    "month": 12,
    "year": 2019,
    "created_by": 97,
    "created_at": "2019-10-02T17:28:29Z"
}
```

## Delete Invoice Entry

- `DELETE /invoice_entries/{invoiceEntryId}` - Deletes a specific invoice payment.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/invoice_payments/1
