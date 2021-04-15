# Paths

## GET /getGrainBids 

> The getGrainBids API provides cashbid data and reference data. Cashbid data can be requested for grain buying locations, for geographic coordinates and radius, for zip code and radius, and for a specified county. Cashbid data can be filtered by commodity standard name, by delivery window, by number of locations will be returned, and by maximum number of bids per commodity for each locations. Reference data contains grain buying locations and commodity standard names, providing valid values in use for requesting cash bid data.
 Reference data can be requested for geographic coordinates and radius. If no geographic coordinates are given, reference data will return all valid values by default.


**Summary**: Resturns a list of cashbids grouped by locations.

#### Query Parameters

| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| apikey | <code>String</code> | true | false | The authorized API Key |
| requestType | <code>String</code> | false | false | The type of request that is being requested in order to determine the type of data to be returned. Valid Values: "bids", "commodities", "locations". Default Value: "bids"<br> |
| location | <code>Array</code> | false | false | A location id or a code identifies a or multiple grain buying location(s) that cash bid will be returned for. A valid code consist of multiple location ids separated by a comma, and the code can contain up to 100 locations. A list of valid location ids can be retrieved by using this API with input: requestType = location. location and several other inputs -geographic coordinates, zipCode, maxDistance, county, totalLocations- are mutually exclusive.<br> |
| latitude | <code>Number</code> | false | false | The latitude of a valid geographic coordinates to define the center of area that cashbid will be returned for. The `latitude` Must be used together with `longitude`. Geographic coordinates and Zipcode are mutually exclusive.<br> |
| longitude | <code>Number</code> | false | false | The longitude of a valid geographic coordinates to define the center of area that cashbid will be returned for. Geographic coordinates and Zipcode are mutually exclusive.<br> |
| zipCode | <code>Integer</code> | false | false | A valid US or Canadian zip code to define the area that cash bids orginate from. Default Value: 60606 `zipCode` and Geographic coordinates  are mutually exclusive.<br> |
| maxDistance | <code>Integer</code> | false | false | The maximum distance from searched zipcode or the requested geo coordinates in miles. This input helps to define the area that cash bids will be returned from. Default value is 100. Maximum value is 250.<br> |
| county | <code>String</code> | false | false | A valid string code which represents the concatenation of county name and state code seperated by a hyphen.<br> |
| fipsCode | <code>Integer</code> | false | false | A concatenation of state FIPS code and county FIPS code without separator to define the county that cash bids will be returned for. A list of possible values can be found at (here)[https://www.nass.usda.gov/Data_and_Statistics/County_Data_Files/Frequently_Asked_Questions/county_list.txt].<br> |
| commodityName | <code>String</code> | false | false | A standard commodity name or a name list that separated by pipe "|" to filter cashbid. Note that the input need to be encoded in UTF-8. A list of valid commodity names can be retrieved by using this API with input: requestType = commodities.<br> |
| deliveryStart | <code>String</code> | false | false | The start date for the delivery period for qualified bids, formatted in YYYYMMDD. If this parameter is given, only cash bids whose start delivery date not prior than given deliveryStart will be returned.<br> |
| deliveryEnd | <code>String</code> | false | false | The end date for the delivery period for qualified bids, formatted in YYYYMMDD. If this parameter is given, only cash bids whose end delivery date no later than given deliveryEnd will be returned.<br> |
| totalLocations | <code>Integer</code> | false | false | The maximum number of locations to be returned based of the zip code provided by the user. Default value is 30.<br> |
| getAllBids | <code>Boolean</code> | false | false | Return all cash bids for each location. Default Value: false<br> |
| bidsPerCom | <code>Integer</code> | false | false | The maximum number of cash bids to be returned for each commodity per location. This parameter should be set to the maximum number of cash bids the user wishes to be returned. Default Value: 2<br> |
| numOfDecimals | <code>Integer</code> | false | false | The level of precision in decimal places of price and basis to be returned. Default Value: 2<br> |
| fields | <code>String</code> | false | false | Additional as per-requested fields that the user can define. Requested fields should be separated by a comma. Valid Values: "county_code", "fips_code", "elevatorId", and "crop_district"<br> |

#### Responses

**Status Code**: 200

> OK

**Content Type**: <code>application/json</code>

**Response Type:** [<code>Array&lt;GetGrainBidsResponse&gt;</code>](/content/api/components?id=schemasGetGrainBidsResponse)

* * *

**Status Code**: 400

> Bad Request

* * *

**Status Code**: 500

> Internal Server Error

* * *

## GET /getGrainInstruments 

> The getGrainInstruments API is used to request symbol and metadata information regarding physical grain instruments across Barchart's cash bids and grain indexes. Users can request information based on crop type / root symbol, geo-location, or areas that are codified by FIPS standards. Returned instruments and their corresponding symbols can be passed to getQuote or getHistory to retrieve the associated price data - as requested by the end user. Find our more about our commodity data offerings here.

**Summary**: Look-up symbols for cash bids or grain indexes.

#### Path Parameters

| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| apikey | <code>String</code> | true | false | The authorized API Key. |
| instrumentType | <code>String</code> | true | false | The type of grain instruments. This parameter should be set to the desired instrument type for the query. |
| instrumentRoot | <code>String</code> | true | false | A 2-char indicator for commodities. This parameter should be set to the root that represents the desired commodity for the query. Roots that are denoted as "all" are valid for both bid and index data - if "bids" then there is no index associated with that root.ZC: All kinds of Corn and Milo/Sorghum (all), ZS: All kinds of Soybeans (all), ZW: All kinds of Soft Red Winter Wheat (all), MW: All kinds of Spring Wheat (all), KE: All kinds of Hard Red Winter Wheat (all), FW: All kinds of Feed Wheat (bids), DW: All kinds of Durum Wheat (bids), CW: Wheat (Club) (bids), ZM: Soybean Meal (bids), HS: Soybeans (Hulls) (bids), ZO: Oats (bids), BB: Barley (bids), ZR: Rice (bids), ZK: Ethanol (E85) (bids), GP: Peas (Green) (bids), YP: Peas (Yellow) (bids), SF: Birdseed or Sunflowers (bids), RY: Rye (bids), RS: Canola (bids), PC: Pulse Crops (Peas, Dry Beans, Lentils & Chickpeas) (bids), PB: Beans (Pinto) (bids), LB: Beans (Lentil) (bids), GB: Beans (Garbonzo) (bids), MI: Millet (bids), MD: Distiller Grains (MWDGS) (bids), DG: Distiller Grains (DDGS) (bids), FL: Flax (bids), CS: Cottonseed (bids) |
| zipCode | <code>String</code> | true | false | A valid zip code to refine the area that cash bids orgin from. This parameter is required if stateFipsCode has not been set. This is the only way to query Canada grain bids.|
| stateFipsCode | <code>String</code> | true | false |A valid 2-digit state code used to define the area that the underlying grain data (bids or indexes) will be returned from. This parameter is required if zipCode and indexGroup have not been set. Note that calls using this field will return instruments for counties and districts that are associated with the requested stateFipsCode - in addition any instruments with an area equal to the user specified stateFipsCode. Please click [here](https://www.nass.usda.gov/Data_and_Statistics/County_Data_Files/Frequently_Asked_Questions/county_list.txt) to get a list of possible values. |
| districtCode | <code>String</code> | true | false | A valid 2-digit district code used to define the area that the underlying grain data (bids or indexes) will be returned from. Note that calls using this field will return instruments for counties that are associated with the requested districtCode - in addition any instruments with an area equal to the user specified districtCode. Please click [here](https://www.nass.usda.gov/Data_and_Statistics/County_Data_Files/Frequently_Asked_Questions/county_list.txt) to get a list of possible values. |
| countyFipsCode | <code>String</code> | true | false | A valid 3-digit county code use to define the the area that the underlying grain data (bids or indexes) will be returned from. Please click [here](https://www.nass.usda.gov/Data_and_Statistics/County_Data_Files/Frequently_Asked_Questions/county_list.txt) to get a list of possible values. |
| deliveryMonth | <code>String</code> | true | false | The last month in the delivery window for cash bids or indexes using the following format: "YYYYMM"(i.e. 202104). For example, a bid with a delivery window of 202112 through 202203 can only be retrieved by input of 202203.For instrumentType = 'IndexBasis' or 'IndexCash', this parameter accepts rolling month codes: 'A' - 'L', which represent the forward delivery month from front month (A) to the 11th (L) forward month|
| indexGroup | <code>String</code> | true | false | A valid index aggregate level that returns all index instruments belonging to a specific indexGroup.Combining indexGroup and country or region are the only way to query national indexes and regional indexes.This parameter may required if stateFipsCode has not been set. |
| country | <code>String</code> | true | false | The short country name to further refine the index instruments.|
| region | <code>String</code> | true | false | A short region name to further refine the index instruments. |
| maxRecords | <code>String</code> | true | false | The maximum amount of records returned. This parameter should be set to the maximum number of records desired. Default value is 200 |
| page | <code>String</code> | true | false | The value to set for pagination. |
| locationId | <code>String</code> | true | false | The locationId for which all cash bid symbol should be returned.|


#### Responses

**Status Code**: 200

> A JSON document, conforming to the alert schema, representing requested alert.

**Content Type**: <code>application/json</code>

**Response Type:** [<code>Array&lt;GetGrainInstrumentsResponse&gt;</code>](/content/api/components?id=schemasgetgraininstrumentsresponse)

* * *

**Status Code**: 404

> The alert does not exist.

**Content Type**: <code>application/json</code>

**Response Type:** <code>Object</code>
    
| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| message | <code>String</code> | false | false |  |

**Example**:

```json
{
  "message": "no data"
}
```

* * *

## GET /getQuote 

> The getQuote API is used to request price data by symbol on stocks, indexes, mutual funds, ETFs, futures, foreign exchange, cryptocurrencies, or commodity cash data.

**Summary**: Retrieve latest cash bid(s) by symbol(s).

#### Query Parameters

| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| apikey | <code>String</code> | true | false | The authorized API Key. |
| symbols | <code>String</code> | true | false | A symbol or code that identifies a financial instrument. Multiple symbols separated by a comma may be used. For futures, notation such as for the active contract or for the first nearby is supported, as is for all futures contracts for a given root symbol, as is for all options contracts for a given underlying futures symbol. |
| fields | <code>String</code> | false | true | The fields requested. Valid fields can be found in [getQuoteResponse](/content/api/components?id=schemasgetquoteresponse.|
| only | <code>String</code> | false | true | Returns only specified fields, i.e. symbol,name. |


#### Responses

**Status Code**: 200

> A JSON document, containing an array of quote objects.

**Content Type**: <code>application/json</code>

**Response Type:** [<code>Array&lt;GetQuoteResponse&gt;</code>](/content/api/components?id=schemasgetquoteresponse)

* * *

**Status Code**: 500

> A JSON document, containing an error.

**Content Type**: <code>application/json</code>

**Response Type:** <code>Object</code>

| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| message | <code>String</code> | false | false |  |

**Example**:

```json
{
  "message": "Internal Server Error"
}
```


* * *

## GET /getHistory 

> The getHistory API is used to request historical time series data on stocks, indexes, mutual funds, ETFs, futures, foreign exchange, cryptocurrencies, or cash commodity data. Historical data is available as tick, minute bars or end-of-day data.

**Summary**: Retrieve cash bid history.

#### Path Parameters

| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| apikey | <code>String</code> | true | false | The authorized API Key |
| symbol | <code>String</code> | true | false | A symbol or code that identifies a financial instrument.|
| type | <code>String</code> | false | true | The type of historical data to return, including tick data, minute data, and end-of-day data.|
| startDate | <code>String</code> | false | true | The start date of the historical data query. This parameter should be set to the desired start date/time for the query (the result set will include records back to, and including, this value). If not set, the value will default to the beginning of the day specified in the end parameter, if end is specified, or to the beginning of the current day, if end is not specified. The value should conform to the format yyyymmdd[hhmm[ss]], where fields in brackets are optional (Do not include the brackets themselves). Any optional fields that are not explicitly set will default to 0 (i.e. 20090203 will default to 20090203000000).|
| endDate | <code>String</code> | false | true | The end data of the historical data query. This parameter should be set to the desired end date/time for the query (the result set will include records up to, but not including, this value). If not set, the value will default to the end of the day specified in the start parameter, if specified, or to the end of the current day, if start is not specified. The value should conform to the format yyyymmdd[hhmm[ss]], where fields in brackets are optional (Do not include the brackets themselves). Any optional fields that are not explicitly set will default to 0 (i.e. 20090203 will default to 20090203000000). |
| maxRecords | <code>String</code> | false | true | The maximum amount of records returned. This parameter should be set to the maximum number of records desired. If not specified, there number of records returned will be determined by the date/time parameters specified as well as any defaults that apply to the query. |
| order | <code>String</code> | false | true | An arrangement of fields within a particular record (ascending or descending). This parameter can be set to one of two values ("asc" and "desc") in order to specify the chronological order of the result set returned. If this parameter is not specified, the order results is not guaranteed. |


#### Responses

**Status Code**: 200

> A JSON document, containing an array of alert objects.

**Content Type**: <code>application/json</code>

**Response Type:** [<code>Array&lt;GetHistoryResponse&gt;</code>](/content/api/components?id=schemasgethistoryresponse)

* * *

**Status Code**: 500

> A JSON document, containing an error.

**Content Type**: <code>application/json</code>

**Response Type:** <code>Object</code>
    
| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| message | <code>String</code> | false | false |  |

**Example**:

```json
{
  "message": "Internal Server Error"
}
```

* * *

