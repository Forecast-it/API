# Profiles

## Get company profiles

- `GET v1/profiles` - Returns all company profiles.

| Response fields | Description/format |
|---|---|
| id | Integer
| name | String
| can_be_edited | Boolean
| person_count | Integer, number of people that that have this profile
| profile_permission | List<String>

### Sample JSON response

```javascript
[
   {
      "id":1,
      "name":"Collaborator",
      "can_be_edited":true,
      "person_count":2,
      "profile_permission":[],
   }, ...
]
```

## Get person profiles

- `GET v1/profiles/person/{person_id}` - Returns all person profiles.

| Response fields | Description/format |
|---|---|
| id | Integer
| name | String
| can_be_edited | Boolean
| person_count | Integer, number of people that that have this profile
| profile_permission | List<String>

### Sample JSON response

```javascript
[
   {
      "id":1,
      "name":"Collaborator",
      "can_be_edited":true,
      "person_count":2,
      "profile_permission":[],
   }, ...
]
```
