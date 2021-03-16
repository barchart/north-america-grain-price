# Overview

## Description

Our North American Grain Price dataset represents the benchmark offering for inland grain prices throughout North America.  On average we provide users of this dataset with live grain bids from over 4,000 grain buying facilities across North America. 

Each "grain bid" relates to two key types of data:  
* Price Data - This covers basis and the corresponding cash price.  Records are created pricing events such as a grain facility updating their basis or flat price.  Historical data is available starting in 2008. 
* Metadata - This relates to information that describes either the facility or the bids are related to a given facility.  Typically this will cover geo-location, facility type, fips codes (area definitions), and commodity descriptions.


## What's Included?

|Dataset                 | Source                            | Data Coverage    | Frequency | EOD History   | Tick History |Format |
| :---------------------: | :----------: | :----------: | :-----------: |:-----------: |:-----------: |:-----------:
| North America Grain Prices|Barchart| Grain Bids from 4,000+ North America Elevators  |Realtime| 2008-10-02  | 2018-05-14  | csv, json, xml |


## Product Roadmap
Here are some features that we're working on.  If you would like to submit a feature request, please reach out to cmdty@barchart.com.

Coverage - We are currently in the process of broadening our coverage even further with the stated goal of 4,150 locations on average per day throuhgout 2021.

Location Continuity - Data around grain buying facilities is managed independently and includes information such as  what company owns the facility and how long the company has had ownership. As currently implemented, (example) if a grain buying facility (with a location ID of ‘A’) was sold to a new company, the original location ID A would be marked as inactive. A new location ID (‘B’) would be created to represent the facility after the transfer of ownership to the new company. Cash bids would be stored under the new location ID B.  In 2021 we will continue location ID A with status of Active even after the transfer of ownership.  As a result, cash bids will continue to be stored under location ID A, and users can use facility meta data to track changes in ownership.


## Support and Feature Requests

For level one support, please email mds@barchart.com and a ticket will be automatically generated to track your request.

Feature requests can be submitted to cmdty@barchart.com.  If you are a grain facility and your location is not covered by our service, please reach out to let us know.  We can provide you with several options for getting your bids into our service.


## Getting Started

* Interested in a trial? [Let us know](https://www.barchart.com/cmdty/contact) and we’ll get you started. 
* Just a heads up, data is for internal use only. Redistribution is expressly prohibited. 
* For more information, contact us directly at cmdty@barchart.com. We’d be happy to answer any questions you may have. 


