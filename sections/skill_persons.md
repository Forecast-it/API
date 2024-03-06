# Skill Persons

## Get person skills

* `GET /skill_persons` - Returns skills associated with all persons.

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

* `GET /skill_persons/{personId}` - Returns skills associated with a person.

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

## Get person skill by skill id

* `GET /skill_persons/{personId}/{skillId}` - Returns specific person skill

| Response fields | Description/format |
|-----------------|--------------------|
| personId        | Integer            |
| skillId         | Integer            |
| skillLevelId    | Integer            |

### Sample JSON response
```json
{
    "personId": 1,
    "skillId": 3,
    "skillLevelId": 27
}
```

## Create person skill

* `POST /skill_persons` - Returns created person skill

| Request fields | Description/format |
|----------------|--------------------|
| personId       | (Required) Integer |
| skillId        | (Required) Integer |
| skillLevelId   | Integer            |

### Sample JSON response
```json
{
  "personId": 1,
  "skillId": 3,
  "skillLevelId": 27
}
```


## Delete person skill

* `DELETE /skill_persons/{personId}/{skillId}` - Delete skill associated with a person.
