# API Reference

## cmdty North America Grain Price API 1.0.0 {docsify-ignore}
    
> Access best-in-class intraday and historical cash grain prices for North America using Barchart&#x27;s REST-ful web service

## OpenAPI Definition {docsify-ignore}

[Download](static/openapi.yaml)

## Contents {docsify-ignore}

* [Servers](#Servers)
* [Components](#Components)
* [Paths](#Paths)


## Servers {docsify-ignore}

* [http://ondemand.websol.barchart.com/](http://ondemand.websol.barchart.com/)  - Production

## Components {docsify-ignore}

### Responses 

* [Success](/content/api/components?id=responsesSuccess)
* [Unauthorized](/content/api/components?id=responsesUnauthorized)
* [BadRequest](/content/api/components?id=responsesBadRequest)
* [ServerError](/content/api/components?id=responsesServerError)

### Schemas 

* [GetGrainBidsResponse](/content/api/components?id=schemasGetGrainBidsResponse)
* [GrainBidsByLocation](/content/api/components?id=schemasGrainBidsByLocation)
* [GrainBid](/content/api/components?id=schemasGrainBid)
* [getGrainInstrumentsResponse](/content/api/components?id=schemasgetGrainInstrumentsResponse)
* [getQuoteResponse](/content/api/components?id=schemasgetQuoteResponse)
* [getHistoryResponse](/content/api/components?id=schemasgetHistoryResponse)

### Security 

* [JWT](/content/api/components?id=securityJWT)

## Paths {docsify-ignore}

* [GET /getGrainBids](/content/api/paths?id=get-getGrainBids)
* [GET /getGrainInstruments](/content/api/paths?id=get-getGrainInstruments)
* [GET /getQuote](/content/api/paths?id=get-getQuote)
* [GET /getHistory](/content/api/paths?id=get-getHistory)
