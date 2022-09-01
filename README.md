# What is the Forecast API?

The [Forecast](https://www.forecast.it) API is a complete programmable interface to all Forecast functionality.

This is a [REST](http://en.wikipedia.org/wiki/Representational_state_transfer)-style [API](http://en.wikipedia.org/wiki/Application_programming_interface) that uses [JSON](http://json.org/) for serialization and [HTTP](http://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol).

# What can you do with it?

A ton of stuff! We've exposed all the needed services for you to use in your applications.

# How do I get started?

You'll need a [Forecast](https://www.forecast.it) account, first of all. Then you grab an API key for each app you want to build from the [Forecast](https://www.forecast.it) "Admin" section.

We recommend that you start out by getting to know the concepts and conventions of [Forecast](https://www.forecast.it) (and the API) and learn how to authenticate with us.

## Making a request

All URLs start with `https://api.forecast.it/api/v1/`. **SSL only**. The path contains the API version. If we change the API in backward-incompatible ways, we'll increment the version marker and maintain stable support for the old URLs.

To make a request for all the projects on your account, you'd append the projects index path to the base url e.g. `https://api.forecast.it/api/v1/projects`

Using [curl](http://curl.haxx.se/) it will look like this:

```shell
curl -X GET "https://api.forecast.it/api/v1/projects" -H "X-FORECAST-API-KEY: {API-key}"
```

That's it. Super simple, eh?

## Authentication

If you're making a private integration with [Forecast](https://www.forecast.it) for your own purposes, you can use HTTP header "X-FORECAST-API-KEY". This is secure since all requests in [Forecast](https://www.forecast.it) use [SSL](http://en.wikipedia.org/wiki/Transport_Layer_Security).

API keys are generated in the administration module.

**API keys provide full access to your [Forecast](https://www.forecast.it) account, so keep them like a secret.**

### Disabling an API key

If you're worried that an API key has been compromised, or you're simply no longer using the integration that was accessing your account through a particular API key, [Forecast](https://www.forecast.it) makes it possible to disable or delete that API key.

### API key security

API keys grant full access to your [Forecast](https://www.forecast.it) account, and should be protected the same way you would protect your password. In particular, there are a few common scenarios to keep in mind when working with API keys:

- Give each integration its own API key (or at least use a few). If a specific API key is compromised, you can disable that key without disabling access to all of your other integrations.
- Be careful not to expose the key to the public (such as in screenshots, videos, help documentation, source control, etc). Remember that blurring your data isn't always enough. It's best to use "cut" functions in your graphics program to remove the data completely.
- If a key needs to be shared, generate a new key so it can be disabled, if needed. Make sure never to email the API key; if your email account becomes compromised, the emailed key would allow hackers access to your [Forecast](https://www.forecast.it) account as well.

## No XML, just JSON

We only support [JSON](http://json.org/) for serialization of data. This means that you have to send `Content-Type: application/json; charset=utf-8` when you're POSTing or PUTing data into [Forecast](https://www.forecast.it). **All API URLs only accept and return JSON.**

You'll receive a 415 Unsupported Media Type response code if you don't include the Content-Type header.

## Responses

All GET requests return 200 OK on success along with the JSON of the requested elements (See specific resource entry for JSON examples).

Successful POST requests return 201 CREATED, and successful PUT requests return 200 OK.

Successful PUT and POST requests also return the JSON of the created/updated resource similar to what you would get from a GET request for that specific resource.

Successful DELETE requests return 200 OK

## Pagination

For endpoints with pagination, you can supply the following query parameters:

| Pagination param | Description/Format                                                     |
| ---------------- | ---------------------------------------------------------------------- |
| pageNumber       | Positive integer. Defaults to 1 if not supplied or invalid.            |
| pageSize         | Positive integer. Defaults to 100. Maximum value is subject to change. |

Responses from paginated endpoints will be in the following format:

| Response fields  | Description/Format                                                              |
| ---------------- | ------------------------------------------------------------------------------- |
| pageNumber       | Positive integer. Page number returned.                                         |
| pageSize         | Positive integer. Page size used to generate response.                          |
| totalObjectCount | Positive integer. Size of the total collection of which this page was returned. |
| pageContents     | Array of the objects on the requested page.                                     |

## Handling errors

If [Forecast](https://www.forecast.it) is having trouble, you might see a 5xx error. 500 means that the app is entirely down, but you might also see 502 Bad Gateway, 503 Service Unavailable, or 504 Gateway Timeout. It's your responsibility in all of these cases to retry your request later.

400 Errors usually means that the provided input is invalid and the message will tell you what the problem is.

401 is a failure to authenticate the api key.

404 Errors usually means that you are trying to GET/POST/PUT/DELETE a resource that doesn't exist.

Errors are returned in the following JSON format.

| Response Fields | Description/Format                                                              |
| --------------- | ------------------------------------------------------------------------------- |
| status          | Integer, the status code of the error. This corresponds to the HTTP status code |
| message         | String, a descriptive message explaining the error                              |

### Sample JSON Error Response

```json
{
  "status": 401,
  "message": "Server failed to authenticate the request."
}
```

## API sections (Work in progress)

- [Allocations](sections/allocations.md#allocations)
- [Baseline Expenses](sections/baseline_expenses.md)
- [Baseline Roles](sections/baseline_roles.md)
- [Clients](sections/clients.md#clients)
- [Company](sections/company.md#company)
- [Company contacts](sections/company_contacts.md)
- [Connected projects](sections/connected_projects.md#connected-projects)
- [Departments](sections/departments.md)
- [Exchange rates](sections/exchange_rates.md#exchange-rates)
- [Expense categories](sections/expense_categories.md#expense-categories)
- [Expense items](sections/expense_items.md#expense-items)
- [Financials](sections/financials.md)
- [Holiday calendar entries](sections/holiday_calendar_entries.md)
- [Holiday calendars](sections/holiday_calendars.md#holiday-calendars)
- [Invoices](sections/invoices.md#invoices)
- [Labels](sections/labels.md#labels)
- [Milestones (Deprecated - Name changed to Phases)](sections/milestones_deprecated.md#milestones)
- [Non project time](sections/non_project_time.md#non-project-time)
- [Persons](sections/persons.md#persons)
- [Person cost periods](sections/person_cost_periods.md#person-cost-periods)
- [Person labels (skills)](sections/person_labels.md)
- [Phases](sections/phases.md#phases)
- [Priority levels](sections/priority_levels.md#priority_levels)
- [Project team](sections/project_team.md#project-team)
- [Projects](sections/projects.md#projects)
- [Profiles](sections/profiles.md#profiles)
- [Rate card rates](sections/rate_card_rates.md#rate-card-rates)
- [Rate card versions](sections/rate_card_versions.md#rate-card-versions)
- [Rate cards](sections/rate_cards.md#rate-cards)
- [Repeating tasks](sections/repeating_tasks.md#repeating-tasks)
- [Roles](sections/roles.md#roles)
- [Sprints](sections/sprints.md#sprints)
- [Sub tasks](sections/sub_tasks.md#sub-tasks)
- [Tasks](sections/tasks.md#tasks)
- [Task Financials](sections/task_financials.md)
- [Teams](sections/teams.md#teams)
- [Time registrations](sections/time_registrations.md#time-registrations)
- [Webhook subscriptions](sections/webhook_subscriptions.md#webhook-subscriptions)
- [Workflow columns](sections/workflow_columns.md#workflow-columns)
- [Deleted data](sections/DeletedData.md#deleted-data)
  - [Deleted time registrations](sections/DeletedData.md#deleted-time-registrations)
  - [Deleted tasks](sections/DeletedData.md#deleted-tasks)

## API libraries

- [Google APIs Client Library](https://code.google.com/p/google-api-java-client/) - Java
- [Jersey](https://jersey.java.net/) - Java
- Feel free to add libraries for other languages :)

## Help us make it better

Please tell us how we can make the API better. If you have a specific feature request or if you've found a bug, please contact us.

You can always reach us via email at info@forecast.it
