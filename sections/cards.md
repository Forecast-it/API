# Cards

## Get all cards

* `GET /cards` - Returns all cards in your account (This may be a large dataset).
* `GET /cards?updated_after=DDMMYYYYTHHmmss` - Returns all cards in your account that have been updated after the specified time. Example value: `16022018T210047`.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|title | String|
|description | String|
|project_id | Integer, ID of project|
|role | Integer, ID of role|
|low_estimate | Decimal|
|high_estimate | Decimal|
|forecast | Decimal|
|approved | Boolean|
|start_date | Date|
|end_date | Date|
|bug | Boolean|
|un_billable | Boolean|
|blocked | Boolean|
|sprint | Integer, ID of sprint|
|workflow_column | Integer, ID of workflow column|
|milestone | Integer, ID of milestone|
|assigned_persons | List<Integer>, List ID of assigned persons|
|labels | List<Integer>, List ID of labels|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
[
   {
      "id":1,
      "title":"Design login screen",
      "description":"",
      "project_id":1,
      "role":1,
      "low_estimate":10.0,
      "high_estimate":20.0,
      "forecast":26.0,
      "approved":true,
      "start_date":"2017-01-01",
      "end_date":"2017-01-20",
      "bug":false,
      "un_billable":false,
      "blocked":false,
      "sprint":1,
      "workflow_column":2,
      "milestone":1,
      "assigned_persons":[1,2,3],
      "labels":[1,2,3],
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z"
   }, ...
]
```

## Get cards in project

* `GET /projects/{projectId}/cards` - Returns all cards of the project.
* `GET /projects/{projectId}/cards?updated_after=DDMMYYYYTHHmmss` - Returns all cards of the project that have been updated after the specified time. Example value: `16022018T210047`.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|title | String|
|description | String|
|project_id | Integer, ID of project|
|role | Integer, ID of role|
|low_estimate | Decimal|
|high_estimate | Decimal|
|forecast | Decimal|
|approved | Boolean|
|start_date | Date|
|end_date | Date|
|bug | Boolean|
|un_billable | Boolean|
|blocked | Boolean|
|sprint | Integer, ID of sprint|
|workflow_column | Integer, ID of workflow column|
|milestone | Integer, ID of milestone|
|assigned_persons | List<Integer>, List ID of assigned persons|
|labels | List<Integer>, List ID of labels|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
[
   {
      "id":1,
      "title":"Design login screen",
      "description":"",
      "project_id":1,
      "role":1,
      "low_estimate":10.0,
      "high_estimate":20.0,
      "forecast":26.0,
      "approved":true,
      "start_date":"2017-01-01",
      "end_date":"2017-01-20",
      "bug":false,
      "un_billable":false,
      "blocked":false,
      "sprint":1,
      "workflow_column":2,
      "milestone":1,
      "assigned_persons":[1,2,3],
      "labels":[1,2,3],
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z"
   }, ...
]
```

## Get card

* `GET /cards/{cardId}` - Returns a specific card.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|title | String|
|description | String|
|project_id | Integer, ID of project|
|role | Integer, ID of role|
|low_estimate | Decimal|
|high_estimate | Decimal|
|forecast | Decimal|
|approved | Boolean|
|start_date | Date|
|end_date | Date|
|bug | Boolean|
|un_billable | Boolean|
|blocked | Boolean|
|sprint | Integer, ID of sprint|
|workflow_column | Integer, ID of workflow column|
|milestone | Integer, ID of milestone|
|assigned_persons | List<Integer>, List ID of assigned persons|
|labels | List<Integer>, List ID of labels|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
{
   "id":1,
   "title":"Design login screen",
   "description":"",
   "role":1,
   "project_id":1,
   "low_estimate":10.0,
   "high_estimate":20.0,
   "forecast":26.0,
   "approved":true,
   "start_date":"2017-01-01",
   "end_date":"2017-01-20",
   "bug":false,
   "un_billable":false,
   "blocked":false,
   "sprint":1,
   "workflow_column":2,
   "milestone":1,
   "assigned_persons":[1,2,3],
   "labels":[1,2,3],
   "created_by":1,
   "updated_by":1,
   "created_at":"2017-01-14T18:46:56Z",
   "updated_at":"2017-01-14T18:47:58Z"
}
```

## Create card

* `POST /cards` - Creates a new card. Returns the same object as getting a single card.

|Request fields | Description/format|
|------------ | -------------|
|title | String|
|description | String|
|role | Integer, ID of role|
|project_id | (Required) Integer, ID of project|
|low_estimate | Decimal|
|high_estimate | Decimal|
|approved | Boolean (Defaults to true)|
|start_date | Date|
|end_date | Date|
|bug | Boolean|
|un_billable | Boolean|
|blocked | Boolean|
|sprint | Integer, ID of sprint|
|workflow_column | Integer, ID of workflow column|
|milestone | Integer, ID of milestone|
|assigned_persons | List<Integer>, List ID of assigned persons|
|labels | List<Integer>, List ID of labels|

### Sample JSON request
POST https://api.forecast.it/api/v1/cards

```javascript
{
   "title":"Implement login page",
   "role":2,
   "project_id":1,
   "low_estimate":20.0,
   "high_estimate":40.0,
   "approved":true,
   "sprint":2
}
```

## Update card

* `PUT /cards/{cardId}` - Updates an card. Returns the same object as getting a single card.

|Request fields | Description/format|
|------------ | -------------|
|title | String|
|description | String|
|role | Integer, ID of role|
|project_id | Integer, ID of project|
|low_estimate | Decimal|
|high_estimate | Decimal|
|approved | Boolean (Defaults to true)|
|start_date | Date|
|end_date | Date|
|bug | Boolean|
|un_billable | Boolean|
|blocked | Boolean|
|sprint | Integer, ID of sprint|
|workflow_column | Integer, ID of workflow column|
|milestone | Integer, ID of milestone|
|assigned_persons | List<Integer>, List ID of assigned persons|
|labels | List<Integer>, List ID of labels|

### Sample JSON request
PUT https://api.forecast.it/api/v1/cards/1

```javascript
{
   "title":"Implement and test login page"
}
```

## Delete card

* `DELETE /cards/{cardId}` - Deletes a card.

### Sample JSON request
DELETE https://api.forecast.it/api/v1/cards/1

## Get deleted cards

* `GET /cards/deleted` - Returns all cards that have been deleted.
* `GET /cards/deleted?updated_after=DDMMYYYYTHHmmss` - Returns all cards that have been deleted. after the specified time. Example value: `16022018T210047`.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer, ID of the card that has been deleted|
|deleted_by | Integer, ID of person|
|deleted_at | Date|

### Sample JSON response
```javascript
[
   {
      "id":1,
      "deleted_by":1,
      "deleted_at":"2017-01-14T18:46:56Z",
   }, ...
]
```