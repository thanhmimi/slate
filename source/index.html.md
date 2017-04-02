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

Parameter | Required | Type | Description
--------- | -------- | ------- | -----------


### Body Parameters
Parameter | Required | Type | Description
--------- | -------- | ------- | -----------
outlet_id | true | integer | TODO
adult_pax | true | integer | TODO
children_pax | true | integer | TODO

## Create reservation

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
    "------WebKitFormBoundarybFnjGV21oAxa8T1Q\r\nContent-Disposition:_form-data;_name": "\"outlet_id\"\r\n\r\n1\r\n------WebKitFormBoundarybFnjGV21oAxa8T1Q\r\nContent-Disposition: form-data; name=\"salutation\"\r\n\r\nMr.\r\n------WebKitFormBoundarybFnjGV21oAxa8T1Q\r\nContent-Disposition: form-data; name=\"first_name\"\r\n\r\nAnh\r\n------WebKitFormBoundarybFnjGV21oAxa8T1Q\r\nContent-Disposition: form-data; name=\"last_name\"\r\n\r\nLe Hoang\r\n------WebKitFormBoundarybFnjGV21oAxa8T1Q\r\nContent-Disposition: form-data; name=\"email\"\r\n\r\nlehoanganh25991@gmail.com\r\n------WebKitFormBoundarybFnjGV21oAxa8T1Q\r\nContent-Disposition: form-data; name=\"phone_country_code\"\r\n\r\n 84\r\n------WebKitFormBoundarybFnjGV21oAxa8T1Q\r\nContent-Disposition: form-data; name=\"phone\"\r\n\r\n903865657\r\n------WebKitFormBoundarybFnjGV21oAxa8T1Q\r\nContent-Disposition: form-data; name=\"adult_pax\"\r\n\r\n1\r\n------WebKitFormBoundarybFnjGV21oAxa8T1Q\r\nContent-Disposition: form-data; name=\"children_pax\"\r\n\r\n0\r\n------WebKitFormBoundarybFnjGV21oAxa8T1Q\r\nContent-Disposition: form-data; name=\"reservation_timestamp\"\r\n\r\n2017-03-30 20:00:00\r\n------WebKitFormBoundarybFnjGV21oAxa8T1Q\r\nContent-Disposition: form-data; name=\"step\"\r\n\r\nform-step-3\r\n------WebKitFormBoundarybFnjGV21oAxa8T1Q--"
  }
}
```

Create a reservation.

### HTTP Request

`POST https://alfred.hoipos.com/laravel-reservation/`

### Query Parameters

Parameter | Required | Type | Description
--------- | -------- | ------- | -----------


### Body Parameters
Parameter | Required | Type | Description
--------- | -------- | ------- | -----------
outlet_id | true | integer | TODO
salutation | false | string | TODO
first_name | false | string | TODO
last_name | false | string | TODO
email | false | string | TODO
phone_country_code | false | integer | TODO
phone | false | integer | TODO
adult_pax | true | integer | TODO
children_pax | true | integer | TODO
reservation_timestamp | false | integer | TODO
step | false | string | TODO





