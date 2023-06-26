# Programs (Beta)

The following endpoints are available for programs:

- [Get programs](#get-programs)
- [Get program](#get-program)
- [Create program](#create-program)
- [Update program](#update-program)
- [Delete program](#delete-program)
- [Add projects to program](#add-projects-to-grogram)
- [Remove projects from program](#remove-projects-from-program)
- [Get program financials](#get-program-financials)
- [Update program financials](#update-program-financials)
- [Get program stages](#get-program-stages)
- [Update program stage](#update-program-stage)
- [Update program client](#update-program-client)
- [Remove client from program](#remove-client-from-program)
- [Get program team](#get-program-team)
- [Add team member](#add-team-member)
- [Update team member](#update-team-member)
- [Remove team member](#remove-team-member)

## Get programs

- `GET /programs` - Returns all programs.

| Response fields | Description/format                                    |
| --------------- | ----------------------------------------------------- |
| id              | UUID                                                  |
| key             | String                                                |
| name            | String                                                |
| description     | String                                                |
| stage           | String (OPPORTUNITY, PLANNING, RUNNING, HALTED, DONE) |
| color           | String, Hex value                                     |
| start_date      | Date                                                  |
| end_date        | Date                                                  |
| projects        | List<Integer>, List ID of projects                    |
| client          | Integer, ID of client                                 |

### Sample JSON response

```javascript
[
   {
        "id": "4ec178b1-f229-47c2-b5c3-b3aaf6da2a4e",
        "key": "NP",
        "name": "New Program",
        "description": "This is a new Program",
        "stage": {
            "id": "11eda956-33cf-8baa-800b-0242ac120003",
            "name": "OPPORTUNITY"
        },
        "color": "#75C2FF",
        "start_date": "2022-01-31",
        "end_date": "2024-03-02",
        "projects": [1,2,3],
        "client": 1
    }, ...
]
```

## Get program

- `GET /program/{programId}` - Returns a single program.

| Response fields | Description/format                                    |
| --------------- | ----------------------------------------------------- |
| id              | UUID                                                  |
| key             | String                                                |
| name            | String                                                |
| description     | String                                                |
| stage           | String (OPPORTUNITY, PLANNING, RUNNING, HALTED, DONE) |
| color           | String, Hex value                                     |
| start_date      | Date                                                  |
| end_date        | Date                                                  |
| projects        | List<Integer>, List ID of projects                    |
| client          | Integer, ID of client                                 |

### Sample JSON response

```javascript
{
    "id": "4ec178b1-f229-47c2-b5c3-b3aaf6da2a4e",
    "key": "NP",
    "name": "New Program",
    "description": "This is a new Program",
    "stage": {
        "id": "11eda956-33cf-8baa-800b-0242ac120003",
        "name": "OPPORTUNITY"
    },
    "color": "#75C2FF",
    "start_date": "2022-01-31",
    "end_date": "2024-03-02",
    "projects": [1,2,3],
    "client": 1
}
```

## Create program

- `POST /programs` - Creates a new program.

| Request fields | Description/format                    |
| -------------- | ------------------------------------- |
| name           | String                                |
| key            | String, Max 5 alphanumeric characters |
| description    | String                                |
| color          | String, Hex color                     |
| stage_id       | UUID                                  |
| start_date     | Date, ISO 8601                        |
| end_date       | Date, ISO 8601                        |
| owners         | List<Integer>                         |

### Sample JSON request

POST https://api.forecast.it/api/v1/programs

```javascript
{
   "name": "New Program",
   "key": "NP",
   "description": "This is a new Program",
   "color": "#75C2FF",
   "stage_id": "11eda956-33cf-8baa-800b-0242ac120003",
   "start_date": "2022-01-31",
   "end_date": "2024-03-02",
   "owners": [1,2,3]
}
```

## Update program

- `PUT /programs/{programId}` - Updates an existing program.

| Request fields | Description/format                    |
| -------------- | ------------------------------------- |
| name           | String                                |
| key            | String, Max 5 alphanumeric characters |
| description    | String                                |
| color          | String, Hex color                     |
| stage_id       | UUID                                  |
| start_date     | Date, ISO 8601                        |
| end_date       | Date, ISO 8601                        |

### Sample JSON request

PUT https://api.forecast.it/api/v1/programs/4ec178b1-f229-47c2-b5c3-b3aaf6da2a4e

```javascript
{
   "name": "New Program",
   "key": "NP",
   "description": "This is a new Program",
   "color": "#75C2FF",
   "stage_id": "11eda956-33cf-8baa-800b-0242ac120003",
   "start_date": "2022-01-31",
   "end_date": "2024-03-02"
}
```

## Delete program

- `DELETE /programs/{programId}` - Deletes a project.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/programs/4ec178b1-f229-47c2-b5c3-b3aaf6da2a4e

## Add projects to program

- `PUT /programs/{programId}/add_projects` - Adds projects to an existing program.

| Request fields | Description/format             |
| -------------- | ------------------------------ |
| project_ids    | List<Integer>, IDs of projects |

### Sample JSON request

PUT https://api.forecast.it/api/v1/programs/4ec178b1-f229-47c2-b5c3-b3aaf6da2a4e/add_projects

```javascript
{
   "project_ids": [1,2,3]
}
```

## Remove projects from program

- `PUT /programs/{programId}/remove_projects` - Removes projects from an existing program.

| Request fields | Description/format             |
| -------------- | ------------------------------ |
| project_ids    | List<Integer>, IDs of projects |

### Sample JSON request

PUT https://api.forecast.it/api/v1/programs/4ec178b1-f229-47c2-b5c3-b3aaf6da2a4e/remove_projects

```javascript
{
   "project_ids": [1,2,3]
}
```

## Get program financials

- `GET /programs/{programId}/financials` - Returns the financial settings of an existing program.

| Response fields | Description/format                                                                |
| --------------- | --------------------------------------------------------------------------------- |
| budget_type     | String                                                                            |
| budget_value    | Number, Represents either revenue cap or fixed price depending on the budget type |

### Sample JSON response

```javascript
{
    "budget_type": "CAPPED",
    "budget_value": 50000
}
```

## Update program financials

- `PUT /programs/{programId}/financials` - Updates the financial settings of an existing program.

| Request fields | Description/format                                                                |
| -------------- | --------------------------------------------------------------------------------- |
| budget_type    | String, (UNCAPPED, CAPPED, FIXED_PRICE)                                           |
| budget_value   | Number, Represents either revenue cap or fixed price depending on the budget type |

### Sample JSON request

PUT https://api.forecast.it/api/v1/programs/4ec178b1-f229-47c2-b5c3-b3aaf6da2a4e/financials

```javascript
{
    "budget_type": "CAPPED",
    "budget_value": 50000
}
```

## Get program stages

- `GET /programs/stages` - Returns possible stages of programs.

| Response fields | Description/format |
| --------------- | ------------------ |
| id              | UUID               |
| name            | String             |

### Sample JSON response

```javascript
[
    {
        "id": "11eda956-33cf-8baa-800b-0242ac120003",
        "name": "OPPORTUNITY"
    }, ...
]
```

## Update program stage

- `PUT /programs/{programId}/stages/{stageId}` - Updates the stage of an existing program.

### Sample JSON request

PUT https://api.forecast.it/api/v1/programs/4ec178b1-f229-47c2-b5c3-b3aaf6da2a4e/stages/11eda956-33cf-8baa-800b-0242ac120003

## Update program client

- `PUT /programs/{programId}/client/{clientId}` - Updates the client of an existing program.

### Sample JSON request

PUT https://api.forecast.it/api/v1/programs/4ec178b1-f229-47c2-b5c3-b3aaf6da2a4e/client/123

## Remove client from program

- `DELETE /programs/{programId}/client` - Removes client from an existing program.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/programs/4ec178b1-f229-47c2-b5c3-b3aaf6da2a4e/client

## Get program team

- `GET /programs/{programId}/team` - Returns the team of an existing program.

| Response fields | Description/format |
| --------------- | ------------------ |
| id              | UUID               |
| person_id       | Integer            |
| program_role    | String             |

### Sample JSON response

```javascript
[
    {
        "id": "9dfe5e85-2869-40ce-9c1f-99ee0f8b182e",
        "person_id": 123,
        "program_role": "OWNER"
    }, ...
]
```

## Add team member

- `POST /programs/{projectId}/team` - Add new team members to an existing program.

| Request fields | Description/format            |
| -------------- | ----------------------------- |
| person_ids     | List<Integer>, IDs of persons |
| program_role   | String, (USER, OWNER)         |

### Sample JSON request

POST https://api.forecast.it/api/v1/programs/4ec178b1-f229-47c2-b5c3-b3aaf6da2a4e/team

```javascript
{
    "person_ids": [1,2,3],
    "program_role": "USER"
}
```

## Update team member

- `PUT /programs/team/{memberId}` - Updates an existing project team member.

| Request fields | Description/format    |
| -------------- | --------------------- |
| program_role   | String, (USER, OWNER) |

### Sample JSON request

PUT https://api.forecast.it/api/v1/programs/team/9dfe5e85-2869-40ce-9c1f-99ee0f8b182e

```javascript
{
    "program_role": "OWNER"
}
```

## Remove team member

- `DELETE /programs/team/{memberId}` - Removes team member from an existing program.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/programs/team/9dfe5e85-2869-40ce-9c1f-99ee0f8b182e
