# Holiday Calendars

## Get holiday calendars

* `GET /holiday_calendar_entries` - Returns all holiday calendar entries.

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

## Create holiday calendar entry

* `POST /holiday_calendar_entries` - Creates a new holiday calendar entries. Returns the created calendar entry.

|Request fields | Description/format|
|------------ | -------------|
|holiday_calendar_id | Integer|
|year | Integer|
|month | Integer|
|day | Integer|
|name | String|

### Sample JSON request
POST https://api.forecast.it/api/v1/holiday_calendar_entries

```javascript
{
   "name":"Constitution day",
   "holiday_calendar_id": 1,
   "year": 2020,
   "month": 6,
   "day": 5
}
```

## Update holiday calendar entry

* `PUT /holiday_calendar_entries/{holidayCalendarEntryId}` - Updates a holiday calendar entry. Returns the updated calendar entry.

|Request fields | Description/format|
|------------ | -------------|
|year | Integer|
|month | Integer|
|day | Integer|
|name | String|

### Sample JSON request
PUT https://api.forecast.it/api/v1/holiday_calendar_entries/1

```javascript
{
    "name": "Juledag",
    "year": 2019,
    "month": 12,
    "day": 25
}
```

## Delete label

* `DELETE /holiday_calendar_entries/{holidayCalendarId}` - Deletes a label.

### Sample JSON request
DELETE https://api.forecast.it/api/v1/holiday_calendar_entries/1