# Company

## Get company

* `GET /company` - Returns your company details

|Response fields | Description/format|
|------------ | -------------|
|name | String|
|street | String|
|zip | String|
|city | String|
|country | String|
|vat_number | String|
|currency | String, 3 letter iso code|
|monday | Integer, working hours in minutes|
|tuesday | Integer, working hours in minutes|
|wednesday | Integer, working hours in minutes|
|thursday | Integer, working hours in minutes|
|friday | Integer, working hours in minutes|
|saturday | Integer, working hours in minutes|
|sunday | Integer, working hours in minutes|
|timezone | String|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
{
   "name":"John Dow Inc.",
   "street":"Broadway 1",
   "zip":"90210",
   "city":"Los Angeles",
   "country":"United States",
   "vat_number":null,
   "currency":"USD",
   "monday":480,
   "tuesday":480,
   "wednesday":480,
   "thursday":480,
   "friday":480,
   "saturday":0,
   "sunday":0,
   "timezone":"Europe/Copenhagen"
   "created_by":1,
   "updated_by":1,
   "created_at":"2017-01-14T18:46:56+01:00",
   "updated_at":"2017-01-14T18:47:58+01:00"
}
```