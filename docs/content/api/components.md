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
| symbol | <code>String</code> | true | false | A unique symbol that identifies a grain bid or a grain index. |
| symbolDescription | <code>String</code> | true | false | A short description of a grain bid or a grain index. |
| elevator | <code>String</code> | true | false | Name of the applicable grain buying elevator. (ONLY returned for instrument type bidBasis or bidCash.) |
| commodity | <code>String</code> | true | false | Standardized commodity name. |
| underlyingFuture | <code>String</code> | true | false | Futures symbol of tied futures contract. |
| deliveryStart | <code>String</code> | true | false | Delivery start date of grain bid. (ONLY returned for instrument type bidBasis or bidCash.) |
| deliveryEnd | <code>String</code> | true | false | Delivery end date of the associated grain instrument. |
| location | <code>String</code> | true | false | Name of location that grain bid originated from. (ONLY returned for instrument type bidBasis or bidCash.) |
| facilityType | <code>String</code> | true | false | The type of facility. (ONLY returned for instrument type bidBasis or bidCash.) |
| phone | <code>String</code> | true | false | Phone number of location. (ONLY returned for instrument type bidBasis or bidCash.) |
| website | <code>String</code> | true | false | Website associated with elevator. (ONLY returned for instrument type bidBasis or bidCash.) |
| address | <code>String</code> | true | false | The street address of the location. (ONLY returned for instrument type bidBasis or bidCash.) |
| city | <code>String</code> | true | false | City associated with the underlying grain bid. (ONLY returned for instrument type bidBasis or bidCash.) |
| state | <code>String</code> | true | false | 2-char abbreviation of the state that contains the applicable cash bid or index. |
| zipCode | <code>String</code> | true | false | Zip code associated with the underlying grain bid.  |
| longitude | <code>String</code> | true | false | The longitude of the location. (ONLY returned for instrument type bidBasis or bidCash.) |
| latitude | <code>String</code> | true | false | The latitude of the location. (ONLY returned for instrument type bidBasis or bidCash.) |
| county | <code>String</code> | true | false | The name of the county containing the applicable cash bid or index. |
| countyCode | <code>String</code> | true | false | Concatenation of stateFipsCode, countyFipsCode, and classFipsCode. (ONLY returned for instrument type bidBasis or bidCash.)
| fipsCode | <code>String</code> | true | false | FIPS code for the county. Concatenation of stateFipsCode and countyFipsCode. (ONLY returned for instrument type bidBasis or bidCash.) |
| countyFipsCode | <code>String</code> | true | false | 3-digit FIPS code of the county is associated with the applicable cash bid or index. |
| districtCode | <code>String</code> | true | false | 2-digit district code of crop reporting district that is associated with the applicable cash bid or index. |
| stateFipsCode | <code>String</code> | true | false | 2-digit FIPS code of state that is associated with the applicable cash bid or index. |

**Example**:

```json
{
    "results": [
        {
            "symbol": "ZCBQ20-5827-5398.CM",
            "symbolDescription": "Cargill US Beardstown, IL Corn (#2 Yellow) Aug 20 Basis",
            "elevator": "Cargill US",
            "commodity": "Corn (#2 Yellow)",
            "underlyingFuture": "ZCU20",
            "deliveryStart": "2020-08-01T00:00:00-05:00",
            "deliveryEnd": "2020-08-31T23:59:59-05:00",
            "location": "Beardstown, CAH",
            "facilityType": "Country Elevator",
            "phone": "800-742-2789",
            "website": "www.cargillag.com",
            "address": "814 West Main Street",
            "city": "Beardstown",
            "state": "IL",
            "zipCode": "62618",
            "longitude": "-90.44167",
            "latitude": "40.0153",
            "county": "Cass County",
            "countyCode": "IL-17-017-H1",
            "fipsCode": "17017",
            "countyFipsCode": "017",
            "districtCode": "60",
            "stateFipsCode": "17"
        }
    ]
}
```

* * *

### getQuoteResponse :id=schemasgetquoteresponse
**Type**: <code>Object</code>
    
| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| symbol | <code>String</code> | true | false | A symbol or code that identifies a financial instrument. |
| name | <code>String</code> | true | false | The name of instrument. |
| dayCode | <code>String</code> | true | false | The day code for the session. Day codes are "1-9" for days 1 through 9, "0" (zero) for the 10th of the month, and "A - U" for days 11 through 31. |
| serverTimestamp | <code>String</code> | false | true | The time the message was generated on the server. |
| mode | <code>String</code> | true | true | An indicator representing if the quote is real-time ("R"), delayed ("I") or end-of-day ("D") if available. |
| lastPrice | <code>Number</code> | true | false | The last price the instrument traded. |
| tradeTimestamp | <code>String</code> | true | false | The exchange timestamp for the last traded price. |
| netChange | <code>Number</code> | true | false | The difference between the last traded price and the previous close. |
| percentChange | <code>Number</code> | true | true | The percent difference between the last traded price and the previous close. |
| unitCode | <code>String</code> | true | false | The corresponding unit code. |
| open | <code>Number</code> | true | false | The opening (first) price for the session. |
| high | <code>Number</code> | true | false | The highest traded price for the session. |
| low | <code>Number</code> | true | false | The lowest traded price for the session. |
| close | <code>Number</code> | true | true | The last traded price for the session. |
| numTrades | <code>Number</code>| true | false | The number of individual transactions over the course of a trading session. |
| dollarVolume | <code>Number</code>| true | true | The current Dollar Volume. |
| flag | <code>String</code> | true | false | If present, can be one of the following: "c" meaning that the market is closed for this instrument. "p" meaning that the market is in a pre-open state. This occurs when there are bids and offers being placed, but no trade has occurred yet. This is normally seen shortly before the official opening time for busy markets, but can also be seen throughout the day for lightly traded markets. "s" meaning that the instrument has settled, and that this is the final, settlement price. |
| volume | <code>Number</code> | true | false | The quantity of shares or contracts traded. |
| previousVolume | <code>Number</code>| true | false |The quantity of shares or contracts traded from the previous day. |

**Example**:

```json
{
  "results": [
      {
        "symbol": "ZCBJ21-5827-5398.CM",
        "name": "Cargill US; Beardstown, IL; Corn (#2 Yellow) Apr 21 Basis",
        "dayCode": "D",
        "serverTimestamp": "2021-04-15T15:49:20-05:00",
        "mode": "i",
        "lastPrice": 20,
        "tradeTimestamp": "2021-04-14T16:16:06-05:00",
        "netChange": 0,
        "percentChange": 0,
        "unitCode": "4",
        "open": 19,
        "high": 20,
        "low": 18,
        "close": null,
        "numTrades": 0,
        "dollarVolume": null,
        "flag": "s",
        "volume": 0,
        "previousVolume": null
      }
  ]
}
```

* * *

### getHistoryResponse :id=schemasgethistoryresponse
**Type**: <code>Object</code>
    
| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| symbol| <code>String</code> | true | false | A symbol or code that identifies a financial instrument. |
| timestamp | <code>String</code> | true | false | The exchange time of the price. Format: HH:MM:SS.FFF. |
| tradingDay | <code>String</code> | true | false |  The date of the trade. Format: YYYY-MM-DD.|
| open | <code>String</code> | true | true | The opening (first) price for the period. |
| high | <code>String</code> | true | true | The highest traded price for the period. |
| low | <code>String</code> | true | false | The lowest traded price for the period. |
| close | <code>String</code> | true | false | The last traded price for the period. |
| volume | <code>String</code> | true | false | The quantity of shares or contracts traded per the period. |
| openInterest | <code>String</code> | true | true | The total number of options and/or futures contracts that have not been offset. |

**Example**:

```json
{
  "results": [
      {
        "symbol": "ZCBJ21-5827-5398.CM",
        "timestamp": "2020-08-26T00:00:00-04:00",
        "tradingDay": "2020-08-26",
        "open": 4,
        "high": 4,
        "low": 4,
        "close": 4,
        "volume": 0,
        "openInterest": null
          },...,
      ]
}
```

* * *