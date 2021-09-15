# Rate card versions

## Get all versions of a rate card

- `GET /rate_cards/{rate_cardId}/versions` - Returns all versions of a rate card.

| Response fields | Description/format      |
| --------------- | ----------------------- |
| start_date      | Date, Start date (`null` if first version) |
| end_date        | Date, End date (`null` if no later replacement version exists)   |
| default_rate    | Decimal, default rate |
| rates           | Array, of [Rate Card Rates](rate_card_rates.md) |

### Sample JSON response

```json
[
    {
        "start_date": null,
        "end_date": "2021-09-08",
        "default_rate": 100,
        "rates": [
            {
                "role": 13,
                "rate": 100,
                "created_by": 1,
                "updated_by": 1,
                "created_at": "2021-09-13T10:43:13Z",
                "updated_at": "2021-09-15T06:48:32Z"
            }
        ]
    },
    {
        "start_date": "2021-09-09",
        "end_date": "2021-09-14",
        "default_rate": 55,
        "rates": [...]
    },
    {
        "start_date": "2021-09-15",
        "end_date": null,
        "default_rate": 105,
        "rates": [...]
    },
    ...
]
```

## Get version of a rate card for a specific date

- `GET /rate_cards/{rate_cardId}/versions/{date}` - Returns the version of a rate card that is active for a specific date.
- `date` should be in ISO 8601 date format, e.g. `2021-09-15`.

| Response fields | Description/format      |
| --------------- | ----------------------- |
| start_date      | Date, Start date (null if first version) |
| end_date        | Date, End date (null if no later replacement version exists)   |
| default_rate    | Decimal, default rate |
| rates           | Array, of [Rate Card Rates](rate_card_rates.md) |

### Sample JSON response

```json
{
    "start_date": "2021-09-15", 
    "end_date": null,
    "default_rate": 100,
    "rates": [
        {
            "role": 13,
            "rate": 100,
            "created_by": 1,
            "updated_by": 1,
            "created_at": "2021-09-13T10:43:13Z",
            "updated_at": "2021-09-15T06:48:32Z"
        },
       ...
    ]
}
```