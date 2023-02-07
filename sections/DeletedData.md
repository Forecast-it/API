# Deleted data
In this section you can find all endpoints for deleted data such as deleted time registrations and deleted tasks. 

## Deleted Time registrations

### Get all deleted time registrations in your company

- `GET v4/time_registrations/deleted` - Returns all deleted time registrations in a paginated response. 

| Response fields   | Description/format                                    |
| ----------------  | -------------------------------                       |
| minutesRegistered | Integer, time registration in minutes                 |
| person            | Object ({id: Integer, name: String})                                                |                        |
| registeredOn      | Object ({type: String, id: Integer, name: String, project: Object ({id: Integer, name: String}) ***Only on task type*** }) |
| datetime          | Datetime, date and time of registration               |

#### Sample JSON response

```javascript
[
   {
     "minutesRegistered": 1440,
      "person": {
        "name": "John Doe",
        "email": "johndoe@doe.inc"
      },
      "registeredOn": {
        "type": "TASK",
        "id": 235,
        "name": "Build hovercraft",
        "project": {
          "id": 55,
          "name": "The greatest project"
        }
      },
      "datetime": "2021-11-02T13:42:40+01:00"
    }, ...
]
```

## Deleted Tasks

### Get all deleted tasks in your company

- `GET v4/tasks/deleted` - Returns all deleted tasks in a paginated response. 

| Response fields   | Description/format                                    |
| ----------------  | -------------------------------                       |
| task             | Object ({id: Integer, name: String, deleted_at: Datetime})                |
| project      | Object ({id: Integer, name: String})                                               |           |
| phase              | Object ({id: Integer, name: String})             |
| sprint              | Object ({id: Integer, name: String})   |
| assignedPersons              | Object[] ({id: Integer, name: String})  |
| labels              | Object[] ({id: Integer, name: String})  |
| comments              | String[]   |

#### Sample JSON response

```javascript
[
   {
            "task": {
                "id": 206,
                "name": "taskName",
                "deleted_at": "2021-10-26T10:57:20+02:00"
            },
            "project": {
                "id": 49,
                "name": "projectName"
            },
            "phase": {},
            "sprint": {
                "id": 19,
                "name": "sprintName"
            },
            "assignedPersons": [
                {
                    "id": 2,
                    "name": "assigneeName"
                }
            ],
            "labels": [
            {
                    "id": 214,
                    "name": "labelName"
                }],
            "comments": [
                "Comment1",
                "Comment2",
                "Comment3",
                "Comment4"
            ]
        }, ...
]
```
