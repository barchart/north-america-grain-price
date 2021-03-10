## Dataset Information

#### What is the cash price? What is the basis?

Cash price is the price grain buyers desire to pay for grain. The getGrainBids API returnes values with units of "dollar per bushel".

Basis is the difference between the cash price grain buyers desire to pay for grain and the futures price of an associated futures contract. Its unit is “cents per bushel” in the getGrainBids API.

Cash Price = Basis + Futures Price

#### What is the data source of grain bid data?

60% of grain bids come from our web-hosting service, where we directly manage grain bids in our system.

35% of grain bids come from web-scrapping.

And finally, 5% grain bids come from our partner firms' APIs. They provide us with direct access to their APIs in order to integrate their data into our ecosystem.

#### How many times does Barchart update the same bid per day?

Managed grain bids are updated on real-time. Whenever elevators update grain bids, our grain bids will reflect that.

Web-scrapped bids are updated 4 times per day at 9AM, 12PM, 3PM, and 6PM Central Time.

Partner firms' bids are updated hourly.

#### How does Barchart calculate intraday cash values?

All intra-day cash values are calculated on the fly based on the most recent futures price and basis whenever the server receives requests.

#### How does Barchart calculate EOD cash values?

All EOD cash values are calculated based on the futures settlement price and the basis at 4PM CT.

#### How far back does historical cash bid data go?

Our cash bid historical data dates back to 2008.

#### What is the current coverage, and roadmap?

We currently cover 4,000 locations across North America. By the end of 2021, we will increase our coverage to 4,200 locations.

#### Should every basis value have a corresponding cash value?

Yes. Each basis value should have a corresponding cash value.

#### Should every cash value have a corresponding basis value?

No, not every cash value has a corresponding basis value. Some grain bids are only quoted in cash prices-- this mostly happens for crops that do not have corresponding futures contracts, like ‘Flaxseed’,’ “chick peas”, ..., etc.




