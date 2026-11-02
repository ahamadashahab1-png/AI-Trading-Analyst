
# LIQUIDITY ANALYSIS — COMPLETE A–Z MASTER ENGINE
Version: 1.0
Category: Market Liquidity, ICT/SMC, Order Flow and Quantitative Liquidity Research
Parent Skill: AI Trading Analyst
Output Language: Natural Hinglish

---

# 1. PURPOSE AND OBJECTIVES

This reference defines a complete liquidity analysis and research framework.

The AI must understand and analyze:

- Market liquidity.
- Bid and ask liquidity.
- Buy-side liquidity (BSL).
- Sell-side liquidity (SSL).
- Internal and external liquidity.
- Equal highs and equal lows.
- Swing liquidity.
- Trendline liquidity.
- Range liquidity.
- Previous day, week and month liquidity.
- Session liquidity.
- Liquidity pools.
- Stop clusters.
- Liquidity sweeps.
- Stop hunts and stop runs.
- Liquidity raids.
- Inducement.
- Liquidity voids.
- Thin liquidity.
- Order-book depth.
- Spread and market impact.
- Hidden and displayed liquidity.
- Absorption and replenishment.
- ICT/SMC liquidity models.
- Liquidity-based entry and exit strategies.
- Institutional execution concepts.
- Automated liquidity detection.
- Historical validation and quantitative testing.

**Core principle:** Liquidity concepts are analytical models. A chart pattern cannot prove the location of every trader's stop-loss or reveal the identity and intention of institutional participants.

The AI must separate:

1. Directly observed market data.
2. Price-based liquidity estimates.
3. Order-book evidence.
4. ICT/SMC interpretations.
5. Unverified assumptions.

---

# 2. WHAT IS MARKET LIQUIDITY?

Market liquidity describes how easily an asset can be traded without causing excessive price impact.

A liquid market generally offers:

- Tight bid-ask spreads.
- Sufficient market depth.
- Frequent trading.
- Lower expected execution impact for a given order size.

An illiquid market may have:

- Wide spreads.
- Thin order books.
- Large price gaps.
- Slippage.
- Unstable execution.
- Difficulty entering or exiting positions.

## 2.1 Important distinction

There are two related but different meanings of liquidity.

### Market microstructure liquidity

This concerns:

- Bid and ask quotes.
- Resting orders.
- Executed volume.
- Market depth.
- Spread.
- Market impact.
- Order execution.

### Chart-based liquidity

This refers to price areas where stop orders or breakout orders may be clustered.

Examples:

- Equal highs.
- Equal lows.
- Previous swing highs.
- Previous swing lows.
- Range boundaries.
- Previous day high and low.

Chart-based liquidity is an estimate. It is not direct observation of hidden stop orders.

---

# 3. MARKET MICROSTRUCTURE FUNDAMENTALS

## 3.1 Bid price

The highest displayed price at which a buyer is currently willing to buy.

## 3.2 Ask price

The lowest displayed price at which a seller is currently willing to sell.

## 3.3 Bid-ask spread

```text
Spread = Best Ask - Best Bid
```

A smaller spread generally indicates better displayed execution conditions, although depth and volatility also matter.

## 3.4 Market orders

Market orders prioritize execution rather than a guaranteed execution price.

They can consume available liquidity and create price impact.

## 3.5 Limit orders

Limit orders specify a maximum purchase price or minimum selling price.

They may not execute.

## 3.6 Stop orders

A stop order becomes active after its trigger condition is met.

Exact behavior depends on broker, exchange and order type.

## 3.7 Resting liquidity

Displayed or known limit orders waiting for execution.

## 3.8 Aggressive liquidity taking

Marketable orders that execute against available resting orders.

## 3.9 Passive liquidity provision

Limit orders that provide displayed or non-displayed liquidity.

Do not assume every resting order will remain available.

---

# 4. LIQUIDITY CLASSIFICATION

The system must classify liquidity into separate categories.

```text
MARKET_DEPTH_LIQUIDITY
DISPLAYED_ORDER_LIQUIDITY
HIDDEN_LIQUIDITY
EXECUTED_VOLUME
ESTIMATED_STOP_LIQUIDITY
BUY_SIDE_LIQUIDITY
SELL_SIDE_LIQUIDITY
INTERNAL_LIQUIDITY
EXTERNAL_LIQUIDITY
SESSION_LIQUIDITY
SWING_LIQUIDITY
RANGE_LIQUIDITY
OPTIONS_RELATED_LIQUIDITY
UNKNOWN_LIQUIDITY
```

Each category must include its source and confidence.

---

# 5. BUY-SIDE LIQUIDITY (BSL)

Buy-side liquidity generally refers to potential buy orders above important price highs.

Possible chart-based locations:

- Equal highs.
- Previous swing high.
- Previous day high.
- Previous week high.
- Previous month high.
- Range high.
- Session high.
- Major resistance high.
- Trendline-related highs.

Potential order types near these areas:

- Buy stops.
- Breakout entries.
- Stop-loss orders from short positions.
- Other conditional orders.

Important:

The exact composition and location of orders are not visible from ordinary candles.

## 5.1 BSL detection

Identify:

1. Relevant swing highs.
2. Repeated highs.
3. Equal-high clusters.
4. Previous session highs.
5. Range boundaries.
6. Higher-timeframe highs.
7. Nearby market structure.

## 5.2 BSL strength

Evaluate:

- Number of interactions.
- Time since formation.
- Price distance.
- Higher-timeframe significance.
- Visibility of the level.
- Subsequent reactions.
- Whether liquidity has already been traded through.

A frequently tested high is not automatically stronger than a fresh, significant high.

---

# 6. SELL-SIDE LIQUIDITY (SSL)

Sell-side liquidity generally refers to potential sell orders below important price lows.

Possible locations:

- Equal lows.
- Previous swing low.
- Previous day low.
- Previous week low.
- Previous month low.
- Range low.
- Session low.
- Major support low.
- Trendline-related lows.

Potential orders:

- Sell stops.
- Breakdown entries.
- Stop-loss orders from long positions.
- Other conditional orders.

## 6.1 SSL detection

Identify:

1. Relevant swing lows.
2. Repeated lows.
3. Equal-low clusters.
4. Previous session lows.
5. Range boundaries.
6. Higher-timeframe lows.
7. Nearby market structure.

## 6.2 SSL strength

Evaluate:

- Swing significance.
- Number of interactions.
- Age of the level.
- Higher-timeframe alignment.
- Price distance.
- Previous sweep behavior.
- Whether the level remains relevant.

---

# 7. EQUAL HIGHS AND EQUAL LOWS

## 7.1 Equal highs

Two or more highs that occur within a defined price tolerance.

They may indicate a visible area where buy stops or breakout orders could be concentrated.

## 7.2 Equal lows

Two or more lows within a defined price tolerance.

They may indicate a visible area where sell stops or breakout orders could be concentrated.

## 7.3 Tolerance calculation

Equal highs and lows should not require exact price equality.

Possible tolerance methods:

- Tick-size tolerance.
- Percentage tolerance.
- ATR-based tolerance.
- Instrument-specific tolerance.

Example:

```python
def prices_are_equal(a, b, tolerance):
    if tolerance < 0:
        return False

    return abs(a - b) <= tolerance
```

## 7.4 Cluster detection

A valid cluster should contain:

- At least two meaningful swing points.
- A consistent tolerance rule.
- Ordered timestamps.
- A known timeframe.
- Price-level boundaries.
- Cluster invalidation conditions.

## 7.5 Equal-high/low quality

Evaluate:

- Number of touches.
- Distance between points.
- Time between points.
- Swing prominence.
- Trend context.
- Volume.
- Higher-timeframe significance.

Do not interpret every pair of similar highs as a meaningful liquidity pool.

---

# 8. SWING HIGH AND SWING LOW LIQUIDITY

## 8.1 Swing high

A swing high is a local price high relative to surrounding candles.

A common pivot definition:

- High is greater than highs of N candles before.
- High is greater than or equal to highs of N candles after.

The exact equality rule must be defined consistently.

## 8.2 Swing low

A swing low is a local low relative to surrounding candles.

## 8.3 Pivot confirmation

A pivot requiring future candles is not known in real time until the confirmation candles have closed.

Backtests must use the actual confirmation timestamp.

Never assign a pivot to an earlier time and trade it before it was observable.

## 8.4 Major and minor swing liquidity

Classify:

- Major external swing.
- Intermediate swing.
- Internal swing.
- Minor intrabar swing.

The classification must use explicit rules rather than visual preference alone.

---

# 9. INTERNAL AND EXTERNAL LIQUIDITY

## 9.1 External liquidity

Potential liquidity outside a defined major range or dealing range.

Examples:

- Major swing high.
- Major swing low.
- Range boundary.
- Higher-timeframe extreme.

## 9.2 Internal liquidity

Potential liquidity inside a larger defined range.

Examples:

- Internal swing highs.
- Internal swing lows.
- Minor equal highs/lows.
- Internal consolidation boundaries.

## 9.3 Dealing range

A defined range between meaningful high and low points.

The range must specify:

- Start time.
- End time.
- High.
- Low.
- Selection method.
- Timeframe.

## 9.4 Internal-to-external liquidity model

Potential sequence:

1. Price trades through internal liquidity.
2. Price moves toward external liquidity.
3. External liquidity is reached or rejected.
4. Structure changes or continues.

This is a model for analysis, not a guaranteed sequence.

---

# 10. LIQUIDITY SWEEP

A liquidity sweep is a price event where price moves through a previously identified high or low.

Bullish reversal candidate:

1. Price trades below a relevant low.
2. Price returns above the level.
3. Downside continuation fails.
4. Bullish displacement or structure confirmation appears.

Bearish reversal candidate:

1. Price trades above a relevant high.
2. Price returns below the level.
3. Upside continuation fails.
4. Bearish displacement or structure confirmation appears.

## 10.1 Sweep versus breakout

A sweep candidate requires a return or rejection under a predefined rule.

A breakout may show sustained acceptance beyond the level.

## 10.2 Sweep confirmation

Check:

- Close location.
- Subsequent candle behavior.
- Displacement.
- BOS/CHoCH/MSS.
- Volume.
- Order flow.
- Higher-timeframe context.
- News conditions.

## 10.3 Sweep invalidation

A reversal hypothesis weakens when price accepts beyond the swept level and continues in the breakout direction.

Do not call every break above or below a level a sweep.

---

# 11. LIQUIDITY RAID AND STOP RUN

These terms are often used to describe rapid movement through a visible liquidity area.

Possible evidence:

- Break beyond a prior extreme.
- Rapid price expansion.
- Return inside the original range.
- Strong rejection.
- Subsequent structure shift.

A chart cannot prove that an institution deliberately hunted stops.

Use wording such as:

- Potential stop-run behavior.
- Liquidity sweep candidate.
- Breakout failure.
- Price traded beyond visible liquidity.

Avoid claiming hidden institutional intentions as verified facts.

---

# 12. INDUCEMENT

Inducement is an ICT/SMC interpretation of a price move that may attract traders before price moves toward another liquidity area.

Potential examples:

- Minor swing before major liquidity.
- Small pullback that appears to confirm continuation.
- Local breakout before a reversal.
- Internal liquidity before external liquidity.

Rules:

1. Define the relevant higher-timeframe context.
2. Identify the internal swing.
3. Identify the external target.
4. Observe price interaction.
5. Require independent confirmation.
6. Record the exact definition used.

Inducement is not directly observable order-flow data.

Different trading educators may define it differently. The system must document the selected definition.

---

# 13. TRENDLINE LIQUIDITY

Trendlines may create visible reference points.

Potential liquidity areas:

- Above repeated trendline highs.
- Below repeated trendline lows.
- Beyond a trendline break.
- Around a retest.

A trendline must be drawn using objective swing points.

Do not claim every trendline break is a stop hunt.

---

# 14. RANGE LIQUIDITY

A range may contain:

- Buy-side liquidity above range high.
- Sell-side liquidity below range low.
- Internal liquidity near minor highs/lows.
- Potential breakout orders.
- Potential stop-loss orders.

## 14.1 Range high sweep

1. Define range high.
2. Observe price moving above it.
3. Check whether price accepts above.
4. If price returns inside, evaluate rejection.
5. Wait for confirmation.
6. Define invalidation.

## 14.2 Range low sweep

Apply the inverse logic below the range low.

## 14.3 Range expansion

A confirmed breakout may lead to price discovery outside the previous range.

Do not automatically fade every range breakout.

---

# 15. PREVIOUS PERIOD LIQUIDITY

Track:

- Previous Day High (PDH).
- Previous Day Low (PDL).
- Previous Week High (PWH).
- Previous Week Low (PWL).
- Previous Month High (PMH).
- Previous Month Low (PML).
- Previous Session High.
- Previous Session Low.
- Previous Year High/Low when relevant.

For every level store:

```text
Instrument
Exchange
Timeframe
Reference Period
Level Type
Price
Timestamp
Timezone
Source
Status
```

## 15.1 PDH/PDL

Useful for intraday context.

## 15.2 PWH/PWL

Useful for swing and higher-timeframe context.

## 15.3 PMH/PML

Useful for broader structural context.

## 15.4 Session levels

Define session times using the correct exchange timezone.

Never mix UTC and local time without conversion.

---

# 16. SESSION LIQUIDITY

Session definitions vary by instrument and daylight-saving rules.

Common Forex sessions:

- Asian session.
- London session.
- New York session.

Common concepts:

- Asian range.
- London high/low.
- New York high/low.
- London open.
- New York open.
- Session overlap.

## 16.1 Asian range

Define:

- Session start.
- Session end.
- Range high.
- Range low.
- Midpoint.
- Timezone.

## 16.2 London liquidity

Monitor:

- Asian range sweep.
- London opening volatility.
- Previous session extremes.
- Major economic releases.

## 16.3 New York liquidity

Monitor:

- London extremes.
- US economic releases.
- Equity market open.
- Futures activity.
- Session overlap.

## 16.4 Kill zones

ICT kill zones are time-based analytical concepts.

Their exact time definitions can differ by source and daylight-saving conventions.

Store the selected timezone and configuration. Do not hardcode an unverified universal schedule.

---

# 17. LIQUIDITY AND MARKET STRUCTURE

Combine liquidity with:

- HH/HL.
- LH/LL.
- BOS.
- CHoCH.
- MSS.
- Protected highs/lows.
- External structure.
- Internal structure.
- Displacement.

## 17.1 Bullish liquidity model

Potential sequence:

1. Bearish move approaches a relevant low.
2. Sell-side liquidity is traded through.
3. Price reclaims the level.
4. Bullish displacement occurs.
5. A meaningful lower high breaks.
6. Pullback forms.
7. Long entry is evaluated.

## 17.2 Bearish liquidity model

Potential sequence:

1. Bullish move approaches a relevant high.
2. Buy-side liquidity is traded through.
3. Price falls back below the level.
4. Bearish displacement occurs.
5. A meaningful higher low breaks.
6. Pullback forms.
7. Short entry is evaluated.

## 17.3 Structure must be objective

Specify:

- Swing algorithm.
- Confirmation requirement.
- Break threshold.
- Close versus wick rule.
- Timeframe.
- Invalidation.

---

# 18. LIQUIDITY AND FVG

Fair Value Gap can be evaluated after a displacement move.

Bullish FVG:

First candle high is below third candle low.

Bearish FVG:

First candle low is above third candle high.

Liquidity-based model:

1. Identify liquidity event.
2. Confirm displacement.
3. Detect FVG.
4. Observe retracement.
5. Evaluate entry.
6. Define invalidation.

FVG is not proof that unfilled institutional orders remain at that price.

---

# 19. LIQUIDITY AND ORDER BLOCKS

An Order Block must have an objective definition.

Potential validation:

- Defined pre-displacement candle or candle cluster.
- Subsequent directional displacement.
- Structure break.
- Zone boundaries.
- Retest behavior.
- Invalidation.

Combine with:

- Liquidity sweep.
- Market structure.
- FVG.
- Volume.
- Higher-timeframe context.

Never assume every opposing candle is an institutional Order Block.

---

# 20. LIQUIDITY VOID AND THIN LIQUIDITY

## 20.1 Liquidity void

A region where price moves rapidly with relatively little two-way trading or limited interaction.

Depending on the data, it may be approximated by:

- Large price gaps.
- Low traded volume.
- Rapid movement.
- Sparse order-book depth.

## 20.2 Thin order-book liquidity

A market has relatively little displayed depth near the current price.

This can increase potential market impact.

## 20.3 Liquidity void limitations

OHLCV candles alone cannot prove that a region had no resting orders.

Distinguish:

- Price gap.
- Low-volume area.
- Low order-book depth.
- ICT-style liquidity void.

These are related but not identical concepts.

---

# 21. ORDER BOOK LIQUIDITY ANALYSIS

Use suitable Level 2 or Level 3 data where available.

Analyze:

- Best bid.
- Best ask.
- Spread.
- Bid depth.
- Ask depth.
- Depth imbalance.
- Price-level concentration.
- Order additions.
- Order cancellations.
- Replenishment.
- Market impact.
- Execution probability.

## 21.1 Depth imbalance

```text
Depth Imbalance =
(Bid Depth - Ask Depth) /
(Bid Depth + Ask Depth)
```

Python:

```python
def depth_imbalance(bid_depth, ask_depth):
    if bid_depth < 0 or ask_depth < 0:
        return None

    total = bid_depth + ask_depth

    if total == 0:
        return None

    return (bid_depth - ask_depth) / total
```

## 21.2 Order-book limitations

- Displayed orders may be cancelled.
- Hidden orders may exist.
- Feeds may be delayed.
- Different exchanges have different depth.
- Spoofing can distort displayed liquidity.
- Depth is not the same as executed volume.

Never interpret displayed order-book depth as guaranteed future support or resistance.

---

# 22. ABSORPTION AND REPLENISHMENT

Absorption may occur when aggressive orders execute but price makes limited progress.

Potential evidence:

- High executed volume.
- Limited price movement.
- Repeated trading at a price.
- Replenishment of displayed liquidity.
- Failure to continue.
- Subsequent displacement.

Reliable analysis requires trade-level or suitable order-flow data.

OHLCV-only observations must be labeled as absorption candidates, not verified absorption.

---

# 23. LIQUIDITY AND VOLUME

Combine with `volume-analysis.md`.

Evaluate:

- Relative volume at sweep.
- Volume after sweep.
- Delta.
- CVD.
- Volume Profile.
- VWAP.
- Footprint.
- Absorption.
- Volume climax.

Example bullish candidate:

1. Price trades below SSL.
2. Returns above the level.
3. Relative volume expands.
4. Bearish continuation fails.
5. Bullish structure confirmation appears.

High volume does not guarantee a reversal.

---

# 24. LIQUIDITY AND PRICE ACTION

Combine with `price-action-strategies.md`.

Useful confirmation patterns:

- Pin bar.
- Engulfing.
- Rejection candle.
- Outside bar.
- Inside-bar failure.
- Breakout and retest.
- Failed breakout.
- Momentum displacement.

Pattern names must have reproducible definitions.

---

# 25. LIQUIDITY AND MULTI-TIMEFRAME ANALYSIS

Use three layers:

## Higher timeframe

Identify:

- Major external liquidity.
- Weekly/monthly extremes.
- Major structure.
- Large dealing range.
- Important zones.

## Intermediate timeframe

Identify:

- Internal liquidity.
- Session levels.
- Local equal highs/lows.
- Sweep candidates.
- Displacement.

## Lower timeframe

Identify:

- Confirmation.
- Entry trigger.
- Invalidation.
- Execution quality.

If timeframes conflict:

- Reduce confidence.
- Wait for confirmation.
- Prefer NO TRADE when risk cannot be controlled.

---

# 26. MARKET-SPECIFIC LIQUIDITY ANALYSIS

## 26.1 Forex

Consider:

- OTC market fragmentation.
- Broker-specific volume.
- Session liquidity.
- Currency pair liquidity.
- Spread.
- Economic releases.
- Rollover.
- Central bank announcements.

Do not claim a single retail broker feed represents all global Forex liquidity.

## 26.2 Cryptocurrency

Consider:

- Exchange-specific order books.
- Spot liquidity.
- Futures liquidity.
- Funding rates.
- Open interest.
- Liquidation clusters.
- Exchange outages.
- Weekend activity.
- Token unlocks.
- Fragmented liquidity.

Never combine exchange volumes without verifying units and methodology.

## 26.3 Indian Stocks

Consider:

- NSE and BSE.
- Bid/ask depth.
- Delivery volume.
- Intraday volume.
- Circuit limits.
- Block and bulk deals.
- Opening gaps.
- Corporate announcements.
- Stock-specific liquidity.

## 26.4 Global Stocks

Consider:

- Primary exchange.
- Consolidated volume.
- Pre-market liquidity.
- After-hours liquidity.
- Dark-pool reporting limitations.
- Earnings.
- Trading halts.

## 26.5 Indices

Consider:

- Cash index limitations.
- Futures depth.
- ETF liquidity.
- Constituents.
- Opening gaps.
- Index rebalancing.

## 26.6 Commodities

Consider:

- Contract month.
- Expiry.
- Rollover.
- Delivery.
- Inventory reports.
- Seasonal liquidity.
- Contract specifications.

## 26.7 Futures

Consider:

- Tick size.
- Tick value.
- Contract multiplier.
- Open interest.
- Expiry.
- Roll dates.
- Margin.
- Limit moves.

## 26.8 Options

Consider:

- Strike-level liquidity.
- Bid/ask spread.
- Open interest.
- Traded volume.
- Expiry.
- Implied volatility.
- Gamma exposure estimates.
- Exercise and settlement.

Option-chain data does not directly reveal the exact location of all dealer hedging orders.

---

# 27. LIQUIDITY-BASED STRATEGIES

Every strategy must define objective entry, stop, target and invalidation rules.

## Strategy 1: Buy-Side Liquidity Sweep Reversal

Conditions:

1. Relevant BSL identified.
2. Price trades above it.
3. Price returns below.
4. Bearish confirmation appears.
5. Structure supports reversal.
6. Risk is acceptable.

Potential entry:

- Break of confirmation candle.
- Retest of failed breakout area.

Invalidation:

- Price accepts above the swept high according to the strategy rule.

## Strategy 2: Sell-Side Liquidity Sweep Reversal

Conditions:

1. Relevant SSL identified.
2. Price trades below it.
3. Price returns above.
4. Bullish confirmation appears.
5. Structure supports reversal.
6. Risk is acceptable.

## Strategy 3: Equal High Sweep

- Detect equal highs.
- Define tolerance.
- Wait for a sweep.
- Confirm rejection.
- Evaluate short setup.

## Strategy 4: Equal Low Sweep

- Detect equal lows.
- Define tolerance.
- Wait for a sweep.
- Confirm recovery.
- Evaluate long setup.

## Strategy 5: Previous Day High/Low Sweep

- Mark PDH and PDL.
- Observe price interaction.
- Distinguish acceptance from rejection.
- Confirm with structure.
- Plan entry and invalidation.

## Strategy 6: Asian Range Liquidity Model

- Define Asian session.
- Mark high/low.
- Monitor London or another specified session.
- Evaluate sweep.
- Require confirmation.
- Include session-specific risk.

## Strategy 7: Internal-to-External Liquidity Target

- Define dealing range.
- Identify internal liquidity.
- Identify external liquidity.
- Observe directional structure.
- Set target based on a valid external level.

## Strategy 8: Liquidity Sweep + FVG Retracement

- Identify sweep.
- Confirm displacement.
- Detect FVG.
- Wait for retracement.
- Confirm entry.
- Set invalidation beyond the structural extreme.

## Strategy 9: Liquidity Sweep + Order Block

- Identify sweep.
- Confirm displacement and structure break.
- Define Order Block objectively.
- Wait for retracement.
- Evaluate entry.

## Strategy 10: Liquidity Breakout Continuation

- Identify important liquidity boundary.
- Confirm acceptance beyond it.
- Observe follow-through.
- Evaluate retest.
- Avoid fading a valid breakout without evidence.

## Strategy 11: Range Liquidity Rejection

- Define range.
- Identify boundary liquidity.
- Observe rejection.
- Confirm return into range.
- Target midpoint or opposing boundary when justified.

## Strategy 12: Liquidity Void Continuation

- Identify rapid movement or thin-volume region.
- Verify with suitable data.
- Confirm directional structure.
- Evaluate continuation.
- Define risk.

---

# 28. ENTRY, STOP-LOSS AND TARGET FRAMEWORK

Every trade plan must specify:

- Instrument.
- Exchange.
- Direction.
- Timeframe.
- Liquidity level.
- Setup type.
- Entry trigger.
- Entry price or condition.
- Stop-loss.
- TP1.
- TP2.
- TP3.
- Position size.
- Risk amount.
- R:R.
- Invalidation.
- News risk.
- Data timestamp.

## 28.1 Entry methods

- Market entry.
- Limit entry.
- Stop entry.
- Confirmation entry.
- Breakout entry.
- Retest entry.

## 28.2 Stop-loss

Possible placement:

- Beyond sweep extreme.
- Beyond protected swing.
- Beyond structure.
- Beyond relevant zone.
- ATR-adjusted.

Do not place a stop solely to create a desired R:R.

## 28.3 Targets

Potential targets:

- Internal liquidity.
- External liquidity.
- Previous swing.
- Opposing range boundary.
- PDH/PDL.
- PWH/PWL.
- POC or value area.
- Measured move.

Targets must be based on actual chart levels and strategy rules.

---

# 29. POSITION SIZING AND EXECUTION RISK

Simplified calculation:

```python
def calculate_position_size(
    account_balance,
    risk_percent,
    entry,
    stop,
    value_per_price_unit=1.0
):
    risk_amount = account_balance * risk_percent / 100
    stop_distance = abs(entry - stop)

    if stop_distance <= 0:
        return None

    if value_per_price_unit <= 0:
        return None

    return risk_amount / (
        stop_distance * value_per_price_unit
    )
```

This is a simplified formula.

Production calculations must include:

- Contract multiplier.
- Lot size.
- Tick value.
- Pip value.
- Currency conversion.
- Fees.
- Spread.
- Slippage.
- Minimum quantity.
- Quantity step.
- Margin.

Liquidity risk must be included in expected execution costs.

---

# 30. LIQUIDITY QUALITY SCORING

Score each factor from 0 to 5:

| Factor | Score |
|---|---:|
| Level significance | 0–5 |
| Swing quality | 0–5 |
| Equal-high/low quality | 0–5 |
| Higher-timeframe alignment | 0–5 |
| Sweep evidence | 0–5 |
| Rejection confirmation | 0–5 |
| Structure confirmation | 0–5 |
| Volume/order-flow evidence | 0–5 |
| Execution liquidity | 0–5 |
| Risk suitability | 0–5 |

Maximum: 50.

Important:

- This is a heuristic score.
- It is not a win probability.
- Missing data reduces confidence.
- A hard risk failure overrides the score.
- Strategy thresholds require historical validation.

---

# 31. LIQUIDITY DETECTION ENGINE

Recommended processing pipeline:

```text
MARKET DATA INPUT
       |
       v
DATA VALIDATION
       |
       v
SESSION AND TIMEZONE NORMALIZATION
       |
       v
SWING HIGH / LOW DETECTION
       |
       v
EQUAL HIGH / LOW CLUSTERING
       |
       v
PREVIOUS PERIOD LEVELS
       |
       v
INTERNAL / EXTERNAL LIQUIDITY
       |
       v
SWEEP / BREAKOUT CLASSIFICATION
       |
       v
MARKET STRUCTURE CONFIRMATION
       |
       v
VOLUME / ORDER FLOW CONFIRMATION
       |
       v
MULTI-TIMEFRAME VALIDATION
       |
       v
ENTRY / SL / TP
       |
       v
RISK VALIDATION
       |
       v
BUY / SELL / WAIT / NO TRADE
```

## 31.1 Liquidity object schema

```python
liquidity_level = {
    "level_id": None,
    "instrument": None,
    "exchange": None,
    "timeframe": None,
    "level_type": None,
    "direction": None,
    "price": None,
    "upper_boundary": None,
    "lower_boundary": None,
    "created_at": None,
    "confirmed_at": None,
    "source": None,
    "touch_count": None,
    "status": "ACTIVE",
    "confidence": None,
    "invalidation_rule": None
}
```

## 31.2 Liquidity event schema

```python
liquidity_event = {
    "event_id": None,
    "level_id": None,
    "event_type": None,
    "timestamp": None,
    "observed_price": None,
    "close_price": None,
    "volume": None,
    "data_source": None,
    "confirmation_status": "UNCONFIRMED",
    "invalidation_status": "NOT_INVALIDATED"
}
```

## 31.3 Event types

```text
LEVEL_CREATED
LEVEL_TESTED
LEVEL_SWEPT
BREAKOUT_CONFIRMED
BREAKOUT_FAILED
REJECTION_CONFIRMED
ACCEPTANCE_CONFIRMED
LEVEL_INVALIDATED
```

---

# 32. PYTHON LIQUIDITY DETECTION

## 32.1 Equal high/low detection

```python
def detect_equal_levels(
    prices,
    tolerance,
    minimum_touches=2
):
    if tolerance < 0:
        raise ValueError("Tolerance cannot be negative")

    if minimum_touches < 2:
        raise ValueError("At least two touches required")

    clusters = []

    for index, price in enumerate(prices):
        if price is None:
            continue

        matched = False

        for cluster in clusters:
            center = sum(cluster["prices"]) / len(cluster["prices"])

            if abs(price - center) <= tolerance:
                cluster["prices"].append(price)
                cluster["indices"].append(index)
                matched = True
                break

        if not matched:
            clusters.append({
                "prices": [price],
                "indices": [index]
            })

    return [
        cluster
        for cluster in clusters
        if len(cluster["prices"]) >= minimum_touches
    ]
```

This is a basic clustering example. Production systems should use confirmed swing points, objective clustering and tests for overlapping clusters.

## 32.2 Basic sweep candidate detection

```python
def detect_high_sweep(
    previous_high,
    current_high,
    current_close
):
    if current_high is None or current_close is None:
        return False

    return (
        current_high > previous_high
        and current_close < previous_high
    )


def detect_low_sweep(
    previous_low,
    current_low,
    current_close
):
    if current_low is None or current_close is None:
        return False

    return (
        current_low < previous_low
        and current_close > previous_low
    )
```

These functions identify simple wick-through-and-close-back conditions. They do not confirm a complete reversal or prove stop orders were triggered.

## 32.3 Data validation

Validate:

- OHLC relationships.
- Timestamp order.
- Missing candles.
- Duplicate candles.
- Tick size.
- Session boundaries.
- Timezone.
- Exchange.
- Contract expiry.
- Data source.

Never use a future-confirmed pivot before its actual confirmation time.

---

# 33. BACKTESTING LIQUIDITY STRATEGIES

Every strategy must define:

- Instrument.
- Exchange.
- Data source.
- Timeframe.
- Swing detection rules.
- Level detection rules.
- Sweep definition.
- Confirmation rules.
- Entry.
- Stop.
- Target.
- Position sizing.
- Fees.
- Spread.
- Slippage.
- Execution model.

Measure:

- Trade count.
- Win rate.
- Average win.
- Average loss.
- Expectancy.
- Profit factor.
- Maximum drawdown.
- Sharpe ratio.
- Sortino ratio.
- Recovery factor.
- MAE.
- MFE.
- Holding time.
- Exposure.
- Cost sensitivity.

Prevent:

- Look-ahead bias.
- Survivorship bias.
- Data leakage.
- Repainting.
- Future-confirmed swing usage.
- Incorrect session definitions.
- Unrealistic fills.
- Overfitting.

Refer to `backtesting.md` for the complete research methodology.

---

# 34. TEN-MILLION-SCENARIO TESTING FRAMEWORK

Target: Up to 10,000,000 executable, unique and auditable scenarios.

Possible dimensions:

- Swing lookback.
- Equal-level tolerance.
- Minimum touch count.
- Sweep buffer.
- Close-back rule.
- Confirmation candles.
- ATR filters.
- Volume thresholds.
- Session filters.
- Timeframes.
- Instruments.
- Stop methods.
- Target multiples.
- Spread.
- Slippage.
- Volatility regimes.
- News conditions.
- Parameter perturbations.
- Bootstrap samples.
- Monte Carlo sequences.
- Synthetic stress cases.

## 34.1 Scenario record

```python
scenario_record = {
    "scenario_id": None,
    "strategy_version": None,
    "dataset_id": None,
    "instrument": None,
    "timeframe": None,
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

## 34.2 Testing categories

Report separately:

- Historical trade simulations.
- Parameter combinations.
- Monte Carlo simulations.
- Bootstrap resampling.
- Synthetic stress scenarios.

These are not interchangeable.

## 34.3 Completion states

```text
NOT_RUN
PLANNED
RUNNING
PARTIALLY_COMPLETED
COMPLETED
FAILED
```

Never claim 10 million completed scenarios unless execution records verify the completed count.

---

# 35. MONTE CARLO AND ROBUSTNESS TESTING

Evaluate:

- Random trade sequences.
- Bootstrap resampling.
- Spread expansion.
- Slippage expansion.
- Delayed execution.
- Missed fills.
- Liquidity reduction.
- Gap risk.
- Volatility shocks.
- Parameter perturbations.
- Market regime changes.
- Exchange outages.

Report:

- Median outcome.
- Performance percentiles.
- Drawdown distribution.
- Risk of ruin under stated assumptions.
- Cost sensitivity.
- Worst-case scenario.
- Parameter stability.

These are simulations under assumptions, not predictions.

---

# 36. LIQUIDITY ALERT SYSTEM

Potential alerts:

```text
BSL_IDENTIFIED
SSL_IDENTIFIED
EQUAL_HIGHS_DETECTED
EQUAL_LOWS_DETECTED
PDH_APPROACHING
PDL_APPROACHING
PWH_APPROACHING
PWL_APPROACHING
LIQUIDITY_SWEEP_CANDIDATE
LIQUIDITY_SWEEP_CONFIRMED
BREAKOUT_CONFIRMED
BREAKOUT_FAILED
STRUCTURE_SHIFT
DISPLACEMENT_DETECTED
FVG_CREATED
ORDER_BLOCK_RETEST
LOW_LIQUIDITY_WARNING
SPREAD_EXPANSION
ORDER_BOOK_IMBALANCE
DATA_FEED_WARNING
```

Each alert must contain:

- Instrument.
- Price.
- Timeframe.
- Timestamp.
- Event type.
- Evidence.
- Data source.
- Confirmation status.
- Invalidation.

An alert is not automatically a trade instruction.

---

# 37. COMMON MISTAKES AND MYTHS

Avoid:

1. Assuming all equal highs contain stop orders.
2. Calling every wick a liquidity sweep.
3. Assuming every sweep reverses.
4. Calling every breakout a stop hunt.
5. Claiming institutions deliberately manipulated every move.
6. Treating chart-based liquidity as verified order-book data.
7. Ignoring higher-timeframe structure.
8. Ignoring market regime.
9. Ignoring news.
10. Ignoring spread and slippage.
11. Using future-confirmed pivots in backtests.
12. Treating FVG as guaranteed unfilled institutional orders.
13. Treating Order Blocks as guaranteed institutional footprints.
14. Assuming a visible order will remain available.
15. Ignoring exchange fragmentation.
16. Using incorrect session times.
17. Overfitting liquidity detection parameters.
18. Claiming backtests that were never executed.

---

# 38. PROFESSIONAL LIQUIDITY ANALYSIS REPORT

All user-facing explanations must be in natural Hinglish.

## Market Information

- Instrument:
- Exchange:
- Current price:
- Timeframe:
- Data timestamp:
- Timezone:
- Data source:

## Market Structure

- Higher-timeframe trend:
- Current regime:
- Major swing high:
- Major swing low:
- Internal structure:
- External structure:

## Liquidity Map

- Buy-side liquidity:
- Sell-side liquidity:
- Equal highs:
- Equal lows:
- Internal liquidity:
- External liquidity:
- Previous day high/low:
- Previous week high/low:
- Session high/low:

## Liquidity Event

- Sweep/breakout:
- Swept level:
- Wick extreme:
- Candle close:
- Follow-through:
- Confirmation:
- Invalidation:

## Confluence

- BOS/CHoCH/MSS:
- FVG:
- Order Block:
- Volume:
- Delta/CVD:
- VWAP:
- Higher-timeframe alignment:

## Trade Plan

- Direction:
- Strategy:
- Entry trigger:
- Entry:
- Stop-loss:
- TP1:
- TP2:
- TP3:
- R:R:
- Position size:
- Maximum account risk:

## Risk

- News risk:
- Spread:
- Slippage:
- Liquidity risk:
- Data quality:
- Missing information:

## Validation

- Backtest status:
- Out-of-sample status:
- Walk-forward status:
- Monte Carlo status:
- Scenario count:
- Strategy version:

## Final Decision

- BUY / SELL / WAIT / NO TRADE
- Supporting evidence:
- Confidence category:
- What must happen next:

---

# 39. FINAL DECISION ENGINE

## BUY

Only when:

- A valid bullish setup exists.
- Liquidity event is sufficiently confirmed.
- Market structure supports the trade.
- Entry is actionable.
- Stop and targets are defined.
- Risk controls pass.
- Data quality is sufficient.

## SELL

Only when:

- A valid bearish setup exists.
- Liquidity event is sufficiently confirmed.
- Market structure supports the trade.
- Entry is actionable.
- Stop and targets are defined.
- Risk controls pass.
- Data quality is sufficient.

## WAIT

Use when:

- Price approaches a liquidity level.
- Sweep has not occurred.
- Confirmation is missing.
- Retest is pending.
- Market structure remains unclear.

## NO TRADE

Use when:

- Data is unreliable.
- Liquidity is insufficient.
- Spread is excessive.
- Risk is unacceptable.
- Market is unstable.
- Setup is invalid.
- Confirmation fails.
- Reward-to-risk is inadequate.

A high liquidity score cannot override a hard risk failure.

---

# 40. SECURITY AND EXECUTION SAFETY

Never expose:

- Broker passwords.
- Exchange API secrets.
- Private keys.
- Authentication tokens.

Use secure secret storage.

Before any automated order:

- Verify instrument.
- Verify exchange.
- Verify order side.
- Verify quantity.
- Verify stop-loss.
- Verify maximum risk.
- Verify margin.
- Check duplicate orders.
- Check connection.
- Check order response.
- Reconcile actual positions.

An analysis engine must not silently become an execution engine.

Live trading requires explicit authorization and separate safety controls.

---

# 41. FINAL OPERATING RULES

1. Liquidity analysis must distinguish estimates from observed data.
2. Never claim to know hidden stop locations.
3. Never claim institutional intent without evidence.
4. Always define the reference level.
5. Always define the sweep rule.
6. Always distinguish sweep from breakout.
7. Always confirm with price action and structure.
8. Use order-book evidence only when available.
9. Include market-specific limitations.
10. Use correct timezone and session definitions.
11. Prevent look-ahead bias.
12. Include execution costs.
13. Define invalidation.
14. Calculate risk before recommending a trade.
15. Never invent live data.
16. Never fabricate backtest results.
17. Never claim 10 million scenarios were completed without logs.
18. Prefer WAIT when confirmation is missing.
19. Prefer NO TRADE when risk is unacceptable.
20. Explain trading decisions in natural Hinglish.
21. Technical English terms may be used but should be explained simply.
22. Never guarantee profit.

---

# 42. REFERENCE INTEGRATION

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
- `volume-analysis.md`

Load relevant references based on the user's request.

---

# END OF LIQUIDITY ANALYSIS MASTER REFERENCE
