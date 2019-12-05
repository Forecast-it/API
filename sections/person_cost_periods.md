# Person Cost Periods

## Get all Person Cost Periods

* `GET /person_cost_periods` - Returns all person cost periods.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|company_id | Integer|
|person_id | Integer|
|start_year | Integer|
|start_month | Integer|
|start_day | Integer|
|cost | Integer|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
[
    {
        "id": 1,
        "company_id": 1,
        "person_id": 1,
        "cost": 6,
        "created_by": 1,
        "updated_by": 1,
        "created_at": "2019-10-03T08:49:58Z",
        "updated_at": "2019-10-22T07:58:07Z"
    },
    {
        "id": 2,
        "company_id": 1,
        "person_id": 1,
        "start_year": 2019,
        "start_month": 12,
        "start_day": 5,
        "cost": 10,
        "created_by": 1,
        "updated_by": 1,
        "created_at": "2019-12-05T12:28:27Z",
        "updated_at": "2019-12-05T12:28:27Z"
    }, ...
]
```

## Get Person Cost Periods by person ids

* `GET /person_cost_periods?pid={personId}&pid={personid}` - Returns all person cost periods for given person ids.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|company_id | Integer|
|person_id | Integer|
|start_year | Integer|
|start_month | Integer|
|start_day | Integer|
|cost | Integer|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
[
    {
        "id": 1,
        "company_id": 1,
        "person_id": 1,
        "cost": 6,
        "created_by": 1,
        "updated_by": 1,
        "created_at": "2019-10-03T08:49:58Z",
        "updated_at": "2019-10-22T07:58:07Z"
    },
    {
        "id": 2,
        "company_id": 1,
        "person_id": 1,
        "start_year": 2019,
        "start_month": 12,
        "start_day": 5,
        "cost": 10,
        "created_by": 1,
        "updated_by": 1,
        "created_at": "2019-12-05T12:28:27Z",
        "updated_at": "2019-12-05T12:28:27Z"
    }, ...
]