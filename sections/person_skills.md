# Person Skills

## Get person skills

* `GET /person_skills` - Returns skills associated with all persons.

| Response fields | Description/format |
|-----------------|--------------------|
| personId        | Integer            |
| skillId         | Integer            |
| skillLevelId    | Integer            |

### Sample JSON response
```json
[
	{
		"personId": 1,
		"skillId": 3,
		"skillLevelId": 27
	}, ...
]
```

## Get person skills for person

* `GET /person_skills/{personId}` - Returns skills associated with a person.

| Response fields | Description/format |
|-----------------|--------------------|
| personId        | Integer            |
| skillId         | Integer            |
| skillLevelId    | Integer            |

### Sample JSON response
```json
[
	{
		"personId": 1,
		"skillId": 3,
		"skillLevelId": 27
	}, ...
]
```


## Delete person skill

* `DELETE /person_skills/{personId}/{skillId}` - Delete skill associated with a person.


