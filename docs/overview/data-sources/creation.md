---
sidebar_position: 2
---

# Creating a Data Source

This section provides instructions on creating a data source. Here, we will explore the necessary steps for generating a functional data source that can retrieve specific types of data.

[#](#writing-the-data-source) Writing the data source
-----------------------------------------------------

To run the data source correctly, it's essential to include a shebang line with `#!/usr/bin/env python3` and to print the function output. Below is an uncomplicated "Hello Odin!" example that illustrates this approach.

```python title="data-source-example.py"
#!/usr/bin/env python3 

import sys 

def main(): 
    return "Hello Odin!" 
    
if __name__ == "__main__":
    try: 
        print(main())
    except Exception as e: 
        print(str(e), file=sys.stderr) 
        sys.exit(1)
```

[#](#advanced-examples) Advanced examples
---------------------------------

To gain a deeper comprehension of the arrangement and execution of a data source, we will analyze one additional example: Osmosis prices. By examining this case, we can further illustrate the design and operation of data sources within Odin's oracle system.

### [#](#osmosis-price) Osmosis Price

To begin, we will examine a data source that retrieves the current price of one token on the Osmosis network by querying [an LCD node of Osmosis](https://lcd-osmosis.blockapsis.com/osmosis/gamm/v1beta1). The script is written in Python and this particular data source requires a list of the tokens we want to request.

```python title="osmosis-prices.py"
#!/usr/bin/env python3
import sys
import requests
from typing import List

URL = "https://lcd-osmosis.blockapsis.com/osmosis/gamm/v1beta1"

SYMBOL_MAP = {
    "OSMO": [
        {
            "pool_id": 678,
            "pool_pair": {"base": "USDC", "quote": "OSMO"},
            "base": "ibc/D189335C6E4A68B513C10AB227BF1C1D38C746766278BA3EEB4FB14124F1D858",
            "quote": "uosmo",
        }
    ],
    "ATOM": [
        {
            "pool_id": 1,
            "pool_pair": {"base": "ATOM", "quote": "OSMO"},
            "base": "ibc/27394FB092D2ECCD56123C74F36E4C1F926001CEADA9CA97EA622B25F41E5EB2",
            "quote": "uosmo",
        }
    ]
}


def get_prices(symbol: str) -> float:
    price = 1
    for pool in SYMBOL_MAP[symbol]:
        pool_id = pool["pool_id"]
        r = requests.get(
            url=f"{URL}/pools/{pool_id}/prices",
            params={"base_asset_denom": pool["base"], "quote_asset_denom": pool["quote"]},
        )
        r.raise_for_status()
        price *= float(r.json()["spot_price"]) if symbol != "OSMO" else float(r.json()["spot_price"])
    return price


def main(symbols: List[str]) -> str:
    if not all(x in SYMBOL_MAP for x in symbols):
        raise Exception("Contains Unsupported Symbols")
    return ",".join([str(round(get_prices(symbol), 8)) for symbol in symbols])


if __name__ == "__main__":
    try:
        print(main(sys.argv[1:]))
    except Exception as e:
        print(str(e), file=sys.stderr)
        sys.exit(1)
```

* ### Defining variables

In the code, the initial step is to define the `URL` of a public node for sending requests, as well as our symbol map for specifying the permissible list of symbols for the request. It's worth noting that the LCD node returns the price of the token relative to the base asset.

* ### The entry function

The `main` function will verify that the provided parameters fall within our symbol map, and in case unsupported assets are included, it will raise an exception. Subsequently, it will invoke the get_prices function for each symbol.

* ### Sending the requests

Lastly, the `get_prices` function dispatches individual requests to the node. For instance, if we request the price of OSMO relative to ATOM, one example of the request sent would be as follows::

```
https://lcd-osmosis.blockapsis.com/osmosis/gamm/v1beta1/pools/1/prices?base_asset_denom=ibc/27394FB092D2ECCD56123C74F36E4C1F926001CEADA9CA97EA622B25F41E5EB2&quote_asset_denom=uosmo
```


### [#](#other-examples) More examples

To explore additional data source samples, kindly refer to those accessible on our [Mainnet](https://mainnet.odinprotocol.io/data-sources/) This will provide you with a glimpse of the various kinds of data sources leveraged on Odin Protocol:

*   [Latest crypto prices from OKX](https://mainnet.odinprotocol.io/data-sources/8)
*   [Latest crypto prices from Binance](https://mainnet.odinprotocol.io/data-sources/7)
*   [Latest crypto prices from CoinGecko](https://mainnet.odinprotocol.io/data-sources/13)
