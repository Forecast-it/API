# Webhook subscriptions

## Webhooks

Webhooks allow you to subscribe to task and time registration events from Forecast and get notified at a url of your choice.

When an event that you have subscribed to occours in Forecast, a webhook with the following format will be sent to the url you specified in your subscription:

| Webhook fields   | Description/format                                                                                                                                  |
| ---------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| timestamp        | String. A UTC timestamp of when the event happened                                                                                                  |
| event            | String. A string consisting of the type of object and the type of event.                                                                            |
| object           | JSON object                                                                                                                                         |
| &nbsp;&nbsp;↳ id | Integer. The id of the object in question.                                                                                                          |
| person           | JSON object                                                                                                                                         |
| &nbsp;&nbsp;↳ id | Integer. The id of the person who triggered the event in Forecast                                                                                   |
| fields_changed   | Array of strings. <b>Only present on UPDATE hooks.</b><br>The array contains strings denoting which fields on the object were updated in this event |

### Sample webhook

```javascript
{
    "timestamp": "2021-09-23T07:30:00Z",
    "event": "task_updated",
    "object": {
        "id": 655383
    },
    "person": {
        "id": 50363
    },
    "fields_changed": [
        "description"
    ]
}
```

## Webhook retries

When Forecast sends a webhook to a specific subscription url and the url responds with a HTML response status code different from 2xx, then Forecast will retry the webhook up to 5 times adding an incrementally increasing delay:

| # of retries | Delay  |
| ------------ | ------ |
| 1            | 1 min  |
| 2            | 2 min  |
| 3            | 3 min  |
| 4            | 5 min  |
| 5            | 10 min |

## Endpoints

The following endpoints can be used to subscribe to Forecast webhooks.

## Get all webhook subscriptions

- `GET /v1/webhook_subscriptions` - Returns all webhook subscriptions.

| Response fields | Description/format              |
| --------------- | ------------------------------- |
| id              | Integer                         |
| name            | String                          |
| type            | String (TASK, TIME_REG, PROJECT, PHASE)         |
| event           | String (CREATE, UPDATE, DELETE) |
| url             | String                          |
| active          | Boolean                         |

### Sample JSON response

```javascript
[
    {
        "id": 1,
        "name": "Task created webhook subscription",
        "type": "TASK",
        "event": "CREATE",
        "url": "https://domain.com/webhook/task/created",
        "active": true
    }, ...
]
```

## Get single webhook subscription

- `GET /v1/webhook_subscriptions/{webhook_id}` - Returns a specific webhook subscription.

| Response fields | Description/format              |
| --------------- | ------------------------------- |
| id              | Integer                         |
| name            | String                          |
| type            | String (TASK, TIME_REG, PROJECT, PHASE)         |
| event           | String (CREATE, UPDATE, DELETE) |
| url             | String                          |
| active          | Boolean                         |

### Sample JSON request

GET https://api.forecast.it/api/v1/webhook_subscriptions/1

### Sample JSON response

```javascript
{
    "id": 1,
    "name": "Task created webhook subscription",
    "type": "TASK",
    "event": "CREATE",
    "url": "https://domain.com/webhook/task/created",
    "active": true
}
```

## Create a webhook subscription

- `POST /v1/webhook_subscriptions`- Creates a new webhook subscription.

| Request fields | Description/format                         |
| -------------- | ------------------------------------------ |
| name           | (Required) String                          |
| type           | (Required) String (TASK, TIME_REG, PROJECT, PHASE)         |
| event          | (Required) String (CREATE, UPDATE, DELETE) |
| url            | (Required) String                          |
| active         | Boolean (Defaults to true)                 |

### Sample JSON request

POST https://api.forecast.it/api/v1/webhook_subscriptions

```javascript
{
    "name": "Task created webhook subscription",
    "type": "TASK",
    "event": "CREATE",
    "url": "https://domain.com/webhook/task/created"
}
```

### Sample JSON response

```javascript
{
    "id": 1,
    "name": "Task created webhook subscription",
    "type": "TASK",
    "event": "CREATE",
    "url": "https://domain.com/webhook/task/created",
    "active": true
}
```

## Update a webhook subscription

- `PUT /v1/webhook_subscriptions/{webhook_id}`- Updates a specific webhook subscription.

| Request fields | Description/format              |
| -------------- | ------------------------------- |
| name           | String                          |
| type           | String (TASK, TIME_REG, PROJECT, PHASE)         |
| event          | String (CREATE, UPDATE, DELETE) |
| url            | String                          |
| active         | Boolean                         |

### Sample JSON request

PUT https://api.forecast.it/api/v1/webhook_subscriptions/1

```javascript
{
    "name": "Webhook subscription with updated name",
}
```

### Sample JSON response

```javascript
{
    "id": 1,
    "name": "Webhook subscription with updated name",
    "type": "TASK",
    "event": "CREATE",
    "url": "https://domain.com/webhook/task/created",
    "active": true
}
```

## Dalete a webhook subscription

- `DELETE /v1/webhook_subscriptions/{webhook_id}`- Deletes a specific webhook subscription.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/webhook_subscriptions/1
