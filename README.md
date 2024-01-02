# Smart Trend Trading System MT5

This is the code for the Smart Trend Trading System MT5, developed by the Forex Robot Easy Team. Please note that ForexRobotEasy is not the official developer of this product. We only provide a sample code that can work as described in this product. To find the official developer of this product, please use MQL5.

For detailed reviews and trading results of this product, please visit [Forex Robot Easy](https://forexroboteasy.com/forex-robot-review/smart-trend-trading-system-mt5-unbiased-review/).

## Description

The Smart Trend Trading System MT5 is a trading system that uses various strategies to determine the market trend and execute trades accordingly. It includes three main strategies: trend following, reversal, and scalping.

The code is written in MQL5 and can be used in the MetaTrader 5 platform. It utilizes the Trade and Indicators libraries for trading and indicator calculations, respectively.

## Installation

To use this trading system, follow these steps:

1. Include the necessary libraries:
```mql5
#include <Trade\Trade.mqh>
#include <Indicators\Indicators.mqh>
```

2. Define the constants:
```mql5
#define SYMBOL_NAME 'EURUSD'
#define STOP_LOSS 50
#define TAKE_PROFIT 100
#define LOT_SIZE 0.01
```

3. Create an instance of the trade class:
```mql5
CTrade trade;
```

4. Implement the `OnInit` function to initialize the trade class:
```mql5
void OnInit()
{
   trade.Init(Symbol(), 0);
}
```

5. Implement the `OnTick` function to execute trades based on the market conditions:
```mql5
void OnTick()
{
   double bid = SymbolInfoDouble(SYMBOL_NAME, SYMBOL_BID);

   if (isTrendFollowing(bid))
   {
      trade.Buy(LOT_SIZE, bid, bid - STOP_LOSS, bid + TAKE_PROFIT, '');
   }
   else if (isReversal(bid))
   {
      trade.Sell(LOT_SIZE, bid, bid + STOP_LOSS, bid - TAKE_PROFIT, '');
   }
   else if (isScalping(bid))
   {
      trade.Buy(LOT_SIZE, bid, bid - STOP_LOSS, bid + TAKE_PROFIT, '');
   }
}
```

6. Implement the strategy functions `isTrendFollowing`, `isReversal`, and `isScalping` to define the specific criteria for each strategy.

7. Implement the `OnDeinit` function to perform any necessary cleanup tasks before the program terminates.

## Strategy Functions

### `isTrendFollowing`

This function implements the trend following strategy. It takes the current price as a parameter and should return `true` if the criteria for trend following are met, otherwise `false`.

### `isReversal`

This function implements the reversal strategy. It takes the current price as a parameter and should return `true` if the criteria for reversal are met, otherwise `false`.

### `isScalping`

This function implements the scalping strategy. It takes the current price as a parameter and should return `true` if the criteria for scalping are met, otherwise `false`.

## Disclaimer

Please note that the Smart Trend Trading System MT5 is a product developed by the Forex Robot Easy Team. ForexRobotEasy is not the official developer of this product and only provides a sample code that can work as described in this product. To find the official developer of this product, please use MQL5.

For detailed reviews and trading results of this product, please visit [Forex Robot Easy](https://forexroboteasy.com/forex-robot-review/smart-trend-trading-system-mt5-unbiased-review/).
