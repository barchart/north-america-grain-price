## Get intra-day grain bids quotes

You can use getGrainBids API to request the most recent grain bid data.  The getGrainBids API provides grain bid data and reference data.

Grain bid data can be requested for:
* Grain buying locations
* Geographic coordinates and radius
* Zip code and radius 
* A specified county

Looking for something more specific? Grain bid data can be filtered by commodity name, delivery window, the number of locations that will be returned, and by the maximum number of bids per commodity for each location.

Reference data contains grain buying locations and commodity standard names, which provides valid values in use for requesting cash bid data.

Reference data can be requested for geographic coordinates and radius. If no geographic coordinates are given, reference data will return all valid values by default.

See examples in below answers.



## Get a list of active locations

An active location is defined as a grain buying facility that has at least one active grain bid.

You can pull all active locations by using the getGrainBids API with input parameter “requestType=locations”:

http://ondemand.websol.barchart.com/getGrainBids.json?apikey=[YOUR_API_KEY]&requestType=locations

## Get a list of commodity names

You can pull all supported commodity names by using getGrainBids API with input parameter “requestType=commodities”:

http://ondemand.websol.barchart.com/getGrainBids.json?apikey=[YOUR_API_KEY]&requestType=commodities

## Get grain bids for the specified area
An area can be defined by geographic coordinates and radius, by zip code and radius, by county fips code, and by county name.

Get all bids for an area defined by lat&lng and maxDistance:

http://ondemand.websol.barchart.com/getGrainBids.json?apikey=YOUR_API_KEY&getAllBids=1&latitude=41.00189&longitude=-83.325035&maxDistance=20

Get all bids for up to closet 50 locations within an area defined by zipCode and maxDistance:

http://ondemand.websol.barchart.com/getGrainBids.json?apikey= YOUR_API_KEY&getAllBids=1&zipCode=43351&maxDistance=50&totalLocations=50

Get all bids for a county by fips code:

http://ondemand.websol.barchart.com/getGrainBids.json?apikey=YOUR_API_KEY&getAllBids=1&fipsCode=17053

Get all bids for a county by county name:

http://ondemand.websol.barchart.com/getGrainBids.json?apikey=YOUR_API_KEY&getAllBids=1&county=Boone%20COUNTY-IA

## Get grain bids for specified crops
You can filter the grain bids by crop via adding input “commodityName=[commodity_name]“. Heads up, commodity_name needs to be encoded.

Get all Corn(#2 yellow) bids for up to closet 50 locations within an area defined by zipCode and maxDistance:

http://ondemand.websol.barchart.com/getGrainBids.json?apikey= YOUR_API_KEY&getAllBids=1&zipCode=43351&maxDistance=50&totalLocations=50&commodityName=Corn%20%28%232%20Yellow%29


## Get grain bids from specified location(s)
Get all bids for specified locationIds:

http://ondemand.websol.barchart.com/getGrainBids.json?apikey=YOUR_API_KEY&getAllBids=1&location=51,402,10250
