# Pine Script®

Note on Pine Script® 

- [Language Reference Manual](https://www.tradingview.com/pine-script-reference/v6/)
- [User Manual](https://www.tradingview.com/pine-script-docs/)

Interesting repositories:

- [pAulseperformance/awesome-pinescript](https://github.com/pAulseperformance/awesome-pinescript)

It's very important that every usage of Pine Script® have a reserved symbol appended to it.

## Syntax Notes

Multiline functions must be indented, but not be a multiple of 4 spaces. Having the closing bracket at the same indentation level will cause a compilation error. Multiline functions must reference.

Arms of if/else statements must return values of the same type.

## Language & SDK Notes

`plot` declarations must be in the global scope, and cannot be within functions.

Updating the `scale` of an indicator requires removing and re-adding the indicator on the chart.

Indicators have a `scale=scale.none` option that should mean the the auto-chart scaling doesn't take into account this indicator when scaling the y-axis, but it still seems to anyway. The better choice seems to be right clicking on the price scale and selecting "Scale price chart only".

Important time-related variables:
- `time` the UNIX timestamp of the current bar being computed.
-  `last_bar_time` the UNIX timestamp of the most recently loaded bar on the chart.
- `timenow` the UNIX timestamp of the current time in reality (irrespective of whether we are in replay mode or not).

There is no ability to "look forward" arbitrarily from the current bar, either during replay mode or when evaluating a historical bar.

`request.security` can be provided an `expression` which can be a function that can return a complex value to reduce the number of individual `request.security` calls made (as there is a limit of 40 calls to the `request` namespace per script).

## Execution Environment

Variable assignments are executed once, and not re-evaluated per bar.

There are many [limitations](https://www.tradingview.com/pine-script-docs/writing/limitations) around PineScript execution per script, such as time limits:

- A 2 minute script compilation limit (3 consecutive warnings for this can result in a 1-hour compilation ban)
- 40 seconds of execution time for non-basic accounts.
- 500 milliseconds of loop execution per bar.

And element limits:

- 64 plots (from `plot` and friends).
- 50 lines/boxes/polylines/labels.
- 9 tables.

As well as call/language limits:

- 40 unique calls in the `request.*()` namespace (duplicate calls do not count, as the duplicated calls reuse data from the first call).
- Each scope can have 1000 variables.
- Compilation requests for scripts cannot exceed 5MB.
- A maximum of 100,000 elements per array/matrix/map.

## Bugs

One documented bug I have discovered is that `session.ismarket` (as well as `session.ispremarket` and `session.ispostmarket`) return incorrect values on intraday charts for U.S. equities when in bar replay mode. Specifically:

- `session.ismarket` will always return true (even if it is pre- or post-market).
- `session.ispremarket` will always return false.
- `session.ispostmarket` will always return false.

When not in bar-replay mode, these functions seem to return correct values. This bug is as of 20 June 2025.