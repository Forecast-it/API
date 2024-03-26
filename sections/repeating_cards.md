# Repeating cards

> [!CAUTION]
> **DEPRECATED**
> <br/>
> NB! These endpoints have been deprecated. Use [Repeating Tasks](repeating_tasks.md#repeating-tasks)) instead.

## Get a repeating card

-   `GET /repeating_cards/{repeatingCardId}` - Returns a repeating card by its id.

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

## Get card repeating card

-   `GET /cards/{cardId}/repeating_cards` - Returns repeating card for a card.

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

## Get project repeating cards

-   `GET /projects/{projectId}/repeating_cards` - Returns repeating card for a card.

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

## Create a repeating card

-   `POST /repeating_cards` - Creates a repeating card. Returns the same object as getting a single repeating card.

| Request fields | Description/format             |
| -------------- | ------------------------------ |
| task_id        | (Required) Integer, ID of card |
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

POST https://api.forecast.it/api/v1/repeating_cards

```javascript
{
    "repeat_type": "WEEKLY",
    "thursday": true,
    "task_id": 76
}
```

## Update repeating card

-   `PUT /repeating_cards/{repeatingCardId}` - Updates a repeating card. Returns the same object as getting a single repeating card.

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

PUT https://api.forecast.it/api/v1/repeating_cards/1

```javascript
{
    "repeat_type": "WEEKLY",
    "thursday": false,
    "friday": true
}
```

## Delete repeating card

-   `DELETE /repeating_cards/{repeatingCardId}` - Deletes a repeating card by its id.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/repeating_cards/1
