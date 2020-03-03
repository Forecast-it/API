# Repeating tasks

(Formerly known as Repeating Cards. See old docs here: [Repeating cards](sections/repeating_cards.md#repeating-cards))

## Get a repeating task

-   `GET /repeating_tasks/{repeatingTaskId}` - Returns a repeating task by its id.

| Response fields | Description/format    |
| --------------- | --------------------- |
| id              | Integer               |
| monday          | Boolean               |
| tuesday         | Boolean               |
| wednsday        | Boolean               |
| thursday        | Boolean               |
| friday          | Boolean               |
| saturday        | Boolean               |
| sunday          | Boolean               |
| monthly_day     | Integer               |
| repeat_type     | String                |
| created_by      | Integer, ID of person |
| updated_by      | Integer, ID of person |
| created_at      | Date                  |
| updated_at      | Date                  |

### Sample JSON response

```javascript
{
    "id": 15,
    "monday": true,
    "tuesday": false,
    "wednesday": false,
    "thursday": true,
    "friday": false,
    "saturday": false,
    "sunday": false,
    "monthly_day": 1,
    "repeat_type": "WEEKLY",
    "created_by": null,
    "updated_by": null
}
```

## Get task's repeating task

-   `GET /tasks/{taskId}/repeating_tasks` - Returns repeating task for a task.

| Response fields | Description/format    |
| --------------- | --------------------- |
| id              | Integer               |
| monday          | Boolean               |
| tuesday         | Boolean               |
| wednsday        | Boolean               |
| thursday        | Boolean               |
| friday          | Boolean               |
| saturday        | Boolean               |
| sunday          | Boolean               |
| monthly_day     | Integer               |
| repeat_type     | String                |
| created_by      | Integer, ID of person |
| updated_by      | Integer, ID of person |
| created_at      | Date                  |
| updated_at      | Date                  |

### Sample JSON response

```javascript
{
    "id": 15,
    "monday": true,
    "tuesday": false,
    "wednesday": false,
    "thursday": true,
    "friday": false,
    "saturday": false,
    "sunday": false,
    "monthly_day": 1,
    "repeat_type": "WEEKLY",
    "created_by": null,
    "updated_by": null
}
```

## Get project repeating tasks

-   `GET /projects/{projectId}/repeating_tasks` - Returns repeating tasks for a project.

| Response fields | Description/format    |
| --------------- | --------------------- |
| id              | Integer               |
| monday          | Boolean               |
| tuesday         | Boolean               |
| wednsday        | Boolean               |
| thursday        | Boolean               |
| friday          | Boolean               |
| saturday        | Boolean               |
| sunday          | Boolean               |
| monthly_day     | Integer               |
| repeat_type     | String                |
| created_by      | Integer, ID of person |
| updated_by      | Integer, ID of person |
| created_at      | Date                  |
| updated_at      | Date                  |

### Sample JSON response

```javascript
{
    "id": 15,
    "monday": true,
    "tuesday": false,
    "wednesday": false,
    "thursday": true,
    "friday": false,
    "saturday": false,
    "sunday": false,
    "monthly_day": 1,
    "repeat_type": "WEEKLY",
    "created_by": null,
    "updated_by": null
}
```

## Create a repeating task

-   `POST /repeating_tasks` - Creates a repeating task. Returns the same object as getting a single repeating task.

| Request fields | Description/format             |
| -------------- | ------------------------------ |
| task_id        | (Required) Integer, ID of task |
| repeat_type    | String, WEEKLY or MONTHLY      |
| monday         | Boolean                        |
| tuesday        | Boolean                        |
| wednesday      | Boolean                        |
| thursday       | Boolean                        |
| friday         | Boolean                        |
| saturday       | Boolean                        |
| sunday         | Boolean                        |
| monthly_day    | Integer (day of month)         |

### Sample JSON request

POST https://api.forecast.it/api/v1/repeating_tasks

```javascript
{
    "repeat_type": "WEEKLY",
    "thursday": true,
    "task_id": 76
}
```

## Update repeating task

-   `PUT /repeating_tasks/{repeatingTaskId}` - Updates a repeating task. Returns the same object as getting a single repeating task.

| Request fields | Description/format        |
| -------------- | ------------------------- |
| repeat_type    | String, WEEKLY or MONTHLY |
| monday         | Boolean                   |
| tuesday        | Boolean                   |
| wednesday      | Boolean                   |
| thursday       | Boolean                   |
| friday         | Boolean                   |
| saturday       | Boolean                   |
| sunday         | Boolean                   |
| monthly_day    | Integer (day of month)    |

### Sample JSON request

PUT https://api.forecast.it/api/v1/repeating_tasks/1

```javascript
{
    "repeat_type": "WEEKLY",
    "thursday": false,
    "friday": true
}
```

## Delete repeating task

-   `DELETE /repeating_tasks/{repeatingTaskId}` - Deletes a repeating task by its id.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/repeating_tasks/1
