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
    https://stat-api.deex.exchange:2087/get_market_data/DEEX/BTS/ \
    { \
      "ticker": { \
        "base": "DEEX", \
        "base\_volume": "71385.4675", \
        "highest\_bid": "2.2278165503489533", \
        "latest": "2.2753128555176336", \
        "lowest\_ask": "2.2753128555176336", \
        "quote": "BTS", \
        "quote\_volume": "31709.22701", \
        "time": "2018-09-20T13:59:47" \
      } \
    }, where:

-   base — the base asset;
-   base\_volume — 24hs volume of the base asset on this market;
-   quote — the quote asset;
-   quote\_volume — 24hs volume of the quote asset on this market;
-   time — time when this volume was fixed;
-   highest\_bid — the highest price a buyer of an asset is willing to
    pay for that asset;
-   latest — latest price of filled order;
-   lowest\_ask — the lowest price a seller of an asset is willing to
    accept for that asset.

**Error:** If there is an error, the system responds with a 404 error code.
