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

### HTTP Request

`GET https://alfred.hoipos.com/laravel-reservation/api/outlets`

or

`POST https://alfred.hoipos.com/laravel-reservation/api/outlets`

In POST case, we need specify which `action type` call

### Query Parameters

Parameter | Required | Type | Value | Description
--------- | -------- | ------- | ------- | -----------

### Body Parameters
Parameter | Required | Type | Value | Description
--------- | -------- | ------- | ------- | -----------
type | true | string | AJAX_ALL_OUTLETS | const action name to fetch outlets

> Result format is JSON structure:

```json
    {
        "statusCode": 200,
        "statusMsg": "AJAX_SUCCESS",
        "data": [
            {
                "id": 1,
                "brand_id": 1,
                "outlet_name": "HoiPOS Cafe (West)",
                "outlet_address": "#02-21/AB/C Great World City\\n1 Kim Send Promenade\\nSingapore, 237994\\nTel No. 6732-3061\\nGST No: 19-880070-D",
                "outlet_receipt_footer": "THANK YOU FOR SUPPORTING US\\nHAVE A WONDERFUL DAY",
                "outlet_logo": "tunglok_logo",
                "outlet_receipt_logo": "tunglok_logo_receipt",
                "outlet_receipt_footer_logo": null,
                "flow_type": 1,
                "enabled": 1,
                "license_key": "aaa",
                "modified_timestamp": "2015-08-02 23:00:00",
                "created_timestamp": null
            },
            {
                "id": 2,
                "brand_id": 1,
                "outlet_name": "HoiPOS Cafe (East)",
                "outlet_address": "No. 2 Orchard Turn\\n#B2-51 Ion Orchard\\nSingapore 238801",
                "outlet_receipt_footer": "THANK YOU FOR SUPPORTING US\\nHAVE A WONDERFUL DAY",
                "outlet_logo": "",
                "outlet_receipt_logo": "",
                "outlet_receipt_footer_logo": null,
                "flow_type": 0,
                "enabled": 1,
                "license_key": null,
                "modified_timestamp": "2015-08-02 23:00:00",
                "created_timestamp": null
            },
            {
                "id": 3,
                "brand_id": 1,
                "outlet_name": "HoiPOS Cafe (North)",
                "outlet_address": "Ang Mo Kio Ave. 3 #B2-26\\nSingapore 569933\\nTEL: 6453 2521/1976",
                "outlet_receipt_footer": "THANK YOU FOR SUPPORTING US\\nHAVE A WONDERFUL DAY",
                "outlet_logo": "",
                "outlet_receipt_logo": "",
                "outlet_receipt_footer_logo": null,
                "flow_type": 0,
                "enabled": 1,
                "license_key": null,
                "modified_timestamp": "2015-08-02 23:00:00",
                "created_timestamp": null
            },
            {
                "id": 6,
                "brand_id": 1,
                "outlet_name": "Test Outlet (Duplication Test)",
                "outlet_address": "101 HarbourFront Walk, #02-150\\nSingapore 098585\\nGST Reg No: 201510863E",
                "outlet_receipt_footer": "Thank You\\nWe'd love to hear from you!\\nwww.caffebene.com.sg/feedback",
                "outlet_logo": "",
                "outlet_receipt_logo": "",
                "outlet_receipt_footer_logo": null,
                "flow_type": 0,
                "enabled": 1,
                "license_key": "BBCC",
                "modified_timestamp": "2016-05-23 12:14:15",
                "created_timestamp": "2016-05-23 12:14:15"
            },
            {
                "id": 13,
                "brand_id": 1,
                "outlet_name": "Happy Dine",
                "outlet_address": "15 Kent Ridge Drive, #01-03\nS 119245",
                "outlet_receipt_footer": "Thank You",
                "outlet_logo": "",
                "outlet_receipt_logo": "",
                "outlet_receipt_footer_logo": "",
                "flow_type": 1,
                "enabled": 1,
                "license_key": "TLTE",
                "modified_timestamp": "2016-10-29 01:14:22",
                "created_timestamp": "2016-06-20 09:46:53"
            }
        ]
    }
```

Fallback when fetch fail

> Result format is JSON structure:

```json
    {
      "statusCode": 200,
      "statusMsg": "AJAX_UNKNOWN_CASE",
      "data": []
    }
```

Search available time

### HTTP Request

`POST https://alfred.hoipos.com/laravel-reservation/`

### Query Parameters

Parameter | Required | Type | Value | Description
--------- | -------- | ------- | ------- | -----------

### Body Parameters
Parameter | Required | Type | Value | Description
--------- | -------- | ------- | ------- | -----------
outlet_id | true | integer |  | TODO
adult_pax | true | integer |  | TODO
children_pax | true | integer |  | TODO
type | true | string | AJAX_SEARCH_AVAILABLE_TIME | const action name to search

> Result format is JSON structure:

```json
    {
        "statusCode": 200,
        "statusMsg": "AJAX_AVAILABLE_TIME_FOUND",
        "data": {
            "2017-04-04": [
                {
                    "time": "11:00",
                    "session_type": 0,
                    "session_name": "Lunch time",
                    "first_arrival_time": "11:00:00",
                    "interval_minutes": 30,
                    "capacity_1": 1,
                    "capacity_2": 1,
                    "capacity_3_4": -1,
                    "capacity_5_6": 1,
                    "capacity_7_x": 1,
                    "max_pax": 20,
                    "children_allowed": true
                }
            ],
            "2017-04-05": [
                {
                    "time": "11:00",
                    "session_type": 0,
                    "session_name": "Lunch time",
                    "first_arrival_time": "11:00:00",
                    "interval_minutes": 30,
                    "capacity_1": 1,
                    "capacity_2": 1,
                    "capacity_3_4": 1,
                    "capacity_5_6": 1,
                    "capacity_7_x": 1,
                    "max_pax": 20,
                    "children_allowed": true
                },
                {
                    "time": "11:30",
                    "session_type": 0,
                    "session_name": "Lunch time",
                    "first_arrival_time": "11:00:00",
                    "interval_minutes": 30,
                    "capacity_1": 1,
                    "capacity_2": 1,
                    "capacity_3_4": 1,
                    "capacity_5_6": 1,
                    "capacity_7_x": 1,
                    "max_pax": 20,
                    "children_allowed": true
                }
            ],
            "2017-04-06": [
                {
                    "time": "11:00",
                    "session_type": 0,
                    "session_name": "Lunch time",
                    "first_arrival_time": "11:00:00",
                    "interval_minutes": 30,
                    "capacity_1": 1,
                    "capacity_2": 1,
                    "capacity_3_4": 1,
                    "capacity_5_6": 1,
                    "capacity_7_x": 1,
                    "max_pax": 20,
                    "children_allowed": true
                },
                {
                    "time": "11:30",
                    "session_type": 0,
                    "session_name": "Lunch time",
                    "first_arrival_time": "11:00:00",
                    "interval_minutes": 30,
                    "capacity_1": 1,
                    "capacity_2": 1,
                    "capacity_3_4": 1,
                    "capacity_5_6": 1,
                    "capacity_7_x": 1,
                    "max_pax": 20,
                    "children_allowed": true
                }
            ]
        }
    }
```

When no timing found

Response in same structure, with array of timing is empty []

> Result format is JSON structure:

```json
    {
        "statusCode": 200,
        "statusMsg": "AJAX_AVAILABLE_TIME_FOUND",
        "data": {
            "2017-04-04": [],
            "2017-04-05": [],
            "2017-04-06": [],
            "2017-04-07": [],
            "2017-04-08": [],
            "2017-04-09": []
        }
    }
```

###


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





