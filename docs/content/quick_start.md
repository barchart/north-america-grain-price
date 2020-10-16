## 01 Get an API key

GO to [cmdty website](https://www.barchart.com/cmdty/data/grain-prices) and fill out the `Get Started` form.
Barchart team will set-up an API Key for you.

## 02 Make your first query

Let's retrieve all grain bids from all elevators in your zip code area:
* Open any browser you have
* Put your API key and Zip Code into the url template -  http://ondemand.websol.barchart.com/getGrainBids.json?apikey={YOUR_API_KEY}&getAllBids=1&zipCode={YOUR_ZIP_CODE} -, then copy it
* Past the url into the browser, and hit enter
* Voila! Should qualified grain bids return to your browser, similar to below:
```
"status": {
    "code": 200,
    "message": "Success."
    },
"results": [
    {"bids": [
        {"id": "39550822",
         "commodity": "CORN",
         "symbol": "ZCZ20",
         "delivery_start": "2020-10-01 00:00:00",
         "delivery_end": "2020-10-31 23:59:59",
         "basis": "-22.00",
         "notes": null,
         "active": true,
         "commodity_display_name": "Corn (#2 Yellow)",
         "currency": "USD",
         "deliveryMonth": "Oct20",
         "deliveryYear": "2020",
         "basismonth": "Dec 2020",
         "timestamp": 1602820323,
         "as_of": "22:52",
         "change": "-0.005",
         "cashprice": "3.81",
         "delivery_end_raw": "2020-10-31 23:59:59",
         "basisSymbol": "ZCBV20-47011-6164.CM",
         "cashPriceSymbol": "ZCPV20-47011-6164.CM",
         ...
        },...,],
        "distance": "6 miles away",
        "company": "Landus Cooperative",
        "locationId": 47011,
        "location": "Dawson",
        "facility_type": "Country Elevator",
        "address": "212 S 1st St",
        "city": "Dawson",
        "state": "IA",
        "lng": -94.2217547,
        "lat": 41.8422732,
        "phone": "515-428-8334",
        "url": "www.landuscooperative.com",
        "zip": "50066",
        "county": "Dallas County",
        "basisTimestamp": "2020-10-15T18:04:22-05:00",
        "basisTimestampRaw": 1602803062
    }]
```

## 03 Explore more

Congrats! You've made your first query. Now, you can check detailed API documentation at API Reference Section, and explore more advanced methods to query grain prices data in API Examples Section