
# VOLUME ANALYSIS — COMPLETE A–Z MASTER ENGINE
Version: 1.0
Category: Volume Analysis, Volume Profile, VWAP & Order Flow
Parent Skill: AI Trading Analyst
Output Language: Natural Hinglish

---

# 1. PURPOSE AND OBJECTIVES

This reference defines a comprehensive volume-analysis system for professional trading research.

The system must analyze:

- Trading volume.
- Relative volume.
- Volume expansion and contraction.
- Buying and selling participation.
- Volume-price relationship.
- Volume divergence.
- Volume climax.
- Accumulation and distribution.
- Volume at Price.
- Volume Profile.
- VWAP and Anchored VWAP.
- Bid/Ask volume.
- Volume Delta.
- Cumulative Volume Delta.
- Footprint charts.
- Order-book liquidity.
- Absorption and imbalance.
- Open interest and derivatives participation.
- Market-specific volume characteristics.
- Volume-based strategy development.
- Backtesting and quantitative validation.

**Core rule:** Volume is evidence of trading activity, not direct proof of buyer or seller intention.

Every volume observation must be interpreted with price action, market structure, liquidity, timeframe and data quality.

---

# 2. WHAT IS TRADING VOLUME?

Trading volume measures the quantity of an instrument traded during a specified period.

Depending on the market, volume may represent:

- Shares.
- Contracts.
- Coins or tokens.
- Lots.
- Units.
- Base currency quantity.
- Quote currency value.

Never assume all platforms calculate volume in the same way.

## 2.1 Volume versus turnover

Volume measures quantity traded.

Turnover measures the monetary value of transactions.

Example:

A stock trades 10,000 shares at an average price of ₹100.

Approximate turnover:

```text
10,000 × ₹100 = ₹10,00,000
```

Turnover and volume provide different information.

## 2.2 Tick volume

Tick volume measures the number of price updates or ticks within a period.

It does not necessarily represent actual traded contracts or shares.

Commonly encountered in OTC Forex feeds.

Use tick volume as a proxy only when its limitations are understood.

## 2.3 Real volume

Real volume represents actual reported traded quantity from a market data source.

It may still be incomplete because of:

- Exchange coverage.
- Consolidated versus single-exchange feeds.
- Reporting delays.
- Dark-pool reporting.
- OTC market fragmentation.
- Data-provider limitations.

## 2.4 Volume data categories

Classify volume data as:

```text
EXCHANGE_REPORTED_VOLUME
CONSOLIDATED_VOLUME
SINGLE_EXCHANGE_VOLUME
TICK_VOLUME
BASE_ASSET_VOLUME
QUOTE_CURRENCY_VOLUME
CONTRACT_VOLUME
UNKNOWN_VOLUME_TYPE
```

If the volume type is unknown, clearly disclose it.

---

# 3. VOLUME DATA QUALITY

Before analyzing volume, validate the data.

Check:

1. Timestamp.
2. Exchange.
3. Instrument.
4. Timeframe.
5. Trading session.
6. Volume unit.
7. Duplicate records.
8. Missing candles.
9. Abnormal spikes.
10. Corporate actions.
11. Contract expiry.
12. Exchange reporting differences.
13. Feed delays.
14. Timezone consistency.

## 3.1 Invalid volume conditions

Flag:

- Negative volume.
- Missing volume.
- Impossible volume values.
- Duplicate timestamps.
- Unexplained extreme spikes.
- Inconsistent units.
- Incorrect session boundaries.
- Volume attached to incomplete candles.

Do not silently replace missing volume with zero.

## 3.2 Volume data confidence

Use:

```text
HIGH
MEDIUM
LOW
UNKNOWN
```

Example:

- Exchange-reported stock volume: potentially high, subject to feed quality.
- Broker-specific Forex tick volume: proxy data.
- Unverified screenshot volume: limited confidence.
- Missing volume: unavailable.

---

# 4. BASIC VOLUME INTERPRETATION

## 4.1 High volume

High volume indicates unusually high trading activity relative to a suitable baseline.

Possible explanations:

- Strong participation.
- News reaction.
- Breakout.
- Capitulation.
- Distribution.
- Absorption.
- Liquidation.
- Event-driven trading.

High volume is not automatically bullish or bearish.

## 4.2 Low volume

Low volume indicates reduced activity relative to the selected baseline.

Possible explanations:

- Consolidation.
- Reduced participation.
- Holiday trading.
- Low-liquidity session.
- Pullback.
- Lack of conviction.

Low volume does not automatically predict reversal.

## 4.3 Increasing volume

Check whether increasing volume accompanies:

- Price expansion.
- Breakout.
- Breakdown.
- Reversal.
- Volatility expansion.
- News-driven movement.

## 4.4 Decreasing volume

Potentially relevant during:

- Weakening trends.
- Pullbacks.
- Consolidation.
- Failed continuation.
- Low-participation breakouts.

Interpretation depends on location and price behavior.

---

# 5. RELATIVE VOLUME

Relative Volume compares current volume with historical volume for a defined baseline.

Basic formula:

```text
RVOL = Current Volume / Average Historical Volume
```

Example:

Current volume = 150,000 shares.

Average volume = 100,000 shares.

RVOL = 1.5.

This means current volume is 1.5 times the selected average.

## 5.1 Python calculation

```python
def calculate_rvol(current_volume, average_volume):
    if average_volume is None or average_volume <= 0:
        return None

    if current_volume is None or current_volume < 0:
        return None

    return current_volume / average_volume
```

## 5.2 Relative volume categories

Illustrative thresholds:

| RVOL | Interpretation |
|---|---|
| Below 0.5 | Very low relative activity |
| 0.5–0.8 | Below average |
| 0.8–1.2 | Near average |
| 1.2–2.0 | Elevated |
| 2.0–3.0 | High |
| Above 3.0 | Extremely elevated |

These are configurable research thresholds, not universal market laws.

## 5.3 Time-of-day relative volume

Intraday volume varies naturally throughout the trading session.

Compare current volume with the same time-of-day historical periods.

Example:

Compare today's first 30-minute volume with the first 30-minute volume of previous sessions.

Do not compare the opening 15 minutes with a full-day average without normalization.

---

# 6. VOLUME AND PRICE RELATIONSHIP

Volume must be analyzed alongside price movement.

## 6.1 Rising price with rising volume

Possible interpretation:

- Increasing participation.
- Stronger upward auction.
- Potential trend continuation.

Confirm with:

- Market structure.
- Candle closes.
- Breakout acceptance.
- Higher-timeframe direction.

## 6.2 Rising price with falling volume

Possible interpretation:

- Weakening participation.
- Reduced demand.
- Potentially fragile rally.

However, volume may naturally decline during a controlled pullback or low-activity session.

## 6.3 Falling price with rising volume

Possible interpretation:

- Strong selling activity.
- Liquidation.
- Panic.
- Distribution.
- Breakdown participation.

Do not assume every high-volume decline is institutional selling.

## 6.4 Falling price with falling volume

Possible interpretation:

- Reduced selling participation.
- Weak pullback.
- Decreasing activity.

Check whether buyers actually return before considering a bullish entry.

---

# 7. VOLUME EXPANSION AND CONTRACTION

## 7.1 Volume expansion

Identify volume expansion using:

- RVOL.
- Moving average of volume.
- Standard deviation.
- Time-of-day comparison.
- Percentile ranking.

Example:

```python
def volume_expansion(current_volume, average_volume, multiplier=1.5):
    if average_volume is None or average_volume <= 0:
        return False

    return current_volume >= average_volume * multiplier
```

## 7.2 Volume contraction

A contraction may indicate reduced activity.

Measure:

- Volume relative to recent average.
- Number of declining-volume candles.
- Price range compression.
- ATR contraction.

## 7.3 Volume dry-up

Volume dry-up occurs when activity becomes unusually low.

Potential context:

- Controlled trend pullback.
- Consolidation.
- Pre-breakout compression.

It does not guarantee an upcoming breakout.

---

# 8. VOLUME CLIMAX

## 8.1 Buying climax

Potential characteristics:

- Extended bullish movement.
- Exceptional volume.
- Wide candle range.
- Large upper wick or weak close.
- Failure to continue upward.

Possible interpretations:

- Aggressive buying.
- Profit booking.
- Absorption.
- Distribution.

## 8.2 Selling climax

Potential characteristics:

- Extended bearish movement.
- Exceptional volume.
- Wide range.
- Strong lower-wick rejection.
- Recovery or stabilization.

Possible interpretations:

- Panic selling.
- Liquidation.
- Absorption.
- Capitulation.

## 8.3 Climax confirmation

Look for:

1. Subsequent candles.
2. Structure change.
3. Failed continuation.
4. Relative volume normalization.
5. Support/resistance interaction.
6. Follow-through.

A climax label must be based on measurable thresholds.

---

# 9. VOLUME DIVERGENCE

## 9.1 Price-volume bearish divergence

Example:

- Price makes a higher high.
- Participation decreases relative to comparable previous highs.

Possible warning of weakening demand.

## 9.2 Price-volume bullish divergence

Example:

- Price makes a lower low.
- Selling volume decreases relative to comparable previous lows.

Possible warning of weakening selling pressure.

## 9.3 Divergence limitations

Volume divergence:

- Can persist for a long time.
- Can fail.
- Can appear during healthy trends.
- Can differ across exchanges.
- Depends on the selected swing points.

Never enter a trade solely because volume divergence exists.

---

# 10. ACCUMULATION AND DISTRIBUTION

## 10.1 Accumulation hypothesis

Possible characteristics:

- Extended decline followed by stabilization.
- Range formation.
- Repeated support defense.
- Selling pressure weakens.
- Demand response appears.
- Breakout with participation.

## 10.2 Distribution hypothesis

Possible characteristics:

- Extended rally followed by stabilization.
- Repeated resistance rejection.
- Failed upward attempts.
- Supply response.
- Breakdown with participation.

These are analytical hypotheses.

Volume alone cannot reveal the identity or intentions of institutional participants.

---

# 11. ON-BALANCE VOLUME (OBV)

OBV accumulates volume according to price direction.

Rules:

- Close above previous close: add volume.
- Close below previous close: subtract volume.
- Equal close: keep previous OBV.

Formula:

```text
OBV(today) =
    OBV(previous) + Volume(today), if close rises
    OBV(previous) - Volume(today), if close falls
    OBV(previous), if close is unchanged
```

Python:

```python
def calculate_obv(closes, volumes):
    if len(closes) != len(volumes):
        raise ValueError("Input lengths must match")

    if not closes:
        return []

    obv = [0]

    for i in range(1, len(closes)):
        if closes[i] > closes[i - 1]:
            obv.append(obv[-1] + volumes[i])
        elif closes[i] < closes[i - 1]:
            obv.append(obv[-1] - volumes[i])
        else:
            obv.append(obv[-1])

    return obv
```

Analyze:

- OBV trend.
- OBV breakout.
- Price-OBV divergence.
- OBV support/resistance.
- OBV confirmation.

OBV does not directly measure actual aggressive buying and selling.

---

# 12. MONEY FLOW INDEX (MFI)

MFI combines price and volume to estimate buying and selling pressure.

It is commonly called a volume-weighted momentum oscillator.

Typical period: 14.

Components:

- Typical Price.
- Raw Money Flow.
- Positive Money Flow.
- Negative Money Flow.
- Money Ratio.
- MFI.

Formula:

```text
Typical Price = (High + Low + Close) / 3

Raw Money Flow = Typical Price × Volume

Money Ratio = Positive Money Flow / Negative Money Flow

MFI = 100 - (100 / (1 + Money Ratio))
```

Common reference zones:

- Above 80: Potentially overbought.
- Below 20: Potentially oversold.

These are context indicators, not automatic reversal signals.

---

# 13. ACCUMULATION / DISTRIBUTION LINE

A/D Line uses close location within the candle range and volume.

Money Flow Multiplier:

```text
((Close - Low) - (High - Close)) / (High - Low)
```

Money Flow Volume:

```text
Money Flow Multiplier × Volume
```

A/D Line accumulates Money Flow Volume.

Python:

```python
def money_flow_multiplier(high, low, close):
    candle_range = high - low

    if candle_range <= 0:
        return 0.0

    return ((close - low) - (high - close)) / candle_range
```

Use A/D to study participation and price movement together.

Do not confuse A/D with actual exchange order-flow data.

---

# 14. CHAIKIN MONEY FLOW (CMF)

CMF estimates accumulation/distribution pressure over a rolling period.

Typical period: 20 or 21.

General interpretation:

- Positive CMF: Positive money-flow pressure.
- Negative CMF: Negative money-flow pressure.
- Zero-line cross: Possible change in pressure.

Always check price structure and data quality.

---

# 15. OTHER VOLUME INDICATORS

Understand and evaluate:

- Force Index.
- Ease of Movement.
- Volume Price Trend.
- Positive Volume Index.
- Negative Volume Index.
- Volume Oscillator.
- Chaikin Oscillator.
- Klinger Volume Oscillator.
- Relative Volume at Time.
- Volume Rate of Change.
- Volume Weighted Momentum.

For every indicator document:

1. Formula.
2. Inputs.
3. Default parameters.
4. Interpretation.
5. Limitations.
6. Market suitability.
7. Strategy usage.
8. Backtesting requirements.

Do not treat indicator signals as guaranteed predictions.

---

# 16. VWAP — VOLUME WEIGHTED AVERAGE PRICE

VWAP estimates the average traded price weighted by volume.

Formula:

```text
VWAP = Sum(Price × Volume) / Sum(Volume)
```

Typical price is often:

```text
Typical Price = (High + Low + Close) / 3
```

## 16.1 VWAP interpretation

- Price above VWAP: Trading above session volume-weighted average.
- Price below VWAP: Trading below session volume-weighted average.
- VWAP slope: Direction of the average price reference.
- VWAP reclaim: Price returns above VWAP.
- VWAP rejection: Price fails to hold above or below VWAP.

These conditions do not automatically define trade direction.

## 16.2 Python VWAP

```python
def calculate_vwap(highs, lows, closes, volumes):
    if not (
        len(highs) == len(lows) == len(closes) == len(volumes)
    ):
        raise ValueError("Input lengths must match")

    cumulative_pv = 0.0
    cumulative_volume = 0.0
    output = []

    for high, low, close, volume in zip(
        highs, lows, closes, volumes
    ):
        if volume is None or volume < 0:
            output.append(None)
            continue

        typical_price = (high + low + close) / 3

        cumulative_pv += typical_price * volume
        cumulative_volume += volume

        if cumulative_volume == 0:
            output.append(None)
        else:
            output.append(
                cumulative_pv / cumulative_volume
            )

    return output
```

This function calculates a cumulative VWAP over the supplied sequence. Reset it at the correct session boundary for session VWAP.

## 16.3 VWAP bands

Possible methods:

- Standard deviation bands.
- ATR bands.
- Percentage bands.

Document the chosen calculation.

## 16.4 VWAP strategies

- VWAP reclaim.
- VWAP rejection.
- VWAP pullback.
- VWAP trend continuation.
- VWAP deviation reversal.
- VWAP plus opening range.
- VWAP plus liquidity sweep.

Every strategy requires explicit entry, stop, target and invalidation rules.

---

# 17. ANCHORED VWAP

Anchored VWAP begins from a selected event or reference point.

Possible anchors:

- Major swing high.
- Major swing low.
- Earnings release.
- News event.
- Breakout candle.
- Significant gap.
- Monthly or yearly start.
- Major market low/high.

Important:

The anchor must be selected using information available at the time of the trade.

Do not use future information to choose historical anchors during backtesting.

---

# 18. VOLUME PROFILE

Volume Profile displays traded volume at different price levels.

Unlike ordinary volume bars, it groups volume by price.

Core concepts:

## 18.1 Point of Control (POC)

Price level with the highest volume in the selected profile period.

## 18.2 Value Area

A selected range containing a specified proportion of total profile volume.

A commonly used setting is 70%, but it is configurable.

## 18.3 Value Area High (VAH)

Upper boundary of the selected value area.

## 18.4 Value Area Low (VAL)

Lower boundary of the selected value area.

## 18.5 High Volume Node (HVN)

Price region with relatively high traded volume.

Potentially indicates acceptance or balance.

## 18.6 Low Volume Node (LVN)

Price region with relatively low traded volume.

May indicate faster movement or reduced acceptance.

## 18.7 Volume Profile types

- Session Profile.
- Fixed Range Profile.
- Visible Range Profile.
- Daily Profile.
- Weekly Profile.
- Monthly Profile.
- Composite Profile.
- Developing Profile.

## 18.8 Profile interpretation

Evaluate:

- Price relative to POC.
- VAH and VAL.
- Profile shape.
- Developing value area.
- Acceptance outside value.
- Rejection back into value.
- HVN/LVN transitions.
- Higher-timeframe profile.

## 18.9 Profile shapes

Common descriptive classifications:

- D-shaped.
- P-shaped.
- b-shaped.
- Double distribution.

These shapes are descriptive, not definitive predictions of market direction.

## 18.10 Volume-at-price calculation

A production implementation must define how candle volume is distributed across price levels.

OHLCV candles do not reveal the exact traded volume at every price.

Possible methods:

- Tick-level volume.
- Trade-level data.
- Footprint data.
- Approximate candle-range allocation.

Always label approximated profiles as approximations.

---

# 19. BID/ASK VOLUME

Bid/Ask volume separates transactions classified at bid and ask prices.

Simplified interpretation:

- Ask-side executed volume: Aggressive buying classification.
- Bid-side executed volume: Aggressive selling classification.

Important limitations:

- Classification depends on the data feed.
- Quote changes can complicate trade classification.
- OTC markets may lack consolidated data.
- Not all platforms expose reliable bid/ask volume.

Never claim exact aggressor identification if the source does not provide it.

---

# 20. VOLUME DELTA

Volume Delta is commonly defined as:

```text
Delta = Ask Volume - Bid Volume
```

Positive delta:

- More volume classified at ask.

Negative delta:

- More volume classified at bid.

Zero delta:

- Balanced classified volume.

Delta is meaningful only when its calculation and data source are known.

## 20.1 Delta divergence

Bullish delta divergence:

- Price makes a lower low.
- Delta becomes less negative or positive.

Bearish delta divergence:

- Price makes a higher high.
- Delta becomes less positive or negative.

Interpret with structure, location and confirmation.

---

# 21. CUMULATIVE VOLUME DELTA (CVD)

CVD accumulates volume delta.

```text
CVD(today) = CVD(previous) + Delta(today)
```

Analyze:

- CVD direction.
- Price-CVD divergence.
- CVD breakout.
- CVD failure.
- Session reset.
- Anchored CVD.

CVD is not universally comparable across exchanges or feeds.

---

# 22. FOOTPRINT CHART ANALYSIS

A footprint chart displays bid/ask executed volume at individual price levels within a candle or bar.

Study:

- Bid volume.
- Ask volume.
- Delta.
- Diagonal imbalance.
- Stacked imbalance.
- Absorption.
- Exhaustion.
- Volume clusters.
- POC within candle.
- High-volume rejection.

## 22.1 Imbalance

An imbalance compares buying and selling volume at corresponding price levels.

A common diagonal ratio is configurable, for example 3:1.

Never assume a 3:1 threshold is universally optimal.

## 22.2 Stacked imbalance

Several consecutive price levels show a directional imbalance.

Potentially indicates aggressive participation.

Require context and follow-through.

## 22.3 Absorption

Absorption may occur when aggressive orders trade heavily but price makes limited progress.

Potential clues:

- High executed volume.
- Limited price movement.
- Repeated tests.
- Failure to continue.
- Subsequent rejection.

Do not claim absorption from ordinary OHLCV alone.

Reliable detection requires suitable order-flow data.

## 22.4 Exhaustion

Potential exhaustion occurs when aggressive participation weakens near an extreme.

Require more than one observation.

---

# 23. ORDER BOOK AND LIQUIDITY

Analyze:

- Bid depth.
- Ask depth.
- Spread.
- Depth imbalance.
- Liquidity concentration.
- Order cancellations.
- Replenishment.
- Market impact.

Potential metrics:

```text
Spread = Best Ask - Best Bid

Depth Imbalance =
(Bid Depth - Ask Depth) /
(Bid Depth + Ask Depth)
```

Order-book data has important limitations:

- Orders can be cancelled.
- Displayed liquidity may not execute.
- Hidden liquidity may exist.
- Data can be delayed.
- Spoofing and layering can distort displayed depth.

Never treat displayed orders as guaranteed support or resistance.

---

# 24. OPEN INTEREST AND DERIVATIVES VOLUME

Volume and Open Interest are different.

Volume:

- Contracts traded during a period.

Open Interest:

- Outstanding contracts that remain open.

Study:

- Price up, OI up.
- Price up, OI down.
- Price down, OI up.
- Price down, OI down.
- Volume spikes.
- OI changes around expiry.
- Funding rate.
- Liquidations.

These combinations are contextual interpretations, not definitive proof of new long or short positions.

## 24.1 Futures

Consider:

- Contract expiry.
- Rollover.
- Front-month versus next-month volume.
- Contract multiplier.
- Exchange-specific reporting.

## 24.2 Options

Consider:

- Call volume.
- Put volume.
- Strike concentration.
- Expiry concentration.
- Implied volatility.
- Open interest.
- Bid/ask spread.
- Gamma exposure estimates.

Do not infer dealer positioning without reliable methodology and data.

---

# 25. MARKET-SPECIFIC VOLUME ANALYSIS

## 25.1 Forex

Consider:

- Tick volume versus real volume.
- Broker-specific feeds.
- Session overlap.
- Central bank announcements.
- Economic releases.
- Liquidity differences between pairs.

Spot Forex is decentralized. One broker's volume is not a complete global market volume measure.

## 25.2 Crypto

Consider:

- Exchange-specific volume.
- Aggregated exchange volume.
- Spot versus futures volume.
- Funding rate.
- Open interest.
- Liquidation volume.
- Wash trading concerns.
- Exchange outages.
- Weekend activity.

Do not treat one exchange's data as the entire crypto market.

## 25.3 Indian Stocks

Consider:

- NSE and BSE volume.
- Delivery quantity.
- Intraday volume.
- Block deals.
- Bulk deals.
- Corporate announcements.
- Market opening.
- Circuit limits.
- Stock liquidity.

Delivery data and intraday traded volume are different measurements.

## 25.4 Global Stocks

Consider:

- Primary exchange volume.
- Consolidated volume.
- Pre-market volume.
- After-hours volume.
- Earnings events.
- Corporate actions.
- Dark-pool reporting limitations.

## 25.5 Indices

Cash index volume may be unavailable or calculated differently.

Use suitable underlying futures, ETFs or exchange-specific products where appropriate.

## 25.6 Commodities

Consider:

- Contract month.
- Futures rollover.
- Inventory releases.
- Seasonal patterns.
- Delivery periods.
- Exchange volume.
- Spread trading.

---

# 26. VOLUME-BASED STRATEGIES

Every strategy must have objective and testable rules.

## Strategy 1: Relative Volume Breakout

Conditions:

1. Defined support/resistance.
2. Price closes beyond the level.
3. RVOL exceeds a validated threshold.
4. Follow-through confirms.
5. Risk-to-reward is acceptable.

Invalidation:

- Price returns into the range according to the defined failure rule.

## Strategy 2: Low-Volume Pullback

Conditions:

1. Established trend.
2. Impulse move.
3. Pullback volume contracts.
4. Price respects structural support/resistance.
5. Directional confirmation appears.

## Strategy 3: Volume Climax Reversal

Conditions:

1. Extended movement.
2. Statistically unusual volume.
3. Rejection or stabilization.
4. Structure shift.
5. Risk-defined entry.

## Strategy 4: VWAP Reclaim

Conditions:

1. Price trades below session VWAP.
2. Price reclaims VWAP.
3. Close or retest confirms.
4. Higher-timeframe context supports the trade.
5. Stop and target are defined.

## Strategy 5: VWAP Rejection

Conditions:

1. Price approaches VWAP.
2. Rejection occurs.
3. Confirmation appears.
4. Market structure agrees.
5. Risk is acceptable.

## Strategy 6: Volume Profile Value Area Rejection

Conditions:

1. Defined profile period.
2. Price tests VAH or VAL.
3. Rejection or acceptance behavior is visible.
4. Confirmation follows.
5. Target is based on profile structure.

## Strategy 7: POC Reversion

Conditions:

1. Price deviates from POC.
2. Market remains in a balanced regime.
3. Reversion signal appears.
4. Target and invalidation are defined.

Avoid using this strategy in a strong directional trend unless separately validated.

## Strategy 8: Delta Divergence

Conditions:

1. Reliable bid/ask data.
2. Price makes a new extreme.
3. Delta behavior diverges.
4. Structure confirms.
5. Entry and invalidation are defined.

## Strategy 9: Absorption Reversal

Conditions:

1. Reliable footprint or trade-level data.
2. Significant aggressive volume.
3. Limited price progress.
4. Repeated rejection or replenishment evidence.
5. Directional confirmation.

## Strategy 10: Opening Range Volume Breakout

Conditions:

1. Define the opening range.
2. Measure relative volume.
3. Wait for confirmed breakout.
4. Evaluate retest.
5. Define stop and target.
6. Include opening volatility and spread.

## Strategy 11: Volume Dry-Up Continuation

Conditions:

1. Existing trend.
2. Controlled pullback.
3. Reduced relative volume.
4. Structure remains intact.
5. Directional confirmation.

## Strategy 12: Price-Volume Divergence

Conditions:

1. Objectively defined swing points.
2. Price makes a new high/low.
3. Volume behavior diverges.
4. Structure confirms a change.
5. Risk is acceptable.

---

# 27. STRATEGY CONFLUENCE ENGINE

Potential confluences:

- Market structure.
- Support/resistance.
- Candlestick confirmation.
- Relative volume.
- VWAP.
- Volume Profile.
- Delta.
- CVD.
- Liquidity sweep.
- FVG.
- Order Block.
- Higher-timeframe alignment.
- News risk.

Do not count highly correlated indicators as independent confirmations.

Example:

RSI, Stochastic and CCI may all reflect momentum and should not automatically count as three independent confirmations.

---

# 28. VOLUME ANALYSIS SCORING

Score each factor from 0 to 5:

| Factor | Score |
|---|---:|
| Volume data quality | 0–5 |
| Relative volume | 0–5 |
| Price-volume alignment | 0–5 |
| Market structure | 0–5 |
| Volume location | 0–5 |
| VWAP/Profile context | 0–5 |
| Order-flow confirmation | 0–5 |
| Higher-timeframe agreement | 0–5 |
| Execution liquidity | 0–5 |
| Risk suitability | 0–5 |

Maximum: 50.

Rules:

- This is a heuristic score.
- It is not a win probability.
- Missing data must reduce confidence.
- Hard risk failures override the score.
- Thresholds must be validated per strategy and market.

---

# 29. VOLUME ANALYSIS PYTHON ARCHITECTURE

Recommended modules:

```text
volume_engine/
    data_validation.py
    volume_metrics.py
    relative_volume.py
    volume_indicators.py
    vwap.py
    anchored_vwap.py
    volume_profile.py
    volume_delta.py
    cumulative_delta.py
    footprint.py
    order_book.py
    open_interest.py
    volume_patterns.py
    strategy_engine.py
    backtesting.py
    reporting.py
    tests/
```

Each module must have:

- Defined input schema.
- Output schema.
- Error handling.
- Data validation.
- Unit tests.
- Logging.
- Version information.

---

# 30. VOLUME METRICS

Implement and validate:

1. Total volume.
2. Average volume.
3. Median volume.
4. Relative volume.
5. Time-of-day relative volume.
6. Volume moving average.
7. Volume standard deviation.
8. Volume percentile.
9. Volume rate of change.
10. Up/down volume classification.
11. Volume-price correlation.
12. Volume expansion.
13. Volume contraction.
14. Session volume.
15. Volume concentration.

Example:

```python
def volume_rate_of_change(current, previous):
    if previous is None or previous == 0:
        return None

    return ((current - previous) / previous) * 100
```

---

# 31. BACKTESTING VOLUME STRATEGIES

Every strategy must define:

- Instrument.
- Exchange.
- Data source.
- Volume type.
- Timeframe.
- Session.
- Entry conditions.
- Exit conditions.
- Position sizing.
- Fees.
- Spread.
- Slippage.
- Execution assumptions.

Measure:

- Total trades.
- Win rate.
- Net expectancy.
- Average win/loss.
- Profit factor.
- Maximum drawdown.
- Sharpe ratio.
- Sortino ratio.
- Recovery factor.
- MAE.
- MFE.
- Exposure.
- Turnover.
- Cost sensitivity.

## 31.1 Bias prevention

Prevent:

- Look-ahead bias.
- Survivorship bias.
- Data leakage.
- Repainting.
- Incomplete candle usage.
- Future-selected VWAP anchors.
- Incorrect session resets.
- Incorrect volume aggregation.
- Unrealistic fills.

## 31.2 Validation

Use:

- In-sample.
- Out-of-sample.
- Walk-forward.
- Regime analysis.
- Parameter sensitivity.
- Monte Carlo.
- Bootstrap.
- Stress testing.

Refer to `backtesting.md` for the complete research framework.

---

# 32. TEN-MILLION-SCENARIO TESTING FRAMEWORK

The target is up to 10,000,000 executable and auditable scenarios.

Possible scenario dimensions:

- RVOL thresholds.
- Volume moving-average periods.
- VWAP settings.
- Profile periods.
- Breakout buffers.
- Entry rules.
- Stop distances.
- Target multiples.
- Timeframes.
- Instruments.
- Sessions.
- Volatility regimes.
- Spread conditions.
- Slippage conditions.
- Market gaps.
- Historical resampling.
- Parameter perturbations.
- Synthetic stress cases.

Each scenario must have a unique record.

```python
scenario_record = {
    "scenario_id": None,
    "strategy_version": None,
    "dataset_id": None,
    "instrument": None,
    "timeframe": None,
    "volume_data_type": None,
    "parameter_hash": None,
    "simulation_type": None,
    "execution_status": "NOT_RUN",
    "trade_count": None,
    "net_return": None,
    "max_drawdown": None,
    "profit_factor": None,
    "expectancy": None
}
```

Separate reporting for:

- Historical trades.
- Parameter combinations.
- Monte Carlo simulations.
- Bootstrap samples.
- Synthetic stress scenarios.

Never claim 10 million scenarios completed unless logs verify that number of distinct completed runs.

---

# 33. MONTE CARLO AND STRESS TESTING

Test:

- Random trade sequence.
- Bootstrap resampling.
- Spread expansion.
- Slippage expansion.
- Missing volume data.
- Delayed feed.
- Exchange outage.
- Volatility shock.
- Gap risk.
- Low-liquidity conditions.
- Parameter perturbation.

Report:

- Median performance.
- Outcome percentiles.
- Drawdown distribution.
- Risk of ruin under assumptions.
- Cost sensitivity.
- Worst-case scenarios.

These are simulations, not future guarantees.

---

# 34. LIVE VOLUME MONITORING

Monitor:

- Current volume.
- RVOL.
- VWAP distance.
- POC distance.
- Value area position.
- Delta.
- CVD.
- Spread.
- Depth.
- Open interest.
- Funding.
- Session status.

Possible alerts:

```text
RVOL_SPIKE
VOLUME_DRY_UP
VOLUME_CLIMAX
VWAP_RECLAIM
VWAP_REJECTION
POC_RETEST
VALUE_AREA_BREAKOUT
DELTA_DIVERGENCE
CVD_DIVERGENCE
ABSORPTION_CANDIDATE
ORDER_BOOK_IMBALANCE
LOW_LIQUIDITY_WARNING
DATA_FEED_WARNING
```

Alerts must be distinguished from confirmed trade signals.

---

# 35. DATA SOURCES AND API INTEGRATION

Potential data categories:

- Exchange OHLCV.
- Broker market data.
- Consolidated equity feeds.
- Tick data.
- Trade-level data.
- Order-book snapshots.
- Futures volume.
- Options volume.
- Open interest.
- Funding data.

For every provider, verify:

- Coverage.
- Licensing.
- Latency.
- Historical depth.
- Rate limits.
- Volume definition.
- Exchange coverage.
- Timestamp format.
- Missing-data policy.

Do not assume an API is free or suitable without checking its current documentation.

Never expose API keys in code or reports.

---

# 36. FAILURE ANALYSIS

Common mistakes:

1. Treating high volume as automatically bullish.
2. Treating low volume as automatically bearish.
3. Ignoring time-of-day effects.
4. Comparing incompatible volume feeds.
5. Ignoring exchange fragmentation.
6. Treating tick volume as real traded volume.
7. Calling every high-volume candle absorption.
8. Using unverified Volume Profile approximations.
9. Ignoring futures rollover.
10. Ignoring corporate actions.
11. Using future information to select an anchor.
12. Ignoring spread and slippage.
13. Overfitting volume thresholds.
14. Treating divergence as a guaranteed reversal.
15. Using incomplete candles.
16. Confusing volume with open interest.
17. Claiming institutional activity without evidence.

---

# 37. PROFESSIONAL VOLUME ANALYSIS REPORT

All user-facing explanations must be natural Hinglish.

## Market Information

- Instrument:
- Exchange:
- Timeframe:
- Data timestamp:
- Data provider:
- Volume type:
- Session:

## Volume Condition

- Current volume:
- Average volume:
- RVOL:
- Volume trend:
- Volume expansion/contraction:
- Data quality:

## Price-Volume Relationship

- Price direction:
- Volume direction:
- Confirmation/divergence:
- Climax:
- Participation:

## VWAP

- Session VWAP:
- Price relative to VWAP:
- VWAP slope:
- Reclaim/rejection:

## Volume Profile

- POC:
- VAH:
- VAL:
- HVN:
- LVN:
- Acceptance/rejection:

## Order Flow

- Delta:
- CVD:
- Imbalance:
- Absorption:
- Footprint evidence:
- Data limitations:

## Strategy

- Strategy:
- Direction:
- Entry:
- Stop:
- TP1:
- TP2:
- TP3:
- R:R:
- Position size:
- Invalidation:

## Validation

- Backtest status:
- Out-of-sample status:
- Walk-forward status:
- Monte Carlo status:
- Scenario count:
- Strategy version:

## Final Decision

- BUY / SELL / WAIT / NO TRADE
- Evidence:
- Risks:
- Missing information:
- Next confirmation required:

---

# 38. FINAL OPERATING RULES

1. Volume is participation data, not guaranteed directional intent.
2. Always identify the volume data type.
3. Always validate the source.
4. Compare volume with an appropriate baseline.
5. Account for session and time-of-day effects.
6. Combine volume with price action.
7. Combine volume with market structure.
8. Use order-flow claims only when suitable data exists.
9. Never infer institutional intent from one candle.
10. Never invent volume, delta, CVD or profile values.
11. Include spread and slippage.
12. Avoid look-ahead and data leakage.
13. Backtest objective rules.
14. Keep scenario logs auditable.
15. Never claim unexecuted testing is complete.
16. Prefer WAIT or NO TRADE when evidence is insufficient.
17. Explain all important conclusions in natural Hinglish.
18. Technical terms may remain in English but must be explained simply.
19. Never guarantee trading profits.
20. Preserve risk management as the highest priority.

---

# 39. REFERENCE INTEGRATION

This file works with:

- `SKILL.md`
- `news-analysis.md`
- `fundamental-analysis.md`
- `candlestick-patterns.md`
- `chart-patterns.md`
- `technical-indicators.md`
- `ict-smc.md`
- `risk-management.md`
- `trade-management.md`
- `backtesting.md`
- `order-flow.md`
- `multi-timeframe-analysis.md`
- `market-structure.md`
- `support-resistance.md`
- `price-action-strategies.md`

Load relevant references based on the user's question.

---

# END OF VOLUME ANALYSIS MASTER REFERENCE
