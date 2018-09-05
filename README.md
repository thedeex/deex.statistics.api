# deex.statistics.api
Deex.exchange statistics API
============================

How to use
----------

The service root URL:

[https://stat-api.deex.exchange:2087/api/v1/markets](https://stat-api.deex.exchange:2087/api/v1/markets)

There are three requests you could use to get the information:
--------------------------------------------------------------

-   ### Get all deex assets

**Request:** /get\_all\_assets/ \
**Response:** JSON list of assets \
[„Asset1“, „Asset2“…] \
**Error:** If there is an error, the system responds with a 404 error
code.

-   ### Get all markets for asset

**Request: /get\_markets/\<name\>/** \
**Attributes:** \
**\<name\>** - the asset name \
**Response:** JSON list of the asset’s markets \
[{ \
  „market“ : „Asset1/Asset2“, \
  „last\_price“: 11111 \
 }] \
**Example:** \
/get\_markets/DEEX/ \
**Error:** If there is an error, the system responds with a 404 error
code.

-   ### Get detailed information about market

    **Request:** /get\_market\_data/// \
    **Attributes:** \
    ◦ **\<base\_asset\>** - the base asset name \
    ◦ **\<quote\_asset\>** - the quote asset name \
    **Response:** JSON with 24hs volume and ticker data. \
    **Example:** \
    /get\_market\_data/DEEX/DEEX.PRIZM/ \
    { \
      "ticker": { \
        "base": "DEEX", \
        "base\_volume": "109.0586", \
        "highest\_bid": "13.000013000013000013", \
        "latest": "13.000013000013000013", \
        "lowest\_ask": "24.999992781988628126", \
        "quote": "DEEX.PRIZM", \
        "quote\_volume": "8.0199", \
        "time": "2018-07-27T12:15:39" \
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

**Error:** If there is an error, the system responds with a 404 error
code.

