## Short Description

The North America Grain Prices dataset features grain bids data from over 4,000 grain buying facilities across North America. Each grain bid incorporates two key types of data:  the first is price data, which covers basis and cash price created on price events with deep history available. Grain bids also include rich metadata, covering geo-location, facility type, fips codes, and more.


## What's Included?

|Dataset                 | Source                            | Data Coverage    | Frequency | EOD History   | Tick History |Format |
| :---------------------: | :----------: | :----------: | :-----------: |:-----------: |:-----------: |:-----------:
| North America Grain Prices|Barchart| Grain Bids from 4,000+ North America Elevators  |Realtime| 2008-10-02  | 2018-05-14  | csv, json, xml |


## Roadmap

By the end of 2020, we’ll have increased our location coverage from 4,000 to 4,200. Just another reason to be looking forward to closing out this year!

Data around the grain buying facilities is managed independently. We also track the facility history, including what company owns the facility and how long the company has had ownership. 

* Example: If a grain buying facility (with a location ID of ‘A’) was sold to a new company, the original location ID A would be marked as inactive. A new location ID (‘B’) would be created to represent the facility after the transfer of ownership to the new company. Cash bids would be stored under the new location ID B.
* Once new logic is implemented on our end of things, we will instead continue to use the first location ID A for the facility after the transfer of ownership. Cash bids will continue to be stored under location ID A. 


## Support and Feature Request

Something not right? Need assistance? Don’t hesitate to submit a ticket to our support desk at https://help.barchart.com/support/tickets/new. We’ll get the issue sorted out ASAP. 


## Terms

* Interested in a trial? [Let us know](https://www.barchart.com/cmdty/contact) and we’ll get you started. 
* Just a heads up, data is for internal use only. Redistribution is expressly prohibited. 
* For more information, contact Barchart directly at cashdata@barchart.com. We’d be happy to answer any questions you may have. 


