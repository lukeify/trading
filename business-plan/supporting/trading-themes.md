# Trading Themes

Recording the themes, colours, and styles I use to style my charts/platforms.

## TradingView

These are the default colours of the TradingView interface, and are not editable.

| Description                  | Hex       | RGB                  | OKLCH               |
| ---------------------------- | --------- | -------------------- | ------------------- |
| TradingView Dark Background  | `#0F0F0F` | `rgb(15, 15, 15)`    | `oklch(0.1684 0 0)` |
| TradingView Light Background | `#FFFFFF` | `rgb(255, 255, 255)` | `oklch(1 0 0)`      |

```palette
#0F0F0F
#FFFFFF
```

## Chart Elements

Non-study, non-data related elements on the chart.

- **Pane separators** refers to the lines that separate the primary chart from any secondaries such as RSI, TSI, etc.
- **Grid lines** are usually disabled for visual clarity and to reduce clutter.
- **Watermark** refers to the label of the ticker in the centre of the chart.
- **Text** refers to any textual elements such as axis values.
- **Lines** refers to axis lines on the chart.
- **Crosshair** is the dashed vertical and horizontal lines that appear when hovering over the chart.

| Description             | Hex         | RGB                         | OKLCH                               |
| ----------------------- | ----------- | --------------------------- | ----------------------------------- |
| Chart Dark Background   | `#161A21`   | `rgb(22, 26, 33)`           | `oklch(0.2168 0.0151 261.62)`       |
| Chart Light Background  | `#FFFFFF`   | `rgb(255, 255, 255)`        | `oklch(1 0 0)`                      |
| Chart Pre-market Hours  | `#FF980014` | `rgba(255, 152, 0, 0.08)`   | `oklch(0.7703 0.1741 64.05 / 8%)`   |
| Chart Post-market Hours | `#2962FF14` | `rgba(41, 98, 255, 0.08)`   | `oklch(0.5624 0.2404 264.4 / 8%)`   |
| Grid lines              | `#F2F2F20F` | `rgba(242, 242, 242, 0.06)` | `oklch(0.9612 0 0 / 6%)`            |
| Pane separators         | `#2E2E2E`   | `rgb(46, 46, 46)`           | `oklch(0.3012 0 0)`                 |
| Watermark               | `#50535E40` | `rgba(80, 83, 94, 0.25)`    | `oklch(0.4436 0.0184 273.52 / 25%)` |
| Text                    | `#B8B8B8`   | `rgb(184, 184, 184)`        | `oklch(0.7826 0 0)`                 |
| Lines                   | `#2E2E2E`   | `rgb(46, 46, 46)`           | `oklch(0.3012 0 0)`                 |
| Crosshair               | `#9C9C9C`   | `rgb(156, 156, 156)`        | `oklch(0.6927 0 0)`                 |

```palette
#161A21
#FFFFFF
#FF980014
#2962FF14
#F2F2F20F
#2E2E2E
#50535E40
#B8B8B8
#2E2E2E
#9c9c9c
```

## Candles

Used to colour the candle bars themselves.

| Description    | Hex       | RGB                | OKLCH                         |
| -------------- | --------- | ------------------ | ----------------------------- |
| Bullish Candle | `#12A657` | `rgb(18, 166, 87)` | `oklch(0.6369 0.1626 152.21)` |
| Bearish Candle | `#EC2535` | `rgb(236, 37, 53)` | `oklch(0.607 0.2282 24.37)`   |

```palette
#12A657
#EC2535
```

## Volume

Used to colour the volume bars for each candle, as well as render the volume profile (if shown).

| Description    | Hex       | RGB                 | OKLCH                         |
| -------------- | --------- | ------------------- | ----------------------------- |
| Bullish Volume | `#26A69A` | `rgb(38, 166, 154)` | `oklch(0.6563 0.1071 185.34)` |
| Bearish Volume | `#EF5350` | `rgb(239, 83, 80)`  | `oklch(0.6539 0.1926 25.14)`  |

```palette
#26A69A
#EF5350
```

## Studies

Studies are additional information that can be derived from other data present on the chart.

| Description                          | Hex       | RGB                 | OKLCH                        |
| ------------------------------------ | --------- | ------------------- | ---------------------------- |
| Volume Weighted Average Price (VWAP) | `#FF9800` | `rgb(255, 152, 0)`  | `oklch(0.7703 0.1741 64.05)` |
| Simple Moving Average (SMA)          | `#9D27B0` | `rgb(157, 39, 176)` | `oklch(0.5183 0.2155 321.6)` |
| Exponential Moving Average (EMA)     | `#2962FF` | `rgb(41, 98, 255)`  | `oklch(0.5624 0.2404 264.4)` |

```palette
#FF9800
#9D27B0
#2962FF
```

## Markers

Markers can be used to delineate important points or horizontal zones on a chart. "Custom levels" refers to levels I have implemented in the _Levels_ indicator which uses Pine Script®'s `color.gray` constant.

| Description              | Hex       | RGB                  | OKLCH                         |
| ------------------------ | --------- | -------------------- | ----------------------------- |
| Previous Day Close (PDC) | `#555555` | `rgb(85, 85, 85)`    | `oklch(0.4495 0 0)`           |
| Horizontal Line          | `#2962FF` | `rgb(41, 98, 255)`   | `oklch(0.5624 0.2404 264.4)`  |
| Custom Levels            | `#797B86` | `rgb(121, 123, 134)` | `oklch(0.5849 0.0169 277.65)` |

```palette
#555555
#2962FF
#797B86
```

## Level 2

Used for displaying blocks of Level 2/montage price action, with the top colour being the closest to the bid/ask, and the depth increasing beyond that.

| Description        | Hex       | RGB                 | OKLCH                         |
| ------------------ | --------- | ------------------- | ----------------------------- |
| Apple Retro Green  | `#61BB45` | `rgb(97, 187, 69)`  | `oklch(0.7112 0.1775 139.03)` |
| Apple Retro Yellow | `#FDB827` | `rgb(253, 184, 39)` | `oklch(0.8259 0.1626 79.66)`  |
| Apple Retro Orange | `#F5821E` | `rgb(245, 130, 30)` | `oklch(0.7221 0.1717 54.16)`  |
| Apple Retro Red    | `#E03A3E` | `rgb(224, 58, 62)`  | `oklch(0.6016 0.2024 24.6)`   |
| Apple Retro Purple | `#963D97` | `rgb(150, 61, 151)` | `oklch(0.515 0.1636 327.19)`  |
| Apple Retro Blue   | `#568FF9` | `rgb(86, 143, 249)` | `oklch(0.6624 0.1689 261.64)` |

```palette
#61BB45
#FDB827
#F5821E
#E03A3E
#963D97
#568FF9
```
