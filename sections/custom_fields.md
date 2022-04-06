# Custom fields (Beta)

Custom fields are available for PROJECT, PHASE, TIME_REG and TASK. For setting custom field value for an entity the custom field for that entity type have to be defined in the admin UI.

## Set custom fields (Create or Update APIs)

Setting value for a custom field can be done in creation or update of an entity, it is just an extra field for that entity. The key for the entity type must be pre-defined in the admin UI.

### Sample JSON request
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

## Get custom fields 

For getting custom fields along with the entity, the parameter ?includeCustomFields=true has to be added to the end of the get APIs for that entity type.

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
