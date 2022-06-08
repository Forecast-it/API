# Priority Levels

## Get priority levels

- `GET /priority_levels` - Returns all priority levels

| Response fields              | Description/format                                               |
| ---------------------------- | ---------------------------------------------------------------- |
| id                           | Integer                                                          |
| name                         | String                                                           |
| weight                       | Double (Between 0.0 and 1.0)                                     |
| created_at                   | Date                                                             |
| created_by                   | Integer, ID of person                                            |
| updated_at                   | Date                                                             |
| updated_by                   | Integer, ID of person                                            |
| use_count                    | Integer, number of projects with this priority level             |
| disabled                     | Boolean                                                          |

### Sample JSON response

GET https://api.forecast.it/api/v1/priority_levels

```javascript
[
   {
    "id": 24,
    "name": "HIGH PRIORITY",
    "weight": 1,
    "created_at": "2022-06-06T14:44:32Z",
    "created_by": 4,
    "updated_at": "2022-06-06T16:06:07Z",
    "updated_by": 4,
    "use_count": 0,
    "disabled": false
  },
  {
    "id": 27,
    "name": "MEDIUM PRIORITY",
    "weight": 0.5,
    "created_at": "2022-06-06T15:47:06Z",
    "created_by": 4,
    "updated_at": "2022-06-06T16:06:07Z",
    "updated_by": 4,
    "use_count": 0,
    "disabled": false
  },
  {
    "id": 26,
    "name": "LOW PRIORITY",
    "weight": 0,
    "created_at": "2022-06-06T14:44:32Z",
    "created_by": 4,
    "updated_at": "2022-06-06T16:06:07Z",
    "updated_by": 4,
    "use_count": 0,
    "disabled": false
  }, ...
]
```

## Update all priority levels

- `PUT /priority_levels` - Updates ordering, names and disabled status of all existing priority levels. The request body should contain an array of objects with the below fields. Only, and all, existing priority levels should be included (as indicated by their ids) otherwise an error will result.

| Request fields               | Description/format                                               |
| ---------------------------- | ---------------------------------------------------------------- |
| id                           | Integer                                                          |
| name                         | String                                                           |
| disabled                     | Boolean                                                          |

### Sample JSON request

The below sample request contains all existing priority levels from the GET example, with:
- HIGH PRIORITY set to disabled;
- LOW PRIORITY moved above MEDIUM PRIORITY;
- MEDIUM PRIORITY renamed

PUT https://api.forecast.it/api/v1/priority_levels

```javascript
[
   {
    "id": 24,
    "name": "HIGH PRIORITY",
    "disabled": true
  },
  {
    "id": 26,
    "name": "LOW PRIORITY",
    "disabled": false
  },
  {
    "id": 27,
    "name": "RENAMED FROM MEDIUM PRIORITY",
    "disabled": false
  }, ...
]
```

## Add priority levels

- `POST /priority_levels` - Adds one or more priority levels. The request body should contain an array of objects with the following single field. The new priority levels will be appended to the end of the existing list (i.e. lowest priorities); these can then be reordered using the PUT request above.

| Request fields               | Description/format                                               |
| ---------------------------- | ---------------------------------------------------------------- |
| name                         | String                                                           |

## Sample JSON request

POST https://api.forecast.it/api/v1/priority_levels

```javascript
[
    { "name": "NEW PRIORITY LEVEL 1" },
    { "name": "NEW PRIORITY LEVEL 2" },
    ...
]
```

## Update a single priority level

- `PATCH /priority_levels/{priorityLevelId}` - Update name or disabled status of a specified priority level. One or both of the following fields must be provided.

| Request fields               | Description/format                                               |
| ---------------------------- | ---------------------------------------------------------------- |
| name                         | String                                                           |
| disabled                     | Boolean                                                          |

## Sample JSON request

PATCH https://api.forecast.it/api/v1/priority_levels/17

```javascript
{
    "name": "UPDATED NAME",
    "disabled": false
}
```

## Delete a priority level with no replacement

- `DELETE /priority_levels/{priorityLevelId}` - Delete the specified priority level. Any projects that are set with this priority are subsequently set to "No priority".

### Sample JSON request

DELETE https://api.forecast.it/api/v1/priority_levels/17

## Delete a priority level with replacement

- `DELETE /priority_levels/{priorityLevelId}/{replacementId}` - Delete the specified priority level, and update projects that are set with this priority level to the specified replacement priority level.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/priority_levels/17/19
