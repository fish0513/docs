# Futures Spot Arbitrage Bot
A futures spot arbitrage command line program based on binance exchange.

# Features
* provide 15% ~ 50% APR based on USD stable coin
* start arbitrage by just few commands
* auto rebalance to maximize profit and prevent liquidation

# Screenshot
<img width="444" alt="screenshot" src="https://user-images.githubusercontent.com/5153181/111059889-cac7f500-84d3-11eb-8c00-9d2d028862b6.png">

# Build
build program by `make`, `go` is required.
```
$ cd futures-spot-arbitrage
$ make
```

# Usage
* export API key and secret of your binance exchange in environment
* execute `bot` program
* input commands to control your position

## Example
### Export API key and secret
```
$ export API_KEY= S8jH...wX9Z
$ export API_SECRET=QsY2...IZBD
$ ./bot
```
### Open Position
```
>>> set_trading_pair ETHUSDT
>>> set_trading_volume 30
>>> set_leverage 2
>>> open
```

### Close Position
```
>>> set_trading_pair ETHUSDT
>>> close
```

### Show Market and Position
```
>>> show
Position
========
 Symbol |  Position      |          Profit (last time | 7 days)
    ETH |    0.010       |                 0.00000000 | 0.04896385
------------------------------------------------------------------------
Market
========
  Pair  |  Funding Rate  |  Futures-Spot Spread (Open | Close Position)
ETHUSDT |     0.100%     |                    0.174%  | 0.175%
SXPUSDT |     0.142%     |                    0.179%  | 0.216%
------------------------------------------------------------------------
```
