# Milestones

## Get milestones

-  `GET /projects/{projectId}/milestones` - Returns all milestones of the project.

| Response fields         | Description/format    |
| ----------------------- | --------------------- |
| id                      | Integer               |
| name                    | String                |
| start_date              | Date                  |
| end_date                | Date                  |
| baseline_target_minutes | Integer               |
| baseline_target_price   | Double                |
| created_by              | Integer, ID of person |
| updated_by              | Integer, ID of person |
| created_at              | Date                  |
| updated_at              | Date                  |

### Sample JSON response

```javascript
[
   {
      "id":1,
      "name":"Milestone 1",
      "start_date":"2017-01-14",
      "end_date":"2017-06-14",
      "baseline_target_minutes": 2400,
      "baseline_target_price": null,
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:56Z",
      "updated_at":"2017-01-14T18:47:58Z"
   }, ...
]
```

## Get milestone

-  `GET /projects/{projectId}/milestones/{milestoneId}` - Returns a specific milestone.

| Response fields         | Description/format    |
| ----------------------- | --------------------- |
| id                      | Integer               |
| name                    | String                |
| start_date              | Date                  |
| end_date                | Date                  |
| baseline_target_minutes | Integer               |
| baseline_target_price   | Double                |
| created_by              | Integer, ID of person |
| updated_by              | Integer, ID of person |
| created_at              | Date                  |
| updated_at              | Date                  |

### Sample JSON response

```javascript
{
     "id":1,
     "name":"Milestone 1",
     "start_date":"2017-01-14",
     "end_date":"2017-06-14",
     "baseline_target_minutes": null,
     "baseline_target_price": 1000.0,
     "created_by":1,
     "updated_by":1,
     "created_at":"2017-01-14T18:46:56Z",
     "updated_at":"2017-01-14T18:47:58Z"
}
```

## Create milestone

-  `POST /projects/{projectId}/milestones` - Creates a new milestone. Returns the same object as getting a single milestone.

| Request fields             | Description/format                                        |
| -------------------------- | --------------------------------------------------------- |
| name                       | (Required) String                                         |
| start_date                 | Date                                                      |
| end_date                   | Date                                                      |
| baseline_target_minutes    | Integer (mutually exclusive with baseline_target_price)   |
| baseline_target_price      | Double  (mutually exclusive with baseline_target_minutes) |  

### Sample JSON request

POST https://api.forecast.it/api/v1/projects/1/milestones

```javascript
{
   "name":"Milestone 2",
   "start_date":"2017-06-14",
   "end_date":"2017-09-14",
   "baseline_target_minutes": null,
   "baseline_target_price": 1000.0,
}
```

## Update milestone

-  `PUT /projects/{projectId}/milestones/{milestoneId}` - Updates a milestone. Returns the same object as getting a single milestone.

| Request fields             | Description/format                                        |
| -------------------------- | --------------------------------------------------------- |
| name                       | String                                                    |
| start_date                 | Date                                                      |
| end_date                   | Date                                                      |
| baseline_target_minutes    | Integer (mutually exclusive with baseline_target_price)   |
| baseline_target_price      | Double  (mutually exclusive with baseline_target_minutes) | 

### Sample JSON request

PUT https://api.forecast.it/api/v1/projects/1/milestones/1

```javascript
{
   "name":"Milestone 3",
}
```

## Delete milestone

-  `DELETE /projects/{projectId}/milestones/{milestoneId}` - Deletes a milestone. Does not delete tasks in the milestone.

### Sample JSON request

DELETE https://api.forecast.it/api/v1/projects/1/milestones/1
