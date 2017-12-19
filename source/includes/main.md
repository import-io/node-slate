# Introduction

Welcome to the Import.io API! This documentation describes how to use our API to access Import.io API endpoints, which allow you to leverage the Import.io platform to configure and retrieve data, reports and attachments.  

It's important to note that we've separated the API documentation into two primary sections: the first section is called "Maestro" and is intended to be a more user-friendly and approachable API that should cover most common use cases.  In the second section, we describe our underlying external API endpoints for more advanced or non-standard integrations.  If you have an use case for the platform API that we don't cover, please reach out and we'll help you figure out how to get it done or work to get it on the platform roadmap.

We currently have language bindings in Python and Javascript that we're working to extend and expand upon.  We're also working to create and expose public repositories for usage examples in each language, and will update this document with links and usage instructions as they become available. You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Overview

The Import.io API is organized around [REST](http://en.wikipedia.org/wiki/Representational_state_transfer). We have predictable, resource-oriented URLs, and use HTTP response codes to indicate API errors. We also use built-in HTTP features, like HTTP authentication and HTTP verbs, which are understood by off-the-shelf HTTP clients. We support cross-origin resource sharing ([CORS](http://enable-cors.org/)), allowing you to interact securely with our API from a client-side web application (although you should never expose your secret API key in any public website's client-side code). 

JSON is returned by all API responses, including errors. Our non-Maestro endpoints return newline-delimted JSON, and our Maestro endpoints allow you to indicate return format via an optional argument.  As we continue to build our API libraries, they will convert responses to appropriate language-specific objects.

We send information on new additions and changes to Stripe's API and language libraries to the API announce mailing list. Be sure to subscribe to stay informed.

# Error Codes

We use conventional HTTP response codes to indicate success or failure of an API request. Codes in the 2xx range indicate success, codes in the 4xx range indicate an error that resulted from the provided information (e.g. a required parameter was missing) and codes in the 5xx range indicate an error with our servers.

# Authentication

> To authorize:

```python
import importio

api = importio.authorize('fe2eacc27c1d45c8a872abbc36cac86574a279e74106edfad11959e9da4c49ee6eb67369f6f4cedacbdc68d2ea56a924a791c9adae80b372ebea4530d2f7c2edd39b2d5bd8a6135f44f312bf6f9bc87b')
```

```javascript
const importio = require('importio');

let api = importio.authorize('fe2eacc27c1d45c8a872abbc36cac86574a279e74106edfad11959e9da4c49ee6eb67369f6f4cedacbdc68d2ea56a924a791c9adae80b372ebea4530d2f7c2edd39b2d5bd8a6135f44f312bf6f9bc87b');
```

> Make sure to replace the sample key with your API key found on your [User Account](https://account.import.io) page. 

Import.io uses API keys to allow access to the API. You can generate a new Import.io API key at your [User Account](https://account.import.io) page.

The Import.io platform expects that the API key will be included in all API requests in one of two forms: via header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Kittens

## Get All Kittens

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```bash
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```bash
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve
