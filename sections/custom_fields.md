# Custom fields (Beta)

Custom fields are enabled for PROJECT, PHASE, TIME_REG and TASK, for setting custom field value for an entity the custom field for that entity type have to be defined in the admin UI.

## Set custom fields (Create or Update APIs)

Setting value for a custom field can be done in creation or update of an entity, it is just an extra field for that entity.

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

For getting custom fields along with the entity this `?includeCustomFields=true` parameter have to be added to the end of get APIs for specified entity types.

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
