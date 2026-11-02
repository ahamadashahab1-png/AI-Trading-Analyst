# PRICE ACTION STRATEGIES — COMPLETE A–Z TRADING ENGINE
Version: 1.0  
Category: Professional Price Action Research, Strategy Design & Execution  
Parent Skill: AI Trading Analyst  
Primary Language: Natural Hinglish  
Coverage: Forex, Crypto, Indian Stocks, Global Stocks, Indices, Commodities, Futures and Options

---

# 1. PURPOSE AND CORE OBJECTIVE

This reference defines a complete price action trading system.

The AI must be capable of:

- Reading price charts and OHLCV data.
- Identifying market conditions and structure.
- Detecting high-quality price action setups.
- Developing continuation and reversal strategies.
- Combining price action with volume, liquidity, ICT/SMC and indicators.
- Performing multi-timeframe analysis.
- Creating objective entry, stop-loss and target levels.
- Calculating position size and financial risk.
- Evaluating trade quality.
- Backtesting and validating strategies.
- Comparing strategy performance across market conditions.
- Producing BUY, SELL, WAIT or NO TRADE decisions.

**Primary principle:** Price action signals must be evaluated in context. A candle pattern alone is not sufficient evidence for a trade.

The AI must never guarantee profit or claim that an unexecuted strategy has been tested.

---

# 2. PRICE ACTION FUNDAMENTALS

## 2.1 What is price action?

Price action is the study of price movement over time using:

- Open
- High
- Low
- Close
- Volume, when available
- Time and session information

It examines how buyers and sellers interact through price movement.

Price action analysis can identify:

1. Direction of the market.
2. Strength or weakness of a move.
3. Rejection of particular price areas.
4. Breakout and breakdown attempts.
5. Momentum changes.
6. Trend continuation.
7. Potential reversals.
8. Range-bound conditions.
9. Liquidity-related price movement.
10. Areas where a trade idea becomes invalid.

## 2.2 OHLC candle structure

Every standard candlestick contains:

- Open: Starting price.
- High: Highest traded price.
- Low: Lowest traded price.
- Close: Ending price.
- Body: Distance between open and close.
- Upper wick: Distance from body to high.
- Lower wick: Distance from low to body.

### Important calculations

```python
def candle_metrics(open_price, high, low, close):
    candle_range = high - low
    body = abs(close - open_price)

    upper_wick = high - max(open_price, close)
    lower_wick = min(open_price, close) - low

    if candle_range <= 0:
        return None

    return {
        "range": candle_range,
        "body": body,
        "upper_wick": upper_wick,
        "lower_wick": lower_wick,
        "body_ratio": body / candle_range,
        "upper_wick_ratio": upper_wick / candle_range,
        "lower_wick_ratio": lower_wick / candle_range,
        "bullish": close > open_price,
        "bearish": close < open_price
    }
```

## 2.3 Candle interpretation

A large bullish body may indicate strong buying pressure, but it does not automatically mean buyers will remain in control.

A large bearish body may indicate strong selling pressure, but it does not guarantee further downside.

Always consider:

- Previous market structure.
- Candle location.
- Relative volume.
- Volatility.
- Session.
- Higher-timeframe direction.
- Nearby liquidity.
- News events.
- Follow-through candles.

## 2.4 Relative candle strength

Compare candle body and range with recent candles.

Useful measurements:

- Body-to-range ratio.
- Range compared with ATR.
- Relative volume.
- Closing position within the candle.
- Distance moved relative to recent volatility.

A candle with a large range compared with recent ATR may represent expansion. It may also represent exhaustion, especially after an extended move.

---

# 3. MARKET CONDITIONS AND REGIME DETECTION

Before selecting a strategy, classify the current market.

## 3.1 Trending market

Bullish trend:

- Higher Highs (HH).
- Higher Lows (HL).
- Buyers defend pullbacks.
- Bullish structure remains intact.

Bearish trend:

- Lower Highs (LH).
- Lower Lows (LL).
- Sellers defend rallies.
- Bearish structure remains intact.

## 3.2 Ranging market

Characteristics:

- Price repeatedly moves between identifiable boundaries.
- No sustained directional structure.
- Breakouts frequently fail.
- Mean reversion may become more relevant.

Range trading should not assume that every boundary will hold.

## 3.3 Consolidation

Consolidation occurs when price temporarily compresses or moves sideways.

Potential characteristics:

- Smaller candle ranges.
- Reduced directional movement.
- Overlapping candles.
- Compression near a key level.

A consolidation may resolve into expansion in either direction.

## 3.4 Volatility expansion

Look for:

- Increasing ATR.
- Expanding candle ranges.
- Strong closes near candle extremes.
- Increased volume, if available.
- Breakout from a previously defined structure.

## 3.5 Market regime classification

The AI should classify:

```text
STRONG_BULLISH_TREND
WEAK_BULLISH_TREND
STRONG_BEARISH_TREND
WEAK_BEARISH_TREND
RANGE_BOUND
VOLATILITY_COMPRESSION
VOLATILITY_EXPANSION
HIGH_VOLATILITY_UNSTABLE
TRANSITIONAL
UNKNOWN
```

Do not force a strategy when the regime is UNKNOWN.

---

# 4. TREND CONTINUATION STRATEGIES

## 4.1 Higher High and Higher Low continuation

Conditions:

1. Higher-timeframe bullish structure.
2. Confirmed HH and HL.
3. Pullback toward a meaningful support area.
4. Selling pressure weakens.
5. Bullish confirmation appears.
6. Risk-to-reward is acceptable.

Entry methods:

- Break above confirmation candle.
- Retest of broken minor structure.
- Limit entry at a validated support zone.

Invalidation:

- Relevant protected low breaks.
- Bullish structure fails.
- Pullback develops into bearish structure.

## 4.2 Lower High and Lower Low continuation

Conditions:

1. Bearish higher-timeframe structure.
2. Confirmed LH and LL.
3. Rally toward resistance.
4. Buying pressure weakens.
5. Bearish confirmation appears.

Entry:

- Break below confirmation candle.
- Retest of broken support.
- Validated resistance rejection.

Invalidation:

- Protected high breaks.
- Bearish structure fails.

## 4.3 Trendline pullback

Process:

1. Identify at least two meaningful swing points.
2. Draw a trendline without forcing alignment.
3. Observe the third interaction.
4. Check whether price respects the area.
5. Seek confirmation.
6. Define invalidation beyond relevant structure.

Trendlines are subjective. Use reproducible swing-detection rules during backtesting.

## 4.4 Moving-average pullback

Possible tools:

- 20 EMA.
- 50 EMA.
- 100 EMA.
- 200 EMA.

Example strategy:

- Price above rising 50 EMA.
- Higher-timeframe bullish structure.
- Pullback toward 20 EMA or 50 EMA.
- Bullish price action confirmation.
- Entry after confirmation.

Moving averages are dynamic reference tools, not guaranteed support or resistance.

## 4.5 Momentum continuation

Conditions:

- Strong directional displacement.
- Limited opposing candle overlap.
- Increasing relative range.
- Structure breakout.
- Follow-through confirmation.

Avoid chasing a move when price is already extended and the stop becomes excessively large.

---

# 5. TREND REVERSAL STRATEGIES

## 5.1 Exhaustion reversal

Potential warning signs:

- Extended directional move.
- Reduced follow-through.
- Large rejection wick.
- Failed continuation.
- Divergence.
- Nearby major level.

These signs are warnings, not confirmation.

## 5.2 Structure-break reversal

Bullish reversal:

1. Previous bearish structure.
2. Selling pressure weakens.
3. Price breaks a meaningful lower high.
4. Bullish displacement or follow-through.
5. Retest or confirmation.
6. Entry with defined invalidation.

Bearish reversal:

1. Previous bullish structure.
2. Buying pressure weakens.
3. Price breaks a meaningful higher low.
4. Bearish displacement.
5. Retest or confirmation.
6. Entry with defined invalidation.

## 5.3 Failed breakout reversal

A failed breakout occurs when price moves beyond a defined boundary but cannot sustain acceptance outside it.

Process:

1. Mark the original range.
2. Observe the breakout.
3. Wait for price to return inside.
4. Confirm rejection or structure change.
5. Define entry and invalidation.
6. Target the opposite side or intermediate liquidity.

Do not label every wick beyond a level as a failed breakout.

## 5.4 Double top reversal

Requirements:

- Two meaningful highs.
- Identifiable intervening reaction low.
- Resistance area.
- Confirmation through neckline or structure break.

The two highs do not need to be exactly equal.

## 5.5 Double bottom reversal

Requirements:

- Two meaningful lows.
- Intervening reaction high.
- Support area.
- Confirmation through neckline or structure break.

## 5.6 Head and shoulders

Components:

- Left shoulder.
- Head.
- Right shoulder.
- Neckline.

A valid trading plan requires neckline behavior and confirmation, not merely visual resemblance.

## 5.7 Inverse head and shoulders

Components:

- Left low.
- Head.
- Right low.
- Neckline.

Confirm through neckline acceptance or a reproducible breakout rule.

---

# 6. BREAKOUT STRATEGIES

## 6.1 Horizontal resistance breakout

Conditions:

1. Clearly defined resistance zone.
2. Multiple meaningful interactions.
3. Compression or pressure near resistance.
4. Candle closes above the zone.
5. Follow-through or retest.
6. Acceptable stop distance.

## 6.2 Horizontal support breakdown

Reverse the bullish breakout logic:

- Defined support.
- Bearish close below support.
- Confirmation.
- Retest or continuation.
- Defined invalidation.

## 6.3 Range breakout

Steps:

1. Identify range high and low.
2. Measure range width.
3. Check volatility compression.
4. Monitor breakout close.
5. Evaluate relative volume.
6. Wait for confirmation or retest.
7. Calculate target using structure and volatility.

Do not assume the measured-move target will be reached.

## 6.4 Trendline breakout

A trendline break alone is insufficient.

Check:

- Candle close.
- Market structure.
- Retest.
- Volume.
- Higher-timeframe context.
- Whether the line was objectively drawn.

## 6.5 Breakout and retest strategy

Bullish example:

- Resistance breaks.
- Price closes above it.
- Price returns to the previous resistance area.
- The area holds as support.
- Bullish confirmation appears.

Bearish example:

- Support breaks.
- Price closes below it.
- Price retests the broken area.
- The area holds as resistance.
- Bearish confirmation appears.

## 6.6 Volatility compression breakout

Possible compression structures:

- Narrow range.
- Inside-bar sequence.
- Bollinger Band contraction.
- ATR contraction.
- Triangle.
- Tight consolidation.

Entry should follow a defined breakout rule.

---

# 7. FAKEOUT AND LIQUIDITY-BASED STRATEGIES

## 7.1 Fakeout identification

Potential conditions:

- Break beyond a known level.
- Weak acceptance outside the level.
- Rapid return inside.
- Opposite-side displacement.
- Structure change.

## 7.2 Liquidity sweep

A liquidity sweep may occur around:

- Previous swing high.
- Previous swing low.
- Equal highs.
- Equal lows.
- Range high.
- Range low.
- Previous day high/low.

A sweep does not guarantee reversal.

## 7.3 Stop-run reversal model

1. Identify a liquidity pool.
2. Observe price trading beyond it.
3. Wait for rejection.
4. Look for displacement away from the level.
5. Confirm a structure shift.
6. Plan entry.
7. Place invalidation beyond the relevant extreme.

## 7.4 Turtle Soup concept

A false breakout of a prior high or low can create a reversal opportunity.

Validation requires:

- Precisely defined reference high/low.
- Breakout event.
- Return inside.
- Confirmation.
- Consistent entry and stop rules.

## 7.5 Range liquidity strategy

In a range:

- Upper boundary may contain buy-side liquidity.
- Lower boundary may contain sell-side liquidity.
- Middle of the range may provide poor reward-to-risk.

Trade only after evidence of rejection or acceptance.

---

# 8. PULLBACK AND RETRACEMENT STRATEGIES

## 8.1 Shallow pullback

Price retraces a small portion of the preceding impulse.

Look for:

- Strong trend.
- Limited countertrend movement.
- Continued structure.
- Confirmation candle.

## 8.2 Deep pullback

A deeper retracement may reach:

- Previous swing structure.
- Support/resistance.
- Fibonacci zones.
- Moving averages.
- Supply/demand.
- Order blocks.

Do not enter merely because a Fibonacci percentage is reached.

## 8.3 Fibonacci pullback

Common reference levels:

- 23.6%.
- 38.2%.
- 50%.
- 61.8%.
- 78.6%.

Use a consistently defined impulse leg.

Confluence may improve context, but Fibonacci levels are not independently predictive.

## 8.4 Impulse and retracement model

Measure:

- Impulse distance.
- Retracement percentage.
- Time spent retracing.
- Relative volume.
- Candle overlap.
- Structural integrity.

A weak pullback against a strong trend may offer a continuation opportunity.

---

# 9. CANDLESTICK PRICE ACTION SETUPS

## 9.1 Pin bar

Bullish pin bar:

- Long lower wick.
- Small real body.
- Rejection near a relevant support area.
- Preferably bullish follow-through.

Bearish pin bar:

- Long upper wick.
- Small real body.
- Rejection near resistance.
- Preferably bearish follow-through.

## 9.2 Engulfing pattern

Bullish engulfing:

- Bullish candle body engulfs the previous bearish body.
- More meaningful near support or after a decline.

Bearish engulfing:

- Bearish candle body engulfs the previous bullish body.
- More meaningful near resistance or after a rally.

Body engulfing and full-range engulfing must be treated as separate definitions in code.

## 9.3 Inside bar

An inside bar has a high below the previous candle's high and a low above the previous candle's low.

Potential uses:

- Compression.
- Breakout.
- Trend continuation.
- Reversal after a false break.

## 9.4 Outside bar

An outside bar has a higher high and lower low than the previous candle.

Interpret using its close location, trend and context.

## 9.5 Rejection candle

Look for:

- Wick beyond a key zone.
- Close back inside or away from the zone.
- Follow-through.
- Meaningful structural location.

## 9.6 Three-candle reversal

Examples:

- Morning Star.
- Evening Star.
- Three White Soldiers.
- Three Black Crows.

Do not trade pattern names without testing exact definitions.

## 9.7 Candlestick pattern scoring

Evaluate:

- Location.
- Trend.
- Higher-timeframe context.
- Relative candle range.
- Body/wick proportions.
- Volume.
- Follow-through.
- Risk-to-reward.
- Market session.

---

# 10. INSIDE BAR AND COMPRESSION STRATEGIES

## 10.1 Inside bar breakout

Rules:

1. Identify mother candle.
2. Identify inside candle.
3. Define breakout trigger.
4. Define stop methodology.
5. Avoid entry during poor liquidity.
6. Check higher-timeframe direction.

## 10.2 Multiple inside bars

A sequence of inside bars indicates compression.

Potential expansion may occur, but direction remains unknown until a defined trigger.

## 10.3 Failed inside bar breakout

If price breaks one side and quickly returns into the structure, evaluate a reversal only after confirmation.

---

# 11. RANGE TRADING STRATEGIES

## 11.1 Range boundary rejection

Bullish:

- Price reaches lower boundary.
- Rejection appears.
- Follow-through confirms.
- Target is range midpoint or upper boundary.

Bearish:

- Price reaches upper boundary.
- Rejection appears.
- Follow-through confirms.
- Target is midpoint or lower boundary.

## 11.2 Range midpoint strategy

Midpoint trades often offer weaker reward-to-risk.

Require stronger confirmation and compare the opportunity with boundary entries.

## 11.3 Range breakout failure

If price fails to hold outside a range, evaluate a return-to-range strategy.

## 11.4 Range invalidation

A range is invalidated when the predefined acceptance or structural break rule is met.

---

# 12. MOMENTUM STRATEGIES

## 12.1 Momentum candle continuation

Requirements:

- Strong body relative to range.
- Close near candle extreme.
- Meaningful structure break.
- Suitable volatility.
- Acceptable stop distance.

## 12.2 Consecutive candle momentum

Measure:

- Number of directional candles.
- Average body size.
- Overlap.
- Range expansion.
- Relative volume.
- Distance from reference levels.

Do not blindly enter after an extended sequence.

## 12.3 Momentum exhaustion

Potential signals:

- Reduced body size.
- Increasing opposing wicks.
- Failed new high/low.
- Divergence.
- Loss of follow-through.

Confirm with structure before taking a countertrend trade.

---

# 13. PRICE ACTION WITH ICT/SMC

Combine this section with `ict-smc.md`.

## 13.1 BOS plus pullback

- Identify meaningful structure.
- Confirm break of structure.
- Observe displacement.
- Wait for pullback.
- Evaluate FVG, OB or previous structure.
- Confirm entry.

## 13.2 CHoCH/MSS reversal

- Identify prior trend.
- Identify meaningful liquidity event.
- Observe opposing displacement.
- Confirm structure shift.
- Wait for retracement.
- Define invalidation.

## 13.3 Fair Value Gap strategy

Bullish FVG:

- First candle high is below third candle low.

Bearish FVG:

- First candle low is above third candle high.

Check:

- Gap size.
- Displacement quality.
- Market structure.
- Location.
- Fill behavior.
- Invalidation.

FVG is not a guaranteed price magnet.

## 13.4 Order Block plus confirmation

An order block must be objectively defined.

Potential validation:

- Preceding opposing candle or candle cluster.
- Subsequent displacement.
- Structure break.
- Zone boundaries.
- Retest behavior.
- Invalidation.

## 13.5 Premium and discount

Use a defined dealing range.

- Above equilibrium: premium.
- Below equilibrium: discount.
- Around equilibrium: midpoint.

This classification alone is not an entry signal.

## 13.6 Liquidity sweep plus displacement

A high-quality candidate setup may combine:

1. External liquidity sweep.
2. Strong displacement.
3. Structure shift.
4. FVG or OB retracement.
5. Lower-timeframe confirmation.
6. Defined risk.

---

# 14. PRICE ACTION WITH WYCKOFF AND AUCTION THEORY

## 14.1 Wyckoff phases

Study:

- Accumulation.
- Markup.
- Distribution.
- Markdown.

Events:

- Selling Climax.
- Automatic Rally.
- Secondary Test.
- Spring.
- Test.
- Sign of Strength.
- Last Point of Support.
- Buying Climax.
- Automatic Reaction.
- Upthrust.
- Sign of Weakness.
- Last Point of Supply.

Do not force Wyckoff labels when the chart evidence is insufficient.

## 14.2 Auction Market Theory

Analyze:

- Balance.
- Imbalance.
- Acceptance.
- Rejection.
- Value Area.
- Point of Control.
- Initiative activity.
- Responsive activity.

## 14.3 Failed auction

A failed auction occurs when price explores beyond an area but fails to establish acceptance.

Check the return, volume and subsequent structure.

---

# 15. VOLUME-CONFIRMED PRICE ACTION

## 15.1 Volume expansion

A breakout with higher relative volume may indicate stronger participation.

It does not guarantee continuation.

## 15.2 Volume climax

Extremely high volume near an extended move may indicate:

- Capitulation.
- Climax buying.
- Climax selling.
- Absorption.
- Distribution.

Context is essential.

## 15.3 Volume divergence

Compare price movement with volume behavior.

Example:

- Price makes a new high.
- Volume participation decreases.

This is a warning, not a standalone short signal.

## 15.4 VWAP confirmation

Use VWAP as a reference for intraday price relative to volume-weighted average price.

Consider:

- Price above/below VWAP.
- VWAP slope.
- Reclaim or rejection.
- Anchored VWAP.
- Session context.

## 15.5 Volume Profile

Relevant concepts:

- POC.
- VAH.
- VAL.
- HVN.
- LVN.

Use profile levels with market structure and price acceptance.

---

# 16. MULTI-TIMEFRAME PRICE ACTION

Use `multi-timeframe-analysis.md` for the complete framework.

## 16.1 Three-layer model

Higher timeframe:

- Direction.
- Major structure.
- Important zones.
- Overall market regime.

Intermediate timeframe:

- Setup formation.
- Pullback.
- Breakout.
- Liquidity event.

Lower timeframe:

- Entry trigger.
- Confirmation.
- Stop placement.

## 16.2 Example timeframe combinations

Scalping:

- 1H / 15M / 1M or 5M.

Intraday:

- 4H / 1H / 5M or 15M.

Swing:

- 1D / 4H / 1H.

Positional:

- 1W / 1D / 4H.

These are examples, not mandatory combinations.

## 16.3 Conflicting timeframes

If higher and lower timeframes disagree:

- Reduce confidence.
- Wait for alignment.
- Use a clearly defined countertrend strategy only if independently validated.
- Prefer NO TRADE when the conflict creates unacceptable uncertainty.

---

# 17. MARKET-SPECIFIC PRICE ACTION

## 17.1 Forex

Consider:

- Currency pair.
- Pip value.
- Spread.
- Session liquidity.
- Central bank decisions.
- Economic releases.
- Rollover.
- Swap.
- Broker execution.

## 17.2 Cryptocurrency

Consider:

- 24/7 trading.
- Exchange differences.
- Funding rates.
- Liquidation levels.
- Open interest.
- Weekend liquidity.
- Exchange outages.
- Token-specific events.

## 17.3 Indian equities

Consider:

- NSE/BSE.
- Market opening and closing.
- Circuit limits.
- Corporate actions.
- Earnings.
- SEBI regulations.
- Stock liquidity.
- Delivery and intraday rules.
- Brokerage and taxes.

## 17.4 Global equities

Consider:

- Exchange hours.
- Earnings.
- Pre-market and after-hours gaps.
- Corporate actions.
- Currency conversion.
- Market-specific regulations.

## 17.5 Indices

Consider:

- Constituents.
- Index futures.
- Cash/futures basis.
- Opening gaps.
- Economic data.
- Volatility.

## 17.6 Commodities

Consider:

- Contract specifications.
- Expiry.
- Storage and supply-demand factors.
- Seasonality.
- Inventory reports.
- Geopolitical events.

## 17.7 Futures

Consider:

- Tick size.
- Tick value.
- Contract multiplier.
- Margin.
- Expiry.
- Rollovers.
- Limit moves.
- Slippage.

## 17.8 Options

Price action on the underlying does not directly determine option premium.

Consider:

- Strike.
- Expiry.
- Delta.
- Gamma.
- Theta.
- Vega.
- Implied volatility.
- Bid/ask spread.
- Liquidity.
- Exercise and settlement rules.

Never assume an underlying chart's stop distance equals the option's actual premium risk.

---

# 18. TRADING STYLE ADAPTATION

## 18.1 Scalping

Priorities:

- Spread.
- Execution speed.
- Liquidity.
- Small price movements.
- Strict risk control.
- Low-latency data.

Avoid scalping when execution costs overwhelm expected movement.

## 18.2 Intraday

Priorities:

- Session levels.
- Opening range.
- VWAP.
- Intraday structure.
- News.
- End-of-session exposure.

## 18.3 Swing

Priorities:

- Daily and 4H structure.
- Major support/resistance.
- Earnings and event risk.
- Overnight gaps.
- Position sizing.

## 18.4 Positional

Priorities:

- Weekly and daily structure.
- Macro regime.
- Fundamental context.
- Long-term volatility.
- Portfolio exposure.

---

# 19. STRATEGY SELECTION ENGINE

Choose strategy according to market regime.

| Market condition | Candidate strategies |
|---|---|
| Strong bullish trend | Bullish pullback, continuation |
| Strong bearish trend | Bearish pullback, continuation |
| Range-bound | Boundary rejection, range breakout |
| Volatility compression | Confirmed breakout |
| Volatility expansion | Momentum continuation |
| Extended trend | Wait, exhaustion analysis |
| Liquidity sweep | Reversal after confirmation |
| Structure transition | BOS/CHoCH-based setup |
| Unknown regime | WAIT / NO TRADE |

The AI must not force a strategy simply because a pattern is visible.

---

# 20. ENTRY EXECUTION FRAMEWORK

Every proposed trade must contain:

1. Instrument.
2. Market.
3. Timeframe.
4. Direction.
5. Strategy name.
6. Market regime.
7. Higher-timeframe bias.
8. Setup zone.
9. Entry trigger.
10. Entry price or condition.
11. Stop-loss.
12. TP1.
13. TP2.
14. TP3.
15. Position size.
16. Risk amount.
17. R:R.
18. Invalidation.
19. News/event risk.
20. Data timestamp.

## 20.1 Entry types

- Market entry.
- Limit entry.
- Stop entry.
- Breakout entry.
- Retest entry.
- Confirmation entry.

## 20.2 Stop-loss methods

Possible methods:

- Beyond swing high/low.
- Beyond structure.
- Beyond rejection wick.
- Beyond liquidity sweep extreme.
- ATR-based.
- Volatility-adjusted.

Stop placement must be based on invalidation, not on an arbitrary desired loss amount.

## 20.3 Target methods

Possible targets:

- Previous swing high/low.
- Opposing liquidity.
- Support/resistance.
- Range boundary.
- Measured move.
- ATR projection.
- Volume Profile levels.

## 20.4 R:R calculation

For a long position:

```python
def long_rr(entry, stop, target):
    risk = entry - stop
    reward = target - entry

    if risk <= 0:
        return None

    return reward / risk
```

For a short position:

```python
def short_rr(entry, stop, target):
    risk = stop - entry
    reward = entry - target

    if risk <= 0:
        return None

    return reward / risk
```

Include fees, spread and expected slippage in the actual trade evaluation.

---

# 21. POSITION SIZING

Basic formula:

```python
def calculate_position_size(
    account_balance,
    risk_percent,
    entry,
    stop,
    value_per_price_unit=1.0
):
    risk_amount = account_balance * risk_percent / 100
    distance = abs(entry - stop)

    if distance <= 0 or value_per_price_unit <= 0:
        return None

    size = risk_amount / (distance * value_per_price_unit)

    return {
        "risk_amount": risk_amount,
        "position_size": size
    }
```

This is a simplified model.

Real implementation must account for:

- Contract multiplier.
- Lot size.
- Pip value.
- Tick value.
- Currency conversion.
- Fees.
- Slippage.
- Minimum quantity.
- Quantity step.
- Margin.
- Instrument-specific rules.

Never recommend a position size without the required contract specifications.

---

# 22. TRADE MANAGEMENT

After entry, monitor:

- Initial risk.
- Stop integrity.
- Price structure.
- Partial booking.
- Target progress.
- Volatility.
- News.
- Spread.
- Liquidity.
- Trade invalidation.

Possible actions:

- HOLD.
- REDUCE.
- PARTIAL_BOOK.
- MOVE_STOP.
- TRAIL_STOP.
- EXIT.
- NO_ACTION.

Never move a stop farther away simply to avoid taking a loss unless the original strategy explicitly defines such a rule and its risk remains controlled.

Refer to `trade-management.md` for full execution and lifecycle details.

---

# 23. STRATEGY QUALITY SCORING

Score each category from 0 to 5:

| Factor | Score |
|---|---:|
| Higher-timeframe alignment | 0–5 |
| Market structure | 0–5 |
| Entry location | 0–5 |
| Price action confirmation | 0–5 |
| Volume confirmation | 0–5 |
| Liquidity context | 0–5 |
| Volatility suitability | 0–5 |
| Risk-to-reward | 0–5 |
| Execution quality | 0–5 |
| News/event safety | 0–5 |

Maximum: 50.

Important:

- This score is a heuristic, not a probability.
- Do not convert 40/50 into an 80% win probability.
- Missing data must reduce confidence.
- A hard risk violation must override a high score.
- Strategy-specific thresholds must be validated using historical data.

---

# 24. PRICE ACTION STRATEGY DETECTION ENGINE

Recommended processing pipeline:

```text
DATA INPUT
   |
   v
DATA VALIDATION
   |
   v
CANDLE CALCULATION
   |
   v
SWING DETECTION
   |
   v
MARKET STRUCTURE
   |
   v
MARKET REGIME
   |
   v
SUPPORT / RESISTANCE
   |
   v
PRICE ACTION PATTERN DETECTION
   |
   v
VOLUME / LIQUIDITY ANALYSIS
   |
   v
MULTI-TIMEFRAME CONFIRMATION
   |
   v
STRATEGY SELECTION
   |
   v
ENTRY / SL / TARGET CALCULATION
   |
   v
RISK VALIDATION
   |
   v
BACKTEST / VALIDATION STATUS
   |
   v
BUY / SELL / WAIT / NO TRADE
```

## 24.1 Data schema

Each candle should contain:

```python
candle = {
    "timestamp": None,
    "open": None,
    "high": None,
    "low": None,
    "close": None,
    "volume": None,
    "symbol": None,
    "timeframe": None,
    "exchange": None
}
```

## 24.2 Data validation

Reject or flag:

- Missing OHLC values.
- High below low.
- Open outside high-low.
- Close outside high-low.
- Duplicate timestamps.
- Incorrect ordering.
- Missing intervals.
- Impossible negative prices where instrument rules prohibit them.
- Unexplained data spikes.
- Inconsistent timezone.
- Incomplete candles.

Never use a still-forming candle as if its close were final.

## 24.3 Pattern detection architecture

Separate:

1. Data preparation.
2. Swing detection.
3. Structure classification.
4. Pattern detection.
5. Context evaluation.
6. Confirmation.
7. Trade planning.
8. Risk validation.
9. Backtesting.
10. Reporting.

Each detector must return:

- Pattern name.
- Direction.
- Start/end timestamps.
- Relevant price levels.
- Detection conditions.
- Confirmation status.
- Invalidation level.
- Data quality.
- Confidence category.
- Reason for detection.

---

# 25. PYTHON PRICE ACTION ENGINE

Example candle detection:

```python
def detect_engulfing(previous, current):
    previous_bearish = previous["close"] < previous["open"]
    previous_bullish = previous["close"] > previous["open"]

    current_bullish = current["close"] > current["open"]
    current_bearish = current["close"] < current["open"]

    bullish = (
        previous_bearish
        and current_bullish
        and current["open"] <= previous["close"]
        and current["close"] >= previous["open"]
    )

    bearish = (
        previous_bullish
        and current_bearish
        and current["open"] >= previous["close"]
        and current["close"] <= previous["open"]
    )

    if bullish:
        return "BULLISH_ENGULFING"

    if bearish:
        return "BEARISH_ENGULFING"

    return None
```

Example inside bar:

```python
def detect_inside_bar(previous, current):
    return (
        current["high"] < previous["high"]
        and current["low"] > previous["low"]
    )
```

Example pin bar:

```python
def detect_pin_bar(
    open_price,
    high,
    low,
    close,
    wick_body_ratio=2.0,
    max_body_ratio=0.35
):
    candle_range = high - low

    if candle_range <= 0:
        return None

    body = abs(close - open_price)
    upper_wick = high - max(open_price, close)
    lower_wick = min(open_price, close) - low

    body_ratio = body / candle_range

    if body_ratio > max_body_ratio:
        return None

    if lower_wick >= wick_body_ratio * max(body, 1e-12):
        return "BULLISH_PIN_BAR"

    if upper_wick >= wick_body_ratio * max(body, 1e-12):
        return "BEARISH_PIN_BAR"

    return None
```

These examples are educational building blocks. They do not constitute a complete production trading system.

---

# 26. BACKTESTING REQUIREMENTS

Every strategy must have objective rules for:

- Instrument.
- Exchange.
- Timeframe.
- Trading session.
- Entry.
- Exit.
- Stop.
- Targets.
- Position sizing.
- Costs.
- Slippage.
- Signal timing.
- Data requirements.

Measure:

- Number of trades.
- Win rate.
- Average win.
- Average loss.
- Expectancy.
- Profit factor.
- Maximum drawdown.
- Sharpe ratio.
- Sortino ratio.
- Recovery factor.
- Consecutive wins/losses.
- Exposure.
- Average holding time.
- MAE.
- MFE.
- Net return after costs.

Use:

- In-sample testing.
- Out-of-sample testing.
- Walk-forward testing.
- Cross-validation where appropriate.
- Regime-specific analysis.
- Parameter sensitivity.
- Monte Carlo analysis.

Avoid:

- Look-ahead bias.
- Survivorship bias.
- Data leakage.
- Repainting.
- Overfitting.
- Unrealistic fills.
- Ignoring fees.
- Ignoring slippage.
- Cherry-picking results.

Refer to `backtesting.md` for the complete validation system.

---

# 27. TEN-MILLION-SCENARIO TESTING FRAMEWORK

The requested testing ambition is up to 10,000,000 scenarios.

It must be implemented as an executable, auditable research process.

## 27.1 Scenario categories

Possible scenario dimensions:

- Entry parameters.
- Stop parameters.
- Target parameters.
- Volatility regimes.
- Trend regimes.
- Range regimes.
- Market sessions.
- Instruments.
- Timeframes.
- Spread conditions.
- Slippage conditions.
- Fee structures.
- Market gaps.
- News conditions.
- Parameter perturbations.
- Monte Carlo trade sequences.
- Bootstrap resampling.
- Synthetic stress scenarios.

## 27.2 Important distinction

Do not confuse:

- Historical trade count.
- Parameter combinations.
- Monte Carlo simulations.
- Bootstrap samples.
- Synthetic stress scenarios.
- Distinct market observations.

These are different measurements and must be reported separately.

## 27.3 Scenario execution record

Every run must store:

```python
scenario_record = {
    "scenario_id": None,
    "strategy_version": None,
    "dataset_id": None,
    "instrument": None,
    "timeframe": None,
    "parameter_hash": None,
    "simulation_type": None,
    "start_time": None,
    "end_time": None,
    "trade_count": None,
    "net_return": None,
    "max_drawdown": None,
    "profit_factor": None,
    "expectancy": None,
    "execution_status": "NOT_RUN"
}
```

## 27.4 Completion rules

The AI may report:

- NOT RUN.
- PLANNED.
- RUNNING.
- PARTIALLY COMPLETED.
- COMPLETED.
- FAILED.

Only report 10 million completed scenarios if execution logs verify 10 million distinct completed scenario records.

Never fabricate test results.

---

# 28. MONTE CARLO AND ROBUSTNESS TESTING

Evaluate:

- Randomized trade sequence.
- Bootstrap resampling.
- Parameter perturbation.
- Spread expansion.
- Slippage stress.
- Delayed execution.
- Missed fills.
- Volatility shocks.
- Gap risk.
- Regime changes.

Report:

- Median outcome.
- Worst-case percentile.
- Best-case percentile.
- Drawdown distribution.
- Probability of ruin under stated assumptions.
- Sensitivity to parameters.

Monte Carlo results depend on assumptions and historical data quality. They are not predictions or guarantees.

---

# 29. STRATEGY OPTIMIZATION

Optimize only after defining a baseline strategy.

Potential parameters:

- Swing lookback.
- ATR period.
- ATR stop multiplier.
- Breakout buffer.
- Pullback depth.
- Candle body threshold.
- Relative volume threshold.
- Session filter.
- Confirmation candles.
- Target multiple.

Rules:

1. Do not optimize on the entire dataset.
2. Keep a final untouched test set.
3. Avoid excessive parameter combinations.
4. Penalize complexity.
5. Evaluate nearby parameter values.
6. Test different market regimes.
7. Prefer stable parameter regions over one perfect result.
8. Record every experiment.

---

# 30. STRATEGY FAILURE ANALYSIS

Identify:

- False breakout.
- Weak confirmation.
- Late entry.
- Poor location.
- Countertrend entry.
- Incorrect swing detection.
- Bad stop placement.
- Poor R:R.
- Excessive spread.
- Slippage.
- News shock.
- Regime change.
- Low liquidity.
- Overtrading.
- Repainting.
- Data errors.
- Execution mismatch.
- Overfitting.

Every losing trade must be categorized without automatically assuming the strategy was defective.

A valid strategy can experience losses.

---

# 31. PRICE ACTION CONFIDENCE AND DECISION ENGINE

The AI must select one of four outputs:

## BUY

Use only when:

- A valid bullish setup exists.
- Confirmation requirements are satisfied.
- Entry is actionable.
- Stop and targets are calculable.
- Risk limits pass.
- Data quality is sufficient.

## SELL

Use only when:

- A valid bearish setup exists.
- Confirmation requirements are satisfied.
- Entry is actionable.
- Stop and targets are calculable.
- Risk limits pass.
- Data quality is sufficient.

## WAIT

Use when:

- Setup is forming.
- Confirmation is missing.
- Price is approaching an important zone.
- A retest is required.
- Market conditions need clarification.

## NO TRADE

Use when:

- Data is insufficient.
- Risk is unacceptable.
- Spread is too high.
- Market is unstable.
- Setup is invalid.
- Reward-to-risk is inadequate.
- Required confirmation fails.
- Strategy has not been validated for the conditions.

## 31.1 Hard rejection rules

A high strategy score cannot override:

- Missing stop-loss.
- Unacceptable account risk.
- Invalid market data.
- Unavailable contract specifications.
- Prohibited trading conditions.
- Unmanageable execution risk.

---

# 32. PROFESSIONAL PRICE ACTION REPORT

Every analysis should follow this format:

## Market Information

- Instrument:
- Exchange:
- Current price:
- Data timestamp:
- Timezone:
- Primary timeframe:
- Analysis type:

## Market Condition

- Regime:
- Trend:
- Market structure:
- Volatility:
- Volume condition:

## Important Levels

- Major support:
- Major resistance:
- Supply zone:
- Demand zone:
- Previous high:
- Previous low:
- Liquidity areas:

## Price Action Evidence

- Detected patterns:
- Candle confirmation:
- Breakout/retest:
- Momentum:
- Rejection:
- Structure shift:

## Multi-Timeframe Analysis

- Higher timeframe:
- Intermediate timeframe:
- Entry timeframe:
- Alignment:

## Strategy

- Strategy name:
- Direction:
- Setup status:
- Entry trigger:
- Entry price or zone:
- Stop-loss:
- TP1:
- TP2:
- TP3:
- R:R:
- Position size:
- Maximum account risk:

## Risks

- News risk:
- Liquidity risk:
- Spread/slippage:
- Invalidation:
- Missing information:

## Validation

- Historical backtest status:
- Out-of-sample status:
- Walk-forward status:
- Monte Carlo status:
- Scenario count:
- Strategy version:

## Final Decision

- BUY / SELL / WAIT / NO TRADE
- Evidence:
- Confidence category:
- What must happen next:

All user-facing explanation must be in natural Hinglish.

---

# 33. SCREENSHOT AND CHART IMAGE ANALYSIS

When a user uploads a chart screenshot:

1. Identify visible instrument if possible.
2. Identify timeframe if visible.
3. Read visible price scale.
4. Identify candle direction and structure.
5. Mark visible support/resistance.
6. Detect potential patterns.
7. Identify possible liquidity areas.
8. Evaluate trend and volatility.
9. Separate visible facts from assumptions.
10. Explain missing information.

Never invent:

- Exact current price.
- Unseen candles.
- Hidden indicators.
- Exchange.
- Timeframe.
- Volume.
- Live news.

If exact price levels cannot be read, request OHLC data or a clearer screenshot.

Do not claim image-based analysis is equivalent to tick-level backtesting.

---

# 34. STRATEGY RESEARCH AND DEVELOPMENT

Each strategy should have a unique identity.

```text
Strategy ID
Strategy Name
Version
Market
Instrument
Timeframe
Market Regime
Entry Rules
Exit Rules
Stop Rules
Target Rules
Risk Rules
Filters
Data Requirements
Backtest Results
Out-of-Sample Results
Walk-Forward Results
Monte Carlo Results
Known Limitations
Last Updated
```

A strategy change must create a new version.

Maintain reproducible research logs.

---

# 35. AUTOMATION AND ALERT SYSTEM

Possible alert types:

- Price reaches support.
- Price reaches resistance.
- Breakout confirmed.
- Breakdown confirmed.
- Retest detected.
- Liquidity sweep detected.
- Structure shift detected.
- Entry condition satisfied.
- Stop-loss approached.
- Target reached.
- News event approaching.
- Spread exceeds threshold.
- Data feed disconnected.

Alerts must distinguish:

- Informational alert.
- Setup alert.
- Entry confirmation.
- Risk alert.
- Exit alert.

An alert is not automatically an order.

Automated trading requires separate authorization, broker integration, security controls, testing and risk limits.

---

# 36. SECURITY AND EXECUTION SAFETY

Never expose:

- API keys.
- Broker passwords.
- Exchange secrets.
- Private keys.
- Authentication tokens.

Use environment variables and secure secret storage.

Before automated execution:

- Validate instrument.
- Validate quantity.
- Validate order side.
- Validate stop.
- Validate maximum risk.
- Validate available margin.
- Check duplicate orders.
- Check connection status.
- Check exchange response.
- Reconcile positions.

Provide emergency stop functionality.

---

# 37. FINAL OPERATING PRINCIPLES

1. Price action must be evaluated in context.
2. Never trade a candle pattern blindly.
3. Never force a strategy in an unsuitable market regime.
4. Never invent live data.
5. Never guarantee returns.
6. Never claim a backtest was executed without evidence.
7. Never claim 10 million scenarios were completed without execution records.
8. Always calculate risk before recommending a trade.
9. Always define invalidation.
10. Prefer WAIT over an unconfirmed entry.
11. Prefer NO TRADE over an unsafe trade.
12. Keep strategy rules objective and reproducible.
13. Include fees, spread and slippage.
14. Separate historical evidence from future expectations.
15. Explain every important trading decision in natural Hinglish.
16. Treat confidence scores as analytical estimates, not win probabilities.
17. Use the relevant reference files rather than duplicating incomplete definitions.
18. Keep all outputs transparent, testable and auditable.

---

# 38. REFERENCE INTEGRATION

This file works with:

- `SKILL.md`
- `candlestick-patterns.md`
- `chart-patterns.md`
- `technical-indicators.md`
- `ict-smc.md`
- `market-structure.md`
- `support-resistance.md`
- `multi-timeframe-analysis.md`
- `order-flow.md`
- `risk-management.md`
- `trade-management.md`
- `backtesting.md`
- `news-analysis.md`
- `fundamental-analysis.md`

The master skill should load relevant references based on the user's request.

---

# END OF PRICE ACTION STRATEGIES MASTER REFERENCE
