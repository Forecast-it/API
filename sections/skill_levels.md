# Skill Levels

## Get all skill levels

* `GET /skill_levels` - Returns all skill levels (configured in the Admin UI).

| Response fields | Description/format    |
|-----------------|-----------------------|
| id              | Integer               |
| level           | Integer               |
| description     | String                |
| created_by      | Integer, ID of person |
| updated_by      | Integer, ID of person |
| created_at      | Date                  |
| updated_at      | Date                  |

### Sample JSON response
```json
[
  {
    "id": 25,
    "level": 1,
    "description": "Beginner",
    "created_by": 1,
    "updated_by": 1,
    "created_at": "2022-05-23T15:35:48+02:00",
    "updated_at": "2023-01-04T15:20:58+01:00"
  }, ...
]
```
