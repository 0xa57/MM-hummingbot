---
tags:
- market making
---

# `perpetual_market_making`

## 📁 [Strategy folder](https://github.com/CoinAlpha/hummingbot/blob/master/hummingbot/strategy/perpetual_market_making)

## 📝 Summary

Perpetual market making allows Hummingbot users to market make on supported derivatives exchanges. The strategy has position management features to make managing positions easier and remove the need to interact with the derivative exchange manually.

Like pure market making strategy, it keeps placing limit buy and sell orders on the order book and waits for other participants (takers) to fill its orders.

## 🏦 Exchanges supported

[`perp` exchanges](/exchanges/#perp)

## 👷 Maintainer

Open

## 🛠️ Strategy configs

[Config map](https://github.com/CoinAlpha/hummingbot/blob/master/hummingbot/strategy/perpetual_market_making/perpetual_market_making_config_map.py)

| Parameter                    | Type        | Default     | Prompt New? | Prompt                                                 |
|------------------------------|-------------|-------------|-------------|--------------------------------------------------------|
| `market`                     | string      |             | True        | Enter the trading pair you would like to provide liquidity on [connector] |
| `leverage`                     | int      |             | True        | How much leverage do you want to use? |
| `position_mode`                     | string      | One-way            | True        | Which position mode do you want to use? (One-way/Hedge) |
| `bid_spread`                     | decimal      |             | True        | How far away from the mid price do you want to place the first bid order? |
| `ask_spread`                     | decimal      |             | True        | How far away from the mid price do you want to place the first ask order? |
| `minimum_spread`                     | decimal      | -100            | False        | At what minimum spread should the bot automatically cancel orders? |
| `order_refresh_time`                     | float      |             | True        | How often do you want to cancel and replace bids and asks (in seconds)? |
| `order_refresh_tolerance_pct`                     | decimal      | 0            | False        | Enter the percent change in price needed to refresh orders at each cycle |
| `order_amount`                     | decimal      |             | True        |  |
| `position_management`                     | string      | Profit_taking            | True        | How would you like to manage your positions? (Profit_taking/Trailing_stop) |
| `long_profit_taking_spread`                     | decimal      | 0            | True        | At what spread from the entry price do you want to place a short order to reduce position? |
| `short_profit_taking_spread`                     | string      | 0            | True        | At what spread from the position entry price do you want to place a long order to reduce position? |
| `ts_activation_spread`                     | string      | 0            | True        | At what spread from the position entry price do you want the bot to start trailing? |
| `ts_callback_rate`                     | string      | 0            | True        | At what spread away from the trailing peak price do you want positions to remain open before they're closed? |
| `stop_loss_spread`                     | string      | 0            | True        | At what spread from position entry price do you want to place stop_loss order? |
| `close_position_order_type`                     | string      | LIMIT            | True        | What order type do you want trailing stop and/or stop loss features to use for closing positions? (LIMIT/MARKET) |
| `price_ceiling`                     | decimal      | -1            | False        | Enter the price point above which only sell orders will be placed |
| `price_floor`                     | decimal      | -1            | False        | Enter the price below which only buy orders will be placed |

## 📓 Description
