# Futures Spot Arbitrage Bot
A futures spot arbitrage command line program based on binance exchange.

# Features
* provide 15% ~ 50% APR based on USD stable coin
* start arbitrage by just few commands
* auto rebalance to maximize profit and prevent liquidation

# Screenshot
<img width="444" alt="screenshot" src="https://user-images.githubusercontent.com/5153181/111059889-cac7f500-84d3-11eb-8c00-9d2d028862b6.png">

# Usage
* export API key and secret of your binance exchange in environment
* execute `fsab` program
* input commands to control your position

## Example
### Export API key and secret into your environment
```
$ export API_KEY= S8jH...wX9Z
$ export API_SECRET=QsY2...IZBD
$ ./fsab
```
### Open Position
```
>>> set_trading_pair ETHUSDT     // 设置交易对
>>> set_trading_volume 30        // 设置开仓金额 30 ~ 100,000 USDT
>>> set_leverage 2               // 设置杠杆倍率 1x,2x,3x
>>> open                         // 开仓/加仓
```

### Close Position
#### close all position
```
>>> set_trading_pair ETHUSDT      // 设置交易对
>>> close all                     // 关闭这个交易对的所有仓位
```
#### close partial position
```
>>> set_trading_pair ETHUSDT      // 设置交易对
>>> close 50%                     // 关闭这个交易对的部分仓位，如果关闭的金额过少，
                                  // 或者小于交易所允许的最小名义值，将关闭失败
```

### Set Futures Spot Spread
```
>>> set_futures_spot_spread 0.1%  // 设置期现价差，支持开仓/关仓运行中设置
```

### Stop
#### stop while open/close position is running
```
>>> stop                          // 停止正在开仓/关仓的操作
```

### Check Progress
```
>>> status                        // 查看当前开仓/关仓的状态
[2021-04-14 14:48:53] Done: 100%, amount: 141.8, commission: 0.0012654(BNB) 
```

### Display Information
#### show your positions
```
>>> show                          // 显示当前仓位信息和仓位信息的资金费率情况
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
>>> show market                    // 显示当前市场行情，包括资金费率，开关仓价差 
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

### Exit Program
```
>>>exit                             // 退出程序，注意，退出程序后自动减仓功能失效
```
