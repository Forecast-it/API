# What is the Forecast API?

The [Forecast](https://www.forecast.it) API is a complete programmable interface to all Forecast functionality.

This is a [REST](http://en.wikipedia.org/wiki/Representational_state_transfer)-style [API](http://en.wikipedia.org/wiki/Application_programming_interface) that uses [JSON](http://json.org/) for serialization and [HTTP](http://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol).

# What can you do with it?

A ton of stuff! We've exposed all the needed services for you to use in your applications. 

# How do I get started?

You'll need a [Forecast](https://www.forecast.it) account, first of all. Then you grab an API key for each app you want to build from the [Forecast](https://www.forecast.it) "Admin" section.

We recommend that you start out by getting to know the concepts and conventions of [Forecast](https://www.forecast.it) (and the API) and learn how to authenticate with us.

## Making a request

All URLs start with https://api.forecast.it/api/v1/. **SSL only**. The path contains the API version. If we change the API in backward-incompatible ways, we'll increment the version marker and maintain stable support for the old URLs.

To make a request for all the projects on your account, you'd append the projects index path to the base url e.g. https://api.forecast.it/api/v1/projects

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
* Give each integration its own API key (or at least use a few). If a specific API key is compromised, you can disable that key without disabling access to all of your other integrations.
* Be careful not to expose the key to the public (such as in screenshots, videos, help documentation, source control, etc). Remember that blurring your data isn't always enough. It's best to use "cut" functions in your graphics program to remove the data completely.
* If a key needs to be shared, generate a new key so it can be disabled, if needed. Make sure never to email the API key; if your email account becomes compromised, the emailed key would allow hackers access to your [Forecast](https://www.forecast.it) account as well.

## No XML, just JSON

We only support [JSON](http://json.org/) for serialization of data. This means that you have to send `Content-Type: application/json; charset=utf-8` when you're POSTing or PUTing data into [Forecast](https://www.forecast.it). **All API URLs only accept and return JSON.**

## Responses

All GET requests return 200 OK on success along with the JSON of the requested elements (See specific resource entry for JSON examples).

Successful POST requests return 201 CREATED, and successful PUT requests return 200 OK. 

Successful PUT and POST requests also return the JSON of the created/updated resource similar to what you would get from a GET request for that specific resource.

Successful DELETE requests return 200 OK

## Handling errors

If [Forecast](https://www.forecast.it) is having trouble, you might see a 5xx error. 500 means that the app is entirely down, but you might also see 502 Bad Gateway, 503 Service Unavailable, or 504 Gateway Timeout. It's your responsibility in all of these cases to retry your request later.

Attempting a DELETE may result in a 403 Forbidden if the resource can not be deleted due to dependencies. Successful deletions return a 200 OK response. **Note that some resources will only be deactivated by a DELETE request and will therefore still appear on GET requests, but with "active" : false.**

400 Errors usually means that the provided input is invalid and the message will tell you what the problem is.

401 is a failure to authenticate the api key.

404 Errors usually means that you are trying to GET/PUT/DELETE a resource that doesn't exist.

Errors are returned in the following JSON format.

|Response Fields | Description/Format|
|------------ | -------------|
|status | Integer, the status code of the error. This corresponds to the HTTP status code|
|message | String, a descriptive message explaining the error|

### Sample JSON Error Response
```json
{
    "status":401,
    "message":"Server failed to authenticate the request."
}
```

## API sections (Work in progress)

* [Company details](sections/company.md#company)
* [Persons](sections/persons.md)
* [Clients](sections/clients.md)
* [Labels](sections/labels.md)
* [Non project time](sections/non_project_time.md)
* [Roles](sections/roles.md)
* [Allocations](sections/allocations.md)
* [Rate cards](sections/rate_cards.md)
* [Rate card rates](sections/rate_card_rates.md)
* [Projects](sections/projects.md)
* [Project team](sections/project_team.md)
* [Milestones](sections/milestones.md)
* [Sprints](sections/sprints.md)
* [Workflow columns](sections/workflow_columns.md)
* [Cards](sections/cards.md)
* [Time registrations](sections/time_registrations.md)
* [Expense items](sections/expense_items.md)

## API libraries

* [Google APIs Client Library](https://code.google.com/p/google-api-java-client/) - Java
* [Jersey](https://jersey.java.net/) - Java
* Feel free to add libraries for other languages :) 

## Help us make it better

Please tell us how we can make the API better. If you have a specific feature request or if you found a bug, please use GitHub issues. Fork these docs and send a pull request with improvements.

To talk with us and other developers about the API, [post a question on Quora](http://www.quora.com/Forecast-it) under the `forecast-it` topic or open a support ticket through the [Forecast](https://www.forecast.it) support system.

You can always reach us via email at info@forecast.it
