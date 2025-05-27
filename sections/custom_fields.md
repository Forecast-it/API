# Custom fields (Beta)

Custom fields are available for PROJECT, PHASE, TIME_REG and TASK. For setting custom field value for an entity the custom field for that entity type have to be defined in the admin UI.

## Set custom fields (Update APIs)

Setting the value for a custom field can be done using the same API endpoints as used to update the entity. The endpoint just needs to be suffixed with `/custom_fields`, and the body should be the wanted custom-field keys and values. The keys for the entity type must be pre-defined in the admin UI.

API endpoints:

- Project: `PUT /projects/{projectId}/custom_fields`
- Phase: `PUT /projects/{projectId}/phases/{phaseId}/custom_fields`
- Time registration: `PUT /time_registrations/{time_registrationId}/custom_fields`
- Task: `PUT /v3/tasks/{taskId}/custom_fields`

### Sample JSON request

```json
{
  "key1": "value1",
  "key2": "value2",
  "key3": "value3"
}
```

## Get custom fields

For getting custom fields along with the entity, the parameter `?includeCustomFields=true` has to be added to the end of the get APIs for that entity type.

### Sample JSON response

```json
{
    ...,

    "custom_fields": {
		"key1": "value1",
		"key2": "value2",
		"key3": "value3"
	}
}
```

## Get custom field options

For getting custom field options for a dropdown type custom field.

Entity type must be one of: "PROJECT", "PHASE", "TASK", or "TIME_REG".

Key refers to the key of the custom field.


* `GET /custom_fields/{entityType}/{key}/options` - Returns all connected projects.

### Sample JSON response

```json
[
   {
    "id": 1,
    "name": "Option 1"
   },
   {
    "id": 2,
    "name": "Option 2"
   },
   ...
]
```