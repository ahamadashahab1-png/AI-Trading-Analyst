# TECHNICAL ANALYSIS MASTER ENCYCLOPEDIA V2
## Complete Indicator, Quantitative Analysis & Trading Strategy Reference

Version: 2.0  
Purpose: Professional multi-market technical analysis reference for the AI Trading Analyst skill.

---

# 1. CORE PRINCIPLES

Technical indicators are mathematical transformations of market data. They do not predict the future with certainty.

The analyst MUST:
- Understand what each indicator measures.
- Use indicators in the correct market regime.
- Confirm signals with price action and market structure.
- Avoid treating indicator readings as guaranteed buy/sell signals.
- Avoid combining multiple indicators that measure essentially the same thing.
- Validate calculations, data quality and indicator warm-up periods.
- Distinguish confirmed signals from developing signals.
- Never invent indicator readings when chart data is unavailable.

## 1.1 Indicator Categories

1. Trend indicators
2. Moving averages
3. Momentum indicators
4. Oscillators
5. Volatility indicators
6. Volume indicators
7. Volume profile and market profile
8. Order-flow indicators
9. Market structure tools
10. Support and resistance tools
11. Fibonacci tools
12. Statistical indicators
13. Quantitative risk metrics
14. Cycle and wave analysis
15. Harmonic and geometric tools
16. Multi-timeframe analysis

## 1.2 Data Requirements

Common market fields:

- Open
- High
- Low
- Close
- Volume
- Timestamp
- Bid
- Ask
- Trade size
- Contract information

Not every market provides all fields.

Important distinctions:

- Exchange-traded volume: actual exchange-reported traded volume.
- Tick volume: number of price updates, not necessarily traded quantity.
- Real volume: actual quantity traded where available.
- Futures volume: exchange-specific contract volume.
- Forex spot volume: often fragmented or broker-specific.
- Crypto volume: exchange-specific and may require aggregation.

Never treat tick volume as identical to centralized exchange volume.

## 1.3 Calculation Standards

Before calculating an indicator:

1. Confirm instrument and exchange.
2. Confirm timeframe.
3. Confirm timezone.
4. Confirm candle construction.
5. Check missing candles.
6. Check duplicate timestamps.
7. Check abnormal price spikes.
8. Check volume reliability.
9. Identify adjusted versus unadjusted stock prices.
10. Apply correct warm-up periods.

For an indicator requiring N observations, do not automatically treat the first N-1 values as valid.

Some indicators require more history because of smoothing or recursive calculations.

---

# 2. MOVING AVERAGE MASTER SUITE

Moving averages smooth price data and help identify trend direction, dynamic support/resistance and momentum changes.

## 2.1 Simple Moving Average (SMA)

Formula:

SMA = Sum of closing prices over N periods / N

Common settings:
- 9
- 20
- 21
- 50
- 100
- 200

Interpretation:
- Price above rising SMA: bullish trend context.
- Price below falling SMA: bearish trend context.
- Flat SMA: possible consolidation.
- Price repeatedly crossing SMA: possible sideways market.

Limitations:
- Lagging indicator.
- Can produce repeated false signals in ranges.
- Does not independently confirm a trend reversal.

## 2.2 Exponential Moving Average (EMA)

EMA gives greater weight to recent prices.

Multiplier:

k = 2 / (N + 1)

EMA = Current Close × k + Previous EMA × (1-k)

Common settings:
- 9 EMA
- 12 EMA
- 20 EMA
- 21 EMA
- 26 EMA
- 50 EMA
- 100 EMA
- 200 EMA

Uses:
- Trend identification.
- Pullback analysis.
- Dynamic support/resistance.
- Momentum shifts.

## 2.3 Weighted Moving Average (WMA)

Recent prices receive linearly greater weights.

WMA = Sum(Price × Weight) / Sum(Weights)

Useful for:
- Responsive trend analysis.
- Comparing smoothing methods.

## 2.4 Volume Weighted Moving Average (VWMA)

VWMA = Sum(Close × Volume) / Sum(Volume)

Uses:
- Price trend weighted by volume.
- Identifying whether higher-volume trading supports a move.

Limitation:
Volume quality must be reliable.

## 2.5 Double Exponential Moving Average (DEMA)

DEMA = 2 × EMA(price) - EMA(EMA(price))

Designed to reduce lag.

## 2.6 Triple Exponential Moving Average (TEMA)

TEMA = 3 × EMA(price) - 3 × EMA(EMA(price)) + EMA(EMA(EMA(price)))

Can react faster but may become noisy.

## 2.7 Hull Moving Average (HMA)

HMA = WMA(2 × WMA(price, N/2) - WMA(price, N), sqrt(N))

Uses:
- Responsive trend direction.
- Short-term momentum.

## 2.8 Kaufman Adaptive Moving Average (KAMA)

Adapts its smoothing based on market efficiency.

Efficiency Ratio:

ER = Absolute price change over N periods / Sum of absolute changes

Uses:
- Adaptation to trending and noisy conditions.
- Reducing unnecessary sensitivity in choppy markets.

## 2.9 Arnaud Legoux Moving Average (ALMA)

Uses a Gaussian weighting distribution.

Settings include:
- Window
- Offset
- Sigma

Use it as an alternative smoothing method, not a guaranteed superior average.

## 2.10 Zero Lag EMA (ZLEMA)

Attempts to compensate for EMA lag using a price adjustment.

Limitation:
Can become sensitive to noise.

## 2.11 McGinley Dynamic

Adaptive moving average that adjusts its response based on price movement.

Useful for:
- Trend following.
- Dynamic price reference.

## 2.12 Least Squares Moving Average (LSMA)

Uses linear regression to estimate the endpoint of a fitted price line.

Useful for:
- Trend direction.
- Regression-based analysis.

## 2.13 Fractal Adaptive Moving Average (FRAMA)

Adapts smoothing using fractal dimension estimates.

Useful for:
- Distinguishing smoother trends from noisy price movement.

## 2.14 Moving Average Signals

Bullish conditions:
- Fast MA above slow MA.
- Both averages rising.
- Price holding above the averages.
- Pullback followed by bullish structure.

Bearish conditions:
- Fast MA below slow MA.
- Both averages falling.
- Price holding below averages.
- Rejection followed by bearish structure.

Neutral conditions:
- Frequent crossovers.
- Flat averages.
- Price repeatedly moving above and below averages.

A crossover alone is not sufficient for a trade.

---

# 3. MOMENTUM AND OSCILLATOR MASTER SUITE

## 3.1 Relative Strength Index (RSI)

Formula:

RSI = 100 - [100 / (1 + RS)]

RS = Average Gain / Average Loss

Common period: 14.

Interpretation:
- Above 70: traditionally overbought.
- Below 30: traditionally oversold.
- Above 50: positive momentum context.
- Below 50: negative momentum context.

Important:
Overbought does not automatically mean SELL.
Oversold does not automatically mean BUY.

In strong trends, RSI can remain extreme for extended periods.

## 3.2 Stochastic Oscillator

%K = 100 × (Close - Lowest Low) / (Highest High - Lowest Low)

%D = Moving average of %K

Common settings:
14, 3, 3.

Interpretation:
- Above 80: traditionally overbought.
- Below 20: traditionally oversold.
- Crossovers may indicate momentum changes.

Use with market structure and trend context.

## 3.3 Stochastic RSI

Applies stochastic calculations to RSI values.

Uses:
- Faster momentum sensitivity.
- Short-term momentum changes.

Limitation:
Can produce frequent signals.

## 3.4 MACD

MACD Line = EMA(12) - EMA(26)

Signal Line = EMA(9) of MACD

Histogram = MACD Line - Signal Line

Interpretation:
- MACD above signal: positive momentum crossover.
- MACD below signal: negative momentum crossover.
- Above zero: positive relative EMA structure.
- Below zero: negative relative EMA structure.

## 3.5 Percentage Price Oscillator (PPO)

PPO = 100 × (Fast EMA - Slow EMA) / Slow EMA

Useful for comparing momentum across instruments with different price levels.

## 3.6 Rate of Change (ROC)

ROC = 100 × (Current Price - Price N periods ago) / Price N periods ago

Positive ROC indicates price is higher than the reference period.

Negative ROC indicates price is lower.

## 3.7 Commodity Channel Index (CCI)

CCI = (Typical Price - SMA of Typical Price) / (0.015 × Mean Deviation)

Typical Price = (High + Low + Close) / 3

Common period: 20.

Traditional levels:
+100 and -100.

## 3.8 Williams %R

%R = -100 × (Highest High - Close) / (Highest High - Lowest Low)

Traditional levels:
-20 and -80.

## 3.9 True Strength Index (TSI)

Uses double-smoothed momentum and double-smoothed absolute momentum.

Useful for:
- Momentum direction.
- Signal-line crossovers.
- Divergence analysis.

## 3.10 Ultimate Oscillator

Combines buying pressure across multiple timeframes.

Traditional periods:
7, 14, 28.

Designed to reduce weaknesses from using only one momentum period.

## 3.11 Fisher Transform

Transforms price values into a normalized statistical distribution.

Useful for:
- Identifying possible turning points.
- Comparing extreme readings.

It does not guarantee reversals.

## 3.12 Chande Momentum Oscillator (CMO)

Measures the difference between upward and downward price movement.

Positive readings suggest upward momentum.
Negative readings suggest downward momentum.

## 3.13 Relative Vigor Index (RVI)

Compares closing price position within the trading range.

Useful for momentum confirmation.

## 3.14 Detrended Price Oscillator (DPO)

Attempts to remove longer-term trend effects to study shorter cycles.

Do not use it as a standalone trend predictor.

## 3.15 Awesome Oscillator (AO)

Uses the difference between short and long median-price moving averages.

Useful for momentum shifts and zero-line analysis.

## 3.16 Accelerator Oscillator (AC)

Measures changes in momentum using the Awesome Oscillator.

Use as a secondary momentum tool.

## 3.17 Momentum Signal Rules

Bullish:
- Momentum turns upward.
- Price forms higher low.
- Indicator confirms higher low.
- Price breaks relevant structure.

Bearish:
- Momentum turns downward.
- Price forms lower high.
- Indicator confirms lower high.
- Price breaks relevant structure.

Avoid trading a single oscillator crossover without context.

---

# 4. TREND STRENGTH AND DIRECTION INDICATORS

## 4.1 Average Directional Index (ADX)

Measures trend strength, not trend direction.

Common period: 14.

Traditional interpretation:
- Below 20: weak trend or range context.
- 20-25: developing trend context.
- Above 25: stronger trend context.
- Above 40: strong trend conditions may exist.

These are conventional reference levels, not universal thresholds.

## 4.2 Directional Movement Index (DMI)

Includes:
- +DI
- -DI
- ADX

Bullish directional context:
+DI above -DI.

Bearish directional context:
-DI above +DI.

Use ADX to evaluate strength.

## 4.3 Aroon Indicator

Uses the time since recent highest high and lowest low.

Components:
- Aroon Up
- Aroon Down

Useful for identifying recent trend dominance.

## 4.4 Vortex Indicator

Uses positive and negative directional movement.

Bullish context:
VI+ above VI-.

Bearish context:
VI- above VI+.

## 4.5 Supertrend

Uses ATR-based bands to estimate trend direction.

Settings:
- ATR period
- Multiplier

A trend flip may be useful as confirmation but can lag or whipsaw.

## 4.6 Parabolic SAR

Uses an acceleration factor to create trailing stop reference points.

Uses:
- Trend-following reference.
- Potential stop management.

Limitation:
Performs poorly in choppy conditions.

## 4.7 Ichimoku Cloud

Components:
- Tenkan-sen
- Kijun-sen
- Senkou Span A
- Senkou Span B
- Chikou Span

Interpretation:
- Price above cloud: bullish context.
- Price below cloud: bearish context.
- Price inside cloud: uncertain or transitional context.
- Tenkan/Kijun cross: possible momentum signal.
- Cloud thickness: visual support/resistance context.

Respect the indicator's forward-shifted cloud calculations and historical displacement.

## 4.8 Alligator Indicator

Components:
- Jaw
- Teeth
- Lips

Uses moving averages with different shifts.

Useful for identifying potential trend development and consolidation.

## 4.9 Gator Oscillator

Visualizes the separation between Alligator averages.

Use as supporting trend information.

## 4.10 Trend Strength Validation

Evaluate:
1. Swing structure.
2. MA slope.
3. ADX.
4. DMI direction.
5. Volume participation.
6. Higher timeframe trend.
7. Breakout and retest quality.

No single trend indicator should override contradictory price structure.

---

# 5. VOLATILITY INDICATORS

## 5.1 Average True Range (ATR)

True Range is the greatest of:

- High - Low
- Absolute value of High - Previous Close
- Absolute value of Low - Previous Close

ATR is a smoothed average of True Range.

Common period: 14.

Uses:
- Stop-loss distance estimation.
- Volatility comparison.
- Position sizing.
- Volatility regime detection.

ATR measures volatility, not direction.

## 5.2 Bollinger Bands

Middle Band = SMA(N)

Upper Band = SMA + (K × Standard Deviation)

Lower Band = SMA - (K × Standard Deviation)

Common setting:
20 periods, 2 standard deviations.

Uses:
- Volatility expansion.
- Volatility contraction.
- Relative price position.
- Mean-reversion context.

A band touch is not an automatic reversal signal.

## 5.3 Bollinger Band Width

Band Width = (Upper Band - Lower Band) / Middle Band

Useful for identifying volatility contraction and expansion.

## 5.4 %B

%B = (Close - Lower Band) / (Upper Band - Lower Band)

Measures closing price relative to the bands.

## 5.5 Keltner Channels

Uses an EMA centerline and ATR-based channel boundaries.

Useful for:
- Trend continuation.
- Volatility expansion.
- Squeeze analysis.

## 5.6 Donchian Channels

Upper Band = Highest High over N periods.

Lower Band = Lowest Low over N periods.

Useful for:
- Breakout strategies.
- Trend-following systems.
- Range boundaries.

## 5.7 Historical Volatility

Calculates standard deviation of historical returns, commonly annualized.

For daily returns:

Annualized Volatility = Standard Deviation × sqrt(Trading Days per Year)

The annualization factor must match the market and return frequency.

## 5.8 Chaikin Volatility

Measures changes in the range of price movement over time.

## 5.9 Ulcer Index

Measures downside volatility and depth/duration of drawdowns.

Useful for evaluating equity curve stress.

## 5.10 Choppiness Index

Attempts to distinguish trending markets from sideways conditions.

Use only as a regime filter, not a directional signal.

## 5.11 Volatility Regimes

Classify conditions as:
- Low volatility.
- Normal volatility.
- Expanding volatility.
- High volatility.
- Extreme volatility.

Compare current ATR or realized volatility with its own historical distribution.

Do not use one universal ATR number across all instruments.

---

# 6. VOLUME INDICATORS

## 6.1 On Balance Volume (OBV)

Adds volume when price closes higher and subtracts volume when price closes lower.

Useful for:
- Volume trend.
- Price-volume divergence.

## 6.2 Money Flow Index (MFI)

Combines typical price and volume.

Often described as a volume-weighted momentum oscillator.

Traditional reference levels:
80 and 20.

## 6.3 Chaikin Money Flow (CMF)

Measures volume-weighted buying and selling pressure over a period.

Positive CMF indicates stronger buying pressure within the calculation period.

Negative CMF indicates stronger selling pressure.

## 6.4 Accumulation/Distribution Line

Uses the close location value within the candle range, multiplied by volume.

Useful for price-volume divergence.

## 6.5 Force Index

Combines price change and volume.

Useful for evaluating the strength of price movement.

## 6.6 Ease of Movement (EOM)

Evaluates the relationship between price movement and volume.

## 6.7 Price Volume Trend (PVT)

Accumulates volume weighted by percentage price change.

## 6.8 Negative Volume Index (NVI)

Focuses on periods when volume decreases.

## 6.9 Positive Volume Index (PVI)

Focuses on periods when volume increases.

## 6.10 Volume Oscillator

Compares short and long volume averages.

Useful for identifying changes in participation.

## 6.11 VWAP

VWAP = Sum(Price × Volume) / Sum(Volume)

Commonly resets by trading session.

Uses:
- Intraday benchmark.
- Institutional execution reference.
- Dynamic support/resistance context.

VWAP depends on the session definition and data quality.

## 6.12 Anchored VWAP

Starts VWAP calculations from a selected event or price point.

Possible anchors:
- Major swing high.
- Major swing low.
- Earnings gap.
- News event.
- Breakout candle.
- Major market event.

The anchor must be selected objectively to avoid hindsight bias.

## 6.13 Relative Volume (RVOL)

RVOL compares current volume with a historical reference.

The comparison should use equivalent sessions or times when intraday seasonality matters.

## 6.14 Volume Interpretation

Bullish evidence may include:
- Price breakout with increased volume.
- Positive volume trend.
- Demand response at support.
- Strong participation after reclaiming a level.

Bearish evidence may include:
- Breakdown with increased volume.
- Selling pressure at resistance.
- Weak recovery volume.
- Negative volume divergence.

Volume alone does not prove institutional activity.

---

# 7. VOLUME PROFILE AND MARKET PROFILE

## 7.1 Volume Profile

Displays traded volume across price levels.

Important concepts:

- POC: Point of Control.
- VAH: Value Area High.
- VAL: Value Area Low.
- HVN: High Volume Node.
- LVN: Low Volume Node.
- Value Area: commonly a selected percentage of total volume, often 70%.

## 7.2 Point of Control

Price level with the highest volume in the selected profile.

Potentially important acceptance or rejection area.

## 7.3 Value Area High and Low

Upper and lower boundaries of the selected value area.

Price acceptance or rejection around these levels can help define market context.

## 7.4 High Volume Nodes

Areas where substantial volume traded.

May act as areas of acceptance or consolidation.

## 7.5 Low Volume Nodes

Areas with relatively low traded volume.

Price may move through them quickly, but this is not guaranteed.

## 7.6 TPO / Market Profile

Time Price Opportunity measures how long price traded at particular levels.

Concepts:
- Initial Balance.
- Value Area.
- Single Prints.
- Poor High.
- Poor Low.
- Excess High.
- Excess Low.

Do not confuse TPO time distribution with traded volume.

## 7.7 Profile Strategy Context

Evaluate:
- Acceptance above value.
- Acceptance below value.
- Rejection from value boundaries.
- POC migration.
- Balance versus imbalance.
- Previous session profile.
- Current session profile.

Profile interpretation depends on session, contract and data source.

---

# 8. ORDER FLOW ANALYSIS

Order-flow analysis requires suitable trade and quote data. Ordinary OHLC candles cannot reproduce a true exchange footprint.

## 8.1 Bid-Ask Delta

Delta = Aggressive Buy Volume - Aggressive Sell Volume

Interpretation depends on how trades are classified.

## 8.2 Cumulative Volume Delta (CVD)

CVD accumulates bid-ask volume delta.

Uses:
- Aggressive buying/selling pressure.
- Divergence with price.
- Potential absorption context.

CVD can differ between exchanges and data providers.

## 8.3 Footprint Charts

Show volume traded at individual price levels.

Analyze:
- Bid volume.
- Ask volume.
- Delta.
- Imbalances.
- Stacked imbalances.
- Absorption.
- Exhaustion.

## 8.4 Bid-Ask Imbalance

Compares buying and selling volume at corresponding price levels.

Thresholds must be defined and tested.

## 8.5 Absorption

Possible absorption occurs when aggressive orders are met by substantial passive liquidity and price makes limited progress.

Do not declare absorption solely from a candle wick.

## 8.6 Exhaustion

Potential exhaustion may appear when aggressive participation weakens near a price extreme.

Requires confirmation.

## 8.7 Iceberg Orders

Hidden order-size inference requires appropriate exchange or order-book data.

Do not claim iceberg detection from ordinary charts.

## 8.8 Open Interest

Important for futures and derivatives.

Analyze:
- Price rising, OI rising.
- Price falling, OI rising.
- Price rising, OI falling.
- Price falling, OI falling.

These combinations describe possible positioning changes, not definitive proof of long or short liquidations.

## 8.9 Funding Rate

For perpetual crypto futures:
- Positive funding generally means longs pay shorts.
- Negative funding generally means shorts pay longs.

Funding is not a standalone reversal signal.

## 8.10 Liquidation Data

Use verified exchange-specific liquidation data where available.

Do not invent liquidation clusters or exact liquidation levels.

---

# 9. PRICE ACTION AND MARKET STRUCTURE TOOLS

## 9.1 Swing High and Swing Low

Identify local highs and lows using a defined pivot method.

A pivot requiring future candles is not confirmed until those candles have closed.

Never use future-confirmed pivots in historical backtests before their actual confirmation time.

## 9.2 Higher High (HH)

A swing high above the previous relevant swing high.

## 9.3 Higher Low (HL)

A swing low above the previous relevant swing low.

## 9.4 Lower High (LH)

A swing high below the previous relevant swing high.

## 9.5 Lower Low (LL)

A swing low below the previous relevant swing low.

## 9.6 Break of Structure (BOS)

A break of a relevant structural swing.

Define whether the method uses candle close, wick penetration or another confirmation rule.

## 9.7 Change of Character (CHoCH)

A potential change in directional structure.

Must be evaluated in context; not every minor swing break changes the larger trend.

## 9.8 Market Structure Shift (MSS)

A structural change supported by meaningful displacement or other predefined confirmation.

## 9.9 Support and Resistance

Identify zones from:
- Repeated reactions.
- Swing highs/lows.
- Volume profile.
- Previous session levels.
- Major timeframe levels.
- Confirmed breakout and retest.

Prefer zones over false precision at one exact price.

## 9.10 Pivot Points

Common traditional formulas:

Pivot = (High + Low + Close) / 3

R1 = 2 × Pivot - Low

S1 = 2 × Pivot - High

R2 = Pivot + (High - Low)

S2 = Pivot - (High - Low)

Additional pivot systems include:
- Fibonacci pivots.
- Camarilla pivots.
- Woodie's pivots.
- DeMark pivots.

Use the correct previous session data.

## 9.11 Trendlines and Channels

A trendline must connect meaningful confirmed pivots.

Avoid drawing lines to force a desired trade.

## 9.12 Range Analysis

Identify:
- Range high.
- Range low.
- Midpoint.
- Failed breakouts.
- Acceptance outside range.
- Rejection back inside range.

---

# 10. FIBONACCI MASTER SUITE

## 10.1 Fibonacci Retracement

Common levels:
- 23.6%
- 38.2%
- 50%
- 61.8%
- 78.6%

The 50% level is widely used but is not a Fibonacci ratio.

## 10.2 Fibonacci Extension

Common reference levels:
- 127.2%
- 161.8%
- 200%
- 261.8%

Used for possible target zones.

## 10.3 Fibonacci Projection

Projects a measured move from a defined swing structure.

## 10.4 Fibonacci Time Zones

Projects possible time intervals from a selected anchor.

Treat as exploratory, not reliable timing predictions.

## 10.5 Fibonacci Fans and Arcs

Geometric tools for studying possible dynamic support/resistance.

Their usefulness is subjective and requires testing.

## 10.6 Fibonacci Rules

- Select confirmed swing points.
- Define the drawing direction.
- Do not move anchors after seeing the outcome.
- Combine with structure and reaction.
- Never assume a level must reverse price.

---

# 11. DIVERGENCE MASTER ENGINE

## 11.1 Regular Bullish Divergence

Price: lower low.

Indicator: higher low.

Possible weakening downside momentum.

## 11.2 Regular Bearish Divergence

Price: higher high.

Indicator: lower high.

Possible weakening upside momentum.

## 11.3 Hidden Bullish Divergence

Price: higher low.

Indicator: lower low.

Potential trend continuation context.

## 11.4 Hidden Bearish Divergence

Price: lower high.

Indicator: higher high.

Potential bearish continuation context.

## 11.5 Exaggerated Divergence

Similar price highs or lows with differing indicator extremes.

Define the exact detection method before backtesting.

## 11.6 Multi-Swing Divergence

Compare multiple confirmed price and indicator pivots.

## 11.7 Divergence Validation

Check:
1. Confirmed price pivots.
2. Confirmed indicator pivots.
3. Same timeframe.
4. Minimum pivot separation.
5. Market structure.
6. Trend context.
7. Confirmation candle.
8. Invalidation level.

Do not use future data to identify a divergence before it was observable.

---

# 12. STATISTICAL AND QUANTITATIVE INDICATORS

## 12.1 Returns

Simple Return:

(Current Price / Previous Price) - 1

Log Return:

ln(Current Price / Previous Price)

Use consistent return definitions.

## 12.2 Rolling Return

Calculates return over a moving historical window.

## 12.3 Z-Score

Z = (Value - Mean) / Standard Deviation

Measures distance from a historical mean in standard deviation units.

A high absolute Z-score does not guarantee mean reversion.

## 12.4 Rolling Standard Deviation

Measures changing dispersion of returns or prices.

## 12.5 Beta

Beta = Covariance(Asset Returns, Benchmark Returns) / Variance(Benchmark Returns)

Measures historical sensitivity to a benchmark.

## 12.6 Correlation

Measures the direction and strength of linear association between two return series.

Correlation does not prove causation and can change across regimes.

## 12.7 Covariance

Measures joint movement of two variables.

## 12.8 Sharpe Ratio

Sharpe = (Portfolio Return - Risk-Free Rate) / Standard Deviation of Returns

Annualization and return frequency must be consistent.

## 12.9 Sortino Ratio

Uses downside deviation instead of total standard deviation.

## 12.10 Calmar Ratio

Annualized Return / Maximum Drawdown

Define whether annualized return is arithmetic or compounded.

## 12.11 Maximum Drawdown

Largest peak-to-trough decline in the equity curve.

## 12.12 Drawdown Duration

Time taken for equity to recover from a peak or remain below it.

## 12.13 Skewness

Measures return distribution asymmetry.

## 12.14 Kurtosis

Measures distribution tail behavior.

## 12.15 Realized Volatility

Calculated from historical returns over a defined interval.

## 12.16 Parkinson Volatility

Uses high-low price ranges to estimate volatility under its model assumptions.

## 12.17 Garman-Klass Volatility

Uses OHLC data to estimate volatility.

## 12.18 Rogers-Satchell Volatility

Uses OHLC data and accommodates nonzero drift under its assumptions.

## 12.19 Amihud Illiquidity

Relates absolute return to traded value.

Requires suitable volume and price data.

## 12.20 Efficiency Ratio

Measures net price movement relative to total absolute movement.

Useful for trend efficiency analysis.

## 12.21 Hurst Exponent

Attempts to characterize persistence or anti-persistence in time series.

Estimates are sensitive to sample size and method.

## 12.22 Entropy

Measures aspects of distributional uncertainty or complexity.

Do not assume high or low entropy directly indicates a trade direction.

## 12.23 Autocorrelation

Measures relationship between a series and its lagged values.

## 12.24 Regime Detection

Possible methods:
- Rolling volatility.
- Trend strength.
- Hidden Markov Models.
- Change-point detection.
- Clustering.
- Volatility-state classification.

Regime models require out-of-sample validation.

---

# 13. ELLIOTT WAVE ANALYSIS

Study:
- Impulse waves.
- Corrective waves.
- Wave 1 to Wave 5.
- ABC corrections.
- Zigzag.
- Flat.
- Triangle.
- Combination corrections.
- Extensions.
- Truncation.
- Alternation.
- Channeling.
- Fibonacci relationships.

Rules:
- Maintain alternate counts.
- Define invalidation levels.
- Do not force a count.
- Identify subjective labeling.
- Require objective confirmation where possible.
- Backtest the actual decision rules, not just chart illustrations.

Elliott Wave labels are interpretive and must not be presented as certainty.

---

# 14. GANN AND GEOMETRIC ANALYSIS

Possible tools:
- Gann angles.
- 1x1 angle.
- Square of Nine.
- Time-price relationships.
- Gann fan.
- Geometric projections.

Limitations:
- Anchor selection is subjective.
- Scaling and chart settings affect interpretation.
- Claims must be independently tested.

Do not claim guaranteed support or resistance from geometric constructions.

---

# 15. HARMONIC PATTERN ANALYSIS

Patterns:
- Gartley.
- Bat.
- Butterfly.
- Crab.
- Deep Crab.
- Shark.
- Cypher.
- AB=CD.

For each candidate:
1. Identify confirmed pivots.
2. Measure leg ratios.
3. Compare with predefined ratio tolerances.
4. Define potential completion zone.
5. Check structure.
6. Wait for confirmation.
7. Define invalidation.
8. Test results objectively.

Do not label approximate shapes as confirmed harmonic patterns.

---

# 16. MARKET CYCLE ANALYSIS

Possible concepts:
- Seasonal patterns.
- Intraday seasonality.
- Weekly cycles.
- Monthly cycles.
- Business cycles.
- Commodity cycles.
- Volatility cycles.
- Fourier analysis.
- Spectral analysis.

Cycle analysis is exploratory.

Avoid claiming a cycle will repeat without statistical evidence.

---

# 17. OPTIONS AND DERIVATIVES METRICS

Where relevant, analyze:

- Implied Volatility (IV).
- Historical Volatility (HV).
- IV Rank.
- IV Percentile.
- Delta.
- Gamma.
- Theta.
- Vega.
- Rho.
- Open Interest.
- Put-Call Ratio.
- Skew.
- Term Structure.
- Expected Move.
- Max Pain.

Important:
- Greeks depend on model assumptions.
- Option chain data must be timestamped.
- Expiry and strike must be verified.
- Max Pain is not a guaranteed expiry target.
- Put-Call Ratio depends on the chosen calculation method.
- Options risk includes nonlinear exposure and time decay.

Never recommend an options trade without checking liquidity, spread, expiry, volatility and maximum possible loss.

---

# 18. INDICATOR CONFLUENCE ENGINE

The goal is not to use the maximum number of indicators.

The goal is to use independent evidence.

## 18.1 Evidence Categories

A. Market Structure
- HH/HL or LH/LL.
- BOS.
- CHoCH.
- Support/resistance.

B. Trend
- EMA structure.
- ADX.
- Supertrend.
- Ichimoku.

C. Momentum
- RSI.
- MACD.
- CCI.
- ROC.

D. Volatility
- ATR.
- Bollinger Band Width.
- Keltner Channels.

E. Volume
- VWAP.
- OBV.
- CMF.
- Volume Profile.

F. Order Flow
- Delta.
- CVD.
- Footprint.
- Imbalance.

G. Fundamental Context
- News.
- Economic releases.
- Earnings.
- Interest rates.

## 18.2 Avoid Duplicate Evidence

Examples:
- RSI and Stochastic RSI are related.
- SMA and EMA both measure trend smoothing.
- MACD and PPO are closely related.
- ATR and ATR-based Supertrend share volatility information.
- OBV and PVT both use price-volume relationships.

Do not count correlated indicators as independent confirmations.

## 18.3 Confluence Scoring

A scoring model may be used only after its rules are defined and tested.

Example categories:
- Structure: 0 to 2.
- Trend: 0 to 2.
- Momentum: 0 to 2.
- Volume: 0 to 2.
- Risk/reward quality: 0 to 2.

Maximum illustrative score: 10.

The score is not a probability of profit.

A score threshold must be calibrated using historical out-of-sample results.

Missing data must not be silently scored as positive evidence.

## 18.4 Trade Gate

Before approving a trade:
- Direction is clear.
- Setup is identifiable.
- Entry trigger is defined.
- Stop loss is logical.
- Target is realistic.
- Position size is calculated.
- Risk/reward is acceptable.
- News risk is checked where relevant.
- Data is sufficiently reliable.
- No major unresolved contradiction exists.

If these conditions are not met, prefer WAIT or NO TRADE.

---

# 19. MULTI-TIMEFRAME INDICATOR ANALYSIS

Recommended hierarchy:

1. Higher timeframe: overall market direction.
2. Middle timeframe: setup and structure.
3. Lower timeframe: entry trigger.

Possible combinations:
- Weekly / Daily / 4H.
- Daily / 4H / 1H.
- 4H / 1H / 15M.
- 1H / 15M / 5M.

These are examples, not universal rules.

Rules:
- Never mix indicator readings from different timestamps without alignment.
- Higher timeframe candles must be confirmed before treating them as closed.
- Lower timeframe signals should not override major higher timeframe risk without explanation.
- Record the timeframe of every indicator reading.

---

# 20. ENTRY, STOP LOSS AND TARGET INTEGRATION

Indicators can help identify conditions, but price structure should define the trade's invalidation.

## 20.1 Entry Methods

Possible methods:
- Breakout.
- Breakout and retest.
- Pullback.
- Reclaim.
- Rejection.
- Momentum continuation.
- Range reversal.
- Mean reversion.

Each method needs a predefined trigger.

## 20.2 Stop Loss Methods

Possible methods:
- Beyond swing high/low.
- Beyond structural invalidation.
- ATR-based distance.
- Beyond support/resistance.
- Volatility-adjusted stop.

Do not place stops using ATR alone if the structural invalidation is elsewhere.

## 20.3 Target Methods

Possible targets:
- Previous swing high/low.
- Support/resistance.
- Risk-reward projection.
- Fibonacci extension.
- Volume profile level.
- Measured move.
- ATR-based exit.

Targets should account for nearby liquidity, volatility and market structure.

## 20.4 Risk Per Trade

Risk Amount = Account Equity × Risk Percentage

Position Size = Risk Amount / Monetary Loss per Unit at Stop

For leveraged markets, calculate contract multiplier, tick value, currency conversion and fees correctly.

Never assume that the same lot size has the same monetary risk across instruments.

## 20.5 Risk/Reward

Reward-to-Risk = Potential Reward / Potential Risk

A high ratio does not automatically make a trade profitable.

Expected Value:

EV = (Win Probability × Average Win) - (Loss Probability × Average Loss)

Include fees, spread, slippage and financing costs.

---

# 21. INDICATOR PARAMETER MANAGEMENT

Every indicator configuration must record:

- Indicator name.
- Formula/version.
- Input source.
- Period.
- Smoothing method.
- Multiplier.
- Timeframe.
- Market.
- Session.
- Data source.
- Warm-up period.
- Timestamp.
- Parameter changes.

Avoid changing parameters after seeing the test outcome.

## 21.1 Standard Settings Are Not Universal

Common settings are starting points, not optimal settings for every market.

A parameter must be tested for:
- Instrument.
- Timeframe.
- Market regime.
- Transaction costs.
- Data quality.
- Execution assumptions.

## 21.2 Warm-Up Rules

Do not generate signals from incomplete initialization.

For recursive indicators, use sufficient pre-sample data.

The required warm-up period should be documented for each implementation.

---

# 22. PYTHON IMPLEMENTATION REQUIREMENTS

A production implementation should separate:

1. Data ingestion.
2. Data validation.
3. Indicator calculations.
4. Signal generation.
5. Strategy rules.
6. Risk calculations.
7. Backtesting.
8. Reporting.

Possible Python libraries:
- pandas
- numpy
- scipy
- statsmodels
- scikit-learn
- TA-Lib
- pandas-ta
- vectorbt
- backtesting.py
- backtrader

Library availability and API versions must be verified before coding.

## 22.1 Implementation Rules

- Avoid look-ahead bias.
- Avoid future candle leakage.
- Handle NaN values explicitly.
- Handle division by zero.
- Handle zero-volume candles.
- Use consistent timezone handling.
- Validate indicator outputs against known references.
- Document smoothing differences between libraries.
- Test edge cases.
- Preserve original raw data.

## 22.2 Calculation Validation

For every indicator:
1. Calculate using the selected implementation.
2. Compare against an independent reference where possible.
3. Check selected historical candles manually.
4. Check warm-up behavior.
5. Check missing-data behavior.
6. Record calculation version.

---

# 23. BACKTESTING AND STRATEGY VALIDATION

A technical indicator is not a profitable strategy by itself.

Test complete entry and exit rules.

## 23.1 Required Backtest Metrics

- Total trades.
- Winning trades.
- Losing trades.
- Win rate.
- Average win.
- Average loss.
- Profit factor.
- Expectancy.
- Net profit.
- Gross profit.
- Gross loss.
- Maximum drawdown.
- Drawdown duration.
- Sharpe ratio.
- Sortino ratio.
- Calmar ratio.
- Average holding period.
- Exposure.
- Turnover.
- Fees.
- Spread.
- Slippage.
- Long performance.
- Short performance.
- Performance by market regime.

## 23.2 Testing Structure

Separate:
- Training data.
- Validation data.
- Out-of-sample test data.

Never optimize on the final test period.

## 23.3 Walk-Forward Testing

1. Select a historical training window.
2. Optimize only within that window.
3. Freeze parameters.
4. Test on the next unseen window.
5. Roll forward.
6. Repeat.
7. Aggregate results.

## 23.4 Robustness Testing

Test:
- Different market periods.
- Different instruments.
- Different timeframes.
- Higher transaction costs.
- Increased slippage.
- Parameter perturbations.
- Volatility regimes.
- Trend and range conditions.

## 23.5 Overfitting Prevention

Watch for:
- Excessive parameter search.
- Too many indicators.
- Too few trades.
- Repeated testing on the same data.
- Survivorship bias.
- Look-ahead bias.
- Data snooping.
- Selection bias.
- Unrealistic fills.

A good historical result is not proof of future profitability.

---

# 24. TEN-MILLION SCENARIO TESTING FRAMEWORK

The user's desired target is to evaluate up to 10,000,000 scenarios before a high-confidence recommendation.

This is an engineering target, not a claim that ten million tests have already been completed.

## 24.1 Scenario Types

Keep these categories separate:

1. Historical trade simulations.
2. Indicator parameter combinations.
3. Strategy parameter combinations.
4. Monte Carlo resampling.
5. Bootstrap simulations.
6. Synthetic market scenarios.
7. Stress tests.
8. Execution-cost scenarios.
9. Market-regime scenarios.
10. Walk-forward test windows.

These are not interchangeable.

## 24.2 Scenario Record

Every completed test should record:

- Unique scenario ID.
- Instrument.
- Timeframe.
- Strategy version.
- Indicator parameters.
- Data period.
- Entry rules.
- Exit rules.
- Transaction costs.
- Slippage assumptions.
- Result.
- Drawdown.
- Validation status.
- Execution timestamp.

## 24.3 Execution Counter

The system should report:

- Target scenarios: 10,000,000.
- Completed scenarios: actual recorded count.
- Failed scenarios: actual recorded count.
- Remaining scenarios: target minus completed count, bounded at zero.
- Completion percentage: completed / target × 100.

Never display 10 million completed unless the engine has actually executed and logged them.

## 24.4 Efficient Testing

Possible methods:
- Vectorized calculations.
- Parallel processing.
- Parameter pruning.
- Distributed computation.
- GPU acceleration where suitable.
- Early rejection of invalid parameter sets.

Do not sacrifice data correctness for speed.

## 24.5 Scenario Conclusion

A scenario count alone does not prove robustness.

Report:
- Number of unique scenarios.
- Number of independent historical periods.
- Number of instruments.
- Out-of-sample performance.
- Parameter stability.
- Sensitivity to costs.
- Worst-case drawdown.
- Remaining uncertainty.

---

# 25. INDICATOR FAILURE CONDITIONS

Do not trust a signal blindly when:

- Market is extremely choppy.
- Spread is unusually wide.
- Liquidity is poor.
- Major news is imminent.
- Price data is incomplete.
- Volume is unreliable.
- Indicator is not warmed up.
- Higher timeframe contradicts the setup.
- Price has already moved too far.
- Risk/reward is poor.
- Stop loss cannot be defined.
- The setup relies on repainting or future information.

Possible decision:
WAIT or NO TRADE.

---

# 26. REPAINTING AND LOOK-AHEAD WARNINGS

A non-repainting indicator should not revise confirmed historical signals using future data.

Potential risks:
- ZigZag pivot confirmation.
- Fractal confirmation.
- Future-confirmed swing points.
- Centered moving averages.
- Higher timeframe unfinished candles.
- Pivot indicators using future bars.
- Security/request functions with incorrect look-ahead settings.
- Retrospective chart annotations.

Always distinguish:
- Developing signal.
- Confirmed signal.
- Historical signal visible only after future confirmation.

Backtests must use information available at the actual decision time.

---

# 27. MARKET-SPECIFIC ADJUSTMENTS

## Forex
- Check broker-specific tick volume.
- Consider session overlap.
- Monitor central-bank events.
- Account for spread and swaps.
- Verify pip and lot calculations.

## Crypto
- Identify the exchange.
- Distinguish spot and perpetual futures.
- Check funding and open interest.
- Account for 24/7 trading.
- Watch exchange-specific volume.
- Consider liquidation and volatility risk.

## Indian Stocks
- Verify NSE/BSE instrument.
- Use correct market session.
- Check corporate actions.
- Check adjusted historical prices.
- Account for circuit limits and liquidity.
- Verify lot sizes for derivatives.
- Monitor earnings and regulatory events.

## Global Stocks
- Verify exchange and currency.
- Account for market holidays.
- Check earnings and corporate actions.
- Use appropriate session and timezone.

## Indices
- Confirm whether data represents cash index, futures or CFD.
- Check contract specifications.
- Do not assume all providers report identical volume.

## Commodities
- Verify contract month.
- Consider expiry and rollover.
- Check contract multiplier and tick value.
- Account for seasonality and inventory reports where relevant.

---

# 28. TECHNICAL ANALYSIS REPORT FORMAT

Every technical analysis report must use natural Hinglish.

## Required Output

### 1. Market Details
- Instrument:
- Exchange:
- Market:
- Current price:
- Data timestamp:
- Timeframe:

### 2. Data Quality
- Data source:
- OHLC availability:
- Volume availability:
- Data limitations:

### 3. Market Structure
- Trend:
- Swing highs:
- Swing lows:
- BOS/CHoCH:
- Support:
- Resistance:

### 4. Indicator Readings
For every indicator actually calculated:
- Name:
- Setting:
- Actual reading:
- Interpretation:
- Timeframe:

Never invent missing readings.

### 5. Momentum and Volatility
- Momentum:
- Trend strength:
- Volatility regime:
- Divergence:

### 6. Volume and Order Flow
- Volume context:
- VWAP:
- Volume profile:
- Delta/CVD if available:
- Data limitations:

### 7. Multi-Timeframe View
- Higher timeframe:
- Middle timeframe:
- Entry timeframe:

### 8. Trade Decision
One of:
- BUY
- SELL
- WAIT
- NO TRADE

### 9. Trade Plan
Only if data supports it:
- Entry zone:
- Trigger:
- Stop loss:
- Target 1:
- Target 2:
- Target 3:
- Risk/reward:
- Position size:

### 10. Scenario Validation
- Actual scenarios executed:
- Target:
- Historical sample:
- Out-of-sample status:
- Monte Carlo status:
- Validation limitations:

### 11. Risk Warnings
Explain the most important risks and invalidation conditions.

### 12. Final Explanation
Explain in simple Hinglish why the decision was made.

---

# 29. FINAL OPERATING RULES

1. Indicators are tools, not guarantees.
2. Price structure remains essential.
3. Never invent readings.
4. Never claim live access without live data.
5. Never claim a backtest ran when it did not.
6. Never claim ten million scenarios were completed without execution logs.
7. Never treat correlated indicators as independent proof.
8. Never use future information in a backtest.
9. Never ignore fees, spread and slippage.
10. Never force a BUY or SELL.
11. WAIT is a valid decision.
12. NO TRADE is a valid decision.
13. Use only confirmed data for confirmed claims.
14. Explain uncertainty clearly.
15. Present all user-facing analysis in natural Hinglish.
16. Prefer a small number of well-validated indicators over a large number of redundant indicators.
17. Explain every important calculation and trading implication.
18. Separate facts, assumptions and hypotheses.
19. Preserve capital before pursuing returns.
20. Do not promise profits or guaranteed accuracy.

---

# END OF TECHNICAL ANALYSIS MASTER ENCYCLOPEDIA V2

