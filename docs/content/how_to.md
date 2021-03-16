# How To
In this section we provide you with practical examples of how you can interact with our data.  Should you have suggestions on what to included, please let us know.

## Get Intraday Grain Prices

You can use the getGrainBids API to request our most recent grain data.  This endpoint will provide the user with quotes based on a specified geolocation along with reference data to help you persist the correct information through to your application.

Grain bid data can be requested for:
* Grain buying locations
* Geographic coordinates and radius
* Zip code and radius 
* A specified county

Looking for something more specific?  Grain bid data can be filtered by commodity name, delivery window, the number of locations that will be returned, and by the maximum number of bids per commodity for each location.

Reference data contains grain buying locations and commodity standard names, which provides valid values in use for requesting cash bid data.

Reference data can be requested for geographic coordinates and radius. If no geographic coordinates are given, reference data will return all valid values by default.

## Get Historical Price Data

### Find Symbols Using getGrainInstrument API:

 https://ondemand.websol.barchart.com/getGrainInstruments.json?apikey=YOUR_API_KEY&instrumentType=bidBasis&instrumentRoot=ZC&stateFipsCode=39&countyFipsCode=069&deliveryMonth=201812

This query returns
```
"status": {
"code": 200,
"message": "Success."
},
"results": [
{
"symbol": "ZCBZ18-26147-8422.CM",
"symbolDescription": "POET Biorefining; Marion, OH; Corn (#2 Yellow) Dec 18",
...,
},
...,]
```
### Request Historical Data by Symbol:

https://ondemand.websol.barchart.com/getHistory.json?apikey=YOUR_API_KEY&symbol=ZCBZ18-26147-8422.CM&type=daily&startDate=20000101
```
{
"status": {
"code": 200,
"message": "Success."
},
"results": [
{
"symbol": "ZCBZ18-26147-8422.CM",
"timestamp": "2017-12-05T00:00:00-05:00",
"tradingDay": "2017-12-05",
"open": -10,
"high": -10,
"low": -10,
"close": -10,
"volume": 0,
"openInterest": null
},
...,
]}
```

## Get a List of Active Locations

An active location is defined as a grain buying facility that has at least one active grain bid.

You can pull all active locations by using the getGrainBids API with input parameter “requestType=locations”:

http://ondemand.websol.barchart.com/getGrainBids.json?apikey=[YOUR_API_KEY]&requestType=locations

## Get a List of Commodity Names

You can pull all supported commodity names by using getGrainBids API with input parameter “requestType=commodities”:

http://ondemand.websol.barchart.com/getGrainBids.json?apikey=[YOUR_API_KEY]&requestType=commodities

## Get Prices For a Apecified Area
An area can be defined by geographic coordinates and radius, by zip code and radius, by county fips code, and by county name.

Get all bids for an area defined by lat&lng and maxDistance:

http://ondemand.websol.barchart.com/getGrainBids.json?apikey=YOUR_API_KEY&getAllBids=1&latitude=41.00189&longitude=-83.325035&maxDistance=20

Get all bids for up to closet 50 locations within an area defined by zipCode and maxDistance:

http://ondemand.websol.barchart.com/getGrainBids.json?apikey= YOUR_API_KEY&getAllBids=1&zipCode=43351&maxDistance=50&totalLocations=50

Get all bids for a county by fips code:

http://ondemand.websol.barchart.com/getGrainBids.json?apikey=YOUR_API_KEY&getAllBids=1&fipsCode=17053

Get all bids for a county by county name:

http://ondemand.websol.barchart.com/getGrainBids.json?apikey=YOUR_API_KEY&getAllBids=1&county=Boone%20COUNTY-IA

## Get Price for Specific Crops
You can filter the grain bids by crop via adding input “commodityName=[commodity_name]“. Heads up, commodity_name needs to be encoded.

Get all Corn(#2 yellow) bids for up to closet 50 locations within an area defined by zipCode and maxDistance:

http://ondemand.websol.barchart.com/getGrainBids.json?apikey= YOUR_API_KEY&getAllBids=1&zipCode=43351&maxDistance=50&totalLocations=50&commodityName=Corn%20%28%232%20Yellow%29


## Get Prices for Specific Location(s)
Get all bids for specified locationIds:

http://ondemand.websol.barchart.com/getGrainBids.json?apikey=YOUR_API_KEY&getAllBids=1&location=51,402,10250



