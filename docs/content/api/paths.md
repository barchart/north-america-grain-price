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

> Retrieves an existing alert.

**Summary**: Retrieve Alert.

**Security**: 
[JWT](/content/api/components?id=securityJWT)
#### Path Parameters

| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| alert_id | <code>String</code> | true | false | The UUID for the alert. |

#### Responses

**Status Code**: 200

> A JSON document, conforming to the alert schema, representing requested alert.

**Content Type**: <code>application/json</code>

**Response Type:** [<code>Array&lt;GetGrainBidsResponse&gt;</code>](/content/api/components?id=schemasGetGrainBidsResponse)

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

> Retrieves all alerts for a single user.

**Summary**: Retrieve Alerts For User.

**Security**: 
[JWT](/content/api/components?id=securityJWT)
#### Path Parameters

| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| user_id | <code>String</code> | true | false | The unique identifier of the user (in the :alert_system) |
| alert_system | <code>String</code> | true | false | The name of the user's system (e.g. "barchart.com" or "grains.com") |

#### Responses

**Status Code**: 200

> A JSON document, containing an array of alert objects.

**Content Type**: <code>application/json</code>

**Response Type:** [<code>Array&lt;GetGrainBidsResponse&gt;</code>](/content/api/components?id=schemasGetGrainBidsResponse)

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
  "message": "string"
}
```

* * *

## GET /getHistory 

> Retrieves all alerts, for a single user, which have a specific &quot;alert_system_key&quot; property value.

**Summary**: Retrieve Alerts By Remote System Key

**Security**: 
[JWT](/content/api/components?id=securityJWT)
#### Path Parameters

| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| user_id | <code>String</code> | true | false | The unique identifier of the user (in the :alert_system) |
| alert_system | <code>String</code> | true | false | The name of the user's system (e.g. "barchart.com" or "grains.com") |
| alert_system_key | <code>String</code> | true | false | The key (specified by the remote system at creation) to match |

#### Responses

**Status Code**: 200

> A JSON document, containing an array of alert objects.

**Content Type**: <code>application/json</code>

**Response Type:** [<code>Array&lt;GetGrainBidsResponse&gt;</code>](/content/api/components?id=schemasGetGrainBidsResponse)

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
  "message": "string"
}
```

* * *

