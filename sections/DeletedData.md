# Deleted data
In this section you can find all endpoints for deleted data such as deleted time registrations and deleted tasks. 

## Deleted Time registrations

### Get all deleted time registrations in your company

- `GET v4/time_registrations/deleted` - Returns all deleted time registrations in a paginated response. 

| Response fields                                 | Description/format                                                                                                          |
| ----------------                                | -------------------------------                                                                                             |
| id                                              | Integer, id of deleted time registration                                                                                    |
| minutesRegistered                               | Integer, time registration in minutes                                                                                       |
| person                                          | Object ({id: Integer, name: String, email: String})                                                                         |
| registeredOn                                    | Object ({type: String, id: Integer, name: String, project: Object ({id: Integer, name: String}) ***Only on task type*** })  |
| datetime                                        | Datetime, date and time of registration                                                                                     |   
| deletedBy                                       | Object ({id: String, name: String, email: String})                                                                          |
| deletedAt                                       | Datetime, date and time of deletion                                                                                         |

#### Sample JSON response

```javascript
[
   {
     "id": 1,
     "minutesRegistered": 1440,
      "person": {
        "id": 23,
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
      "datetime": "2021-11-02T13:42:40+01:00",
      "deletedBy": {
        "id": 24,
        "name": "Jane Doe",
        "email": "janedoe@doe.inc"
       },
       "deletedAt": "2022-2-06T10:14:20+01:00"
    }, ...
]
```

## Deleted Tasks

### Get all deleted tasks in your company

- `GET v4/tasks/deleted` - Returns all deleted tasks in a paginated response. 

| Response fields    | Description/format                                                              |
|--------------------|---------------------------------------------------------------------------------|
| task               | Object ({id: Integer, name: String, deleted_at: Datetime, deleted_by: Integer}) |
| project            | Object ({id: Integer, name: String})                                            |           
| phase              | Object ({id: Integer, name: String})                                            |
| sprint             | Object ({id: Integer, name: String})                                            |
| assignedPersons    | Object[] ({id: Integer, name: String})                                          |
| labels             | Object[] ({id: Integer, name: String})                                          |
| comments           | String[]                                                                        |

#### Sample JSON response

```javascript
[
   {
            "task": {
                "id": 206,
                "name": "taskName",
                "deleted_at": "2021-10-26T10:57:20+02:00",
                "deleted_by": 2
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
