---
title: HOI API Reference

language_tabs:
  - shell
  - ruby
  - python
  - javascript

#toc_footers:
#  - <a href='#'>Sign Up for a Developer Key</a>
#  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

This is API document for HOIPOS. Currently, there are three APIs which are listed out below:
- Get outlet list
- Get timing list
- Create reservation

<!---
# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>
-->
# HOI APIs

## Get timing list

<!---
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

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```
-->
curl "https://alfred.hoipos.com/laravel-reservation/"
> Result format is JSON structure:

```json
{
  "statusCode": 422,
  "statusMsg": {
    "outlet_id": [
      "The outlet id field is required."
    ],
    "adult_pax": [
      "The adult pax field is required."
    ],
    "children_pax": [
      "The children pax field is required."
    ]
  },
  "data": {
    "------WebKitFormBoundaryjAkhtyTWbfsNcz6L\r\nContent-Disposition:_form-data;_name": "\"outlet_id\"\r\n\r\n1\r\n------WebKitFormBoundaryjAkhtyTWbfsNcz6L\r\nContent-Disposition: form-data; name=\"adult_pax\"\r\n\r\n1\r\n------WebKitFormBoundaryjAkhtyTWbfsNcz6L\r\nContent-Disposition: form-data; name=\"children_pax\"\r\n\r\n0\r\n------WebKitFormBoundaryjAkhtyTWbfsNcz6L--"
  }
}
```

Get all available times.

### HTTP Request

`POST https://alfred.hoipos.com/laravel-reservation/`

### Query Parameters

Parameter | Type | Description
--------- | ------- | -----------


### Body Parameters
Parameter | Type | Description
--------- | ------- | -----------
outlet_id | integer | TODO
adult_pax | integer | TODO
children_pax | integer | TODO

<!---
<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>
-->



