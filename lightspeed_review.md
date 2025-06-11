# Lightspeed 

Lightspeed is a direct-access broker that has a reputation for offering very fast, price-efficient fills, and a corresponding trading platform called _Lightspeed Trader_. Recommended and used by Ross Cameron.

## Brokerage

- U.S. brokerage (following the PDT rules).
- Accepts international customers, but does not provide a New Zealand account number for customers, wire transfers or domestic ACH transfers only.
	- Likely possible to workaround this by having a Wise USD-denominated bank account, which could be considered a non-"third-party" account as it is attached to my name. This would avoid the need for potentially expensive fees.
- Does not provide any paper trading facilities.

### Pricing

There are three main fees associated with any trade.

- **Commissions**, with two options: a share rate or a trade rate.
- **Routing fees**, paid to the route provider. This can be a rebate depending on whether you are adding liquidity or taking liquidity.
- **FINRA Trading activity fee**, a regulatory fee applied by the _Financial Industry Regulatory Authority_ to all trades to cover the costs of regulating firms involved in stock brokerage.

Other trading pricing caveats:

- There is a minimum commission of US$0.25/trade on the per-share rate.
- For share prices less than US$1.00, "30 basis points times the total trade value will be charged".
- Pre- and post-market orders have an additional US$0.003/share routing charge.

[Brokerage, service fees](https://lightspeed.com/pricing-fees/brokerage-fees), and [market data pricing](https://lightspeed.com/pricing-fees/market-data) caveats:

- Lightspeed also provide market data for a fee, the ones I would be interested are listed below. For complete Level 2 data, this would be US$91/month.
- Accounts under US$15,000 value with no activity are charged a US$25/month inactivity fee.
- ACH transfers are free, but recalls, reversals, and returns are US$30.
- Wire fees are US$25 and US$50 for domestic and international wires respectively.

#### Level 1 Data

Real time level 1 bundle for all U.S. equities, DJI, and streaming news for $25.00/month. These cannot be combined with the individual Level 2 books. Suspect this is not necessary if purchasing Level 2 data.

#### Level 2 Data

The Level 2 data offering is more expensive than IBKR, but has additional books from EDGX and EDGA. Note that the NASDAQ Level 2 offering is also called _TotalView_ by NASDAQ/IBKR.

| Service                      | Cost               | Relative to IBKR    |
| ---------------------------- | ------------------ | ------------------- |
| ARCA Book                    | US$17.00/month     | 2.125× more         |
| BATS (BZX) Book              | US$9.00/month      | 12.5% more          |
| EDGX Book                    | US$10.00/month     | Not offered by IBKR |
| EDGA                         | US$5.00/month      | Not offered by IBKR |
| NYSE Open Book               | US$28.00/month     | 12% more            |
| NASDAQ Level 2 w/ Book Depth | US$22.00/month     | 33% more            |
| **Sum**                      | **US$91.00/month** | 50.4% more          |

### Per Share Rate examples

The per-share rate makes the most sense if your individual trades are under 1142 shares per trade ($4 ÷ $0.0035) on average. Assumptions in the table below: one buy trade and one sell trade, assuming the most expensive monthly volume (< 250,000 shares traded) at $0.0035/share.

| Share size | Commission | Routing (LSPT, Taking Liquidity, both directions) | FINRA TAF (On sold shares only) | Total   |
| ---------- | ---------- | ------------------------------------------------- | ------------------------------- | ------- |
| 50         | $0.50¹     | $0.15                                             | $0.00595                        | ~$0.66  |
| 200        | $1.40      | $0.60                                             | $0.0238                         | ~$2.02  |
| 1000       | $7.00      | $3.00                                             | $0.119                          | ~$10.12 |
| 5000       | $35.00²    | $15.00                                            | $0.595                          | ~$50.60 |

¹ Minimum commission of $0.25 per trade applies.
² This exceeds the breakeven of 1142 shares traded, if above this regularly it would be more economic to switch to their per-trade rate.
 
## Lightspeed Trader

[Lightspeed Trader](https://lightspeed.com/trading-platforms/lightspeed-trader) is paid software, priced at US$130/month, but is discounted up to the full $130 value on the commissions paid in the prior month—i.e. generate $130 of commissions, and Lightspeed Trader is effectively "free".

 - New accounts receive one month of platform fees free.
 - New accounts funded with $10,000 receive 3 months of Lightspeed Trader free along with 6 months free of TrendSpider & Tradervue.

When on a demo account, Lightspeed Trader has 15-minute delayed market data, which makes it challenging to evaluate its ordering capabilities.

### macOS

Recently, a macOS version has been offered that is claimed to be "[fully optimised](https://www.instagram.com/p/DFGGKW-zs4m/)" for macOS, however I have found this not to be the case in practice. The application utilises [Crossover](https://www.codeweavers.com/crossover/) internally to map Windows system calls to Mac ones, and is not optimised for Retina devices, so unsurprisingly looks dated and is difficult to read.

I chose to run Windows in a virtual machine and run Lightspeed Trader which is significantly more responsive experience.

### Windows

When run within Parallels on a Mac, the Windows version seems to be significantly more responsive, as well as retina. 

### Level 2 data feed

Lightspeed provides its own Level 2 data feed that is integrated into Lightspeed Trader, see prices above.

### Hotkeys

Lightspeed seems to offer the most versatile hotkey entry system for trading of any of the platforms, I've evaluated, possibly with some limitations around closing out positions with partials.

## Questions

1. Can a paper account be opened with an expedited open account process—or is a full account application required? Can paper accounts have their orders reset to allow starting from scratch?
	- Lightspeed does not provide any paper trading facilities.
2. Can the paper account be opened without a full Reg-T Margin deposit of >US$25,000? 
	- No, a full deposit of US$25,000 minimum is required.
3. Can a domestic ACH transfer be initiated using a Wise USD-denominated bank account in my name?
	- On speaking with a representative of Lightspeed, it seems a Wise transfer would work, provided the bank account is in my own name.
4. Does Lightspeed Trader offer hotkeys be created to closeout arbitrary positions such as 1/8th or 1/10th? Or would that have to be controlled through tier size selection?
	- No, closeouts are in the pre-provided quantities only. Other closeout position techniques would require adjusting quantities and placing sell orders.
5. Does Lightspeed Trader provide OCA/OCO functionality for sending stop losses alongside orders?
	- OCA/OCO functionality is not provided, all orders are placed separately. There is a setting that does allow you to "cancel pending orders when a position is closed" however.