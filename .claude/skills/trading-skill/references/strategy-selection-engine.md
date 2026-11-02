# STRATEGY SELECTION ENGINE
## Professional A-Z Trading Strategy Discovery, Classification, Evaluation, Ranking, Optimization, Validation and Decision System

**Version:** 1.0  
**Module:** AI Trading Analyst  
**Category:** Advanced Strategy Intelligence  
**User-facing language:** Natural Hinglish  
**Supported markets:** Forex, Crypto, Indian Stocks, Global Stocks, Indices, Futures, Commodities and Options  
**Supported styles:** Scalping, Intraday, Swing and Positional  
**Decision outputs:** BUY / SELL / WAIT / NO TRADE

---

# 1. CORE PURPOSE

Strategy Selection Engine ka main objective har market condition ke liye suitable trading strategy identify karna hai.

System ko sirf popular strategies recommend nahi karni hain. Usko determine karna hai:

1. Current market regime kya hai?
2. Market trend kar raha hai ya range mein hai?
3. Volatility normal hai ya extreme?
4. Momentum strong hai ya weak?
5. Liquidity sufficient hai ya nahi?
6. Kaunsi strategy current conditions ke saath compatible hai?
7. Kaunsi strategies unsuitable hain?
8. Candidate strategy ke supporting aur opposing signals kya hain?
9. Strategy historically test hui hai ya nahi?
10. Kya strategy out-of-sample validation pass karti hai?
11. Execution cost ke baad expected edge bachta hai ya nahi?
12. Kya risk acceptable hai?
13. Kya trade execute karna justified hai?
14. Kya WAIT ya NO TRADE better decision hai?

**Core principle:** Best strategy woh nahi jo sabse zyada indicators use karti hai. Best candidate woh hai jiska logic clear, risk defined, execution realistic aur evidence independently validated ho.

Strategy selection aur trade execution approval alag processes rahenge.

---

# 2. STRATEGY ENGINE ARCHITECTURE

Recommended architecture:

```text
STRATEGY SELECTION ENGINE
|
|-- 1. Market Data Input
|
|-- 2. Data Validation
|
|-- 3. Market Context Engine
|     |-- Market Regime
|     |-- Trend
|     |-- Volatility
|     |-- Momentum
|     |-- Structure
|     |-- Liquidity
|     |-- Volume
|     |-- News
|
|-- 4. Strategy Registry
|
|-- 5. Strategy Eligibility Filter
|
|-- 6. Strategy Candidate Generator
|
|-- 7. Strategy Compatibility Engine
|
|-- 8. Strategy Scoring Engine
|
|-- 9. Candidate Ranking
|
|-- 10. Historical Validation
|
|-- 11. Execution Cost Analysis
|
|-- 12. Risk Approval Engine
|
|-- 13. Trade Plan Generator
|
|-- 14. Trade Management Engine
|
|-- 15. Reporting and Audit Logs
```

Har module independently testable hona chahiye.

Ek module ki failure ko silently ignore karke false trade approval nahi dena hai.

---

# 3. STRATEGY TAXONOMY

Strategies ko categories aur subcategories mein organize karo.

## 3.1 Trend-Following Strategies

1. Moving Average Trend Following
2. EMA Alignment
3. SMA Crossover
4. Triple Moving Average
5. Moving Average Pullback
6. Trendline Break and Retest
7. ADX Trend Continuation
8. Supertrend Following
9. Ichimoku Trend Following
10. Donchian Trend Following
11. Parabolic SAR Following
12. Price Channel Trend
13. Higher High / Higher Low Continuation
14. Lower High / Lower Low Continuation
15. Momentum Trend Following
16. Breakout Continuation
17. ATR Trend Following
18. Multi-Timeframe Trend Alignment
19. Trailing Stop Trend Strategy
20. Long-Term Position Trend Following

**Suitable environments:**
- Established bullish trend.
- Established bearish trend.
- Sufficient directional movement.
- Acceptable liquidity.
- Manageable volatility.

**Avoid or reduce suitability when:**
- Market is repeatedly reversing.
- Price is stuck in a narrow range.
- Trend strength is deteriorating.
- Execution costs exceed expected edge.

## 3.2 Breakout Strategies

21. Horizontal Resistance Breakout
22. Horizontal Support Breakdown
23. Range Breakout
24. Opening Range Breakout
25. Previous Day High Breakout
26. Previous Day Low Breakdown
27. Previous Week High Breakout
28. Previous Week Low Breakdown
29. Asian Session Range Breakout
30. London Session Breakout
31. New York Session Breakout
32. Donchian Channel Breakout
33. Bollinger Band Squeeze Breakout
34. Volatility Compression Breakout
35. Triangle Breakout
36. Rectangle Breakout
37. Flag Breakout
38. Pennant Breakout
39. Cup and Handle Breakout
40. Trendline Breakout

**Confirmation requirements:**
- Valid breakout level.
- Close or acceptance beyond level.
- Reasonable spread.
- Participation confirmation when volume data is reliable.
- No immediate opposing HTF barrier.
- Risk-reward acceptable.
- False-breakout risk evaluated.

## 3.3 Pullback Strategies

41. EMA 20 Pullback
42. EMA 50 Pullback
43. Moving Average Cluster Pullback
44. Previous Resistance Retest
45. Previous Support Retest
46. Breakout Retest
47. Trendline Retest
48. Fibonacci Retracement Pullback
49. Golden Zone Pullback
50. VWAP Pullback
51. Anchored VWAP Pullback
52. Ichimoku Kijun Pullback
53. Supply-Demand Pullback
54. Order Block Pullback
55. Fair Value Gap Retracement
56. Premium-Discount Pullback
57. Higher Low Pullback Entry
58. Lower High Pullback Entry
59. Multi-Timeframe Pullback
60. Momentum Reset Pullback

**Requirements:**
- Directional context.
- Defined pullback zone.
- Evidence of continuation.
- Valid invalidation level.
- No blind entry solely because price touched an indicator.

## 3.4 Reversal Strategies

61. Double Top Reversal
62. Double Bottom Reversal
63. Triple Top Reversal
64. Triple Bottom Reversal
65. Head and Shoulders
66. Inverse Head and Shoulders
67. Rising Wedge Breakdown
68. Falling Wedge Breakout
69. Bearish Divergence Reversal
70. Bullish Divergence Reversal
71. Failed Breakout Reversal
72. Failed Breakdown Reversal
73. Liquidity Sweep Reversal
74. Spring and Upthrust
75. Candlestick Reversal
76. Support Rejection Reversal
77. Resistance Rejection Reversal
78. Climax Reversal
79. Exhaustion Gap Reversal
80. Volatility Exhaustion Reversal

**Important:** Reversal strategies countertrend risk carry karti hain. Structure confirmation ke bina early reversal prediction mat karo.

## 3.5 Mean-Reversion Strategies

81. Bollinger Band Mean Reversion
82. RSI Mean Reversion
83. Z-Score Mean Reversion
84. VWAP Mean Reversion
85. Anchored VWAP Reversion
86. Moving Average Reversion
87. Range Midpoint Reversion
88. Statistical Deviation Reversion
89. Keltner Channel Reversion
90. Pair Spread Mean Reversion
91. Cointegration-Based Pairs Trading
92. Price Deviation Reversion
93. Intraday Overextension Reversion
94. Volatility-Adjusted Reversion
95. Market Profile Value Area Reversion

**Avoid when:**
- Strong trend is developing.
- Breakout is confirmed.
- News is creating a new valuation.
- Price distribution is unstable.
- Mean and variance assumptions have changed.

## 3.6 Momentum Strategies

96. RSI Momentum Continuation
97. MACD Momentum Continuation
98. ROC Momentum
99. Momentum Breakout
100. Relative Strength Strategy
101. Relative Weakness Strategy
102. Volume Momentum
103. Multi-Timeframe Momentum
104. Momentum Divergence Confirmation
105. Momentum Acceleration
106. Price Rate-of-Change Ranking
107. Sector Momentum Rotation
108. Cross-Asset Momentum
109. Futures Momentum
110. Crypto Relative Momentum

## 3.7 Range Trading Strategies

111. Range Support Buying
112. Range Resistance Selling
113. Range Midpoint Filter
114. Range Rotation
115. Failed Range Breakout
116. False Breakdown Recovery
117. Range Liquidity Sweep
118. Value Area Rotation
119. VWAP Range Rotation
120. Short-Term Box Range Trading

## 3.8 Candlestick Strategies

121. Bullish Engulfing
122. Bearish Engulfing
123. Hammer
124. Shooting Star
125. Morning Star
126. Evening Star
127. Piercing Pattern
128. Dark Cloud Cover
129. Tweezer Top
130. Tweezer Bottom
131. Three White Soldiers
132. Three Black Crows
133. Inside Bar
134. Outside Bar
135. Pin Bar
136. Marubozu Continuation
137. Doji at Key Level
138. Harami Reversal
139. Three-Bar Reversal
140. Mother Bar Breakout

Candlestick patterns ko location, structure, timeframe aur confirmation ke saath use karo.

## 3.9 ICT / SMC Strategies

141. Break of Structure Continuation
142. Change of Character Reversal
143. Market Structure Shift
144. Order Block Retest
145. Breaker Block Retest
146. Mitigation Block Setup
147. Fair Value Gap Retracement
148. Inverse Fair Value Gap
149. Liquidity Sweep Setup
150. Equal High Sweep
151. Equal Low Sweep
152. Buy-Side Liquidity Raid
153. Sell-Side Liquidity Raid
154. Inducement-Based Setup
155. Premium-Discount Model
156. Optimal Trade Entry
157. Dealing Range Setup
158. Power of Three
159. Judas Swing
160. Silver Bullet Model
161. Turtle Soup
162. SMT Divergence
163. Previous Day Liquidity Setup
164. Previous Week Liquidity Setup
165. Session Liquidity Setup

ICT/SMC terminology ko observable price behaviour ke roop mein evaluate karo. Hidden institutional intentions ka unverified claim mat karo.

## 3.10 Volume and Order Flow Strategies

166. Volume Breakout
167. Relative Volume Expansion
168. OBV Trend Confirmation
169. MFI Reversal
170. Chaikin Money Flow
171. VWAP Trend
172. Anchored VWAP
173. Volume Profile POC Reversion
174. Value Area Breakout
175. HVN/LVN Reaction
176. CVD Divergence
177. Delta Imbalance
178. Footprint Absorption
179. Order Book Imbalance
180. Open Interest Expansion
181. Funding Rate Extreme Analysis
182. Liquidation Reversal
183. Volume Climax Reversal
184. Volume Dry-Up Breakout
185. Auction Market Rotation

Use only when the required data source is available and trustworthy.

## 3.11 Statistical and Quantitative Strategies

186. Z-Score Strategy
187. Linear Regression Channel
188. Kalman Filter Trend
189. Pairs Trading
190. Cointegration Strategy
191. Statistical Arbitrage
192. Residual Mean Reversion
193. Volatility Targeting
194. Time-Series Momentum
195. Cross-Sectional Momentum
196. Risk Parity Allocation
197. Factor-Based Ranking
198. Beta-Neutral Portfolio
199. Breakout Probability Model
200. Regime Switching Strategy

Statistical relationships can disappear. Monitor stationarity, parameter stability and structural breaks.

## 3.12 Other Advanced Strategy Categories

201. Seasonal Trading
202. Calendar Spread
203. Futures Term Structure
204. Carry Strategy
205. Volatility Risk Premium Research
206. Options Directional Strategy
207. Options Volatility Strategy
208. Covered Call
209. Protective Put
210. Cash-Secured Put
211. Defined-Risk Vertical Spread
212. Iron Condor
213. Iron Butterfly
214. Calendar Spread
215. Diagonal Spread
216. Event-Driven Strategy
217. Earnings Momentum
218. Post-Earnings Drift
219. Gap-and-Go
220. Gap-Fade
221. Sector Rotation
222. Index Relative Strength
223. Pairs Relative Value
224. Portfolio Rebalancing
225. Multi-Asset Trend Following

Some strategies require specialized instruments, short-selling access, options permissions, or institutional-grade data. Availability must be verified before recommendation.

---

# 4. STRATEGY REGISTRY

Every strategy must have a structured definition.

Required fields:

```text
strategy_id
strategy_name
category
subcategory
version
description
market_compatibility
timeframe_compatibility
trading_style
direction
required_features
optional_features
entry_conditions
confirmation_conditions
invalidation_conditions
stop_loss_method
take_profit_method
position_sizing_method
execution_requirements
risk_constraints
regime_compatibility
known_failure_modes
data_requirements
implementation_status
validation_status
```

## 4.1 Strategy Status

Possible statuses:

- IDEA
- DEFINED
- IMPLEMENTED
- UNIT_TESTED
- BACKTESTED
- WALK_FORWARD_VALIDATED
- OUT_OF_SAMPLE_VALIDATED
- PAPER_TESTED
- LIVE_MONITORED
- SUSPENDED
- RETIRED

Do not label a strategy validated unless required evidence exists.

## 4.2 Strategy Versioning

Every meaningful change should create a new version.

Example:

```text
EMA_PULLBACK_V1
EMA_PULLBACK_V2
EMA_PULLBACK_V3
```

Record:

- Changed parameters.
- Changed entry rules.
- Changed exits.
- Data period.
- Testing period.
- Performance differences.
- Reason for modification.

Do not overwrite historical test results.

---

# 5. STRATEGY INPUT REQUIREMENTS

Before selecting a strategy, gather:

## 5.1 Instrument Information

- Symbol.
- Asset class.
- Exchange.
- Broker.
- Contract specification.
- Quote currency.
- Trading hours.
- Tick size.
- Lot size.
- Minimum order size.

## 5.2 Trading Style

- Scalping.
- Intraday.
- Swing.
- Positional.
- Long-term investing, if supported by a separate portfolio framework.

## 5.3 Timeframes

- Higher timeframe.
- Setup timeframe.
- Entry timeframe.

## 5.4 Risk Profile

- Account equity.
- Maximum risk per trade.
- Daily loss limit.
- Maximum drawdown limit.
- Maximum open positions.
- Correlation restrictions.

Never assume the user's account balance or risk tolerance.

## 5.5 Market Data

- OHLCV.
- Spread.
- Bid/ask.
- Order book, if available.
- Volume.
- Open interest, if relevant.
- News and calendar.
- Corporate actions.
- Funding rates, if relevant.

Missing information should be explicitly marked.

---

# 6. MARKET CONTEXT AND STRATEGY COMPATIBILITY

Strategy selection must start with market context.

Read and integrate:

- market-regime-analysis.md
- market-structure.md
- volatility-analysis.md
- support-resistance.md
- price-action-strategies.md
- liquidity-analysis.md
- volume-analysis.md
- multi-timeframe-analysis.md

## 6.1 Regime Compatibility Matrix

| Market Regime | Preferred Candidate Categories | Caution |
|---|---|---|
| Strong Bullish Trend | Long trend following, pullback, momentum | Avoid late chasing |
| Strong Bearish Trend | Short trend following, rally selling | Short squeeze |
| Sideways Range | Mean reversion, range rotation | Breakout risk |
| Low Volatility | Compression, breakout watch | False signals |
| High Volatility | Selective momentum, reduced risk | Slippage |
| Transitional | Confirmation-based strategies | Whipsaw |
| Uncertain | Observation, WAIT | False confidence |
| Thin Liquidity | Usually no trade | Poor execution |

This matrix creates candidates; it does not approve trades.

## 6.2 Compatibility Rules

A candidate strategy should be rejected or downgraded when:

- Its required regime is absent.
- Its required data is unavailable.
- Execution cost is too high.
- Its timeframe is unsuitable.
- Its expected holding period conflicts with market conditions.
- Its risk cannot be calculated.
- Its validation is inadequate for the intended use.

---

# 7. STRATEGY ELIGIBILITY FILTER

Run hard filters before ranking.

## 7.1 Hard Rejection Conditions

Reject candidate if:

1. Required data is missing.
2. Entry logic is undefined.
3. Stop-loss logic is undefined.
4. Maximum loss cannot be estimated.
5. Instrument does not support the required order type.
6. Strategy requires unavailable short-selling or options access.
7. Spread is unacceptable.
8. Liquidity is insufficient.
9. Strategy is outside its intended market conditions.
10. Data quality fails validation.
11. Backtest contains unresolved look-ahead bias.
12. Position size cannot be calculated.
13. Risk limits would be violated.
14. Execution assumptions are unrealistic.
15. Strategy has no valid invalidation condition.

## 7.2 Soft Rejection Conditions

Downgrade when:

- MTF alignment is weak.
- Trend strength is declining.
- Momentum is contradictory.
- Volume confirmation is absent.
- Regime is unstable.
- News event is approaching.
- Similar strategies show correlated exposure.
- Candidate score is poorly calibrated.

---

# 8. STRATEGY CANDIDATE GENERATION

Generate candidates from independent analytical modules.

Example:

```text
Market: Bullish Trend
Volatility: Normal
Structure: HH/HL
Momentum: Positive
Liquidity: Normal

Generated candidates:
1. Trend Pullback
2. EMA Pullback
3. VWAP Pullback
4. Bullish Breakout Retest
5. Momentum Continuation
6. Bullish FVG Retracement
7. Higher-Low Continuation
```

Then test each candidate against:

- Entry validity.
- Regime compatibility.
- Confirmation.
- Invalidation.
- Risk.
- Execution.
- Historical evidence.

Do not generate a trade merely because a strategy matches the broad regime.

---

# 9. STRATEGY SCORING ENGINE

Use a transparent multi-factor scoring system.

Suggested initial weights:

| Factor | Weight |
|---|---:|
| Market Regime Compatibility | 20 |
| Price Structure | 15 |
| Entry Setup Quality | 15 |
| Multi-Timeframe Agreement | 10 |
| Momentum Confirmation | 10 |
| Volume / Liquidity | 10 |
| Risk-Reward Quality | 10 |
| Execution Quality | 5 |
| Historical Validation | 5 |
| Total | 100 |

These are design defaults, not scientifically established optimal weights.

Calibrate through training data and test on unseen data.

## 9.1 Factor Scoring

Each factor:

- 0 = No support / invalid.
- 1 = Weak support.
- 2 = Partial support.
- 3 = Moderate support.
- 4 = Strong support.
- 5 = Very strong support.

Missing evidence must be marked MISSING, not assigned a strong score.

## 9.2 Weighted Score

```text
Weighted Score =
SUM(Factor Score / 5 × Factor Weight)
```

## 9.3 Example Interpretation

Configurable initial bands:

- 85–100: High-priority candidate.
- 70–84: Potential candidate.
- 55–69: Weak candidate.
- Below 55: Reject or observe.

A high score is not a calibrated win probability.

## 9.4 Confidence Calibration

If the system reports a probability, it must be calibrated using historical predictions and actual outcomes.

Possible methods:

- Reliability diagrams.
- Brier score.
- Log loss.
- Isotonic regression.
- Platt scaling.

If calibration is unavailable, report a score rather than a probability.

---

# 10. STRATEGY RANKING AND SELECTION

Rank only candidates that pass hard filters.

Example:

```text
1. EMA Pullback
   Compatibility: Strong
   Score: Actual calculated score
   Status: Candidate

2. Breakout Retest
   Compatibility: Moderate
   Score: Actual calculated score
   Status: Candidate

3. Mean Reversion
   Compatibility: Weak
   Status: Rejected
   Reason: Strong directional trend
```

Selection rules:

1. Highest score does not override hard rejection.
2. Strategy with missing risk data cannot be approved.
3. Unvalidated strategies must be clearly labelled.
4. Correlated candidates should not be treated as independent confirmation.
5. Multiple similar indicators should not inflate confluence.
6. Final candidate must pass risk approval.
7. If no candidate passes, return WAIT or NO TRADE.

---

# 11. CONFLUENCE ENGINE

Confluence means multiple independent forms of evidence support a setup.

Possible evidence:

- Market structure.
- Support/resistance.
- Trend direction.
- Momentum.
- Volume.
- Liquidity.
- Volatility.
- MTF agreement.
- News context.

## 11.1 Independent Evidence

RSI, Stochastic and MACD can all be related to momentum. They should not automatically count as three independent confirmations.

Avoid indicator stacking.

## 11.2 Confluence Rules

- Record each evidence source.
- Identify overlapping information.
- Record contradictory signals.
- Avoid double-counting.
- Explain why each confirmation matters.

---

# 12. TREND-FOLLOWING STRATEGY SPECIFICATIONS

## 12.1 EMA Pullback

**Market condition:** Established trend.

**Bullish setup:**
- HTF bullish structure.
- Price above selected trend EMA.
- Pullback toward EMA zone.
- Bullish reaction.
- Momentum stabilizes.
- Invalidation below relevant swing structure.

**Bearish setup:**
- HTF bearish structure.
- Price below selected trend EMA.
- Rally toward EMA zone.
- Bearish rejection.
- Invalidation above relevant swing structure.

**Failure modes:**
- Range market.
- Deep trend reversal.
- News shock.
- Repeated EMA crossings.

## 12.2 MA Crossover

Conditions:

- Fast MA crosses slow MA.
- Price structure supports direction.
- Market is not excessively extended.
- Signal is evaluated only after candle confirmation if that is the chosen rule.

Failure modes:

- Sideways whipsaw.
- Lagging entries.
- Late signals.

## 12.3 ADX Trend Strategy

Use ADX for strength, DI for directional context and price structure for confirmation.

Never infer direction from ADX alone.

## 12.4 Donchian Breakout

Define:

- Lookback period.
- Breakout boundary.
- Entry trigger.
- Exit channel.
- Stop method.
- Position size.

Test parameter sensitivity and false breakouts.

---

# 13. BREAKOUT STRATEGY SPECIFICATIONS

## 13.1 Opening Range Breakout

Define:

- Market open time.
- Opening range duration.
- Exchange timezone.
- Breakout confirmation.
- Entry cutoff.
- Stop placement.
- Daily trade limit.

Do not use one exchange's session times for another market.

## 13.2 Range Breakout

Requirements:

- Valid range.
- Defined boundaries.
- Candle close or acceptance rule.
- Volatility assessment.
- Breakout follow-through.
- Risk-reward check.

## 13.3 Breakout Retest

Possible sequence:

1. Price breaks a defined level.
2. Price moves away from the level.
3. Price returns to retest.
4. Retest holds.
5. Confirmation appears.
6. Entry is considered.

A retest is not mandatory in every valid breakout strategy. Its absence should be handled according to the strategy specification.

## 13.4 False Breakout

Potential signals:

- Wick beyond boundary.
- Close back inside range.
- Failed follow-through.
- Opposite-side structure shift.
- Liquidity sweep.

Require explicit confirmation. Do not label every failed breakout a liquidity grab.

---

# 14. MEAN-REVERSION STRATEGY SPECIFICATIONS

## 14.1 Bollinger Mean Reversion

Assess:

- Bandwidth.
- Price deviation.
- Trend regime.
- Volatility.
- Mean stability.
- Re-entry confirmation.

Avoid blindly fading strong band walks.

## 14.2 Z-Score Reversion

```text
Z-Score = (Price - Mean) / Standard Deviation
```

Define:

- Rolling mean.
- Standard deviation window.
- Entry threshold.
- Exit threshold.
- Maximum holding period.
- Regime filter.

Rolling statistical properties must be monitored.

## 14.3 VWAP Reversion

Assess:

- Session VWAP.
- Anchored VWAP.
- Distance from VWAP.
- Trend direction.
- Volume.
- Session structure.

Price being far from VWAP alone does not guarantee a reversal.

## 14.4 Pairs Trading

Requirements:

- Economically meaningful pair.
- Cointegration testing where applicable.
- Hedge ratio estimation.
- Spread calculation.
- Entry/exit thresholds.
- Borrow availability.
- Both legs' execution costs.
- Structural-break monitoring.

Correlation alone does not prove cointegration.

---

# 15. REVERSAL STRATEGY SPECIFICATIONS

A reversal candidate must distinguish:

- Early reversal possibility.
- Confirmed structure change.
- Failed reversal.
- Countertrend pullback.

Assess:

1. Prior trend exhaustion.
2. Important level.
3. Momentum divergence.
4. Liquidity event.
5. Rejection.
6. Structural shift.
7. Retest or follow-through.
8. Invalidation.

Never call a reversal confirmed using one candle pattern alone.

---

# 16. PRICE ACTION STRATEGY INTEGRATION

Use price-action module for:

- Swing structure.
- Breakout.
- Retest.
- Rejection.
- Compression.
- Expansion.
- Pullback.
- Range.
- Failed auction.

Every setup should have:

- Location.
- Context.
- Trigger.
- Invalidation.
- Expected path.
- Alternative scenario.

---

# 17. ICT / SMC STRATEGY INTEGRATION

Possible setups:

- Liquidity sweep.
- BOS continuation.
- CHoCH reversal.
- MSS confirmation.
- Order Block retest.
- Breaker Block.
- Fair Value Gap.
- Inverse FVG.
- Premium/Discount.
- OTE.
- Session-based setup.
- SMT divergence.

Rules:

1. Define swing points objectively.
2. Define what qualifies as displacement.
3. Define the FVG calculation.
4. Define order-block selection.
5. Avoid hindsight marking.
6. Use confirmed candles.
7. Record alternative explanations.
8. Backtest every entry rule.

ICT/SMC concepts are analytical frameworks, not proof of hidden institutional orders.

---

# 18. VOLUME AND ORDER FLOW INTEGRATION

Available tools:

- RVOL.
- OBV.
- MFI.
- CMF.
- VWAP.
- Volume Profile.
- CVD.
- Delta.
- Footprint.
- Order Book.
- Open Interest.
- Funding.
- Liquidations.

Rules:

- Verify source and timestamp.
- Confirm market coverage.
- Avoid mixing incompatible feeds.
- Distinguish exchange volume from total market volume.
- Never invent unavailable order-flow information.

---

# 19. MULTI-TIMEFRAME STRATEGY SELECTION

Use:

- HTF for context.
- ITF for setup.
- LTF for trigger.

Example:

```text
Weekly: Bullish
Daily: Bullish
4H: Pullback
1H: Bullish recovery
15M: Entry confirmation pending
```

Decision:

Bullish pullback strategy candidate may be considered, but trade approval waits for valid entry and risk calculation.

Conflict example:

```text
Daily: Bullish
4H: Bearish
1H: Bearish
15M: Bearish
```

Interpretation:

Potential correction or reversal. Do not automatically buy because the daily chart is bullish.

---

# 20. STRATEGY SELECTION BY TRADING STYLE

## 20.1 Scalping

Requirements:

- Reliable low-latency data.
- Tight spread.
- Adequate liquidity.
- Realistic fee and slippage model.
- Fast execution.
- Strict daily risk limits.

Candidate strategies:

- Micro pullback.
- VWAP reaction.
- Opening momentum.
- Order-flow imbalance.
- Short-term breakout.

If execution quality is unavailable, do not recommend a scalping system as reliably implementable.

## 20.2 Intraday

Candidate strategies:

- Opening Range Breakout.
- VWAP Pullback.
- Previous Day High/Low.
- Session Breakout.
- Intraday Momentum.
- Range Rotation.
- Gap-and-Go.
- Gap-Fade.

Include intraday cutoff and overnight position restrictions where relevant.

## 20.3 Swing

Candidate strategies:

- Daily Trend Pullback.
- Breakout Retest.
- Relative Strength.
- Support/Resistance Reversal.
- Weekly Structure Continuation.
- Momentum Rotation.

Include overnight gaps, earnings and macro event risk.

## 20.4 Positional

Candidate strategies:

- Long-Term Trend Following.
- Sector Rotation.
- Relative Strength.
- Fundamental-Momentum Combination.
- Portfolio Rebalancing.
- Long-Term Breakout.

Include corporate actions, fundamental changes and portfolio concentration.

---

# 21. MARKET-SPECIFIC STRATEGY FILTERS

## 21.1 Forex

Consider:

- Currency pair.
- Base and quote currency.
- Session.
- Spread.
- Rollover.
- Interest-rate differential.
- Economic releases.
- Broker execution.
- Contract size.

Do not assume one broker's tick volume represents the entire Forex market.

## 21.2 Crypto

Consider:

- Exchange.
- Trading pair.
- Liquidity.
- Funding rate.
- Open interest.
- Liquidation risk.
- 24/7 sessions.
- Exchange outage.
- Network and custody risk.
- Asset-specific volatility.

Different exchanges can have different prices and order books.

## 21.3 Indian Stocks

Consider:

- NSE/BSE.
- Cash or derivatives.
- Lot size.
- Tick size.
- Market hours.
- Circuit limits.
- F&O restrictions.
- Corporate actions.
- Earnings.
- SEBI rules.
- Brokerage and statutory charges.

Verify current instrument specifications and regulations before use.

## 21.4 Global Stocks

Consider:

- Exchange.
- Trading hours.
- Earnings calendar.
- Market breadth.
- Sector performance.
- Currency exposure.
- Overnight gaps.
- Short-selling availability.

## 21.5 Indices

Consider:

- Index constituents.
- Breadth.
- Futures basis.
- Volatility.
- Economic events.
- Opening gaps.
- Contract specifications.

## 21.6 Futures

Consider:

- Contract expiry.
- Rollover.
- Tick value.
- Margin.
- Contango/backwardation.
- Contract liquidity.
- Delivery and settlement.

## 21.7 Commodities

Consider:

- Inventory reports.
- Weather.
- Supply-demand.
- Seasonality.
- Geopolitical events.
- Contract expiry.
- Storage and delivery.

## 21.8 Options

Consider:

- Underlying direction.
- Implied volatility.
- Realized volatility.
- IV skew.
- Expiry.
- Greeks.
- Bid-ask spread.
- Open interest.
- Exercise and settlement rules.

Do not select an options strategy using directional signals alone.

---

# 22. OPTIONS STRATEGY SELECTION

Possible categories:

### Bullish
- Long Call.
- Bull Call Spread.
- Cash-Secured Put.
- Protective structure as applicable.

### Bearish
- Long Put.
- Bear Put Spread.
- Defined-risk bearish spread.

### Neutral / Range
- Iron Condor.
- Iron Butterfly.
- Calendar Spread.
- Defined-risk range structures.

### Volatility Expansion
- Long Straddle.
- Long Strangle.
- Other defined-risk long-volatility structures.

### Volatility Contraction
- Carefully evaluated short-volatility structures.
- Defined-risk spreads.

For each strategy calculate:

- Maximum profit.
- Maximum loss.
- Breakeven.
- Net debit or credit.
- Greeks.
- Margin.
- Expiry risk.
- Assignment risk.
- Liquidity.
- Transaction costs.

Never recommend undefined or poorly understood risk structures without explicit risk disclosure.

---

# 23. NEWS AND EVENT FILTER

Before strategy approval, inspect:

- Economic calendar.
- Central bank announcements.
- Inflation releases.
- Employment data.
- Earnings.
- Regulatory announcements.
- Geopolitical events.
- Exchange announcements.
- Commodity inventory releases.

Rules:

1. Use current timestamp.
2. Verify event source.
3. Identify affected instruments.
4. Estimate scheduled event risk.
5. Check whether strategy is designed for event trading.
6. Include gap and slippage risk.
7. Avoid claiming news is live without verified data.

News blackout windows should be strategy-specific and validated.

---

# 24. ENTRY ENGINE

Each strategy must define an exact trigger.

Possible trigger types:

- Candle close.
- Breakout confirmation.
- Retest confirmation.
- Limit-zone touch plus reaction.
- Indicator crossover.
- Structure break.
- Liquidity sweep plus confirmation.
- Order-flow confirmation.

Required output:

```text
Entry Direction:
Entry Type:
Entry Price or Zone:
Trigger:
Confirmation:
Invalidation:
Expiry of Setup:
```

A setup that has already moved far beyond its planned entry may be invalidated.

Do not chase it.

---

# 25. STOP LOSS ENGINE

Possible methods:

- Swing-based.
- Structure-based.
- ATR-based.
- Volatility-based.
- Range boundary.
- Support/resistance.
- Options premium risk.
- Time-based exit.

Rules:

1. Stop must represent trade invalidation.
2. Stop distance must be measurable.
3. Position size must be recalculated after stop selection.
4. Include tick value and contract multiplier.
5. Include fees and estimated slippage.
6. Do not widen a stop to hide a losing position.
7. Avoid placing stop at arbitrary levels without structural reason.

---

# 26. TAKE PROFIT ENGINE

Possible methods:

- Fixed R multiple.
- Next structure level.
- Range boundary.
- Liquidity target.
- ATR projection.
- Trailing stop.
- Partial exits.
- Time-based exit.

Output:

```text
TP1:
TP2:
TP3:
Target Logic:
Expected R:R:
Invalidation:
Trailing Rule:
```

Targets should not be invented when chart data is insufficient.

---

# 27. POSITION SIZING AND RISK APPROVAL

Inputs:

- Account equity.
- Risk percentage.
- Entry.
- Stop.
- Tick size.
- Tick value.
- Contract multiplier.
- Currency conversion.
- Fees.
- Slippage.

Basic formula:

```text
Risk Amount = Equity × Risk Percentage

Position Size =
Risk Amount / Estimated Loss Per Unit
```

Apply:

- Maximum trade risk.
- Daily loss limit.
- Portfolio risk.
- Correlation.
- Leverage.
- Margin.
- Exposure limits.
- Drawdown restrictions.

Risk approval must be independent of strategy score.

A strategy score of 95/100 does not justify exceeding the user's risk limit.

---

# 28. CORRELATED STRATEGY CONTROL

Multiple strategies may produce similar exposures.

Examples:

- EMA pullback and MA pullback.
- RSI momentum and MACD momentum.
- BTC trend and correlated altcoin trend.
- Nifty and Bank Nifty exposure.
- Multiple USD pairs.

Rules:

1. Detect correlated positions.
2. Estimate portfolio-level exposure.
3. Avoid double-counting independent setups.
4. Apply portfolio risk limits.
5. Monitor changing correlations.
6. Recalculate during market stress.

Correlation is dynamic and should not be treated as fixed.

---

# 29. STRATEGY DIVERSIFICATION

Diversify by:

- Asset.
- Timeframe.
- Strategy category.
- Market regime.
- Holding period.
- Return drivers.

Do not combine many strategies that all depend on the same trend factor and call it diversification.

Measure:

- Return correlation.
- Drawdown overlap.
- Exposure overlap.
- Tail dependence.
- Liquidity overlap.

---

# 30. STRATEGY PERFORMANCE METRICS

Every backtested strategy should report:

## Returns
- Gross Return.
- Net Return.
- CAGR where applicable.
- Annualized Return.
- Monthly Return.
- Benchmark-relative Return.

## Risk
- Maximum Drawdown.
- Average Drawdown.
- Drawdown Duration.
- Volatility.
- Value at Risk.
- Expected Shortfall.
- Risk of Ruin estimate.

## Trade Quality
- Number of Trades.
- Win Rate.
- Average Win.
- Average Loss.
- Profit Factor.
- Expectancy.
- Average R.
- Median R.
- Maximum Consecutive Losses.

## Execution
- Spread.
- Slippage.
- Fees.
- Rejections.
- Partial Fills.
- Turnover.
- Market Impact where measurable.

## Stability
- Out-of-Sample Performance.
- Walk-Forward Stability.
- Parameter Sensitivity.
- Regime-Specific Performance.
- Asset-Specific Performance.

---

# 31. EXPECTANCY AND PROFIT FACTOR

Expectancy:

```text
Expectancy =
(Win Rate × Average Win)
-
(Loss Rate × Average Loss)
```

Profit Factor:

```text
Profit Factor =
Gross Profit / Absolute Gross Loss
```

Calculate using net or gross values clearly labelled.

A high win rate does not guarantee positive expectancy.

A profitable backtest does not guarantee future profitability.

---

# 32. OVERFITTING PREVENTION

Avoid:

- Excessive parameter optimization.
- Testing thousands of combinations and reporting only the best.
- Reusing test data for optimization.
- Ignoring delisted assets.
- Ignoring survivorship bias.
- Ignoring transaction costs.
- Ignoring execution delay.
- Selecting only favourable periods.
- Ignoring structural breaks.

Use:

- Training/validation/test separation.
- Walk-forward analysis.
- Parameter stability.
- Multiple markets.
- Multiple regimes.
- Reality-check procedures where appropriate.
- Independent final test data.

---

# 33. BACKTESTING ENGINE INTEGRATION

Use backtesting.md.

Every strategy test must specify:

```text
Strategy ID:
Strategy Version:
Asset:
Exchange:
Timeframe:
Historical Period:
Data Source:
Entry Rules:
Exit Rules:
Stop Method:
Target Method:
Position Sizing:
Fees:
Spread:
Slippage:
Execution Model:
Training Period:
Validation Period:
Test Period:
Results:
Limitations:
```

## 33.1 Execution Simulation

Model:

- Market orders.
- Limit orders.
- Stop orders.
- Stop-limit orders.
- Partial fills.
- Slippage.
- Spread.
- Rejections.
- Gaps.
- Intrabar ambiguity.

If only OHLC bars are available, intrabar fill assumptions must be conservative and disclosed.

## 33.2 Backtest Bias Checks

- Look-ahead bias.
- Survivorship bias.
- Selection bias.
- Data snooping.
- Corporate action errors.
- Timestamp errors.
- Repainting.
- Unrealistic fills.
- Incorrect fees.
- Incorrect futures roll.

---

# 34. WALK-FORWARD VALIDATION

Procedure:

1. Define training window.
2. Fit or configure strategy.
3. Freeze parameters.
4. Test next unseen window.
5. Advance window.
6. Repeat.
7. Aggregate all unseen results.
8. Inspect stability.

Report each window separately.

Do not hide failed windows.

---

# 35. MONTE CARLO AND STRESS TESTING

Possible tests:

- Trade sequence bootstrap.
- Block bootstrap.
- Randomized slippage.
- Randomized fees.
- Execution delays.
- Missed fills.
- Gap shocks.
- Volatility shocks.
- Spread widening.
- Liquidity reduction.
- Parameter perturbation.
- Regime changes.
- Correlation breakdown.

Preserve temporal dependence when necessary.

Do not treat simple random shuffling as a complete model of market behaviour.

---

# 36. 10 MILLION SCENARIO TESTING FRAMEWORK

Target: 10,000,000 distinct scenarios.

This is an engineering target, not a claim of completed execution.

## 36.1 Scenario Dimensions

- Asset.
- Market.
- Exchange.
- Timeframe.
- Strategy.
- Strategy version.
- Market regime.
- Volatility regime.
- Momentum regime.
- Liquidity regime.
- Entry trigger.
- Stop method.
- Target method.
- Position size.
- Slippage.
- Fees.
- Spread.
- Execution delay.
- Market session.
- News condition.
- Parameter variation.
- Correlation condition.
- Regime transition.
- Gap condition.

## 36.2 Scenario Categories

1. Historical market replay.
2. Parameter combinations.
3. Monte Carlo sequences.
4. Synthetic market paths.
5. Execution stress tests.
6. Volatility stress tests.
7. Liquidity stress tests.
8. News event simulations.
9. Regime transition simulations.
10. Cross-asset validation.
11. Walk-forward model tests.
12. Portfolio-level stress tests.

Report every category separately.

A synthetic scenario is not a real historical trade.

A parameter combination is not automatically an independent market observation.

## 36.3 Scenario Generation

Use deterministic seeds and reproducible parameter manifests.

Avoid duplicate scenarios.

Track unique scenario hashes.

## 36.4 Scenario Record

```text
scenario_id
scenario_hash
strategy_id
strategy_version
asset
exchange
timeframe
data_source
data_period
regime
parameter_set
entry_rule
exit_rule
slippage
fees
spread
execution_delay
scenario_type
result
drawdown
validation_status
timestamp
```

## 36.5 Completion Report

```text
Target Scenarios: 10,000,000
Executed: Actual Count
Unique: Verified Count
Successful: Actual Count
Failed: Actual Count
Skipped: Actual Count
Historical Scenarios: Actual Count
Synthetic Scenarios: Actual Count
Parameter Combinations: Actual Count
Out-of-Sample Tests: Actual Count
Execution Status: Actual Status
Results Location: Actual Location
```

Never fabricate results.

---

# 37. STRATEGY FAILURE ANALYSIS

When a strategy fails, classify the cause:

- Wrong regime.
- Incorrect structure interpretation.
- False breakout.
- Early entry.
- Late entry.
- Poor stop placement.
- Overfitting.
- Excessive spread.
- Slippage.
- News shock.
- Liquidity collapse.
- Data error.
- Execution error.
- Correlation shock.
- Model drift.
- Unclear rules.

Record the failure.

Do not modify the strategy merely to make one losing trade look correct.

---

# 38. STRATEGY DRIFT MONITORING

Monitor:

- Win rate drift.
- Expectancy drift.
- Drawdown changes.
- Signal frequency.
- Feature distribution changes.
- Regime frequency changes.
- Execution cost changes.
- Model confidence changes.
- Parameter sensitivity.

Possible actions:

- Continue monitoring.
- Reduce exposure.
- Suspend strategy.
- Retrain model.
- Revalidate.
- Retire strategy.

Retraining does not automatically mean approval for live use.

---

# 39. PAPER TRADING VALIDATION

Before live deployment:

1. Freeze strategy version.
2. Run paper trading.
3. Record every signal.
4. Compare expected and actual fills.
5. Measure spread and slippage.
6. Compare paper results with backtest.
7. Evaluate operational reliability.
8. Review risk controls.
9. Document deviations.
10. Approve or reject deployment.

Paper trading is not equivalent to real-money execution.

---

# 40. LIVE STRATEGY MONITORING

Monitor:

- Market regime.
- Signal quality.
- Open positions.
- Daily P&L.
- Drawdown.
- Margin.
- Slippage.
- Spread.
- Rejections.
- Data latency.
- API errors.
- Strategy drift.

Emergency suspension conditions:

- Data feed unreliable.
- Broker execution unavailable.
- Risk limits exceeded.
- Unexpected order behaviour.
- Duplicate orders.
- Uncontrolled exposure.
- Strategy logic malfunction.

Automation should have a kill switch and reconciliation process.

---

# 41. PYTHON STRATEGY DATA MODEL

```python
from dataclasses import dataclass, field
from typing import List, Optional

@dataclass
class StrategyDefinition:
    strategy_id: str
    name: str
    category: str
    version: str
    supported_markets: List[str]
    supported_regimes: List[str]
    supported_styles: List[str]
    required_features: List[str]
    validation_status: str
    enabled: bool = True

@dataclass
class StrategyCandidate:
    strategy_id: str
    market: str
    timeframe: str
    regime: str
    score: Optional[float]
    evidence: List[str] = field(default_factory=list)
    conflicts: List[str] = field(default_factory=list)
    rejection_reasons: List[str] = field(default_factory=list)
    eligible: bool = False
    validation_status: str = "UNVALIDATED"
```

---

# 42. PYTHON STRATEGY REGISTRY

```python
class StrategyRegistry:

    def __init__(self):
        self._strategies = {}

    def register(self, strategy):
        if strategy.strategy_id in self._strategies:
            raise ValueError("Duplicate strategy ID")

        self._strategies[strategy.strategy_id] = strategy

    def get(self, strategy_id):
        return self._strategies.get(strategy_id)

    def all(self):
        return list(self._strategies.values())

    def enabled(self):
        return [
            s for s in self._strategies.values()
            if s.enabled
        ]

    def by_category(self, category):
        return [
            s for s in self.enabled()
            if s.category == category
        ]
```

Registry should preserve version and validation status.

---

# 43. PYTHON ELIGIBILITY FILTER

```python
def check_strategy_eligibility(
    strategy,
    market,
    regime,
    style,
    available_features
):
    reasons = []

    if not strategy.enabled:
        reasons.append("Strategy disabled")

    if market not in strategy.supported_markets:
        reasons.append("Market not supported")

    if regime not in strategy.supported_regimes:
        reasons.append("Regime incompatible")

    if style not in strategy.supported_styles:
        reasons.append("Trading style incompatible")

    missing = [
        feature
        for feature in strategy.required_features
        if feature not in available_features
    ]

    if missing:
        reasons.append(
            f"Missing features: {missing}"
        )

    return {
        "eligible": len(reasons) == 0,
        "reasons": reasons
    }
```

This filter checks declared compatibility only. It does not prove strategy profitability.

---

# 44. PYTHON SCORING ENGINE

```python
DEFAULT_WEIGHTS = {
    "regime": 20,
    "structure": 15,
    "setup": 15,
    "mtf": 10,
    "momentum": 10,
    "volume_liquidity": 10,
    "risk_reward": 10,
    "execution": 5,
    "validation": 5
}

def calculate_strategy_score(
    factor_scores,
    weights=DEFAULT_WEIGHTS
):
    total = 0
    available_weight = 0

    for factor, weight in weights.items():
        value = factor_scores.get(factor)

        if value is None:
            continue

        if not 0 <= value <= 5:
            raise ValueError(
                f"Invalid score for {factor}"
            )

        total += (value / 5) * weight
        available_weight += weight

    if available_weight == 0:
        return {
            "score": None,
            "coverage": 0
        }

    return {
        "score": round(total, 2),
        "coverage": round(
            available_weight / sum(weights.values()),
            3
        )
    }
```

Coverage report karna mandatory hai.

Incomplete factor data ke saath full-confidence score display mat karo.

---

# 45. PYTHON CANDIDATE RANKING

```python
def rank_candidates(candidates):
    eligible = [
        candidate
        for candidate in candidates
        if candidate.eligible
        and candidate.score is not None
    ]

    return sorted(
        eligible,
        key=lambda x: x.score,
        reverse=True
    )
```

Ranking se pehle hard rejection conditions apply honi chahiye.

---

# 46. PYTHON STRATEGY DECISION

```python
def select_strategy(candidates, minimum_score=70):
    ranked = rank_candidates(candidates)

    if not ranked:
        return {
            "decision": "WAIT",
            "reason": "No eligible strategy"
        }

    best = ranked[0]

    if best.score < minimum_score:
        return {
            "decision": "WAIT",
            "reason": "No candidate passed score threshold"
        }

    if best.validation_status == "UNVALIDATED":
        return {
            "decision": "WAIT",
            "reason": "Candidate has not been validated"
        }

    return {
        "decision": "CANDIDATE_SELECTED",
        "strategy_id": best.strategy_id,
        "score": best.score,
        "reason": "Best eligible candidate"
    }
```

CANDIDATE_SELECTED is not a BUY or SELL approval.

Trade approval must pass the independent risk and execution modules.

---

# 47. TESTING FRAMEWORK

Test:

1. Duplicate strategy IDs.
2. Missing strategy features.
3. Unsupported market.
4. Unsupported regime.
5. Unsupported timeframe.
6. Missing price data.
7. Missing volatility data.
8. Incomplete risk parameters.
9. Invalid stop loss.
10. Negative position size.
11. Excessive spread.
12. Low liquidity.
13. Unvalidated strategy.
14. Out-of-sample failure.
15. Strategy score with missing inputs.
16. Duplicate candidates.
17. Correlated candidates.
18. Conflicting market signals.
19. News event risk.
20. Strategy registry failure.
21. API failure.
22. Backtest data leakage.
23. Parameter instability.
24. Execution mismatch.
25. Daily risk limit breach.

Expected behaviour:

- Invalid input: reject.
- Missing critical evidence: WAIT.
- Risk failure: NO TRADE.
- No eligible candidate: WAIT.
- Unverified result: label clearly.

---

# 48. FINAL DECISION ENGINE

Decision hierarchy:

```text
1. IS DATA VALID?
   NO -> UNCERTAIN / NO TRADE

2. IS MARKET CONTEXT AVAILABLE?
   NO -> WAIT

3. IS REGIME CLASSIFIED?
   NO -> UNCERTAIN / WAIT

4. ARE STRATEGIES COMPATIBLE?
   NO -> WAIT

5. DOES A CANDIDATE PASS HARD FILTERS?
   NO -> WAIT

6. IS ENTRY SETUP VALID?
   NO -> WAIT

7. IS INVALIDATION DEFINED?
   NO -> NO TRADE

8. IS POSITION SIZE CALCULABLE?
   NO -> NO TRADE

9. ARE EXECUTION CONDITIONS ACCEPTABLE?
   NO -> NO TRADE

10. DOES RISK APPROVAL PASS?
    NO -> NO TRADE

11. IS TRADE DIRECTION CONFIRMED?
    YES -> BUY / SELL CANDIDATE
    NO -> WAIT
```

BUY / SELL output tabhi generate karo jab all mandatory checks pass hon.

---

# 49. STANDARD STRATEGY SELECTION REPORT

Har complete analysis mein ye format use karo:

## Strategy Selection Report

**Asset:**  
**Exchange:**  
**Current Price:**  
**Timestamp:**  
**Trading Style:**  
**Analysis Timeframe:**  

### A. Market Context
- Market Regime:
- Trend:
- Volatility:
- Momentum:
- Structure:
- Liquidity:
- News Risk:

### B. Strategy Candidates

| Rank | Strategy | Compatibility | Score | Status |
|---|---|---|---:|---|
| 1 | Actual candidate | Actual assessment | Calculated | Candidate |
| 2 | Actual candidate | Actual assessment | Calculated | Candidate |
| 3 | Actual candidate | Actual assessment | Calculated | Rejected / Candidate |

Never fill example values with invented live results.

### C. Best Candidate
- Strategy:
- Direction:
- Why selected:
- Supporting evidence:
- Opposing evidence:
- Missing information:

### D. Trade Setup
- Entry:
- Entry Trigger:
- Stop Loss:
- TP1:
- TP2:
- TP3:
- Risk-to-Reward:
- Position Size:

If insufficient data, write NOT AVAILABLE.

### E. Strategy Validation
- Backtest Status:
- Historical Period:
- Out-of-Sample Status:
- Walk-Forward Status:
- Paper Trading Status:
- Known Limitations:

### F. Risk Assessment
- Market Risk:
- Volatility Risk:
- Liquidity Risk:
- News Risk:
- Execution Risk:
- Portfolio Risk:

### G. Final Decision
- BUY / SELL / WAIT / NO TRADE
- Reason:
- Required Confirmation:
- Invalidation:

### H. Simple Hinglish Explanation

User ko clearly samjhao:
- Market kis condition mein hai.
- Strategy kyun suitable hai ya unsuitable.
- Trade abhi valid hai ya confirmation pending.
- Sabse important risk kya hai.

---

# 50. SCREENSHOT ANALYSIS RULES

When user uploads chart screenshot:

1. Visible symbol identify karo.
2. Visible timeframe read karo.
3. Price structure identify karo.
4. Market regime assess karo.
5. Available indicators read karo.
6. Candidate strategies identify karo.
7. Supporting evidence note karo.
8. Conflicting evidence note karo.
9. Entry and invalidation only if price scale is readable.
10. Missing data clearly disclose karo.

Do not invent:

- Exact current price.
- Hidden indicator values.
- Volume.
- Order-book data.
- News.
- Historical performance.

A screenshot is not a complete backtest dataset.

---

# 51. USER INTERACTION RULES

If user asks:

**"Best strategy batao"**

First determine asset, trading style and available market context. If necessary, ask one important missing question.

**"BUY ya SELL?"**

Check live data availability and valid setup. Without reliable data, ask for chart or data.

**"Meri strategy test karo"**

Request complete entry, exit, stop, timeframe and instrument rules. Do not invent missing rules.

**"1 crore baar test karo"**

Explain whether actual executable data and compute are available. Build or run the framework only when technically possible. Report actual executed count.

**"Guaranteed profitable strategy do"**

Explain that no strategy can guarantee profit.

**"High win rate strategy do"**

Explain that win rate alone is insufficient. Evaluate expectancy, average loss, drawdown and transaction costs.

**"Free strategy do"**

Prefer transparent, reproducible rules and open-source implementation options. Do not invent free data/API availability.

---

# 52. AUTOMATION AND API ARCHITECTURE

Possible components:

- Market data connector.
- Exchange connector.
- Broker connector.
- Economic calendar connector.
- News connector.
- Feature calculation service.
- Strategy registry.
- Backtest engine.
- Risk engine.
- Alert system.
- Trade journal.
- Model monitoring.

API security:

- Use environment variables.
- Never hardcode API keys.
- Use least-privilege permissions.
- Avoid withdrawal permissions for trading API keys.
- Keep test and live credentials separate.
- Log API errors safely.
- Apply rate limits.
- Reconcile orders and positions.

Do not claim a broker or exchange connection exists unless configured and tested.

---

# 53. STRATEGY GOVERNANCE

Every strategy must have:

- Owner or source.
- Version.
- Documented rules.
- Required data.
- Known risks.
- Testing history.
- Approval status.
- Deployment status.
- Suspension criteria.

Deployment stages:

```text
IDEA
  |
DEFINED
  |
IMPLEMENTED
  |
UNIT TESTED
  |
BACKTESTED
  |
WALK-FORWARD TESTED
  |
OUT-OF-SAMPLE TESTED
  |
PAPER TESTED
  |
RISK APPROVED
  |
LIVE MONITORING
```

Skipping stages must be explicitly justified.

---

# 54. REFERENCE INTEGRATION

This module coordinates with:

- SKILL.md
- news-analysis.md
- fundamental-analysis.md
- candlestick-patterns.md
- chart-patterns.md
- technical-indicators.md
- ict-smc.md
- risk-management.md
- trade-management.md
- backtesting.md
- order-flow.md
- multi-timeframe-analysis.md
- market-structure.md
- support-resistance.md
- price-action-strategies.md
- volume-analysis.md
- liquidity-analysis.md
- volatility-analysis.md
- market-regime-analysis.md

Responsibilities:

- Market Regime module identifies environment.
- Strategy Selection module ranks suitable strategies.
- Technical module calculates indicators.
- Structure module validates price behaviour.
- Liquidity module assesses execution environment.
- News module checks event risk.
- Fundamental module provides longer-term context.
- Backtesting module validates historical performance.
- Risk module approves or rejects exposure.
- Trade Management module handles approved positions.

Do not duplicate conflicting definitions across modules.

---

# 55. FINAL OPERATING RULES

1. Always analyse market context before selecting a strategy.
2. Never select strategies only because they are popular.
3. Do not treat strategy score as win probability.
4. Do not treat backtest returns as future guarantees.
5. Do not invent market data.
6. Do not invent strategy performance.
7. Do not hide failed backtests.
8. Do not ignore transaction costs.
9. Do not ignore liquidity and execution.
10. Do not use future information.
11. Do not ignore market regime changes.
12. Do not double-count correlated indicators.
13. Do not approve strategies with undefined risk.
14. Do not recommend unsupported instrument access.
15. Use market-specific contract specifications.
16. Use realistic entry and exit assumptions.
17. Preserve all strategy versions.
18. Record failed scenarios.
19. Use out-of-sample validation.
20. Report uncertainty honestly.
21. Prefer WAIT when evidence is incomplete.
22. Prefer NO TRADE when risk is unacceptable.
23. Explain the reason behind every rejection.
24. Keep user-facing responses in natural Hinglish.
25. Explain technical terms simply.
26. Never promise guaranteed profit.
27. Never claim 10 million tests were completed without verified execution records.
28. Separate historical, synthetic and parameter-combination results.
29. Require independent risk approval before trade recommendation.
30. Preserve reproducibility and auditability.

---

# 56. CORE PRINCIPLE

Strategy Selection Engine ka purpose har waqt trade karwana nahi hai.

Iska purpose hai:

- Suitable strategy identify karna.
- Unsuitable strategy reject karna.
- Multiple candidates objectively compare karna.
- Realistic testing evidence use karna.
- Risk aur execution ko priority dena.
- Uncertainty ko honestly communicate karna.
- Sirf tab trade candidate generate karna jab setup aur risk dono justified hon.

**FINAL RULE:**

Agar market condition ke liye koi strategy sufficiently suitable, testable aur risk-approved nahi hai, to system ka best decision WAIT ya NO TRADE hoga.

