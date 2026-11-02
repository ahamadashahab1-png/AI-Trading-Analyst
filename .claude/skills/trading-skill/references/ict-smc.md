
# ICT & SMART MONEY CONCEPTS (SMC)
## COMPLETE A TO Z MASTER ENCYCLOPEDIA
### Institutional Market Structure, Liquidity, Price Delivery, Trading Models & Quantitative Validation

Version: 1.0  
Module: AI Trading Analyst  
Scope: Forex, Crypto, Indian Equities, Global Stocks, Indices, Futures and Commodities.

---

# 1. PURPOSE AND CORE PHILOSOPHY

This reference defines a comprehensive framework for analyzing ICT (Inner Circle Trader) concepts and Smart Money Concepts (SMC).

The system must understand, identify, explain, test and evaluate ICT/SMC concepts using measurable market data.

Important principles:

1. Price action must be analyzed in context.
2. Liquidity concepts are interpretations of observable price behavior.
3. An order block does not prove that an institution placed an order there.
4. A fair value gap does not guarantee a future reaction.
5. A liquidity sweep does not guarantee a reversal.
6. Time-based trading models are hypotheses that require validation.
7. ICT terminology must not replace objective trading rules.
8. Every strategy must define entry, exit, invalidation and risk.
9. Every historical test must avoid look-ahead bias.
10. WAIT and NO TRADE are valid decisions.

The system must distinguish:

- Observable price facts.
- ICT/SMC interpretations.
- Strategy hypotheses.
- Statistically validated findings.
- Unverified claims.

## 1.1 What is ICT?

ICT is a price-action trading methodology associated with concepts such as:

- Liquidity.
- Market structure.
- Displacement.
- Fair Value Gaps.
- Order Blocks.
- Dealing Ranges.
- Premium and Discount.
- Time and session behavior.
- Market delivery.

## 1.2 What is SMC?

Smart Money Concepts is a broad trading terminology framework that commonly uses:

- Institutional order blocks.
- Liquidity zones.
- Break of Structure.
- Change of Character.
- Fair Value Gaps.
- Market structure shifts.
- Mitigation and breaker zones.

ICT and SMC overlap, but different educators may define terms differently.

The analyst must record which definition is being used.

---

# 2. MARKET DATA AND CHART PREPARATION

Before analyzing any ICT/SMC setup, verify:

- Instrument name.
- Exchange or broker.
- Market type.
- Trading session.
- Timeframe.
- Timezone.
- OHLC candle data.
- Volume availability.
- Bid/ask availability.
- Spread.
- Historical data completeness.

## 2.1 Candle Structure

Every candle contains:

- Open.
- High.
- Low.
- Close.
- Timestamp.
- Volume, where available.

A bullish candle closes above its open.

A bearish candle closes below its open.

A candle's wick shows the traded price range beyond its body. It does not independently reveal institutional intent.

## 2.2 Confirmed and Unconfirmed Candles

A candle is confirmed only after its timeframe closes.

Do not treat a developing candle as a confirmed signal.

## 2.3 Timezone Rules

Store timestamps consistently, preferably in UTC.

Convert them into the relevant exchange or session timezone for analysis.

Account for daylight saving time where applicable.

Never assume London or New York sessions have fixed UTC times throughout the year.

---

# 3. MARKET STRUCTURE MASTER SYSTEM

## 3.1 Swing High

A local high relative to neighboring price bars.

A pivot-high algorithm must define how many bars are required on both sides.

If future bars are required for confirmation, the pivot is not known until those bars close.

## 3.2 Swing Low

A local low relative to neighboring bars.

Use the same confirmation principles as swing highs.

## 3.3 Higher High (HH)

A confirmed swing high above the previous relevant swing high.

## 3.4 Higher Low (HL)

A confirmed swing low above the previous relevant swing low.

## 3.5 Lower High (LH)

A confirmed swing high below the previous relevant swing high.

## 3.6 Lower Low (LL)

A confirmed swing low below the previous relevant swing low.

## 3.7 Bullish Market Structure

A sequence of higher highs and higher lows.

This indicates an upward structural tendency, not a guarantee of continuation.

## 3.8 Bearish Market Structure

A sequence of lower highs and lower lows.

This indicates a downward structural tendency.

## 3.9 Internal Structure

Smaller price swings inside a larger structural movement.

Useful for lower-timeframe entry analysis.

## 3.10 External Structure

Major swing highs and lows defining a broader dealing range.

## 3.11 Protected High

A high considered structurally important because a subsequent bearish move originated from it and changed relevant structure.

The exact rule for protection must be defined by the selected model.

## 3.12 Protected Low

A low considered structurally important because a subsequent bullish move originated from it and changed relevant structure.

## 3.13 Break of Structure (BOS)

A break of a relevant previous swing in the direction of the existing structural trend.

Bullish BOS:
- Price closes above a selected structural high.

Bearish BOS:
- Price closes below a selected structural low.

The analyst must specify whether the model uses:
- Candle close.
- Wick penetration.
- Minimum distance.
- Displacement confirmation.

Do not mix definitions between historical tests.

## 3.14 Change of Character (CHoCH)

A potential shift in the previous structural behavior.

Example:
- Market was making lower highs and lower lows.
- Price breaks an important lower high.
- A possible bullish transition develops.

CHoCH is a warning of possible change, not proof of reversal.

## 3.15 Market Structure Shift (MSS)

A structural break associated with meaningful directional displacement.

A strict MSS model may require:
1. Relevant swing identified.
2. Break in the opposite direction.
3. Strong candle displacement.
4. Close beyond the selected level.
5. Follow-through or confirmation.

## 3.16 Minor and Major Structure

Keep separate labels for:
- Micro structure.
- Internal structure.
- External structure.
- Higher-timeframe structure.

A minor break must not automatically be treated as a major trend reversal.

## 3.17 Structural Failure

A bullish structure may fail when the protected low is broken according to the selected rules.

A bearish structure may fail when the protected high is broken.

## 3.18 Structure Analysis Output

Record:
- Current structural direction.
- Last confirmed swing high.
- Last confirmed swing low.
- Protected high.
- Protected low.
- Latest BOS.
- Latest CHoCH.
- Latest MSS.
- Internal direction.
- External direction.
- Confirmation status.

---

# 4. LIQUIDITY MASTER ENCYCLOPEDIA

Liquidity in ICT/SMC commonly refers to areas where stop orders or other orders may be concentrated.

Actual resting orders are not visible from ordinary OHLC charts.

Treat chart-based liquidity as an inferred area, not directly observed order-book data.

## 4.1 Buy-Side Liquidity (BSL)

Potential buy-stop liquidity above relevant highs.

Common locations:
- Previous swing highs.
- Equal highs.
- Previous day high.
- Previous week high.
- Range highs.
- Session highs.
- Obvious resistance highs.

## 4.2 Sell-Side Liquidity (SSL)

Potential sell-stop liquidity below relevant lows.

Common locations:
- Previous swing lows.
- Equal lows.
- Previous day low.
- Previous week low.
- Range lows.
- Session lows.
- Obvious support lows.

## 4.3 Equal Highs (EQH)

Two or more highs within a defined price tolerance.

A detection algorithm must define:
- Price tolerance.
- Minimum number of touches.
- Maximum separation.
- Whether candle closes matter.
- Whether the levels are still active.

## 4.4 Equal Lows (EQL)

Two or more lows within a defined price tolerance.

## 4.5 Relative Equal Highs and Lows

Nearby but not perfectly equal swing points.

Avoid forcing equal-high or equal-low labels when the distance exceeds the defined tolerance.

## 4.6 Buy Stops

Orders placed above price that may become active when price rises through their trigger level.

## 4.7 Sell Stops

Orders placed below price that may become active when price falls through their trigger level.

## 4.8 Liquidity Pool

A price zone where orders may be clustered.

Possible sources:
- Equal highs/lows.
- Previous session extremes.
- Major swing points.
- Range boundaries.
- Obvious breakout levels.

## 4.9 Internal Range Liquidity (IRL)

Liquidity within a defined dealing range.

## 4.10 External Range Liquidity (ERL)

Liquidity beyond the boundaries of a defined dealing range.

## 4.11 Liquidity Sweep

Price trades beyond a previously identified liquidity level and then returns.

A strict sweep definition may require:
1. A level identified before the event.
2. Price penetration beyond the level.
3. A confirmed close back inside, if required by the model.
4. A defined observation window.
5. An objective invalidation level.

## 4.12 Liquidity Raid

A term often used for a move into a liquidity area followed by a reaction.

The word does not prove deliberate manipulation.

## 4.13 Liquidity Grab

Common informal term for a rapid move through an obvious high or low.

Use precise price behavior rather than relying on the label alone.

## 4.14 Stop Run

A rapid move through a stop-sensitive price area.

Do not assume every breakout is a stop run.

## 4.15 Liquidity Void

A region where price moved rapidly with relatively little two-way trading or limited candle overlap.

An OHLC chart alone cannot prove actual absence of orders.

## 4.16 Inducement

A suspected intermediate price point that may attract traders before price moves toward another liquidity objective.

This is subjective unless defined by measurable rules.

Possible measurable definition:
- A minor swing forms.
- Price reacts around it.
- The swing is broken.
- A subsequent move reaches a predefined external liquidity target.

## 4.17 Draw on Liquidity (DOL)

The suspected next liquidity objective.

Possible targets:
- Previous day high/low.
- Previous week high/low.
- Equal highs/lows.
- External swing points.
- Session extremes.
- Major range boundaries.

Always present DOL as a scenario, not certainty.

## 4.18 Liquidity Mapping Procedure

1. Identify higher-timeframe range.
2. Mark confirmed swing highs.
3. Mark confirmed swing lows.
4. Identify EQH/EQL.
5. Mark previous session extremes.
6. Mark previous day/week/month extremes.
7. Separate internal from external liquidity.
8. Identify which pools remain untouched.
9. Record distance to each pool.
10. Reassess after new confirmed price action.

---

# 5. DISPLACEMENT AND PRICE DELIVERY

## 5.1 Displacement

A strong directional price movement that may indicate a meaningful shift in market behavior.

Potential measurable characteristics:
- Large candle body relative to ATR.
- Strong close near the candle extreme.
- Break of a relevant structural level.
- Low overlap with preceding candles.
- Creation of a measurable FVG.

## 5.2 Displacement Strength

Possible measurements:

Body Ratio = Absolute(Close - Open) / (High - Low)

Range Expansion = Current True Range / ATR

Close Location = (Close - Low) / (High - Low)

Handle zero-range candles safely.

Do not invent universal thresholds. Calibrate them by instrument and timeframe.

## 5.3 Bullish Displacement

Strong upward price movement that may break a relevant high.

## 5.4 Bearish Displacement

Strong downward movement that may break a relevant low.

## 5.5 Impulse Leg

A strong directional movement.

## 5.6 Retracement Leg

A corrective movement against the preceding impulse.

## 5.7 Expansion

A directional move away from a previous balance area.

## 5.8 Consolidation

A period of relatively limited price movement within a defined range.

## 5.9 Market Delivery

The sequence of price movement between reference areas.

Possible stages:
- Balance.
- Expansion.
- Retracement.
- Repricing.
- Continuation.
- Reversal.

These are descriptive categories, not proof of a hidden algorithm.

---

# 6. FAIR VALUE GAP (FVG) MASTER SYSTEM

## 6.1 Three-Candle Structure

A standard bullish FVG exists when:

Candle 1 High < Candle 3 Low.

The gap zone is:
- Lower boundary: Candle 1 High.
- Upper boundary: Candle 3 Low.

A standard bearish FVG exists when:

Candle 1 Low > Candle 3 High.

The gap zone is:
- Lower boundary: Candle 3 High.
- Upper boundary: Candle 1 Low.

The middle candle is often associated with displacement.

## 6.2 Bullish FVG

An upward imbalance zone created when the first candle's high is below the third candle's low.

## 6.3 Bearish FVG

A downward imbalance zone created when the first candle's low is above the third candle's high.

## 6.4 FVG Boundaries

Record:
- Upper boundary.
- Lower boundary.
- Midpoint.
- Creation time.
- Timeframe.
- Direction.
- Width.
- ATR-normalized width.
- Current status.

## 6.5 Consequent Encroachment (CE)

The 50% midpoint of an FVG.

CE = (Upper Boundary + Lower Boundary) / 2

It is a reference level, not a guaranteed reaction point.

## 6.6 FVG Fill

Price trades into some or all of the gap zone.

Define fill percentage objectively.

Example:

Fill Percentage = Penetrated Gap Width / Total Gap Width × 100

Specify whether wick or candle close is used.

## 6.7 Partial Fill

Price enters the FVG without reaching the opposite boundary.

## 6.8 Full Fill

Price traverses the entire defined gap.

## 6.9 Inversion Fair Value Gap (IFVG)

A previously identified FVG is violated and later considered from the opposite directional perspective under a defined model.

The system must define:
- Original FVG.
- Invalidation event.
- Confirmation event.
- Retest condition.
- New trade direction.

## 6.10 Balanced Price Range (BPR)

An overlap between opposing FVG zones.

Define exact overlap calculation and required confirmation.

## 6.11 Volume Imbalance

A difference between adjacent candle bodies or price areas as defined by a particular ICT model.

Do not confuse this visual concept with actual bid-ask volume delta.

## 6.12 Opening Gap

A discontinuity between one session's close and the next session's open.

An exchange opening gap is not automatically the same as an FVG.

## 6.13 FVG Quality Factors

Evaluate:
- Size relative to ATR.
- Displacement strength.
- Structure break.
- Higher-timeframe location.
- Directional context.
- Creation session.
- Distance to opposing liquidity.
- Number of previous tests.
- Fill percentage.
- Current volatility.

## 6.14 FVG Invalidity

Define invalidity before the test.

Possible rules:
- Close beyond the far boundary.
- Full penetration.
- Structural failure.
- Opposing displacement.
- Expiration after a specified number of candles.

Different FVG strategies may use different rules.

## 6.15 FVG Entry Models

Possible methods:
- First touch.
- Midpoint retracement.
- Full gap retracement.
- Rejection candle confirmation.
- Lower-timeframe structure shift.
- FVG plus order-block confluence.

Never assume every FVG must be traded.

---

# 7. ORDER BLOCK MASTER ENCYCLOPEDIA

An order block is commonly defined in ICT/SMC as a selected candle or price zone preceding a meaningful displacement.

It is not direct proof of institutional orders.

## 7.1 Bullish Order Block

A selected bearish candle or bearish candle zone preceding a meaningful upward displacement.

A strict model may require:
- Relevant bullish displacement.
- Break of structural high.
- Defined candle selection.
- Defined zone boundaries.

## 7.2 Bearish Order Block

A selected bullish candle or bullish candle zone preceding meaningful downward displacement.

## 7.3 Order Block Boundaries

Possible methods:
- Full candle range.
- Candle body.
- Open-to-low zone.
- Open-to-high zone.
- Refined lower-timeframe zone.

The selected method must be recorded.

## 7.4 Refined Order Block

A narrower zone derived from a lower timeframe.

Refinement must not use future information.

## 7.5 Breaker Block

A previously selected order-block zone that fails and is later used from the opposite directional perspective.

Define:
- Original block.
- Failure condition.
- Structural confirmation.
- Retest.
- Invalidation.

## 7.6 Mitigation Block

A term used for a price zone associated with mitigation of prior positioning.

Definitions vary across educators.

The system must store the exact operational definition used.

## 7.7 Rejection Block

A zone selected around a rejection wick or candle structure.

Do not confuse a visually large wick with confirmed institutional rejection.

## 7.8 Propulsion Block

A term used for certain continuation-related candle zones.

Use only when the selected strategy has a precise definition.

## 7.9 Vacuum Block

A term sometimes used for a price area associated with rapid movement or limited trading overlap.

Keep it separate from a formally measured FVG.

## 7.10 Order Block Quality

Evaluate:
1. Was it identified before the outcome?
2. Did meaningful displacement follow?
3. Did price break relevant structure?
4. Is the block aligned with the larger context?
5. Is liquidity nearby?
6. Has the zone been mitigated?
7. Is the risk/reward reasonable?
8. Has the block been invalidated?

## 7.11 First Test and Multiple Tests

Record the number of touches.

Do not assume the first test is always best or that every retest weakens a zone.

Test the effect empirically.

## 7.12 Order Block Trade Planning

Entry:
- At zone touch.
- At selected internal price.
- After lower-timeframe confirmation.

Stop:
- Beyond the defined invalidation boundary.
- Include spread and slippage.

Target:
- Opposing liquidity.
- Structural high/low.
- FVG.
- Higher-timeframe reference.

---

# 8. MITIGATION, BREAKER AND REJECTION MODELS

## 8.1 Mitigation

A return to a previously identified price zone.

Mitigation is not automatically bullish or bearish.

## 8.2 Mitigation of Bullish Zone

Price revisits a bullish reference zone and may respond upward.

## 8.3 Mitigation of Bearish Zone

Price revisits a bearish reference zone and may respond downward.

## 8.4 Breaker Confirmation

A strict breaker strategy should require:
1. An original block.
2. A defined violation.
3. A structural shift.
4. A retest.
5. A directional trigger.

## 8.5 Rejection Confirmation

Possible evidence:
- Wick rejection.
- Close away from zone.
- Displacement.
- Microstructure break.
- Volume confirmation where reliable.

A rejection candle alone is insufficient for a guaranteed reversal.

---

# 9. PREMIUM, DISCOUNT AND EQUILIBRIUM

## 9.1 Dealing Range

A defined range between a selected high and low.

Record:
- Range high.
- Range low.
- Start time.
- End time.
- Timeframe.
- Selection method.

## 9.2 Equilibrium

The midpoint of the dealing range.

Equilibrium = (Range High + Range Low) / 2

## 9.3 Premium

Price above equilibrium.

## 9.4 Discount

Price below equilibrium.

## 9.5 Range Selection Rules

A dealing range must be selected before evaluating the trade.

Do not continuously move its high and low to make price appear to be in premium or discount.

## 9.6 Directional Interpretation

A bullish strategy may prefer discount entries within a bullish higher-timeframe context.

A bearish strategy may prefer premium entries within a bearish higher-timeframe context.

These are strategy preferences, not universal laws.

---

# 10. OPTIMAL TRADE ENTRY (OTE)

OTE is a Fibonacci-based retracement concept.

Commonly referenced zone:
- 62%.
- 70.5%.
- 79%.

The precise Fibonacci direction and anchor points must be defined by the model.

## 10.1 Bullish OTE

Measure a selected upward impulse and identify the defined retracement zone.

Potential confluence:
- Discount.
- Bullish FVG.
- Bullish order block.
- Liquidity sweep.
- Bullish structure shift.

## 10.2 Bearish OTE

Measure a selected downward impulse and identify the defined retracement zone.

Potential confluence:
- Premium.
- Bearish FVG.
- Bearish order block.
- Buy-side liquidity sweep.
- Bearish structure shift.

## 10.3 OTE Validation

Check:
- Swing anchor validity.
- Impulse confirmation.
- Range context.
- Retracement depth.
- Entry trigger.
- Invalidation.
- Target liquidity.

OTE is a setup location, not an entry signal by itself.

---

# 11. PREMIUM/DISCOUNT ARRAYS (PD ARRAYS)

PD Arrays are price reference zones used in ICT-style analysis.

Commonly discussed concepts:

- Fair Value Gaps.
- Inverse Fair Value Gaps.
- Balanced Price Ranges.
- Order Blocks.
- Breaker Blocks.
- Mitigation Blocks.
- Rejection Blocks.
- Old highs.
- Old lows.
- Opening gaps.
- Volume imbalances.
- Liquidity voids.

## 11.1 PD Array Analysis

For every zone record:
- Type.
- Direction.
- Timeframe.
- Upper boundary.
- Lower boundary.
- Midpoint.
- Creation timestamp.
- Test count.
- Fill status.
- Invalidation status.

## 11.2 Confluence

Multiple zones overlapping may create a reference area.

Do not automatically assign a higher win probability because several labels overlap.

Check whether the zones are genuinely independent pieces of evidence.

## 11.3 Zone Priority

A possible research framework:
1. Higher-timeframe structure.
2. Major liquidity objective.
3. Strong displacement.
4. Higher-timeframe FVG/OB.
5. Lower-timeframe entry zone.

Validate priority through actual data rather than assuming it is universal.

---

# 12. INDUCEMENT AND LIQUIDITY ENGINEERING

## 12.1 Inducement Concept

A suspected minor price level that attracts traders before a move toward another reference level.

## 12.2 Measurable Inducement Model

Possible operational rules:
1. Identify a confirmed major structural level.
2. Identify a minor swing before that level.
3. Record the minor swing.
4. Wait for price to trade through it.
5. Observe whether the move reaches the major objective.
6. Record outcomes over many examples.

## 12.3 Liquidity Engineering

An interpretive term for price patterns that may encourage traders to position around obvious highs and lows.

Do not claim to know the intentions of market participants from chart appearance alone.

## 12.4 Failed Inducement

Price fails to produce the expected sequence.

Record it as a failed setup, not as a reason to rewrite the original model.

---

# 13. POWER OF THREE (PO3) AND AMD

Power of Three is a framework commonly describing:

1. Accumulation.
2. Manipulation.
3. Distribution.

## 13.1 Accumulation

A period of consolidation or balance.

Possible evidence:
- Narrow range.
- Repeated high/low tests.
- Reduced directional progress.

## 13.2 Manipulation

A move beyond a reference range followed by a return or directional change.

The label does not prove deliberate manipulation.

## 13.3 Distribution

A directional movement away from the prior range.

## 13.4 Bullish AMD Example

Potential sequence:
1. Range develops.
2. Price moves below the range low.
3. Price reclaims the range.
4. Bullish displacement develops.
5. Price moves toward upper liquidity.

## 13.5 Bearish AMD Example

Potential sequence:
1. Range develops.
2. Price moves above the range high.
3. Price returns inside the range.
4. Bearish displacement develops.
5. Price moves toward lower liquidity.

## 13.6 PO3 Validation

Record:
- Range duration.
- Range size.
- Sweep direction.
- Reclaim condition.
- Displacement.
- Target.
- Session.
- Result.

Do not label every range breakout a PO3.

---

# 14. TIME AND SESSION ANALYSIS

Session behavior is market-specific.

The system must use the correct local exchange/session calendar.

## 14.1 Asian Session

Analyze:
- Asian high.
- Asian low.
- Range size.
- Range expansion.
- Liquidity remaining outside the range.

## 14.2 London Session

Analyze:
- Opening behavior.
- Asian range interaction.
- London high/low.
- Breakout and reversal conditions.
- Volatility changes.

## 14.3 New York Session

Analyze:
- New York opening behavior.
- London range interaction.
- US economic releases.
- New York high/low.
- Trend continuation or reversal.

## 14.4 London-New York Overlap

Potentially higher activity in some instruments.

Volume and volatility must be measured for the specific market.

## 14.5 Kill Zones

Common ICT terminology includes:
- Asian Kill Zone.
- London Kill Zone.
- New York Kill Zone.
- London Close Kill Zone.

The exact windows must be configured for:
- Instrument.
- Timezone.
- Daylight saving.
- Broker/exchange.
- Selected ICT model.

Never hardcode one universal UTC schedule.

## 14.6 Session High and Low

Track:
- Session open.
- Session high.
- Session low.
- Session close.
- Range.
- Range expansion.
- Sweeps.
- Breakouts.

## 14.7 Judas Swing

A term for an early move in one direction followed by a reversal.

Possible model:
1. Identify session context.
2. Define initial range.
3. Observe movement beyond one side.
4. Wait for a return.
5. Require structure shift.
6. Target opposing liquidity.

Not every opening reversal is a Judas Swing.

## 14.8 Silver Bullet

A time-based ICT setup commonly associated with:
- A defined intraday time window.
- Liquidity context.
- Displacement.
- Fair Value Gap.
- Entry into the gap.
- A defined liquidity target.

The exact time window must be configurable and verified against the intended model.

Never assume the setup works every day.

## 14.9 London Close

Analyze late-session liquidity and possible position adjustment.

Do not assume a predictable reversal.

---

# 15. ICT DAILY AND WEEKLY PROFILES

## 15.1 Daily Bias

Develop a daily directional hypothesis using:
- Higher-timeframe structure.
- Previous day high/low.
- Current price location.
- Liquidity objectives.
- News risk.
- Session context.

Daily bias is a hypothesis, not a fixed prediction.

## 15.2 Previous Day High (PDH)

The previous completed trading day's high.

## 15.3 Previous Day Low (PDL)

The previous completed trading day's low.

## 15.4 Previous Day Close (PDC)

The previous completed trading day's close.

## 15.5 Previous Week High (PWH)

The previous completed trading week's high.

## 15.6 Previous Week Low (PWL)

The previous completed trading week's low.

## 15.7 Previous Month High/Low

Major monthly reference levels.

## 15.8 Weekly Opening Price

Opening price of the selected trading week.

Define the week boundary and timezone.

## 15.9 Daily Opening Price

Opening price of the selected trading day.

## 15.10 Midnight Opening Price

A time-specific opening reference used in some ICT models.

Timezone must be specified.

## 15.11 Opening Range

A defined early-session range.

Record exact start and end times.

## 15.12 Daily Range

High minus low of the completed or developing trading day.

## 15.13 Average Daily Range (ADR)

An average of previous daily ranges.

Useful for context and target-distance evaluation.

ADR is not a guaranteed maximum daily movement.

---

# 16. SMT DIVERGENCE

SMT divergence is commonly used to compare correlated instruments.

Examples may include:
- EURUSD and GBPUSD.
- ES and NQ.
- Related stock indices.
- Related currency pairs.
- Bitcoin and selected correlated crypto assets.

## 16.1 Bullish SMT

One instrument makes a lower low while the comparison instrument fails to make a corresponding lower low, under the selected swing-matching method.

## 16.2 Bearish SMT

One instrument makes a higher high while the comparison instrument fails to make a corresponding higher high.

## 16.3 SMT Validation

Check:
1. Correct instrument pair.
2. Correlation stability.
3. Same timeframe.
4. Aligned timestamps.
5. Comparable swing points.
6. Matching sessions.
7. Data quality.
8. Confirmation after divergence.

## 16.4 SMT Limitations

- Correlations change.
- Different trading hours affect comparison.
- One market may lead or lag.
- Instrument-specific news may distort behavior.
- Different contracts may have different expiry effects.

SMT is supporting evidence, not an automatic entry.

---

# 17. TURTLE SOUP AND FALSE BREAKOUT MODELS

Turtle Soup is commonly described as a failed breakout or liquidity sweep around a previous high or low.

## 17.1 Bullish Model

Possible sequence:
1. Identify a previous low.
2. Price trades below it.
3. Price returns above it.
4. Confirm bullish structure or displacement.
5. Define stop below invalidation.
6. Target opposing liquidity.

## 17.2 Bearish Model

Possible sequence:
1. Identify a previous high.
2. Price trades above it.
3. Price returns below it.
4. Confirm bearish structure or displacement.
5. Define stop above invalidation.
6. Target opposing liquidity.

## 17.3 False Breakout Classification

Differentiate:
- Failed breakout.
- Confirmed breakout.
- Liquidity sweep.
- Range expansion.
- Reclaim.
- Rejection.

Use predefined rules to avoid hindsight labeling.

---

# 18. ICT 2022 MODEL AND OTHER SETUPS

ICT 2022-style model descriptions commonly combine:

- Higher-timeframe bias.
- Liquidity sweep.
- Market structure shift.
- Displacement.
- Fair Value Gap.
- Retracement entry.
- Opposing liquidity target.

## 18.1 Bullish Model Template

1. Identify higher-timeframe bullish context.
2. Identify relevant sell-side liquidity.
3. Wait for a sweep or other predefined liquidity event.
4. Wait for bullish displacement.
5. Confirm structure shift.
6. Identify bullish FVG.
7. Define entry.
8. Place stop beyond invalidation.
9. Target buy-side liquidity.
10. Calculate actual risk and reward.

## 18.2 Bearish Model Template

1. Identify higher-timeframe bearish context.
2. Identify relevant buy-side liquidity.
3. Wait for a sweep or other predefined liquidity event.
4. Wait for bearish displacement.
5. Confirm structure shift.
6. Identify bearish FVG.
7. Define entry.
8. Place stop beyond invalidation.
9. Target sell-side liquidity.
10. Calculate actual risk and reward.

## 18.3 Model Failure

The setup is invalid if its predefined invalidation condition occurs.

Do not move the invalidation point to preserve a losing trade.

---

# 19. NEWS AND FUNDAMENTAL INTEGRATION

ICT/SMC analysis must account for major events.

Check:
- Central-bank decisions.
- Inflation reports.
- Employment reports.
- GDP.
- PMI.
- Interest-rate expectations.
- Earnings.
- Regulatory announcements.
- Geopolitical events.
- Commodity inventory releases.

## 19.1 News Risk Procedure

1. Check event date and time.
2. Verify timezone.
3. Identify affected instruments.
4. Check forecast and previous values where available.
5. Check actual result after release.
6. Measure volatility expansion.
7. Avoid inventing news outcomes.
8. Apply the strategy's news trading restrictions.

## 19.2 News Candle Caution

A large news candle can create:
- Wide spread.
- Slippage.
- Sudden gaps.
- Stop execution uncertainty.
- False technical signals.

Do not assume a clean FVG or order block remains tradable during extreme event conditions.

---

# 20. MARKET-SPECIFIC ICT/SMC ADAPTATION

## 20.1 Forex

Check:
- Broker feed.
- Spot versus futures data.
- Tick volume reliability.
- Spread.
- Swap.
- London/New York sessions.
- Central-bank news.

Spot Forex is decentralized. One broker's chart does not represent every market participant.

## 20.2 Crypto

Check:
- Exchange.
- Spot or perpetual contract.
- Funding rate.
- Open interest.
- Exchange-specific volume.
- Liquidations.
- 24/7 sessions.
- Weekend liquidity.
- Exchange outages.

Do not combine different exchange data without documenting the method.

## 20.3 Indian Stocks

Check:
- NSE or BSE.
- Cash market session.
- Pre-open and post-market data treatment.
- Corporate actions.
- Earnings.
- Circuit limits.
- Delivery and traded volume.
- Liquidity.
- Exchange holidays.

Do not apply Forex kill-zone timings as if they were Indian market sessions.

## 20.4 Indian Index Futures

Check:
- Correct contract.
- Expiry.
- Lot size.
- Tick size.
- Rollover.
- Futures basis.
- Open interest.
- Actual exchange volume.

## 20.5 Global Stocks

Check:
- Exchange.
- Regular trading hours.
- Extended-hours data.
- Earnings.
- Splits.
- Dividends.
- Currency.
- Market holidays.

## 20.6 Commodities

Check:
- Contract month.
- Expiry.
- Rollover.
- Inventory reports.
- Seasonality.
- Tick value.
- Trading session.

---

# 21. COMPLETE ICT/SMC ENTRY MODELS

Every model must be expressed as explicit rules.

## 21.1 Liquidity Sweep + MSS + FVG

Bullish:
- Identify sell-side liquidity.
- Confirm sweep.
- Confirm bullish MSS.
- Confirm displacement.
- Identify bullish FVG.
- Define entry.
- Define invalidation.
- Target opposing liquidity.

Bearish:
- Identify buy-side liquidity.
- Confirm sweep.
- Confirm bearish MSS.
- Confirm displacement.
- Identify bearish FVG.
- Define entry.
- Define invalidation.
- Target opposing liquidity.

## 21.2 Order Block + Structure Shift

Require:
- Relevant order block.
- Confirmed structural event.
- Retest.
- Defined entry trigger.
- Defined stop and target.

## 21.3 OTE + FVG

Require:
- Confirmed impulse.
- Valid swing anchors.
- Defined retracement zone.
- FVG overlap or confirmation.
- Risk/reward evaluation.

## 21.4 Breaker Retest

Require:
- Original zone.
- Defined failure.
- Structural confirmation.
- Retest.
- Invalidation.

## 21.5 Range Sweep + Reclaim

Require:
- Established range.
- Sweep beyond boundary.
- Reclaim.
- Confirmation.
- Target inside or beyond range according to model.

## 21.6 Session-Based Model

Require:
- Correct session.
- Defined time window.
- Higher-timeframe context.
- Liquidity objective.
- Confirmation.
- Risk controls.

## 21.7 No-Trade Conditions

Do not enter if:
- No clear setup.
- No confirmed trigger.
- No reliable stop.
- Poor risk/reward.
- Excessive spread.
- Major news risk outside strategy rules.
- Conflicting structural evidence.
- Price has already reached target liquidity.
- Required data is missing.

---

# 22. ENTRY, STOP LOSS AND TAKE PROFIT

## 22.1 Entry Types

- Market entry.
- Limit entry.
- Stop entry.
- FVG entry.
- OB entry.
- Breakout entry.
- Retest entry.
- Confirmation entry.

The system must explain why the chosen order type is suitable.

## 22.2 Stop Loss

Possible placement:
- Beyond swept liquidity.
- Beyond order block invalidation.
- Beyond FVG boundary under a defined model.
- Beyond swing high/low.
- Beyond structural invalidation.

Include spread and expected slippage.

## 22.3 Take Profit

Possible objectives:
- Internal liquidity.
- External liquidity.
- Previous day high/low.
- Previous week high/low.
- Opposing swing.
- FVG.
- Volume profile level.
- Defined risk-reward multiple.

## 22.4 Partial Exits

Define:
- Partial quantity.
- Exit level.
- Remaining quantity.
- New stop rule.
- Fee impact.

## 22.5 Break-Even

A stop moved to entry does not eliminate all risk.

Account for commissions, spread and slippage.

## 22.6 Trailing Stop

Possible methods:
- Swing-based.
- ATR-based.
- Structure-based.
- Fixed distance.
- Moving average.

Rules must be defined before testing.

## 22.7 Position Sizing

Risk Amount = Account Equity × Risk Percentage

Position Size = Risk Amount / Monetary Loss per Unit at Stop

Correctly account for:
- Contract multiplier.
- Pip value.
- Tick value.
- Currency conversion.
- Lot size.
- Brokerage.
- Exchange fees.
- Slippage.

Never invent lot size without instrument specifications.

---

# 23. RISK MANAGEMENT AND TRADE MANAGEMENT

## 23.1 Risk Per Trade

Risk must be selected by the user or explicitly stated as an assumption.

Do not silently assume a risk percentage.

## 23.2 Daily Loss Limit

Define a maximum daily loss before trading.

Stop trading when the limit is reached.

## 23.3 Maximum Open Risk

Calculate total risk across correlated open positions.

## 23.4 Correlation Risk

Several trades may represent one concentrated directional exposure.

## 23.5 Consecutive Losses

Define a pause or review procedure after a specified number of losses.

## 23.6 News Exposure

Account for gap and slippage risk around major events.

## 23.7 Risk/Reward

Reward-to-Risk = Potential Reward / Potential Risk

A visually attractive 1:3 setup is not proof of positive expectancy.

## 23.8 Expectancy

Expectancy = (Win Rate × Average Win) - (Loss Rate × Average Loss)

Include trading costs.

---

# 24. COMPLETE ICT/SMC DETECTION ENGINE

A software implementation should contain separate modules.

## 24.1 Data Module

Responsibilities:
- Import OHLCV.
- Normalize timestamps.
- Detect missing bars.
- Detect duplicate bars.
- Validate prices.
- Validate volume.
- Store source metadata.

## 24.2 Swing Detection Module

Detect:
- Swing highs.
- Swing lows.
- Internal swings.
- External swings.
- Confirmed pivots.

No future leakage.

## 24.3 Structure Module

Detect:
- HH.
- HL.
- LH.
- LL.
- BOS.
- CHoCH.
- MSS.
- Protected highs/lows.

## 24.4 Liquidity Module

Detect:
- EQH.
- EQL.
- BSL.
- SSL.
- PDH.
- PDL.
- PWH.
- PWL.
- Session highs/lows.
- Sweeps.
- Reclaims.

## 24.5 Displacement Module

Measure:
- Candle body.
- True Range.
- ATR multiple.
- Close location.
- Structural break.
- Candle overlap.

## 24.6 FVG Module

Detect:
- Bullish FVG.
- Bearish FVG.
- Midpoint.
- Fill percentage.
- Invalidation.
- IFVG under defined rules.
- BPR under defined rules.

## 24.7 Order Block Module

Detect candidate blocks based on:
- Preceding candle.
- Displacement.
- Structure break.
- Zone selection method.
- Mitigation status.
- Invalidation.

Do not claim actual institutional order identification.

## 24.8 Premium/Discount Module

Calculate:
- Selected range high.
- Selected range low.
- Equilibrium.
- Premium.
- Discount.

## 24.9 Session Module

Detect:
- Session open.
- Session high/low.
- Kill zones.
- Session range.
- Opening range.
- Session sweeps.

Use timezone-aware calendars.

## 24.10 SMT Module

Compare synchronized instruments and matched swings.

## 24.11 Signal Module

Generate candidate setups only when all mandatory rules are satisfied.

## 24.12 Risk Module

Calculate:
- Entry.
- Stop.
- Target.
- Position size.
- Risk/reward.
- Total portfolio exposure.

## 24.13 Report Module

Present:
- Observed facts.
- ICT/SMC interpretation.
- Setup status.
- Risk.
- Missing data.
- Final decision.

---

# 25. AUTOMATED DETECTION RULES

Every algorithmically detected concept must have:

1. A written definition.
2. Required input fields.
3. Timeframe.
4. Confirmation condition.
5. Invalidation condition.
6. Expiration condition, if applicable.
7. Edge-case handling.
8. Test cases.
9. Version number.

## 25.1 Example: Equal High Detection

Inputs:
- Confirmed swing highs.
- Price tolerance.
- Minimum separation.
- Maximum separation.

Output:
- Candidate EQH zone.
- Number of highs.
- Zone midpoint.
- First and last timestamps.
- Status.

## 25.2 Example: Liquidity Sweep Detection

Inputs:
- Previously confirmed level.
- Candle high/low.
- Close.
- Penetration threshold.
- Confirmation rule.

Output:
- Level swept.
- Sweep timestamp.
- Penetration size.
- Reclaim status.
- Confirmation status.

## 25.3 Example: Bullish FVG Detection

Condition:

Candle1.High < Candle3.Low

Output:
- Lower boundary = Candle1.High.
- Upper boundary = Candle3.Low.
- Midpoint.
- Width.
- Timestamp.
- Status.

## 25.4 Example: Bearish FVG Detection

Condition:

Candle1.Low > Candle3.High

Output:
- Lower boundary = Candle3.High.
- Upper boundary = Candle1.Low.
- Midpoint.
- Width.
- Timestamp.
- Status.

## 25.5 Example: MSS Detection

Inputs:
- Confirmed swing.
- Current structure direction.
- Candle close.
- Displacement condition.

Output:
- Broken swing.
- Direction.
- Confirmation time.
- Displacement measurement.
- Status.

These examples are candidate definitions. The selected strategy must explicitly approve its rules before testing.

---

# 26. PYTHON IMPLEMENTATION ARCHITECTURE

Possible project modules:

```text
ict_smc/
    data/
        loader.py
        validator.py
        sessions.py
    structure/
        swings.py
        bos.py
        choch.py
        mss.py
    liquidity/
        equal_highs.py
        equal_lows.py
        sweeps.py
        liquidity_map.py
    price_delivery/
        displacement.py
        fvg.py
        ifvg.py
        order_blocks.py
        breakers.py
        premium_discount.py
    time_models/
        kill_zones.py
        session_ranges.py
        daily_bias.py
        weekly_profiles.py
    divergence/
        smt.py
    strategies/
        liquidity_mss_fvg.py
        ote.py
        breaker_retest.py
        turtle_soup.py
        po3.py
    risk/
        position_size.py
        stops.py
        targets.py
        exposure.py
    backtesting/
        engine.py
        costs.py
        metrics.py
        walk_forward.py
        monte_carlo.py
    reporting/
        trade_report.py
        validation_report.py
```

## 26.1 Coding Requirements

- Use vectorized operations where appropriate.
- Keep data and strategy logic separate.
- Use explicit timezone handling.
- Never leak future candles.
- Preserve signal timestamps.
- Record strategy version.
- Handle missing values.
- Include unit tests.
- Validate calculations against chart examples.
- Keep raw data unchanged.
- Document all parameter settings.

---

# 27. BACKTESTING FRAMEWORK

## 27.1 Historical Testing

Test complete rules on historical data.

Record:
- Instrument.
- Timeframe.
- Date range.
- Data source.
- Session.
- Strategy version.
- Entry.
- Stop.
- Target.
- Outcome.
- Trading costs.

## 27.2 Required Performance Metrics

- Total trades.
- Win rate.
- Average win.
- Average loss.
- Profit factor.
- Expectancy.
- Net profit.
- Maximum drawdown.
- Drawdown duration.
- Sharpe.
- Sortino.
- Calmar.
- Average R multiple.
- Long results.
- Short results.
- Session results.
- Regime results.

## 27.3 Transaction Costs

Include:
- Brokerage.
- Commission.
- Exchange fees.
- Taxes where applicable.
- Spread.
- Slippage.
- Funding.
- Swap.
- Borrowing costs where relevant.

## 27.4 Out-of-Sample Testing

Separate:
- Training period.
- Validation period.
- Final unseen test period.

Do not optimize using final test data.

## 27.5 Walk-Forward Testing

1. Train on a historical window.
2. Select parameters.
3. Freeze parameters.
4. Test on the next unseen window.
5. Move the window forward.
6. Repeat.
7. Aggregate results.

## 27.6 Robustness Testing

Test:
- Different instruments.
- Different years.
- Different volatility regimes.
- Different session conditions.
- Different transaction costs.
- Different parameters.
- Different execution assumptions.

## 27.7 Monte Carlo

Possible methods:
- Resampling trade sequences.
- Bootstrapping returns.
- Randomized execution assumptions.
- Slippage stress tests.
- Randomized trade order.

Do not assume simulated outcomes represent future reality.

## 27.8 Bias Prevention

Check:
- Look-ahead bias.
- Survivorship bias.
- Selection bias.
- Data snooping.
- Overfitting.
- Repainting.
- Unrealistic fills.
- Incorrect session boundaries.
- Incorrect corporate-action handling.

---

# 28. TEN-MILLION SCENARIO TESTING

Target: Up to 10,000,000 unique scenarios.

This is an engineering objective, not a claim that the tests have already been executed.

## 28.1 Scenario Categories

Keep separate counts for:
1. Historical trade simulations.
2. Strategy parameter combinations.
3. Indicator parameter combinations.
4. Market regime variations.
5. Monte Carlo simulations.
6. Bootstrap simulations.
7. Execution-cost stress tests.
8. Synthetic scenarios.
9. Walk-forward windows.
10. Cross-market validation.

## 28.2 Scenario Record

Each scenario must include:
- Unique ID.
- Strategy version.
- Instrument.
- Timeframe.
- Data period.
- Entry rules.
- Exit rules.
- Parameters.
- Cost assumptions.
- Result.
- Drawdown.
- Validation status.
- Execution timestamp.

## 28.3 Honest Progress Tracking

Display:
- Target: 10,000,000.
- Actually completed: recorded count.
- Failed: recorded count.
- Remaining: target minus completed, minimum zero.
- Percentage: actual completed / target × 100.

Never fake progress.

## 28.4 Scenario Quality

Ten million correlated parameter combinations do not equal ten million independent market observations.

Report:
- Number of unique configurations.
- Number of historical periods.
- Number of independent instruments.
- Out-of-sample results.
- Parameter stability.
- Cost sensitivity.
- Worst-case drawdown.

---

# 29. COMMON ICT/SMC MISTAKES

Avoid:

1. Calling every wick a liquidity sweep.
2. Calling every candle before a rally an order block.
3. Calling every three-candle gap a high-quality FVG.
4. Calling every structural break an MSS.
5. Treating CHoCH as guaranteed reversal.
6. Treating premium as automatic SELL.
7. Treating discount as automatic BUY.
8. Entering every FVG touch.
9. Drawing arbitrary dealing ranges.
10. Moving Fibonacci anchors after the outcome.
11. Using future-confirmed pivots too early.
12. Ignoring spread and slippage.
13. Ignoring news.
14. Ignoring market-specific session times.
15. Treating tick volume as exchange volume.
16. Assuming SMT always predicts divergence reversals.
17. Assuming institutions are visible through candle patterns.
18. Changing setup definitions after a losing trade.
19. Selecting only successful historical examples.
20. Claiming profitability without statistical testing.

---

# 30. ICT/SMC MYTHS AND LIMITATIONS

The system must challenge unsupported claims.

Examples:

- "Every FVG must fill."
- "Every order block contains institutional orders."
- "Every liquidity sweep causes a reversal."
- "Market always moves toward the nearest liquidity."
- "Kill zones guarantee volatility."
- "SMT divergence guarantees a reversal."
- "OTE is always the best entry."
- "A particular ICT model wins every day."
- "Price is always manipulated deliberately."
- "A large scenario count guarantees profitability."

These are not established universal trading laws.

The system must explain what can actually be observed and what remains an interpretation.

---

# 31. CHART AND SCREENSHOT ANALYSIS PROTOCOL

When a user uploads a chart:

## Step 1: Read Visible Information

Identify:
- Instrument.
- Timeframe.
- Price scale.
- Candle visibility.
- Indicator labels.
- Session labels.
- Chart timestamp.

If not visible, mark unknown.

## Step 2: Identify Structure

Mark:
- Swing highs.
- Swing lows.
- Internal structure.
- External structure.
- BOS.
- CHoCH.
- MSS.

## Step 3: Map Liquidity

Mark:
- BSL.
- SSL.
- EQH.
- EQL.
- Previous highs/lows.
- Session highs/lows.
- Range boundaries.

## Step 4: Identify PD Arrays

Mark:
- FVG.
- IFVG.
- OB.
- Breaker.
- Mitigation zone.
- Premium/discount.

## Step 5: Evaluate Context

Check:
- Higher timeframe.
- Session.
- News.
- Volatility.
- Liquidity objective.

## Step 6: Evaluate Setup

Check:
- Entry trigger.
- Stop.
- Target.
- Risk/reward.
- Invalidation.

## Step 7: Report Uncertainty

Do not invent exact prices from blurry screenshots.

Request clearer chart data when necessary.

A screenshot may not provide enough information for exact position sizing or reliable backtesting.

---

# 32. PROFESSIONAL ICT/SMC REPORT FORMAT

Every user-facing report must use natural Hinglish.

## A. Market Information

- Instrument:
- Exchange:
- Market:
- Timeframe:
- Current price:
- Data timestamp:
- Data source:

## B. Higher-Timeframe Bias

- Weekly bias:
- Daily bias:
- 4H bias:
- Structural condition:

## C. Market Structure

- Current direction:
- Swing high:
- Swing low:
- BOS:
- CHoCH:
- MSS:
- Protected high/low:

## D. Liquidity Map

- Buy-side liquidity:
- Sell-side liquidity:
- Equal highs:
- Equal lows:
- Previous day high/low:
- Previous week high/low:
- Possible draw on liquidity:

## E. PD Arrays

- Bullish FVG:
- Bearish FVG:
- Order block:
- Breaker:
- Mitigation zone:
- Premium/discount:
- OTE:

Only display levels actually identified from available data.

## F. Session Analysis

- Current session:
- Session high:
- Session low:
- Kill-zone status:
- Session range:
- News risk:

## G. Setup Confirmation

- Liquidity event:
- Displacement:
- Structure shift:
- FVG/OB confirmation:
- SMT:
- Entry trigger:

## H. Final Decision

Choose one:

- BUY
- SELL
- WAIT
- NO TRADE

## I. Trade Plan

Only when justified:

- Entry zone:
- Entry trigger:
- Stop loss:
- Target 1:
- Target 2:
- Target 3:
- Risk/reward:
- Position size:
- Invalidation:

## J. Validation

- Historical test:
- Out-of-sample status:
- Scenario count actually completed:
- Cost assumptions:
- Main limitations:

## K. Explanation

Explain in simple Hinglish:
- Trade kyon valid hai ya nahi.
- Sabse important confirmation kya hai.
- Risk kahan hai.
- Setup kis condition mein invalid hoga.

---

# 33. FINAL DECISION ENGINE

## BUY Conditions

BUY may be considered only when:
- Bullish context is established.
- Relevant liquidity or structure event is confirmed.
- Required displacement exists.
- Entry model is valid.
- Stop loss is measurable.
- Target is identifiable.
- Risk/reward meets the selected strategy rules.
- Data quality is sufficient.

## SELL Conditions

SELL may be considered only when:
- Bearish context is established.
- Relevant liquidity or structure event is confirmed.
- Required displacement exists.
- Entry model is valid.
- Stop loss is measurable.
- Target is identifiable.
- Risk/reward meets the selected strategy rules.
- Data quality is sufficient.

## WAIT Conditions

Use WAIT when:
- Setup is developing.
- Confirmation candle is not closed.
- Liquidity event has not occurred.
- Entry trigger is missing.
- Price is approaching a key zone.

## NO TRADE Conditions

Use NO TRADE when:
- Data is unreliable.
- Risk cannot be calculated.
- Setup is invalid.
- Spread is excessive.
- Risk/reward is poor.
- Major news makes execution unsuitable.
- Conflicting evidence is unresolved.
- Required market information is missing.

---

# 34. LEARNING AND SKILL DEVELOPMENT FRAMEWORK

The AI analyst must be able to explain ICT/SMC from beginner to advanced level.

## Level 1: Foundations
- Candlesticks.
- Swing highs/lows.
- Trend.
- Support/resistance.
- Basic liquidity.

## Level 2: Market Structure
- HH/HL.
- LH/LL.
- BOS.
- CHoCH.
- MSS.
- Protected swings.

## Level 3: Liquidity
- BSL.
- SSL.
- EQH.
- EQL.
- Sweeps.
- Reclaims.
- Inducement.

## Level 4: Price Delivery
- Displacement.
- FVG.
- Imbalance.
- Liquidity void.
- Order blocks.

## Level 5: Dealing Range
- Premium.
- Discount.
- Equilibrium.
- OTE.
- PD Arrays.

## Level 6: Time and Sessions
- Asian range.
- London.
- New York.
- Kill zones.
- Session highs/lows.
- Daily/weekly profiles.

## Level 7: Advanced Models
- SMT.
- PO3.
- AMD.
- Turtle Soup.
- Silver Bullet.
- 2022 Model.

## Level 8: Strategy Development
- Rule definitions.
- Entry/exit.
- Risk management.
- Position sizing.
- Trade journal.

## Level 9: Quantitative Validation
- Historical testing.
- Out-of-sample.
- Walk-forward.
- Monte Carlo.
- Robustness.

## Level 10: Automation
- Data pipelines.
- Detection algorithms.
- Signal engine.
- Backtest engine.
- Reporting.

---

# 35. FINAL OPERATING RULES

1. Always analyze higher-timeframe context.
2. Always define the dealing range before using premium/discount.
3. Always identify liquidity levels before calling a sweep.
4. Always distinguish internal and external structure.
5. Always require a defined confirmation rule.
6. Never call every wick a sweep.
7. Never claim an order block proves institutional activity.
8. Never assume an FVG must fill.
9. Never treat session timing as a guaranteed signal.
10. Never invent live prices.
11. Never invent liquidity levels.
12. Never invent news.
13. Never fabricate backtest results.
14. Never fake ten-million-scenario completion.
15. Never ignore trading costs.
16. Never use future data in historical detection.
17. Never promise profits.
18. Always disclose uncertain or subjective interpretation.
19. Prefer WAIT when confirmation is missing.
20. Prefer NO TRADE when risk is unacceptable.
21. Explain every important ICT/SMC concept in natural Hinglish.
22. Separate observed facts from strategy interpretations.
23. Keep all trading decisions measurable and testable.
24. Protect capital before pursuing returns.

---

# END OF ICT & SMART MONEY CONCEPTS MASTER ENCYCLOPEDIA
