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

Search available time

Create a reservation

#APIs

## Get outlet list 

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
            }
        ]
    }
```

### HTTP Request

`GET https://alfred.hoipos.com/reservation/dev/api/outlets`

or

`POST https://alfred.hoipos.com/reservation/dev/api/outlets`

In POST case, we need specify which `action type` called

### Query Parameters

Parameter | Required | Type | Value | Description
--------- | -------- | ------- | ------- | -----------

### Body Parameters
Parameter | Required | Type | Value | Description
--------- | -------- | ------- | ------- | -----------
type | true | string | AJAX_ALL_OUTLETS | const action name to fetch outlets


> Result format is JSON structure as unknown case:

```json
    {
      "statusCode": 200,
      "statusMsg": "AJAX_UNKNOWN_CASE",
      "data": []
    }
```
### Fallback when action type not specify as unknown case

## Search available time

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
            ]
        }
    }
```

### HTTP Request

`POST https://alfred.hoipos.com/reservation/dev/api`

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

> Result format is JSON structure as timing is empty:

```json
    {
        "statusCode": 200,
        "statusMsg": "AJAX_AVAILABLE_TIME_FOUND",
        "data": {
            "2017-04-04": [],
            "2017-04-05": [],
            "2017-04-06": []
        }
    }
```

### When no timing found, response in same structure

Array of timing is empty, []

Fallback when action type not specify

> Result format is JSON structure for condition validate failed:

```json
    {
        "statusCode": 422,
        "statusMsg": "AJAX_BOOKING_CONDITION_VALIDATE_FAIL",
        "data": {
            "outlet_id": [
                "The outlet id must be a number."
            ]
        }
    }
```

### Validate case

Status code: 422

Status message: AJAX_BOOKING_CONDITION_VALIDATE_FAIL

Reponse with error message inside data, for example

### Fallback when action type not specify as __unknown case__

> Result format is JSON structure as unknown case:

```json
    {
      "statusCode": 200,
      "statusMsg": "AJAX_UNKNOWN_CASE",
      "data": []
    }
```


## Create a reservation

> Result format is JSON structure:

Return the confirm_id of reservation

```json
    {
      "statusCode": 200,
      "statusMsg": "AJAX_RESERVATION_SUCCESS_CREATE",
      "data": {
        "confirm_id" : "GHSG675"
      }
    }    
```

###ERROR CASE

###Validate fail

Params submit not follow type or format required|
--- | --- |
Status code : 422|
Status msg : AJAX_RESERVATION_VALIDATE_FAIL|
Reponse with error message inside res.data|

> Result format is JSON structure for validate fail:

```json
    {
        "statusCode": 422,
        "statusMsg": "AJAX_RESERVATION_VALIDATE_FAIL",
        "data": {
            "outlet_id": [
                "The outlet id must be a number."
            ]
        }
    }
```

###Total pax out of range

Type & format as expect, but total pax out of overall config|
--------- | -------- |
Status code : 422|
Status msg : AJAX_RESERVATION_VALIDATE_FAIL|
Case happen when pax size = adult pax + children pax Out of config pax range, example: Only allow from 2 to 20|

> Result format is JSON structure for pax out of range:

```json
    {
        "statusCode": 422,
        "statusMsg": "AJAX_RESERVATION_VALIDATE_FAIL",
        "data": {
            "pax": "total pax out of overall_range"
        }
    }
```

###No longer available

Someone has occupied the slot|
--- | --- |
Status code : 422|
Status msg : AJAX_RESERVATION_NO_LONGER_AVAILABLE|
Everything is fine, but bcs of delay when booking, someone has submited booking to create reservation before the current customer|

> Result format is JSON structure for no longer available:

```json
    {
        "statusCode": 422,
        "statusMsg": "AJAX_RESERVATION_NO_LONGER_AVAILABLE",
        "data": {}
    }
```

###Reservation require deposit

Payment for deposit is required|
--- | --- |
Status code : 422|
Status msg : AJAX_RESERVATION_REQUIRED_DEPOSIT|
Customer with large number of pax, deposit payment is required|

Ask customer to complete the payment with paypal

Base on deposit amount

> Result format is JSON structure for require deposit:

```json
    {
        "statusCode": 422,
        "statusMsg": "AJAX_RESERVATION_REQUIRED_DEPOSIT",
        "data": {
            "confirm_id" : "AHGTY78",
            "deposit" : 190
        }
    }
```
### Fallback when action type not specify

_|
--- | --- |
Status code: 422|
Status msg: AJAX_UNKNOWN_CASE|
Server not support your action call|

> Result format is JSON structure for fallback case:

```json
    {
      "statusCode": 200,
      "statusMsg": "AJAX_UNKNOWN_CASE",
      "data": []
    }
```






















