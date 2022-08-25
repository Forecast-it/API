# Company contacts

## Get company contacts

* `GET /company_contact` - Returns all company contacts.

| Response fields | Description/format|
|-----------------| -------------|
| id              | Integer|
| person_id       | String|
| contact_type    | Integer|

### Sample JSON response
```javascript
[
   {
      "id":1,
      "person_id":22,
      "contact_type":"PRIMARY"
   }, ...
]
```

## Set company contact

* `PUT /company_contact` - Set a person for specific contact type of company.

|Response fields | Description/format               |
|------------ |----------------------------------|
|person_id | (Required*) Integer              |
|contact_type | (Required*) String {"PRIMARY", "BILLING', "DECISION_MAKER", "ONBOARDING', "TECHNICAL"} |

### Sample JSON response
```javascript
{
   "person_id":1,
   "contact_type":1
}
```

## Delete a company contact

* `DELETE /company_contact/{contactType}` - Remove the person that sets for a specific contact type.

### Sample JSON request
DELETE https://api.forecast.it/api/v1/company_contact/{ONBOARDING}
