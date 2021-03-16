# FAQs

Here are the questions we're asked most often by our users.  If you have an idea for something we should add to this section, let us know by sending an email to cmdty@barchart.com

## General Information / Data Sourcing

#### What is a cash price? What is basis?

Cash price is the price grain buyers desire to pay for grain. The getGrainBids API returnes values with units of "dollar per bushel".

Basis is the difference between the cash price grain buyers desire to pay for grain and the futures price of an associated futures contract. Its unit is “cents per bushel” in the getGrainBids API.

Cash Price = Basis + Futures Price

#### What does your coverage look like?

We currently cover approximately 4,000 locations across North America. By the end of 2021, we will increase our coverage to 4,150 locations on average.  

#### How far back does historical information data go?

Historical data starts from 2008.  The number of locations that are covered by the datset increases over time from inception to present as we have scaled up the service dramatically

#### What are your data sources?

60% of grain bids come from our web-hosting service, where we directly manage grain bids in our system.

35% of grain bids come through web-collection which is often requested by the sites themselves

Approximately 5% grain bids come from our partner firms' APIs. They provide us with direct access to their APIs in order to integrate their data into our ecosystem.


## Data Updates / Calculations

#### How many times does Barchart update the same bid per day?

Managed grain bids are updated on real-time. Whenever elevators update grain bids, our grain bids will reflect that.

Web-scrapped bids are updated 4 times per day at 9AM, 12PM, 3PM, and 6PM Central Time.

Partner firms' bids are updated hourly.

#### How does Barchart calculate intraday cash values?

All intra-day cash values are calculated on the fly based on the most recent futures price and basis whenever the server receives requests.

#### How does Barchart calculate EOD cash values?

All EOD cash values are calculated based on the futures settlement price and the basis at 4PM CT.

#### Should every basis value have a corresponding cash value?

Yes. Each basis value should have a corresponding cash value.

#### Should every cash value have a corresponding basis value?

No, not every cash value has a corresponding basis value. Some grain bids are only quoted in cash prices-- this mostly happens for crops that do not have corresponding futures contracts, like ‘Flaxseed’,’ “chick peas”, ..., etc.




