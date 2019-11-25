# Holiday Calendars

## Get holiday calendars

* `GET /holiday_calendars` - Returns all holiday calendars.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|name | String|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
[
   {
      "id":1,
      "name":"Danish holidays",
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z"
   }, ...
]
```

## Get holiday calendar

* `GET /holiday_calendars/{holidayCalendarId}` - Returns a specific holiday calendar.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|name | String|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
{
   "id":1,
   "name":"Danish holidays",
   "created_by":1,
   "updated_by":1,
   "created_at":"2017-01-14T18:46:56Z",
   "updated_at":"2017-01-14T18:47:58Z"
}
```

## Get holiday calendar entries

* `GET /holiday_calendars/{holidayCalendarId}/holiday_calendar_entries` - Returns a specific holiday calendar.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|holiday_calendar_id | Integer|
|year | Integer|
|month | Integer|
|day | Integer|
|name | String|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
[
    {
        "id": 1,
        "holiday_calendar_id": 1,
        "year": 2019,
        "month": 12,
        "day": 24,
        "name": "Christmas",
        "created_by": 1,
        "updated_by": 1,
        "created_at": "2019-11-25T11:00:56Z",
        "updated_at": "2019-11-25T11:00:56Z"
    },
    {
        "id": 2,
        "holiday_calendar_id": 1,
        "year": 2020,
        "month": 5,
        "day": 30,
        "name": "Ascension Day",
        "created_by": 1,
        "updated_by": 1,
        "created_at": "2019-11-25T11:01:00Z",
        "updated_at": "2019-11-25T11:01:00Z"
    }, ...
]
```

## Create holiday calendar

* `POST /holiday_calendars` - Creates a new holiday calendar. Returns the created calendar.

|Request fields | Description/format|
|------------ | -------------|
|name | (Required) String|

### Sample JSON request
POST https://api.forecast.it/api/v1/holiday_calendars

```javascript
{
   "id":2,
   "name":"Swedish holidays",
   "created_by":1,
   "updated_by":1,
   "created_at":"2017-01-14T18:46:56Z",
   "updated_at":"2017-01-14T18:47:58Z"
}
```

## Update holiday calendar

* `PUT /holiday_calendars/{holidayCalendarId}` - Updates a label. Returns the updated calendar.

|Request fields | Description/format|
|------------ | -------------|
|name | String|

### Sample JSON request
PUT https://api.forecast.it/api/v1/holiday_calendars/1

```javascript
{
    "id": 1,
    "name": "Norwegian holidays",
    "created_by": 2045,
    "updated_by": 2064,
    "created_at": "2019-11-25T11:00:40Z",
    "updated_at": "2019-11-25T11:48:54Z"
}
```

## Delete holiday calendar

* `DELETE /holiday_calendars/{holidayCalendarId}` - Deletes a holiday calendar.

### Sample JSON request
DELETE https://api.forecast.it/api/v1/holiday_calendars/1