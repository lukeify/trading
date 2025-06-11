# MotiveWave

[MotiveWave](https://www.motivewave.com) is a Java-based trading platform that specialises mainly in futures trading and was founded with the intention of developing Elliot Wave analysis tooling before expanding into a fully-fledged trading platform. It is compatible with a number of brokers, including IBKR, which makes it easy to set up and applicable to a wide audience. 

## Broker API Connectivity Issues

Due to limitations with IBKR's API, MotiveWave themselves acknowledge that their product works sub-optimally when connected to IBKR to retrieve historical data. This is because IBKR imposes strict limits ("[pacing limitations](https://ibkrcampus.com/campus/ibkr-api-page/twsapi-doc/#requests-limitations)") on request rates to their gateway.

Buying a [dxfeed data subscription](https://dxfeed.com/platforms/dxfeed-motivewave/) and integrating this into MotiveWave seems to noticeably improve the performance of loading data onto charts—especially volume-related information such as VWAP—if dxfeed is ticked as the "Use for Historical Data" checkbox.

![The MotiveWave configuration panel for integrating dxfeed](motivewave_dxfeed_integration.png)

If ticked for the "Use for Real Time Data" checkbox, one receives significantly more frequent data updates compared to IBKR, on the order of <100ms/update; however dxfeed only offers Level 2 depth of market via Nasdaq TotalView MarketDepth (for US$69/month), which is only one of the many ECN's needed to properly get a complete picture on national depth of market.

## Pricing

[MotiveWave has a number of software license options available](https://motivewave.com/products/products.htm#chartingandtradingsoftware), with serious daytraders likely needing to subscribe to _Pro_ which is US$99/month. This provides support for two key features missing in cheaper offerings:

- "Power Trading Pack" which offers a configurable trade panel and custom keyboard shortcuts for orders. Unfortunately these "custom" keyboard shortcuts are still limited to what customisation options are provided by the MotiveWave interface and there is no functionality to bind a hotkey to an arbitrary script, or any SDK offerings that would be applicable here.
- "Desktops" which essentially offers multi-monitor support.

If only the "Trading Pack" is needed, then the US$24/month _Standard_ offering may be sufficient. If MotiveWave was used purely for charting this would be sufficient.

## Analyses

Analyses are _not_ charts. Analyses are scoped/saved against an individual stock, but seem by default to be copied across to other instruments when the instrument is changed.

## Charts

Compared to TradingView, the charting customisation is extremely in-depth, with the same number (or more) of customisable parameters, without having to pay extra for additional studies. However the ergonomics and design of the charts are not quite as good:

- The auto-scaling functionality seems to arbitrarily turn back on.
- The "labels" that can be displayed on charts lack customisation options around spacing, colour, differentiation between keys and values, etc.
- Interactions around saving "chart templates" and associating them with "analyses" is also clunky.
	- I am constantly being asked to "save" templates and analyses even if I just want to reuse a standard chart design and studies across multiple instruments.

## Trading

- **Orders panel** captures individual buys/sells made, including those that are unfilled or non-transmitted. Orders that are not filled can be edited here.
- **Trades panel**. [This doesn't seem to exist as documented](https://support.motivewave.com/videos/trades-panel/) in MW7—some parts of the functionality appear to live in the Executions Panel as well as the Trade Report panel.
- **Positions panel** shows currently open positions, which has a convenient "Close" button (can also right click and select "Close all positions"). Can also double click a row to specify stops, trails, limits, etc.

### Order Presets

The order presets window lets you configure the presets for _all stocks_—can set the type of the order to LMT/MKT here, as well as the "offset" in ticks, which is defined as the "Default offset (in pips) from the current price when placing an order". This number can't be negative, so marketable limit orders are not possible.

### Chart Trading

Trading can be done on the chart—possibly the most intuitive aspect of the application. By default this always appears to be a limit, regardless of what order preset you selected. The price axis key modifiers can be changed in Preferences → Orders → Submission. Below the current price, the cursor will be blue indicating a buy limit, above the current price it becomes red, indicating a sell limit. Modifiers change the order type:

* ⌘ makes the order a STP.
* ⇧ makes the order MKT. When double clicking on the price axis with shift enabled, the position on the price axis is irrelevant because it is a market order.

By default, the orders are un-transmitted (although this setting can be changed to auto-transmit). Once an order is transmitted, modifications are automatically transmitted.

Once an order is placed, a P&L bar will appear next to the price axis to visually show your order P&L. This can also be tracked in the DOM Ladder. The P&L bar is inclusive of the commission required to enter the trade.

## Summary

| Key          | Value                                                             |
| ------------ | ----------------------------------------------------------------- |
| Cost         | Low–Medium (US$24–99/month depending on chosen plan)              |
| UI           | Very good (relative to other platforms)                           |
| Charting     | Very good, not quite as ergonomic as TradingView.                 |
| Data Quality | Good when integrated with dxfeed, poor when integrated with IBKR. |
| Correctness  | Heavily limited by IB Gateway.                                    |
 
## Outstanding Questions & Issues

1. There seems to be an issue where premarket/after-hours volume is not fetched, regardless of whether I'm using IB Gateway or dxfeed for historical data.
	- If I watch a chart in pre-market, volume will accumulate as per normal, suggesting realtime population of the chart with data is working correctly. Worth investigating if this is fixed in the currently stable MotiveWave 6.9.
2. What is the cutoff between "historical" versus "real-time" data when configuring a data provider? Is it the current date?
3. The VWAP indicator that is displayed on the price axis disappears and re-appears often on 1 minute and 5 minute charts.
4. Occasionally the VWAP study appears in multi-bar segments, often in daily charts.
5. The PDC indicator is not appearing on 1 minute and 5 minute charts, despite being selected as an indicator in my chart settings.
	- Check if this disappears in regular market, it may be pre-market only.
6. Chart candles don't adjust in height if a new high or low is being made.
	1. This could be a MotiveWave version 7 bug—need to recheck if fixed in MotiveWave 6.9.
7. The "Exchange" field is empty in the Time and Sales panel, despite being filled in the MM field in the Order Book and Price Ladder.
	- Additionally, when historical data is loaded, the exchange information is populated with a single letter. What is the meaning of this?
8. The countdown clock to a new candle in the daily chart appears to be incorrect.
9. Is there a way to trim extreme candles without having to manually enter values for them? They add noise to the data and make auto-scaling functionality useless.
	- LightSpeed trader can trim candles that are extreme beyond a customisation standard deviation.
10. Could we set the default tick size to $0.01 for all instruments of a specific type? Or by price range? I'd never usually want stocks to be in increments smaller than that.

### Duplicate STP orders submitted via IBKR TWS Gateway

When submitting a "MKT+STP" order (either from the chart or using a hotkey), the bracket order would be transmitted, the market order would be filled, and then a duplicate STP order would appear, with my original position size, leaving two active STP orders at the same price. This is quite a dangerous situation because if the stops are hit, you will end up in a short position.

Originally, I thought this was perhaps caused by me setting the "Master Client ID" setting in IB Gateway to a non-empty value, but unsetting this did also not fix the issue.

### Error Placing Order(s) Dialog

Occasionally I would also see a dialog stating:

`Cannot invoke "com.motivewave.platform.databean.MWOrder.setUpdatelnProgress(boolean)" because "<parameter1>" is null`

![[motivewave_error_placing_orders.png]]

## Solved

### Is there a way to have the cursor data panel be saved to the same position on each chart?

No, but the question is redundant by configuring "chart labels" to appear in the top left and right, which are much nicer than the cursor data panel and more closely mimic trading view.

### Can the OHLC data be displayed within the chart in the top left?

Yes, see chart labels above. It would be nice to colour them however similar to TradingView, and customisation of the label and value independently is not possible.

### Can I configure a limit order with a price above the current bid to create a _marketable limit_ order?

No. The offset price, regardless of whether is is specified as a negative or positive, will create a limit below the current bid.

### Can a shortcut be configured to take a partial of an open position, proportionate to the original size?

No—all buy and sell shortcuts require absolute quantities. However, there is a (tedious) workaround where you could define the "default" quantities for each stock, including the partial sizing, i.e. if your full quantity would be 400 shares, you would define "partial" quantities of 40, 80, 100, 200 to achieve 1/10, 1/5, ¼, and ½ sizes.
	  
You would need to manually select between the selected size before using the keyboard shortcut though—this would require constant attention and care to placing orders. 

## Post: MotiveWave needs better scalping hotkey support

Outline of a post I would have made to MotiveWave support if it had passed my basic correctness tests.

--- 

I am currently evaluating how well MotiveWave Pro can work as my trading platform for scalping stocks on the 1 minute opening range breakout timeframe. I would like to find a way to make it work for my use case because the charts are high quality, it is reasonably well configurable, and it works on Mac. 

However even with the "Power Trading Pack" in the Pro plan it's missing essential functionality—usually relating to hotkeys and custom shortcuts—that holds it back from being an excellent scalping platform. As a scalper, I do not have time to select trades from context menus in the price axis and drag stop losses and take profits around with my mouse. As much of my trading needs to be keyboard-controlled as possible, and with more in-depth customisation than what is currently allowed with custom orders.

For some background, I am using IBKR as my broker with dxfeed as my tick data source with MotiveWave 7 beta—which should giving MotiveWave the best possible chance to shine.

Here are some examples of functionality I've found lacking during my evaluation. I would very much appreciate it if MotiveWave could discuss if any of these features are planned.

### Unable to specify "marketable limit" orders

TWS and DAS make it trivial to create a buy limit order shortcut above the current bid (and conversely a sell limit order below the current ask). In TWS for example this is specified as "Bid + {someOffset}" where if a stock is at a bid of $9.00, a specified offset of 5c will create a limit order of $9.05, giving you a significantly higher likelihood of getting a quality fill without causing huge slippage.

MW lets me create a custom LMT order where there is an offset, but it's in the _wrong direction_, i.e. the offset reduces your limit, not increases it; which is the conventional setting, but not what you need for scalping. Setting the offset field to a negative value has no effect, I presume the input is being ABS'd.   

Can you allow offsets in both directions, please?

### No ability to take partials as a fraction of my position

I can see no way to bind a keyboard shortcut to close 10%, 20%, 25%, or 50% of my open position. Everything is defined in absolute quantities of shares, rather than relative position sizing.

This is absolutely fundamental to buying down risk when scalping. I realise I can create an exit order and attach that to my buy ahead of time, but that is not the style of trading I am after, as I may want to take an arbitrarily large number of partials.

### No Trading SDK, and no ability to run scripts/functionality on hotkey press

This would be the icing on the cake. There is already a trading aspect to the MotiveWave SDK, but it's tied to execution on strategies, which is not the same and can't be used in the way I am referring to. 

Let me define a snippet of Java code with a MotiveWave "Trading SDK", and run that on a keyboard shortcut. This what. I could query my current position, account size, and arbitrarily create an order based on many metrics, what hotkey I pressed, etc.

### Missing risk management

This is not entirely a requirement but having to manually define my position sizing for instruments ahead of time is somewhat laborious. If MW knows my account size, and it could know my maximum per-trade size, it would be trivial for MW to then determine if I want a "full order" to know how many shares to purchase. An example:

My maximum I am willing to tie up in a trade might be $5000. If a stock is trading at $8, MW should give me the option to buy 625 shares ($5000/$8) automatically, or fractionals of that depending on my confidence of my setup. 

An alternative approach to risk management would be to automatically compute the number of shares to purchase if my maximum risk per trade is $200, etc.

If anyone knows of workarounds for the above issues, I'd appreciate hearing about them. 

Would the MotiveWave team be interested in developing these features? I'd be happy to offer further guidance and suggestions if so because otherwise I'm impressed with the platform and want to find a way to use it. Thanks!

---

