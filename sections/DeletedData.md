# Deleted Time registrations

## Get all deleted time registrations in your company

- `GET v4/time_regisrations/deleted` - Returns all deleted time registrations in a paginated response. 

| Response fields   | Description/format                                    |
| ----------------  | -------------------------------                       |
| minutesRegistered | Integer, time registration in minutes                 |
| person            | Object                                                |
| id                | Integer, id of person                                 |
| name              | String, name of person                                |
| registeredOn      | Object                                                |
| type              | String, type of time registration                     |
| id                | Integer, id of task, project or idle time             |
| name              | String, name of task, project or idle time            |
| project           | Object ***Only on task type***                        |
| id                | Integer, id of task project ***Only on task type***   |
| name              | String, name of task project ***Only on task type***  |
| datetime          | Datetime, date and time of registration               |

### Sample JSON response

```javascript
[
   {
     "minutesRegistered": 1440,
      "person": {
        "name": "Emil Desler",
        "email": "emil.desler+local@forecast.app"
      },
      "registeredOn": {
        "type": "TASK",
        "id": 235,
        "name": "fgad",
        "project": {
          "id": 55,
          "name": "Investigation: Using points for day registrations"
        }
      },
      "datetime": "2021-11-02T13:42:40+01:00"
    }, ...
]
```
