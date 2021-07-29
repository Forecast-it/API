# Company

## Get company

- `GET /company` - Returns your company data.

| Response fields | Description/format          |
| --------------- | --------------------------- |
| city            | String                      |
| contact_email   | String                      |
| contact_name    | String                      |
| contact_phone   | String                      |
| country         | String (ISO 3166-1 Alpha 2) |
| currency        | String                      |
| company_name    | String                      |
| street          | String                      |
| seats           | Integer                     |
| vat_id          | String                      |
| virtual_seats   | Integer                     |
| zip             | String                      |
| companyTarget   | Double                      |

### Sample JSON response

```javascript
{
    "city": "New York City",
    "contact_email": "charles@xyz_company.com",
    "contact_name": "Charles Smith",
    "contact_phone": "(+1)23157342",
    "country": "US",
    "currency": "USD",
    "company_name": "xyz company",
    "seats": 50,
    "vat_id": "12345678",
    "virtual_seats": 10,
    "zip": "12345",
    "companyTarget": 0.7
}
```

## Update company

- `PUT /company` - Updates your company. Returns your company data.

| Request fields | Description/format          |
| -------------- | --------------------------- |
| city           | String                      |
| contact_email  | String                      |
| contact_name   | String                      |
| contact_phone  | String                      |
| country        | String (ISO 3166-1 Alpha 2) |
| currency       | String                      |
| company_name   | String                      |
| street         | String                      |
| vat_id         | String                      |
| zip            | String                      |
| companyTarget  | Double                      |

### Sample JSON request

PUT https://api.forecast.it/api/v1/company

```javascript

{
    "city": "New York City",
    "contact_email": "charles@xyz_company.com",
    "contact_name": "Charles Smith",
    "contact_phone": "(+1)23157342",
    "country": "US",
    "currency": "USD",
    "company_name": "xyz company",
    "seats": 50,
    "vat_id": "12345678",
    "virtual_seats": 10,
    "zip": "12345",
    "companyTarget": 0.7
}
```
