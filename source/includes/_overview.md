# Overview

The Import.io API is organized around [REST](http://en.wikipedia.org/wiki/Representational_state_transfer). We have predictable, resource-oriented URLs, and use HTTP response codes to indicate API errors. We also use built-in HTTP features, like HTTP authentication and HTTP verbs, which are understood by off-the-shelf HTTP clients. We support cross-origin resource sharing ([CORS](http://enable-cors.org/)), allowing you to interact securely with our API from a client-side web application (although you should never expose your secret API key in any public website's client-side code). 

JSON is returned by all API responses, including errors. Our non-Maestro endpoints return newline-delimited JSON, and our Maestro endpoints allow you to indicate return format via an optional argument.  As we continue to build our API libraries, they will convert responses to appropriate language-specific objects.

We send information on new additions and changes to Stripe's API and language libraries to the API announce mailing list. Be sure to subscribe to stay informed.