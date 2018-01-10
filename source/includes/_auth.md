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

`Authorization: Bearer: [apikey]`

<aside class="notice">
You must replace <code>[apikey]</code> with your personal API key for your account.
</aside>