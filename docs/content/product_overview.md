## Short Description

North America Grain Prices dataset includes grain bids data from 4,000+ grain buying facilities across North America. Each grain bid has both price data, covering basis and cash price created on price events with deep history available, and rich metadata, covering geo-location, facility type, fips codes, and more.


## What's Included?

|Dataset                 | Source                            | Data Coverage    | Frequency | EOD History   | Tick History |Format |
| :---------------------: | :----------: | :----------: | :-----------: |:-----------: |:-----------: |:-----------:
| North America Grain Prices|Barchart| Grain Bids from 4,000+ North America Elevators  |Realtime| 2008-10-02  | 2018-05-14  | csv, json, xml |


## Roadmap
The location coverage will increase to 4200 by the end of 2020.

The grain buying facilities data will be managed independently, and the history of the facility(what company owns the facility since when) will be tracked.

For example, if a grain buying facility, whose location id was A, was sold to company Y from X, we currently mark A as inactive, then create a new location id B to represent the same facility after the transaction, and store cash bids under location id B.  However, once we implement the new logic, we will keep use location id A for this facility after the transaction, and store its cash bids.)

## Support and Feature Request
Please submit a ticket at our support desk - https://help.barchart.com/support/tickets/new

## Terms

* [Trials are available](https://www.barchart.com/cmdty/contact)
* Data is for internal use only, and redistribution is expressly forbidden
* Contact Barchart directly at cashdata@barchart.com for more information.
* Hi THis is the test


