---
title: HOI API Reference


#toc_footers:
#  - <a href='#'>Sign Up for a Developer Key</a>
#  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

This is API document for HOIPOS. Currently, there are three APIs which are listed out below:

Get outlet list

Get timing list

Create reservation

# HOI APIs

## Get timing list

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





