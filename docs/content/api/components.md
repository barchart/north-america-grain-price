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
| results | [<code>Array&lt;GrainBidsByLocation&gt;</code>](#schemasGrainBidsByLocation) |  | false | A list of groups of grain bids that are grouped by locations. |

**Example**:

```json
{
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
          "active": true,
          "notes": "Discount Schedule",
          "currency": "USD",
          "cashprice": "10.00"
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
| bids | [<code>Array&lt;GrainBid&gt;</code>](#schemasGrainBid) |  | false | A list of cash bids from a grain buying location. Each cash bid contains the meta and price data applicable to that location. |
| distance | <code>String</code> | false | true | Distance of the grain buying location in miles from the input zip code or lat/lng. |
| company | <code>String</code> | false | false | Name of the applicable grain buying elevator. |
| locationId | <code>Integer</code> | false | false | A internal unique identifier of grain buying location. |
| location | <code>String</code> | false | false | Name of grain buying location that grain bid originated from. |
| facility_type | <code>String</code> | false | false | The type of facility. |
| address | <code>String</code> | false | false | The street address of the location. |
| city | <code>String</code> | false | false | City associated with the underlying grain bid. |
| state | <code>String</code> | false | false | 2-char abbreviation of the state that contains the applicable cash bid. |
| lng | <code>Integer</code> | false | false | The longitude of the grain buying location. |
| lat | <code>Integer</code> | false | false | The latitude of the grain buying location. |
| phone | <code>String</code> | false | true | The phone number for the grain buying location. |
| url | <code>String</code> | false | true | The public website of the grain buying elevator. |
| zip | <code>String</code> | false | false | The zip code for the location. |
| county | <code>String</code> | false | true | The name of the county containing the applicable cash bid. |
| basisTimestamp | <code>String</code> | false | false | Datetime in central timezone when basis was last updated for the given elevator. |
| basisTimestampRaw | <code>Integer</code> | false | false | Unix timestamp when basis was last updated for the given elevator. |

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
      "active": true,
      "notes": "Discount Schedule",
      "currency": "USD",
      "cashprice": "10.00"
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
| id | <code>String</code> | false | false | the internal auto-increment numeric id for the cash bid. |
| commodity | <code>String</code> | false | false | The commodity name displayed in grain buyers' end. |
| symbol | <code>String</code> | false | true | Futures contract symbol of  cash bid's associated futures contract. If no symbol, return "". |
| delivery_start | <code>String</code> | false | false | Delivery start date of cash bid. |
| delivery_end | <code>String</code> | false | false | Delivery end date of cash bid. |
| basis | <code>String</code> | false | false | The difference between the cash price grain buyer desire to pay for grain and the futures price of associated futures contract in cents per bushel. |
| active | <code>Boolean</code> | false | false | The status of the cash bid. |
| notes | <code>String</code> | false | false | Notes for cash bid from grain buyer. If not set, return null. |
| currency | <code>String</code> | false | false | The currency of cash price. |
| cashprice | <code>Number</code> | false | false | Cash price grain buyer desire to pay for grain in dollar per bushel. |

**Example**:

```json
{
  "id": "40204932",
  "commodity": "Soybeans",
  "symbol": "ZSX20",
  "delivery_start": "2020-10-01 00:00:00",
  "delivery_end": "2020-11-30 23:59:59",
  "basis": "-62.00",
  "active": true,
  "notes": "Discount Schedule",
  "currency": "USD",
  "cashprice": "10.00"
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
| conditions | [<code>Array&lt;GetGrainBidsResponse&gt;</code>](#schemasGetGrainBidsResponse) |  | false |  |
| publishers | [<code>Array&lt;GetGrainBidsResponse&gt;</code>](#schemasGetGrainBidsResponse) |  | false |  |
| tracking_server_id | <code>Integer</code> | false | true |  |
| schedules | <code>Array</code> | false | false |  |
| effectivePublishers | [<code>Array&lt;GetGrainBidsResponse&gt;</code>](#schemasGetGrainBidsResponse) |  | false |  |

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
              "active": true,
              "notes": "Discount Schedule",
              "currency": "USD",
              "cashprice": "10.00"
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
  ],
  "publishers": [
    {
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
              "active": true,
              "notes": "Discount Schedule",
              "currency": "USD",
              "cashprice": "10.00"
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
  ],
  "tracking_server_id": 0,
  "schedules": [
    []
  ],
  "effectivePublishers": [
    {
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
              "active": true,
              "notes": "Discount Schedule",
              "currency": "USD",
              "cashprice": "10.00"
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
| conditions | [<code>Array&lt;GetGrainBidsResponse&gt;</code>](#schemasGetGrainBidsResponse) |  | false |  |
| publishers | [<code>Array&lt;GetGrainBidsResponse&gt;</code>](#schemasGetGrainBidsResponse) |  | false |  |
| tracking_server_id | <code>Integer</code> | false | true |  |
| schedules | <code>Array</code> | false | false |  |
| effectivePublishers | [<code>Array&lt;GetGrainBidsResponse&gt;</code>](#schemasGetGrainBidsResponse) |  | false |  |

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
              "active": true,
              "notes": "Discount Schedule",
              "currency": "USD",
              "cashprice": "10.00"
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
  ],
  "publishers": [
    {
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
              "active": true,
              "notes": "Discount Schedule",
              "currency": "USD",
              "cashprice": "10.00"
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
  ],
  "tracking_server_id": 0,
  "schedules": [
    []
  ],
  "effectivePublishers": [
    {
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
              "active": true,
              "notes": "Discount Schedule",
              "currency": "USD",
              "cashprice": "10.00"
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
| conditions | [<code>Array&lt;GetGrainBidsResponse&gt;</code>](#schemasGetGrainBidsResponse) |  | false |  |
| publishers | [<code>Array&lt;GetGrainBidsResponse&gt;</code>](#schemasGetGrainBidsResponse) |  | false |  |
| tracking_server_id | <code>Integer</code> | false | true |  |
| schedules | <code>Array</code> | false | false |  |
| effectivePublishers | [<code>Array&lt;GetGrainBidsResponse&gt;</code>](#schemasGetGrainBidsResponse) |  | false |  |

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
              "active": true,
              "notes": "Discount Schedule",
              "currency": "USD",
              "cashprice": "10.00"
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
  ],
  "publishers": [
    {
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
              "active": true,
              "notes": "Discount Schedule",
              "currency": "USD",
              "cashprice": "10.00"
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
  ],
  "tracking_server_id": 0,
  "schedules": [
    []
  ],
  "effectivePublishers": [
    {
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
              "active": true,
              "notes": "Discount Schedule",
              "currency": "USD",
              "cashprice": "10.00"
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
  ]
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

