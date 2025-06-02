# Acronyms & Encyclopedia

## Candlesticks

Candlestick-specific terminology.

- **Doji**. A specific form of indecision candlestick with an asymmetric wick.
- **Multi-time frame alignment**.
- **Spinning Top**. A candlestick with large, similar sized wicks and a small body, indicating indecision.
- **Shooting Star Doji**. An asymmetric Doji with a large top wick, indicating that there was a high, but the close was lower.
- **Hammer Doji**. The opposite of a Shooting Star Doji. An asymmetric Doji with a large bottom wick, indicating there was a low, but the close was higher.

## Daytrading Terminology

Relating to trading measurements and indicators.

### Average True Range (ATR)

Stocks with a high Average True Range will tend to swing more in price over a day, and can be good candidates for day trading as that volatility creates profit potential. Average True Range is usually measured over a period of 14 days (this length is per the suggestion of _Wilder_, who developed the indicator). [Calculation of a single day's _true range_ is as follows](https://www.investopedia.com/terms/a/atr.asp#toc-how-to-calculate-the-atr):

$$
TR = Max[(H-L), |H-C_{p}|, |L - C_{p}|]
$$

Where:

- H = High of the period
- L = Low of the period
- C<sub>p</sub> = Closing price of previous period

The maximum is then taken of these 3 values:

- (H - L) = High of the period minus low of the period
- |H - C<sub>p</sub>| = Absolute value of the period's high minus the previous period's closing price.
- |L - C<sub>p</sub>| = Absolute value of the period's low minus the previous period's closing price.

Repeat this process for the period of time you are interested in (usually 14 days) to calculate the ATR:

$$
ATR = \left(\frac{1}{n}\right)\sum_{i}^{n}\mathrm{TR}_{i}
$$

Once the ATR has been initially calculated, it can be recomputed efficiently for the next value by factoring in the next true range term:

$$
ATR = \frac{\text{Previous ATR}(n-1) + \text{TR}}{n}
$$

### Others
- **Relative ATR** is a fraction of the ATR versus the overall share price.
- **EMA**. Exponential Moving Average.
- **SMA**. Simple Moving Average.
- **RSI**. Relative Strength Index.
- **TSI**. True Strength Index.
- **VWAP**. *Volume Weighted Average Price*. Represents the average price of a stock based on both volume and price over time. Higher levels of volume will move the VWAP more than lower levels.
- **SVP**. *Session Volume Profile*. A measure of how buy & sell volume is distributed into buckets based on the price the volume occurred in. This is often graphically shown as volume bars on the left-hand side of the charting platform.

## Options Terminology

Captured for completeness, but not interested in this style of trading for now.

- **ATM**. At The Money.
- **ITM**. In The Money.
- **OTM**. Out of The Money.
- **PCS**. Put Credit Spread.
- **PDS**. Put Debit Spread.

### Patterns

- **ABCD**. Doesn't stand for anything, represents a pattern with a fibonacci-approximating price action, with inflection points indicated at A, B, C, and D.
- **ORB**. Opening Range Breakout. A strategy designed to follow the breakout trend on opening of a stock.

### Trade Execution

- **OCA**. One Cancels All.
- **RS**. Relative Strength. The strength of a stock relative to a benchmark, usually the S&P500. If a stock rises more than the benchmark, it will have a >1 relative strength value.
- **RW**. Relative Weakness. The weakness of a stock relative to a benchmark, also usually the S&P500.
- **RR**. Risk to Reward Ratio.
- **SL**. Stop loss.
- **TP**. Take profit.

## Market Terminology

- **Beta**. A measure of how closely a stock follows an index, where 1 = exactly matches. Often the S&P500 for U.S. stocks. High-beta stocks can be more at the whims of general market movement.
- **DOM**. Depth of Market.
- **Float**. The outstanding shares available for trading, usually excluding restricted stock units
	- **Low float** stocks usually have under 20 million shares available for trading.
	- **High float** stocks will be anything above 20 million shares available.
- **FOMC**. A "FOMC day"
- **HTF**. Higher Time Frame.
- **Liquidity Sweep**.
- **Liquidity Pool**.
- **Lower Time Frame**.
- **Order Block**.
- **Order Flow**.
- **Market Capitalisation**. Shares issued multiplied by price per share.
	- **Mega-cap** stocks have >$200 billion in market cap.
	- **Large-cap** stocks have between $10–200 billion.
	- **Mid-cap** stocks have between $2–10 billion.
	- **Small-cap** stocks have between $300 million–2 billion.
	- Anything under $300 million can be classified as **micro-cap** or **nano-cap**.
- **NBBO**. National Best Bid and Offer. The best available price for a stock at any given time across all three major networks.
- **PDC**. Previous Day Close.
- **PDT**. Pattern Day Trader. A series of regulations that U.S. brokers are required to subject their clients to if they hold under $25,000 in funds on a margin account. Traders will be limited to a certain number of trades within a couple day window.
- **POC**. Point of Control.
- **Price Action**.
- **Relative Volume**.
- **SSR**. Short Selling Restriction.
- **Support**.
- **Resistance**.
- **NHOD**. *New High of Day*.
- **NLOD**. *New Low of Day*. When an equity breaches the previous low for the day with a new one. Often colloquially stated as "Ticker XYZ is making NLOD".
- **Tape**. The live feed of trades and quotes on a stock.

### Level 1 Market Data

Provides consolidated realtime market data of the NBBO (National Best Bid and Offer)—often called the "top of book". Without subscribing to Level 1 market data, data will either be delayed, or you will instead pay for snapshots at point of trade.

### Level 2 Market Data

Provides DOM (Depth of Market).

## Markets & Common Tickers

- **ARCA**.
- **BATS**. Better Alternative Trading System, a global stock exchange operator. Owned by CBOE.
- **CBOE**. Chicago Board Options Exchange. Famous for creating the VIX index.
- **CME**. Chicago Mercantile Exchange.
- **NYSE**. New York Stock Exchange.
- **E-Mini**. A smaller, electronically traded futures contract representing a fraction of a traditional “full futures” contract. Traded exclusively on CME’s Globex electronic platform.
- **ES**. The ticker for E-mini S&P500 futures contracts. Each E-mini contract on ES is $50 × the index level.
- **MES**.
- **MNQ**.
- **NQ**. The ticker for E-mini NASDAQ-100 futures contracts. Each E-mini contract on the NQ is $50 × the index level, this is 1/5th the size of a full contract ($250 × the index level).

## Finances

- **NTA**. Net Tangible Assets.
