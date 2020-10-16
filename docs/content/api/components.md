# Components

## Responses 

### Success :id=responsessuccess
> Success

**Content Type**: <code>application/json</code>

**Response Type:** <code><code>Object</code></code>

| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| message | <code>String</code> | false | false |  |
| code | <code>Integer</code> | false | false |  |

**Example**:

```json
{
  "message": "Success.",
  "code": 200
}
```

* * *

### Unauthorized :id=responsesunauthorized
> The unauthorized access.

**Content Type**: <code>application/json</code>

**Response Type:** <code><code>Object</code></code>

| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| message | <code>String</code> | false | false |  |

**Example**:

```json
{
  "message": "API key is missing or not valid."
}
```

* * *

### BadRequest :id=responsesbadrequest
> The request was invalid, please see the message for more information.

**Content Type**: <code>application/json</code>

**Response Type:** <code><code>Object</code></code>

| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| message | <code>String</code> | false | false |  |
| code | <code>Integer</code> | false | false |  |

**Example**:

```json
{
  "message": "No active bids available for the requested location(s) at this time.",
  "code": 204
}
```

* * *

### ServerError :id=responsesservererror
> Something is not working correctly, please contact support.

**Content Type**: <code>application/json</code>

**Response Type:** <code><code>Object</code></code>

| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| message | <code>String</code> | false | false |  |
| code | <code>Integer</code> | false | false |  |

**Example**:

```json
{
  "message": "Something is not working correctly, please contact support.",
  "code": 500
}
```

* * *

## Schemas 

### GetGrainBidsResponse :id=schemasgetgrainbidsresponse
**Type**: <code>Object</code>
    
| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| status | <code>Object</code> |  | false |  |
| status.code | <code>Integer</code> | false | false |  |
| status.message | <code>String</code> | false | false |  |
| results | [<code>Array&lt;GrainBidsByLocation&gt;</code>](#schemasGrainBidsByLocation) |  | false |  |

**Example**:

```json
{
  "status": {
    "code": 200,
    "message": "Success."
  },
  "results": [
    {
      "bids": [
        {
          "id": "40204932",
          "commodity": "Soybeans",
          "symbol": "ZSX20",
          "delivery_start": "2020-10-01 00:00:00",
          "delivery_end": "2020-11-30 23:59:59",
          "basis": "-62.00",
          "active": true
        }
      ],
      "distance": "13 miles away",
      "company": "Heartland Coop",
      "locationId": 29443,
      "location": "Panora/Redfield",
      "facility_type": "Country Elevator",
      "address": "310 E. Clay",
      "city": "Panora, Redfield",
      "state": "IA",
      "lng": -94.3611938,
      "lat": 41.6945319,
      "phone": "641-755-2114",
      "url": "www.heartlandcoop.com",
      "zip": "50216",
      "county": "Guthrie County",
      "basisTimestamp": "2020-10-14T12:01:56-05:00",
      "basisTimestampRaw": 1602694916
    }
  ]
}
```

* * *

### GrainBidsByLocation :id=schemasgrainbidsbylocation
**Type**: <code>Object</code>
    
| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| bids | [<code>Array&lt;GrainBid&gt;</code>](#schemasGrainBid) |  | false |  |
| distance | <code>String</code> | false | false |  |
| company | <code>String</code> | false | false |  |
| locationId | <code>Integer</code> | false | false |  |
| location | <code>String</code> | false | false |  |
| facility_type | <code>String</code> | false | false |  |
| address | <code>String</code> | false | false |  |
| city | <code>String</code> | false | false |  |
| state | <code>String</code> | false | false |  |
| lng | <code>Integer</code> | false | false |  |
| lat | <code>Integer</code> | false | false |  |
| phone | <code>String</code> | false | false |  |
| url | <code>String</code> | false | false |  |
| zip | <code>String</code> | false | false |  |
| county | <code>String</code> | false | false |  |
| basisTimestamp | <code>String</code> | false | false |  |
| basisTimestampRaw | <code>Integer</code> | false | false |  |

**Example**:

```json
{
  "bids": [
    {
      "id": "40204932",
      "commodity": "Soybeans",
      "symbol": "ZSX20",
      "delivery_start": "2020-10-01 00:00:00",
      "delivery_end": "2020-11-30 23:59:59",
      "basis": "-62.00",
      "active": true
    }
  ],
  "distance": "13 miles away",
  "company": "Heartland Coop",
  "locationId": 29443,
  "location": "Panora/Redfield",
  "facility_type": "Country Elevator",
  "address": "310 E. Clay",
  "city": "Panora, Redfield",
  "state": "IA",
  "lng": -94.3611938,
  "lat": 41.6945319,
  "phone": "641-755-2114",
  "url": "www.heartlandcoop.com",
  "zip": "50216",
  "county": "Guthrie County",
  "basisTimestamp": "2020-10-14T12:01:56-05:00",
  "basisTimestampRaw": 1602694916
}
```

* * *

### GrainBid :id=schemasgrainbid
**Type**: <code>Object</code>
    
| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| id | <code>String</code> | false | false |  |
| commodity | <code>String</code> | false | false |  |
| symbol | <code>String</code> | false | false |  |
| delivery_start | <code>String</code> | false | false |  |
| delivery_end | <code>String</code> | false | false |  |
| basis | <code>String</code> | false | false |  |
| active | <code>Boolean</code> | false | false |  |

**Example**:

```json
{
  "id": "40204932",
  "commodity": "Soybeans",
  "symbol": "ZSX20",
  "delivery_start": "2020-10-01 00:00:00",
  "delivery_end": "2020-11-30 23:59:59",
  "basis": "-62.00",
  "active": true
}
```

* * *

### getGrainInstrumentsResponse :id=schemasgetgraininstrumentsresponse
**Type**: <code>Object</code>
    
| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| status | <code>Object</code> |  | false |  |
| status.code | <code>Integer</code> | false | false |  |
| status.message | <code>String</code> | false | false |  |
| alert_state | <code>String</code> | false | false |  |
| alert_system | <code>String</code> | false | false |  |
| alert_state_key | <code>String</code> | false | true |  |
| alert_type | <code>String</code> | false | true |  |
| alert_behavior | <code>String</code> | false | false |  |
| user_id | <code>String</code> | false | false |  |
| name | <code>String</code> | false | false |  |
| user_notes | <code>String</code> | false | true |  |
| system_notes | <code>Object</code> | false | false |  |
| automatic_reset | <code>Boolean</code> | false | false |  |
| create_date | <code>String</code> | false | false |  |
| last_trigger_date | <code>String</code> | false | true |  |
| last_start_date | <code>String</code> | false | true |  |
| conditions | [<code>Array&lt;Condition&gt;</code>](#schemasCondition) |  | false |  |
| publishers | [<code>Array&lt;Publisher&gt;</code>](#schemasPublisher) |  | false |  |
| tracking_server_id | <code>Integer</code> | false | true |  |
| schedules | <code>Array</code> | false | false |  |
| effectivePublishers | [<code>Array&lt;Publisher&gt;</code>](#schemasPublisher) |  | false |  |

**Example**:

```json
{
  "status": "39b633bf-8993-491d-b544-bdc9deed60be",
  "alert_state": "Inactive",
  "alert_system": "barchart.com",
  "alert_state_key": "abcdef",
  "alert_type": "price",
  "alert_behavior": "Terminate",
  "user_id": "barchart-test-user",
  "name": "Buy TSLA",
  "user_notes": "Time to buy Tesla Motors stock",
  "system_notes": {},
  "automatic_reset": true,
  "create_date": "1453673000873",
  "last_trigger_date": "145367399999",
  "last_start_date": "145367399999",
  "conditions": [
    {
      "condition_id": "38a3f731-0f87-40b7-a33b-dd9c792998e2",
      "name": "Gap Down is greater than 10.00",
      "operator": {
        "operator_id": 4,
        "operator_type": "binary",
        "operator_name": "is-indicator",
        "operand_options": [
          [
            "Buy",
            "Sell",
            "Hold"
          ]
        ],
        "operand_literal": true,
        "operand_display": "10",
        "operand": "10",
        "display": {
          "short": ">",
          "medium": "greater than",
          "long": "greater than"
        },
        "modifiers": [
          1,
          2,
          3
        ]
      },
      "property": {
        "property_id": 18,
        "type": "number",
        "format": "0,0.00",
        "group": "Technical",
        "accessor": [
          "gapDown"
        ],
        "category": [
          "Gap & Range Change"
        ],
        "description": [
          "Gap Down"
        ],
        "descriptionShort": [
          "Gap Down"
        ],
        "target": {
          "description": "basic",
          "display": "string",
          "identifier": "TSLA",
          "identifier_description": "symbol",
          "qualifier_descriptions": [
            [
              "location",
              "delivery date"
            ]
          ],
          "kind": "string",
          "target_id": 1,
          "type": "symbol"
        },
        "valid_operators": [
          44
        ],
        "sortOrder": 912
      },
      "templates": {
        "condition": "Gap Down is greater than {{{operator.format.operand}}}",
        "trigger": {
          "email": "Gap Down is {{{event.format.gapDown}}}",
          "sms": "Gap Down for {{{property.target.identifier}}} is {{{event.format.gapDown}}}"
        }
      }
    }
  ],
  "publishers": [
    {
      "publisher_id": "9c864a19-ce77-4a87-8cd6-e0810ecb120e",
      "use_default_recipient": false,
      "recipient": "123-456-7890",
      "format": "It is a good time to buy Telsa stock.",
      "timing": {
        "timezon": "America/Chicago"
      },
      "type": {
        "publisher_type_id": 1,
        "transport": "sms",
        "provider": "twilio"
      }
    }
  ],
  "tracking_server_id": 0,
  "schedules": [
    []
  ],
  "effectivePublishers": [
    {
      "publisher_id": "9c864a19-ce77-4a87-8cd6-e0810ecb120e",
      "use_default_recipient": false,
      "recipient": "123-456-7890",
      "format": "It is a good time to buy Telsa stock.",
      "timing": {
        "timezon": "America/Chicago"
      },
      "type": {
        "publisher_type_id": 1,
        "transport": "sms",
        "provider": "twilio"
      }
    }
  ]
}
```

* * *

### getQuoteResponse :id=schemasgetquoteresponse
**Type**: <code>Object</code>
    
| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| status | <code>Object</code> |  | false |  |
| status.code | <code>Integer</code> | false | false |  |
| status.message | <code>String</code> | false | false |  |
| alert_state | <code>String</code> | false | false |  |
| alert_system | <code>String</code> | false | false |  |
| alert_state_key | <code>String</code> | false | true |  |
| alert_type | <code>String</code> | false | true |  |
| alert_behavior | <code>String</code> | false | false |  |
| user_id | <code>String</code> | false | false |  |
| name | <code>String</code> | false | false |  |
| user_notes | <code>String</code> | false | true |  |
| system_notes | <code>Object</code> | false | false |  |
| automatic_reset | <code>Boolean</code> | false | false |  |
| create_date | <code>String</code> | false | false |  |
| last_trigger_date | <code>String</code> | false | true |  |
| last_start_date | <code>String</code> | false | true |  |
| conditions | [<code>Array&lt;Condition&gt;</code>](#schemasCondition) |  | false |  |
| publishers | [<code>Array&lt;Publisher&gt;</code>](#schemasPublisher) |  | false |  |
| tracking_server_id | <code>Integer</code> | false | true |  |
| schedules | <code>Array</code> | false | false |  |
| effectivePublishers | [<code>Array&lt;Publisher&gt;</code>](#schemasPublisher) |  | false |  |

**Example**:

```json
{
  "status": "39b633bf-8993-491d-b544-bdc9deed60be",
  "alert_state": "Inactive",
  "alert_system": "barchart.com",
  "alert_state_key": "abcdef",
  "alert_type": "price",
  "alert_behavior": "Terminate",
  "user_id": "barchart-test-user",
  "name": "Buy TSLA",
  "user_notes": "Time to buy Tesla Motors stock",
  "system_notes": {},
  "automatic_reset": true,
  "create_date": "1453673000873",
  "last_trigger_date": "145367399999",
  "last_start_date": "145367399999",
  "conditions": [
    {
      "condition_id": "38a3f731-0f87-40b7-a33b-dd9c792998e2",
      "name": "Gap Down is greater than 10.00",
      "operator": {
        "operator_id": 4,
        "operator_type": "binary",
        "operator_name": "is-indicator",
        "operand_options": [
          [
            "Buy",
            "Sell",
            "Hold"
          ]
        ],
        "operand_literal": true,
        "operand_display": "10",
        "operand": "10",
        "display": {
          "short": ">",
          "medium": "greater than",
          "long": "greater than"
        },
        "modifiers": [
          1,
          2,
          3
        ]
      },
      "property": {
        "property_id": 18,
        "type": "number",
        "format": "0,0.00",
        "group": "Technical",
        "accessor": [
          "gapDown"
        ],
        "category": [
          "Gap & Range Change"
        ],
        "description": [
          "Gap Down"
        ],
        "descriptionShort": [
          "Gap Down"
        ],
        "target": {
          "description": "basic",
          "display": "string",
          "identifier": "TSLA",
          "identifier_description": "symbol",
          "qualifier_descriptions": [
            [
              "location",
              "delivery date"
            ]
          ],
          "kind": "string",
          "target_id": 1,
          "type": "symbol"
        },
        "valid_operators": [
          44
        ],
        "sortOrder": 912
      },
      "templates": {
        "condition": "Gap Down is greater than {{{operator.format.operand}}}",
        "trigger": {
          "email": "Gap Down is {{{event.format.gapDown}}}",
          "sms": "Gap Down for {{{property.target.identifier}}} is {{{event.format.gapDown}}}"
        }
      }
    }
  ],
  "publishers": [
    {
      "publisher_id": "9c864a19-ce77-4a87-8cd6-e0810ecb120e",
      "use_default_recipient": false,
      "recipient": "123-456-7890",
      "format": "It is a good time to buy Telsa stock.",
      "timing": {
        "timezon": "America/Chicago"
      },
      "type": {
        "publisher_type_id": 1,
        "transport": "sms",
        "provider": "twilio"
      }
    }
  ],
  "tracking_server_id": 0,
  "schedules": [
    []
  ],
  "effectivePublishers": [
    {
      "publisher_id": "9c864a19-ce77-4a87-8cd6-e0810ecb120e",
      "use_default_recipient": false,
      "recipient": "123-456-7890",
      "format": "It is a good time to buy Telsa stock.",
      "timing": {
        "timezon": "America/Chicago"
      },
      "type": {
        "publisher_type_id": 1,
        "transport": "sms",
        "provider": "twilio"
      }
    }
  ]
}
```

* * *

### getHistoryResponse :id=schemasgethistoryresponse
**Type**: <code>Object</code>
    
| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| status | <code>Object</code> |  | false |  |
| status.code | <code>Integer</code> | false | false |  |
| status.message | <code>String</code> | false | false |  |
| alert_state | <code>String</code> | false | false |  |
| alert_system | <code>String</code> | false | false |  |
| alert_state_key | <code>String</code> | false | true |  |
| alert_type | <code>String</code> | false | true |  |
| alert_behavior | <code>String</code> | false | false |  |
| user_id | <code>String</code> | false | false |  |
| name | <code>String</code> | false | false |  |
| user_notes | <code>String</code> | false | true |  |
| system_notes | <code>Object</code> | false | false |  |
| automatic_reset | <code>Boolean</code> | false | false |  |
| create_date | <code>String</code> | false | false |  |
| last_trigger_date | <code>String</code> | false | true |  |
| last_start_date | <code>String</code> | false | true |  |
| conditions | [<code>Array&lt;Condition&gt;</code>](#schemasCondition) |  | false |  |
| publishers | [<code>Array&lt;Publisher&gt;</code>](#schemasPublisher) |  | false |  |
| tracking_server_id | <code>Integer</code> | false | true |  |
| schedules | <code>Array</code> | false | false |  |
| effectivePublishers | [<code>Array&lt;Publisher&gt;</code>](#schemasPublisher) |  | false |  |

**Example**:

```json
{
  "status": "39b633bf-8993-491d-b544-bdc9deed60be",
  "alert_state": "Inactive",
  "alert_system": "barchart.com",
  "alert_state_key": "abcdef",
  "alert_type": "price",
  "alert_behavior": "Terminate",
  "user_id": "barchart-test-user",
  "name": "Buy TSLA",
  "user_notes": "Time to buy Tesla Motors stock",
  "system_notes": {},
  "automatic_reset": true,
  "create_date": "1453673000873",
  "last_trigger_date": "145367399999",
  "last_start_date": "145367399999",
  "conditions": [
    {
      "condition_id": "38a3f731-0f87-40b7-a33b-dd9c792998e2",
      "name": "Gap Down is greater than 10.00",
      "operator": {
        "operator_id": 4,
        "operator_type": "binary",
        "operator_name": "is-indicator",
        "operand_options": [
          [
            "Buy",
            "Sell",
            "Hold"
          ]
        ],
        "operand_literal": true,
        "operand_display": "10",
        "operand": "10",
        "display": {
          "short": ">",
          "medium": "greater than",
          "long": "greater than"
        },
        "modifiers": [
          1,
          2,
          3
        ]
      },
      "property": {
        "property_id": 18,
        "type": "number",
        "format": "0,0.00",
        "group": "Technical",
        "accessor": [
          "gapDown"
        ],
        "category": [
          "Gap & Range Change"
        ],
        "description": [
          "Gap Down"
        ],
        "descriptionShort": [
          "Gap Down"
        ],
        "target": {
          "description": "basic",
          "display": "string",
          "identifier": "TSLA",
          "identifier_description": "symbol",
          "qualifier_descriptions": [
            [
              "location",
              "delivery date"
            ]
          ],
          "kind": "string",
          "target_id": 1,
          "type": "symbol"
        },
        "valid_operators": [
          44
        ],
        "sortOrder": 912
      },
      "templates": {
        "condition": "Gap Down is greater than {{{operator.format.operand}}}",
        "trigger": {
          "email": "Gap Down is {{{event.format.gapDown}}}",
          "sms": "Gap Down for {{{property.target.identifier}}} is {{{event.format.gapDown}}}"
        }
      }
    }
  ],
  "publishers": [
    {
      "publisher_id": "9c864a19-ce77-4a87-8cd6-e0810ecb120e",
      "use_default_recipient": false,
      "recipient": "123-456-7890",
      "format": "It is a good time to buy Telsa stock.",
      "timing": {
        "timezon": "America/Chicago"
      },
      "type": {
        "publisher_type_id": 1,
        "transport": "sms",
        "provider": "twilio"
      }
    }
  ],
  "tracking_server_id": 0,
  "schedules": [
    []
  ],
  "effectivePublishers": [
    {
      "publisher_id": "9c864a19-ce77-4a87-8cd6-e0810ecb120e",
      "use_default_recipient": false,
      "recipient": "123-456-7890",
      "format": "It is a good time to buy Telsa stock.",
      "timing": {
        "timezon": "America/Chicago"
      },
      "type": {
        "publisher_type_id": 1,
        "transport": "sms",
        "provider": "twilio"
      }
    }
  ]
}
```

* * *

### Alert :id=schemasalert
**Type**: <code>Object</code>
    
| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| alert_id | <code>String</code> | false | false |  |
| alert_state | <code>String</code> | false | false |  |
| alert_system | <code>String</code> | false | false |  |
| alert_state_key | <code>String</code> | false | true |  |
| alert_type | <code>String</code> | false | true |  |
| alert_behavior | <code>String</code> | false | false |  |
| user_id | <code>String</code> | false | false |  |
| name | <code>String</code> | false | false |  |
| user_notes | <code>String</code> | false | true |  |
| system_notes | <code>Object</code> | false | false |  |
| automatic_reset | <code>Boolean</code> | false | false |  |
| create_date | <code>String</code> | false | false |  |
| last_trigger_date | <code>String</code> | false | true |  |
| last_start_date | <code>String</code> | false | true |  |
| conditions | [<code>Array&lt;Condition&gt;</code>](#schemasCondition) |  | false |  |
| publishers | [<code>Array&lt;Publisher&gt;</code>](#schemasPublisher) |  | false |  |
| tracking_server_id | <code>Integer</code> | false | true |  |
| schedules | <code>Array</code> | false | false |  |
| effectivePublishers | [<code>Array&lt;Publisher&gt;</code>](#schemasPublisher) |  | false |  |

**Example**:

```json
{
  "alert_id": "39b633bf-8993-491d-b544-bdc9deed60be",
  "alert_state": "Inactive",
  "alert_system": "barchart.com",
  "alert_state_key": "abcdef",
  "alert_type": "price",
  "alert_behavior": "Terminate",
  "user_id": "barchart-test-user",
  "name": "Buy TSLA",
  "user_notes": "Time to buy Tesla Motors stock",
  "system_notes": {},
  "automatic_reset": true,
  "create_date": "1453673000873",
  "last_trigger_date": "145367399999",
  "last_start_date": "145367399999",
  "conditions": [
    {
      "condition_id": "38a3f731-0f87-40b7-a33b-dd9c792998e2",
      "name": "Gap Down is greater than 10.00",
      "operator": {
        "operator_id": 4,
        "operator_type": "binary",
        "operator_name": "is-indicator",
        "operand_options": [
          [
            "Buy",
            "Sell",
            "Hold"
          ]
        ],
        "operand_literal": true,
        "operand_display": "10",
        "operand": "10",
        "display": {
          "short": ">",
          "medium": "greater than",
          "long": "greater than"
        },
        "modifiers": [
          1,
          2,
          3
        ]
      },
      "property": {
        "property_id": 18,
        "type": "number",
        "format": "0,0.00",
        "group": "Technical",
        "accessor": [
          "gapDown"
        ],
        "category": [
          "Gap & Range Change"
        ],
        "description": [
          "Gap Down"
        ],
        "descriptionShort": [
          "Gap Down"
        ],
        "target": {
          "description": "basic",
          "display": "string",
          "identifier": "TSLA",
          "identifier_description": "symbol",
          "qualifier_descriptions": [
            [
              "location",
              "delivery date"
            ]
          ],
          "kind": "string",
          "target_id": 1,
          "type": "symbol"
        },
        "valid_operators": [
          44
        ],
        "sortOrder": 912
      },
      "templates": {
        "condition": "Gap Down is greater than {{{operator.format.operand}}}",
        "trigger": {
          "email": "Gap Down is {{{event.format.gapDown}}}",
          "sms": "Gap Down for {{{property.target.identifier}}} is {{{event.format.gapDown}}}"
        }
      }
    }
  ],
  "publishers": [
    {
      "publisher_id": "9c864a19-ce77-4a87-8cd6-e0810ecb120e",
      "use_default_recipient": false,
      "recipient": "123-456-7890",
      "format": "It is a good time to buy Telsa stock.",
      "timing": {
        "timezon": "America/Chicago"
      },
      "type": {
        "publisher_type_id": 1,
        "transport": "sms",
        "provider": "twilio"
      }
    }
  ],
  "tracking_server_id": 0,
  "schedules": [
    []
  ],
  "effectivePublishers": [
    {
      "publisher_id": "9c864a19-ce77-4a87-8cd6-e0810ecb120e",
      "use_default_recipient": false,
      "recipient": "123-456-7890",
      "format": "It is a good time to buy Telsa stock.",
      "timing": {
        "timezon": "America/Chicago"
      },
      "type": {
        "publisher_type_id": 1,
        "transport": "sms",
        "provider": "twilio"
      }
    }
  ]
}
```

* * *

### Publisher :id=schemaspublisher
**Type**: <code>Object</code>
    
| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| publisher_id | <code>String</code> | false | false |  |
| use_default_recipient | <code>Boolean</code> | false | false |  |
| recipient | <code>String</code> | false | false |  |
| format | <code>String</code> | false | false |  |
| timing | <code>Object</code> |  | false |  |
| timing.timezon | <code>String</code> | false | false |  |
| type | <code>Object</code> |  | false |  |
| type.publisher_type_id | <code>Integer</code> | false | false |  |
| type.transport | <code>String</code> | false | false |  |
| type.provider | <code>String</code> | false | false |  |

**Example**:

```json
{
  "publisher_id": "9c864a19-ce77-4a87-8cd6-e0810ecb120e",
  "use_default_recipient": false,
  "recipient": "123-456-7890",
  "format": "It is a good time to buy Telsa stock.",
  "timing": {
    "timezon": "America/Chicago"
  },
  "type": {
    "publisher_type_id": 1,
    "transport": "sms",
    "provider": "twilio"
  }
}
```

* * *

### Operator :id=schemasoperator
**Type**: <code>Object</code>
    
| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| operator_id | <code>Integer</code> | false | false |  |
| operator_type | <code>String</code> | false | false |  |
| operator_name | <code>String</code> | false | false |  |
| operand_options | <code>Array</code> | false | false |  |
| operand_options[i] | <code>String</code> | false | false |  |
| operand_literal | <code>Boolean</code> | false | false |  |
| operand_display | <code>String</code> | false | false |  |
| operand | <code>String</code> | false | false |  |
| display | <code>Object</code> |  | false |  |
| display.short | <code>String</code> | false | false |  |
| display.medium | <code>String</code> | false | false |  |
| display.long | <code>String</code> | false | false |  |
| modifiers | <code>Array</code> | false | false |  |
| modifiers[i] | <code>Integer</code> | false | false |  |

**Example**:

```json
{
  "operator_id": 4,
  "operator_type": "binary",
  "operator_name": "is-indicator",
  "operand_options": [
    [
      "Buy",
      "Sell",
      "Hold"
    ]
  ],
  "operand_literal": true,
  "operand_display": "10",
  "operand": "10",
  "display": {
    "short": ">",
    "medium": "greater than",
    "long": "greater than"
  },
  "modifiers": [
    1,
    2,
    3
  ]
}
```

* * *

### Condition :id=schemascondition
**Type**: <code>Object</code>
    
| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| condition_id | <code>String</code> | false | false |  |
| name | <code>String</code> | false | false |  |
| operator | [<code>Operator</code>](#schemasOperator) |  | false |  |
| property | [<code>Property</code>](#schemasProperty) |  | false |  |
| templates | <code>Object</code> |  | false |  |
| templates.condition | <code>String</code> | false | false |  |
| templates.trigger | <code>Object</code> |  | false |  |
| templates.trigger.email | <code>String</code> | false | false |  |
| templates.trigger.sms | <code>String</code> | false | false |  |

**Example**:

```json
{
  "condition_id": "38a3f731-0f87-40b7-a33b-dd9c792998e2",
  "name": "Gap Down is greater than 10.00",
  "operator": {
    "operator_id": 4,
    "operator_type": "binary",
    "operator_name": "is-indicator",
    "operand_options": [
      [
        "Buy",
        "Sell",
        "Hold"
      ]
    ],
    "operand_literal": true,
    "operand_display": "10",
    "operand": "10",
    "display": {
      "short": ">",
      "medium": "greater than",
      "long": "greater than"
    },
    "modifiers": [
      1,
      2,
      3
    ]
  },
  "property": {
    "property_id": 18,
    "type": "number",
    "format": "0,0.00",
    "group": "Technical",
    "accessor": [
      "gapDown"
    ],
    "category": [
      "Gap & Range Change"
    ],
    "description": [
      "Gap Down"
    ],
    "descriptionShort": [
      "Gap Down"
    ],
    "target": {
      "description": "basic",
      "display": "string",
      "identifier": "TSLA",
      "identifier_description": "symbol",
      "qualifier_descriptions": [
        [
          "location",
          "delivery date"
        ]
      ],
      "kind": "string",
      "target_id": 1,
      "type": "symbol"
    },
    "valid_operators": [
      44
    ],
    "sortOrder": 912
  },
  "templates": {
    "condition": "Gap Down is greater than {{{operator.format.operand}}}",
    "trigger": {
      "email": "Gap Down is {{{event.format.gapDown}}}",
      "sms": "Gap Down for {{{property.target.identifier}}} is {{{event.format.gapDown}}}"
    }
  }
}
```

* * *

### Property :id=schemasproperty
**Type**: <code>Object</code>
    
| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| property_id | <code>Integer</code> | false | false |  |
| type | <code>String</code> | false | false |  |
| format | <code>String</code> | false | false |  |
| group | <code>String</code> | false | false |  |
| accessor | <code>Array</code> | false | false |  |
| accessor[i] | <code>String</code> | false | false |  |
| category | <code>Array</code> | false | false |  |
| category[i] | <code>String</code> | false | false |  |
| description | <code>Array</code> | false | false |  |
| description[i] | <code>String</code> | false | false |  |
| descriptionShort | <code>Array</code> | false | false |  |
| descriptionShort[i] | <code>String</code> | false | false |  |
| target | [<code>Target</code>](#schemasTarget) |  | false |  |
| valid_operators | <code>Array</code> | false | false |  |
| valid_operators[i] | <code>Integer</code> | false | false |  |
| sortOrder | <code>Integer</code> | false | false |  |

**Example**:

```json
{
  "property_id": 18,
  "type": "number",
  "format": "0,0.00",
  "group": "Technical",
  "accessor": [
    "gapDown"
  ],
  "category": [
    "Gap & Range Change"
  ],
  "description": [
    "Gap Down"
  ],
  "descriptionShort": [
    "Gap Down"
  ],
  "target": {
    "description": "basic",
    "display": "string",
    "identifier": "TSLA",
    "identifier_description": "symbol",
    "qualifier_descriptions": [
      [
        "location",
        "delivery date"
      ]
    ],
    "kind": "string",
    "target_id": 1,
    "type": "symbol"
  },
  "valid_operators": [
    44
  ],
  "sortOrder": 912
}
```

* * *

### Target :id=schemastarget
**Type**: <code>Object</code>
    
| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| description | <code>String</code> | true | false |  |
| display | <code>String</code> | false | true |  |
| identifier | <code>String</code> | false | false |  |
| identifier_description | <code>String</code> | true | false |  |
| qualifier_descriptions | <code>Array</code> | false | false |  |
| qualifier_descriptions[i] | <code>String</code> | false | false |  |
| kind | <code>String</code> | false | true |  |
| target_id | <code>Integer</code> | true | false |  |
| type | <code>String</code> | true | false |  |

**Example**:

```json
{
  "description": "basic",
  "display": "string",
  "identifier": "TSLA",
  "identifier_description": "symbol",
  "qualifier_descriptions": [
    [
      "location",
      "delivery date"
    ]
  ],
  "kind": "string",
  "target_id": 1,
  "type": "symbol"
}
```

* * *

## Security 

### JWT :id=securityjwt

>The JWT authorization

**Type**: http bearer
    
#### Headers
| Name | Format | Example |
| ---- | ------ | ------- |
| Authorization | JWT | Authorization: Bearer <code>&lt;Token&gt;</code> |

* * *

