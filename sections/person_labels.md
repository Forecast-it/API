# Person Labels

## Get person labels (skills)

* `GET /person_labels/{personId}` - Returns skills (labels) associated with a person.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|name | String|

### Sample JSON response
```javascript
[
   {
      "id":1,
      "name":"Typescript",
   }, ...
]
```

