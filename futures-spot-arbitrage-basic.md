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
* execute `fsab` program
* input commands to control your position

## Example
### Export API key and secret into your environment
```
$ export API_KEY= S8jH...wX9Z
$ export API_SECRET=QsY2...IZBD
$ ./fsaa
```
### Open Position
```
>>> set_trading_pair ETHUSDT
>>> set_trading_volume 30
>>> set_leverage 2
>>> open
```

### Close Position
#### close all position
```
>>> set_trading_pair ETHUSDT
>>> close all
```
#### close partial position
```
>>> set_trading_pair ETHUSDT
>>> close 50%
```

### Set Futures Spot Spread
```
>>> set_futures_spot_spread 0.1%
```

### Stop
#### stop while open/close position is running
```
>>> stop
```

### Check Progress
```
>>> status
[2021-04-14 14:48:53] Done: 100%, amount: 141.8, commission: 0.0012654(BNB) 
```

### Display Information
#### show your positions
```
>>> show
Position
========
  Symbol  | Spot Account | Futures Account |   Next, Last, 7-day's Profit
ETHUSDT   |      16.8210 |         16.8200 |  66.53U   62.20U 1107.93U
SXPUSDT   |    2823.1000 |       2823.1000 |  39.29U   37.39U  474.51U
------------------------------------------------------------------------
Market
========
  Symbol  | Funding Rate | Open Position Spread | Close Position Spread
SXPUSDT   |       0.300% |               0.548% |                0.632%
ETHUSDT   |       0.155% |               0.210% |                0.211%
------------------------------------------------------------------------
```
#### show market
```
>>> show market
Market
========
  Symbol  | Funding Rate | Open Position Spread | Close Position Spread
DENTUSDT  |       0.332% |               0.476% |                0.558%
AVAXUSDT  |       0.331% |               0.451% |                0.515%
RENUSDT   |       0.320% |               0.483% |                0.531%
LINAUSDT  |       0.318% |               0.389% |                0.471%
EGLDUSDT  |       0.318% |               0.356% |                0.435%
REEFUSDT  |       0.318% |               0.460% |                0.557%
```
