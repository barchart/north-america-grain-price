## Get historical grain bid data

### 01 Get the grain bids' symbols using getGrainInstrument API:

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
### 02 Request the history data using getHistory API by symbol:

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


