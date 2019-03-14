# deex.statistics.api
Deex.exchange statistics API
============================

How to use
----------

The service root URL:

[https://stat-api.deex.exchange:2087](https://stat-api.deex.exchange:2087)

There are three requests you could use to get the information:
--------------------------------------------------------------

-   ### Get all deex assets

    **Request: /get\_all\_assets/** \
    **Response:** JSON list of assets \
    [„Asset1“, „Asset2“…] \
    **Example:** \
    https://stat-api.deex.exchange:2087/get_all_assets/ \
    **Error:** If there is an error, the system responds with a 404 error code.

-   ### Get all markets for asset

    **Request: /get\_markets/\<name\>/** \
    **Attributes:** \
    ◦ **\<name\>** - the asset name \
    **Response:** JSON list of the asset’s markets \
    [{ \
      „market“ : „Asset1/Asset2“, \
      „last\_price“: 11111 \
     }] \
    **Example:** \
    https://stat-api.deex.exchange:2087/get_markets/DEEX/ \
    **Error:** If there is an error, the system responds with a 404 error code.

-   ### Get detailed information about market

    **Request: /get\_market\_data/\<base\_asset\>/\<quote\_asset\>/** \
    **Attributes:** \
    ◦ **\<base\_asset\>** - the base asset name \
    ◦ **\<quote\_asset\>** - the quote asset name \
    **Response:** JSON with 24hs volume and ticker data. \
    **Example:** \
    https://stat-api.deex.exchange:2087/get_market_data/BTS/DEEX/ \
    { \
	"ticker": { \
	"time": "2019-03-05T21:51:06", \
	"base": "BTS", \
	"base_volume": "57730.842600", \
	"latest": "0.340000", \
	"lowest_ask": "0.365989", \
	"max_24h_sale": "0.386000", \
	"quote": "DEEX", \
	"highest_bid": "0.330000", \
	"quote_volume": "158823.525900", \
	"min_24h_buy": "0.366000" \
	} \
	}, where:

-   base — the base asset;
-   base\_volume — 24hs volume of the base asset on this market;
-   quote — the quote asset;
-   quote\_volume — 24hs volume of the quote asset on this market;
-   time — time when this volume was fixed;
-   highest\_bid — the highest price a buyer of an asset is willing to pay for that asset;
-   latest — latest price of filled order;
-   lowest\_ask — the lowest price a seller of an asset is willing to accept for that asset;
-   max_24h_sale — 24H maximum sale price;
-   min_24h_buy — 24H minimum buy price.

**Error:** If there is an error, the system responds with a 404 error code.

-   ### Get all markets

    **Request: /get\_all\_markets/** \
    **Response:** JSON list of markets \
    [„last_price“:, „market“:…] \
    **Example:** \
    https://stat-api.deex.exchange:2087/get_all_markets/ \
    **Error:** If there is an error, the system responds with a 404 error code.
