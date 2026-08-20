# Tickets

Tickets are part of the Forecast ticketing module, which must be enabled for your company. A ticket is addressed by its ticket number, which is the number shown for the ticket in the app.

## Get ticket

* `GET /tickets/{ticketNumber}` - Returns a specific ticket.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer, the ticket number|
|slug | String, the ticket reference as shown in the app|
|url | String, link to the ticket in the app|
|subject | String|
|description | String|
|status | String (open, in_progress, waiting_on_customer, resolved, closed)|
|priority | String (low, normal, high, urgent)|
|channel | String (manual, email, phone, chat, internal, api, customer_portal, direct)|
|created_at | Date|
|requester | Object, the name and email of the requester|
|assignee_id | Integer, ID of person|
|labels | Array, IDs of labels|

### Sample JSON response
```javascript
{
   "id":1042,
   "slug":"FOR-1042",
   "url":"https://app.forecast.it/tickets/FOR-1042",
   "subject":"Cannot export my timesheet",
   "description":"The CSV export button does nothing.",
   "status":"open",
   "priority":"high",
   "channel":"email",
   "created_at":"2026-07-24T09:12:03.000Z",
   "requester":{
      "name":"Jane Doe",
      "email":"jane@example.com"
   },
   "assignee_id":55,
   "labels":[1, 4]
}
```

## Create ticket

* `POST /tickets` - Creates a new ticket. Returns the same object as getting a single ticket.

|Request fields | Description/format|
|------------ | -------------|
|subject | (Required) String, Max 255 characters|
|requester_email | (Required) String, email of the requester, Max 254 characters|
|description | String, Max 10000 characters|
|requester_name | String, Max 255 characters (Defaults to requester_email)|
|priority | String (low, normal, high, urgent) (Default is normal)|
|assignee_id | Integer, ID of person\*|

\* The person must have an email address

New tickets are created with the status `open` and the channel `api`.

### Sample JSON request
POST https://api.forecast.it/api/v1/tickets

```javascript
{
   "subject":"Cannot export my timesheet",
   "description":"The CSV export button does nothing.",
   "requester_email":"jane@example.com",
   "requester_name":"Jane Doe",
   "priority":"high",
   "assignee_id":55
}
```

## Update ticket\*

\* At least one field must be supplied

* `PUT /tickets/{ticketNumber}` - Updates a ticket. Returns the same object as getting a single ticket.

|Request fields | Description/format|
|------------ | -------------|
|subject | String, Max 255 characters|
|description | String, Max 10000 characters or null to remove the description|
|status | String (open, in_progress, waiting_on_customer, resolved, closed)|
|priority | String (low, normal, high, urgent)|
|assignee_id | Integer, ID of person or null to unassign|

### Sample JSON request
PUT https://api.forecast.it/api/v1/tickets/1042

```javascript
{
   "status":"resolved",
   "priority":"normal",
   "assignee_id":null
}
```

## Delete ticket

* `DELETE /tickets/{ticketNumber}` - Deletes a ticket.

### Sample JSON request
DELETE https://api.forecast.it/api/v1/tickets/1042
