
# MARKET STRUCTURE MASTER ENCYCLOPEDIA
## AI Trading Analyst | Professional Market Structure Engine

Version: 1.0  
Module: Market Structure Analysis  
Parent: AI Trading Analyst Master Skill

---

# 1. OBJECTIVE

Market Structure Analysis ka objective price movement ko systematically understand karna hai.

AI ko identify karna hoga:

- Market bullish, bearish ya sideways hai.
- Buyers aur sellers mein kis side ka control hai.
- Important swing highs aur swing lows kahan hain.
- Trend continue ho raha hai ya change ho sakta hai.
- BOS, CHoCH aur MSS valid hain ya nahi.
- Breakout genuine hai ya possible fakeout.
- Support, resistance, supply aur demand zones kahan hain.
- Liquidity kis area mein collect ho sakti hai.
- Entry ke liye structure sufficient hai ya nahi.

Core principle:

**Price structure evidence hai, prediction guarantee nahi.**

AI ko market ki direction force nahi karni. Evidence unclear ho to WAIT ya NO TRADE choose karna hai.

---

# 2. MARKET STRUCTURE BASICS

Market structure price ke swing highs, swing lows aur unke relationships se banta hai.

## 2.1 Bullish structure

Bullish market mein generally:

- Higher High (HH)
- Higher Low (HL)

Price previous swing high ke upar move karta hai aur pullback mein previous important low se upar support leta hai.

Interpretation:
- Buyers relatively strong hain.
- Uptrend continue ho sakta hai.
- Structure tab tak bullish maana ja sakta hai jab tak relevant protected low invalid na ho.

## 2.2 Bearish structure

Bearish market mein generally:

- Lower Low (LL)
- Lower High (LH)

Price previous swing low ke neeche move karta hai aur pullback mein previous important high se neeche reject hota hai.

Interpretation:
- Sellers relatively strong hain.
- Downtrend continue ho sakta hai.
- Relevant protected high break hone par bearish structure reconsider karo.

## 2.3 Sideways structure

Sideways market mein:

- Price defined range ke andar move karta hai.
- Repeated highs aur lows bante hain.
- Clear directional progression nahi hoti.
- False breakouts ho sakte hain.

AI ko range ke middle mein low-quality entries avoid karni chahiye.

---

# 3. SWING HIGH AND SWING LOW

## 3.1 Swing High

Swing high ek local price peak hai jiske aas-paas price lower highs banata hai.

Basic pivot example:

Agar candle ka high uske left aur right ki N candles ke highs se greater ho, to woh confirmed pivot high ho sakta hai.

## 3.2 Swing Low

Swing low ek local price bottom hai jiske aas-paas price higher lows banata hai.

Basic pivot example:

Agar candle ka low uske left aur right ki N candles ke lows se lower ho, to woh confirmed pivot low ho sakta hai.

## 3.3 Pivot confirmation

Important:
- Pivot high ko confirm karne ke liye required right-side candles complete honi chahiye.
- Pivot low ke liye bhi right-side candles complete honi chahiye.
- Confirmation se pehle pivot provisional hai.
- Historical backtest mein future candles ka use signal ko artificially improve kar sakta hai.

## 3.4 Major versus minor swings

Major swing:
- Larger price movement represent karta hai.
- Higher timeframe par visible hota hai.
- Important trend decisions mein use hota hai.

Minor swing:
- Short-term movement represent karta hai.
- Internal structure aur entry timing mein useful hai.

Har minor swing ko major trend reversal mat samjho.

---

# 4. HIGHER HIGH, HIGHER LOW, LOWER HIGH, LOWER LOW

## 4.1 HH

Current meaningful swing high previous meaningful swing high se higher ho.

## 4.2 HL

Current meaningful swing low previous meaningful swing low se higher ho.

## 4.3 LH

Current meaningful swing high previous meaningful swing high se lower ho.

## 4.4 LL

Current meaningful swing low previous meaningful swing low se lower ho.

## 4.5 Structure classification

| Swing sequence | Possible interpretation |
|---|---|
| HH + HL | Bullish |
| LH + LL | Bearish |
| Repeated highs and lows | Range |
| Mixed sequence | Transition or unclear |

AI ko swing selection ka method consistent rakhna hai. Different pivot sensitivity se different structure results aa sakte hain.

---

# 5. INTERNAL AND EXTERNAL STRUCTURE

## 5.1 External structure

External structure market ke major swings ko represent karta hai.

Use:
- Main trend.
- Important invalidation.
- Major BOS.
- Major support/resistance.
- HTF direction.

## 5.2 Internal structure

Internal structure major swings ke beech ke smaller price movements ko represent karta hai.

Use:
- Pullback analysis.
- Short-term momentum.
- Entry confirmation.
- Minor BOS and CHoCH.
- Local liquidity.

## 5.3 Structure hierarchy

A minor bearish break inside a major bullish trend automatically major bearish reversal nahi hota.

AI ko identify karna hai:

1. Break internal hai ya external?
2. Kaunsa swing break hua?
3. Swing ki importance kya thi?
4. Higher timeframe kya indicate kar raha hai?
5. Break ke baad follow-through mila ya nahi?

---

# 6. BREAK OF STRUCTURE (BOS)

BOS ka matlab relevant previous swing high ya swing low ka break hona hai.

## 6.1 Bullish BOS

Price meaningful previous swing high ke upar break kare.

Check:
- Relevant swing high identify hua?
- Candle close level ke upar hua?
- Break ke saath displacement hai?
- Follow-through mila?
- Higher timeframe aligned hai?

## 6.2 Bearish BOS

Price meaningful previous swing low ke neeche break kare.

Check:
- Relevant swing low identify hua?
- Candle close level ke neeche hua?
- Strong directional movement hai?
- Follow-through mila?
- HTF context kya hai?

## 6.3 BOS quality

Potentially stronger evidence:
- Clear structural level.
- Strong candle close.
- Meaningful displacement.
- Supportive volume.
- Follow-through.
- Relevant timeframe alignment.

Potentially weaker evidence:
- Sirf wick break.
- Very small candle body.
- Immediate rejection.
- Low liquidity.
- Range ke andar minor break.

BOS ki strength objectively measure karne ke liye backtesting zaroori hai.

---

# 7. CHANGE OF CHARACTER (CHoCH)

CHoCH market behaviour mein possible change ka early indication hai.

Example bullish trend:
- Market HH and HL bana raha tha.
- Price relevant protected low ke neeche break karta hai.
- Bearish CHoCH ka possibility signal mil sakta hai.

Example bearish trend:
- Market LH and LL bana raha tha.
- Price relevant protected high ke upar break karta hai.
- Bullish CHoCH ka possibility signal mil sakta hai.

Confirmation:
1. Previous trend identify karo.
2. Relevant swing identify karo.
3. Structural break check karo.
4. Candle close check karo.
5. Displacement check karo.
6. Follow-through observe karo.
7. HTF context compare karo.

CHoCH early warning hai, guaranteed reversal nahi.

---

# 8. MARKET STRUCTURE SHIFT (MSS)

MSS ka use kuch ICT/SMC methodologies mein meaningful directional shift describe karne ke liye hota hai.

Possible evidence:
- Liquidity sweep.
- Strong displacement.
- Relevant swing break.
- Directional follow-through.
- New structure formation.

Bullish MSS:
- Sell-side liquidity event ho sakta hai.
- Price bullish displacement show kare.
- Relevant high break ho.
- Bullish structure develop ho.

Bearish MSS:
- Buy-side liquidity event ho sakta hai.
- Price bearish displacement show kare.
- Relevant low break ho.
- Bearish structure develop ho.

Terminology trading communities mein vary karti hai. AI ko apni definition explain karni hai.

---

# 9. PROTECTED HIGH AND PROTECTED LOW

Protected swing woh relevant swing level hai jo current directional structure ko maintain karne ke liye important hai.

Bullish structure:
- Relevant protected low break hona bullish structure ko weaken ya invalidate kar sakta hai.

Bearish structure:
- Relevant protected high break hona bearish structure ko weaken ya invalidate kar sakta hai.

Rules:
- Har recent low protected low nahi hota.
- Har recent high protected high nahi hota.
- Swing selection methodology consistent honi chahiye.
- Wick aur candle close ke rules pehle define karo.
- Invalidation ke baad structure ko objectively reassess karo.

---

# 10. DISPLACEMENT

Displacement strong directional price movement ko describe karta hai.

Potential signs:
- Large candle body.
- Strong close near candle extreme.
- Multiple directional candles.
- Previous structure break.
- Relatively strong volume, if reliable data exists.
- Limited immediate retracement.

AI ko displacement ko sirf candle size se judge nahi karna chahiye.

Volatility regime aur ATR ke comparison mein movement evaluate karo.

---

# 11. SUPPORT AND RESISTANCE

## 11.1 Support

Aisa price area jahan historically buying interest ya price reaction observe hua ho.

## 11.2 Resistance

Aisa price area jahan historically selling pressure ya rejection observe hua ho.

## 11.3 Important levels

- Previous day high/low.
- Previous week high/low.
- Previous month high/low.
- Major swing highs/lows.
- Range boundaries.
- Opening range.
- Session highs/lows.
- Volume profile levels.

## 11.4 Level validation

Evaluate:
- Historical reactions.
- Number of tests.
- Strength of departure.
- Volume.
- HTF alignment.
- Nearby liquidity.
- Breakout acceptance.

Support and resistance exact guaranteed reversal prices nahi hain. Inhe zones ke form mein analyse karna often more realistic hota hai.

---

# 12. SUPPLY AND DEMAND STRUCTURE

Supply zone:
- Potential selling interest ka area.

Demand zone:
- Potential buying interest ka area.

Analyse:
1. Zone origin.
2. Departure strength.
3. Base formation.
4. Previous retests.
5. Zone freshness.
6. Structural significance.
7. Liquidity context.
8. Invalidation.

Repeated retests zone ki effectiveness ko reduce kar sakte hain, lekin iska exact impact market-specific testing se establish hoga.

---

# 13. RANGE AND CONSOLIDATION

Range tab develop hoti hai jab price defined boundaries ke beech move karta hai.

Identify:
- Range high.
- Range low.
- Range midpoint.
- Internal swings.
- Liquidity near boundaries.
- False breakouts.
- Volume behaviour.

Possible strategies:
- Range high rejection.
- Range low rejection.
- Breakout and retest.
- Liquidity sweep reversal.

Avoid:
- Range middle mein poor R:R entries.
- Unconfirmed breakout chasing.
- Range ko trend samajhna.

Range breakout ke liye acceptance, candle close aur follow-through evaluate karo.

---

# 14. BREAKOUT, FAKEOUT AND RETEST

## 14.1 Breakout

Price defined structural boundary ke beyond move karta hai.

Evidence:
- Candle close outside range.
- Expansion in price.
- Follow-through.
- Supportive volume where available.

## 14.2 Fakeout

Price boundary ke beyond move karta hai, lekin quickly range ke andar return kar sakta hai.

Possible causes:
- Liquidity grab.
- Weak breakout participation.
- News volatility.
- Low liquidity.
- Poor market conditions.

Sirf failed breakout dekhkar institutional manipulation claim mat karo.

## 14.3 Retest

Breakout ke baad price broken level ko revisit karta hai.

Check:
- Level hold hua?
- Rejection candle bani?
- Structure aligned hai?
- Retest depth acceptable hai?
- Stop-loss logical hai?

Retest compulsory nahi hota. Har breakout retest nahi karta.

---

# 15. LIQUIDITY AND MARKET STRUCTURE

Liquidity concepts ko price structure ke saath combine karo.

Identify:
- Equal Highs (EQH).
- Equal Lows (EQL).
- Buy-side Liquidity (BSL).
- Sell-side Liquidity (SSL).
- Previous day high/low.
- Previous week high/low.
- Session highs/lows.
- Internal liquidity.
- External liquidity.

Possible sequence:

1. Price liquidity level approach karta hai.
2. Level ke beyond trades hoti hain.
3. Price rejection ya reclaim show karta hai.
4. Structure shift develop hota hai.
5. Displacement confirmation deta hai.
6. Entry setup evaluate hota hai.

Liquidity sweep alone trade trigger nahi hai.

---

# 16. MULTI-TIMEFRAME STRUCTURE

Use top-down approach:

## Higher timeframe
- Major HH/HL or LH/LL.
- Main trend.
- Major swing levels.
- Protected swing.
- Important zones.

## Intermediate timeframe
- Pullback or continuation.
- Internal structure.
- Local BOS and CHoCH.
- Setup zone.

## Lower timeframe
- Entry confirmation.
- Minor structure.
- Liquidity event.
- Displacement.
- Risk placement.

Conflicting structure:
- HTF bullish and LTF bearish may be a pullback.
- HTF bearish and LTF bullish may be a correction.
- HTF sideways and LTF directional may be range rotation or breakout attempt.

Never force alignment.

---

# 17. STRUCTURE WITH ICT / SMC

Combine market structure with:

- Liquidity sweep.
- BOS.
- CHoCH.
- MSS.
- Fair Value Gap.
- Order Block.
- Breaker Block.
- Mitigation Block.
- Premium and Discount.
- Equilibrium.
- Dealing Range.
- Displacement.
- Inducement.
- Draw on Liquidity.

AI must explain each concept and distinguish observed evidence from interpretation.

Do not label every candle base as an order block or every gap as a valid FVG.

---

# 18. STRUCTURE WITH CANDLESTICKS

Use candle behaviour at meaningful levels.

Important patterns:
- Bullish engulfing.
- Bearish engulfing.
- Hammer.
- Shooting star.
- Pin bar.
- Inside bar.
- Outside bar.
- Morning star.
- Evening star.
- Doji.

A candle pattern becomes more meaningful when its location, market structure and follow-through support the interpretation.

No single pattern guarantees a reversal or continuation.

---

# 19. STRUCTURE WITH INDICATORS

Possible supporting tools:

Trend:
- EMA.
- SMA.
- ADX.
- Supertrend.
- Ichimoku.

Momentum:
- RSI.
- MACD.
- Stochastic.
- CCI.

Volatility:
- ATR.
- Bollinger Bands.
- Keltner Channels.

Volume:
- OBV.
- MFI.
- CMF.
- VWAP.

Indicators should not override a clear invalidation level or reliable price data.

---

# 20. STRUCTURE BY TRADING STYLE

## Scalping

Focus:
- Internal structure.
- Short-term liquidity.
- Execution costs.
- Spread.
- Fast invalidation.

## Intraday

Focus:
- Session structure.
- Previous day levels.
- Opening range.
- Intraday swing structure.
- News risk.

## Swing

Focus:
- Daily and 4H structure.
- Major supply/demand.
- Weekly context.
- Wider stop-loss and position sizing.

## Positional

Focus:
- Monthly and weekly trend.
- Major market cycles.
- Fundamental events.
- Long-term structure.
- Gap and overnight risk.

---

# 21. MARKET-SPECIFIC STRUCTURE

## Forex
- Session highs and lows.
- Major currency pairs.
- Economic news.
- Broker-specific candle data.
- Spread and rollover.

## Crypto
- Exchange-specific price data.
- 24/7 trading.
- Weekend liquidity.
- Funding and liquidation data.
- Exchange outages.

## Indian Stocks
- NSE/BSE sessions.
- Opening gaps.
- Previous day levels.
- Earnings and corporate announcements.
- Sector structure.
- Circuit limits.

## Global Stocks
- Primary exchange session.
- Earnings.
- Premarket and after-hours.
- Corporate actions.
- Liquidity differences.

## Futures
- Contract expiry.
- Rollover.
- Tick size.
- Tick value.
- Contract-specific liquidity.

---

# 22. MARKET STRUCTURE DETECTION ENGINE

AI should follow this sequence:

1. Validate OHLCV data.
2. Confirm timestamps and timezone.
3. Identify completed candles.
4. Detect swing highs.
5. Detect swing lows.
6. Classify major and minor swings.
7. Build HH/HL/LH/LL sequence.
8. Determine current structure.
9. Identify protected highs and lows.
10. Detect BOS candidates.
11. Detect CHoCH candidates.
12. Evaluate displacement.
13. Identify support and resistance.
14. Detect range boundaries.
15. Identify potential breakout or fakeout.
16. Map liquidity levels.
17. Compare higher timeframes.
18. Calculate invalidation.
19. Evaluate risk.
20. Generate final report.

Every detected event should include:
- Event type.
- Price level.
- Timeframe.
- Timestamp.
- Confirmation status.
- Evidence.
- Invalidation.
- Data quality.

---

# 23. PYTHON IMPLEMENTATION

Example pivot detection:

```python
import pandas as pd

def detect_swings(df, left=3, right=3):
    """
    Detect confirmed swing highs and lows.

    Important:
    A pivot is confirmed only after the required
    right-side candles have completed.
    """

    if left < 1 or right < 1:
        raise ValueError("left and right must be positive")

    required = {"high", "low"}

    if not required.issubset(df.columns):
        raise ValueError("Missing high/low columns")

    if not df.index.is_monotonic_increasing:
        raise ValueError("Data must be sorted by timestamp")

    result = df.copy()

    result["swing_high"] = False
    result["swing_low"] = False

    for i in range(left, len(result) - right):
        window = result.iloc[i-left:i+right+1]

        current_high = result["high"].iloc[i]
        current_low = result["low"].iloc[i]

        if current_high == window["high"].max():
            if (window["high"] == current_high).sum() == 1:
                result.iloc[
                    result.index.get_loc(result.index[i]),
                    result.columns.get_loc("swing_high")
                ] = True

        if current_low == window["low"].min():
            if (window["low"] == current_low).sum() == 1:
                result.iloc[
                    result.index.get_loc(result.index[i]),
                    result.columns.get_loc("swing_low")
                ] = True

    return result
```

Important:
- The function marks the pivot candle, but the pivot is only knowable after `right` candles complete.
- A trading engine must use the confirmation timestamp, not the original pivot timestamp.
- Equal highs/lows require an explicit tie-handling policy.
- This basic function is not a complete production structure engine.

## 23.1 Basic data validation

```python
def validate_market_data(df):
    required = ["open", "high", "low", "close", "volume"]

    if df.empty:
        return False, "Empty dataset"

    if not all(col in df.columns for col in required):
        return False, "Missing OHLCV columns"

    if not df.index.is_monotonic_increasing:
        return False, "Timestamps are not sorted"

    if df.index.has_duplicates:
        return False, "Duplicate timestamps"

    if (df["high"] < df["low"]).any():
        return False, "Invalid high/low"

    if (df["volume"] < 0).any():
        return False, "Negative volume"

    return True, "Basic checks passed"
```

This is only a basic validation layer. Production systems need additional checks for missing candles, zero prices, invalid OHLC relationships, timezone and market sessions.

---

# 24. STRUCTURE BACKTESTING

A market structure strategy must be tested on historical data.

Check:
- Swing detection consistency.
- Pivot confirmation delay.
- Candle-close rules.
- BOS and CHoCH definitions.
- Entry timing.
- Stop-loss and target.
- Spread and fees.
- Slippage.
- Market sessions.
- Data gaps.
- Look-ahead bias.
- Repainting.
- Different market regimes.

Report:
- Number of trades.
- Win rate.
- Profit factor.
- Expectancy.
- Maximum drawdown.
- Average R.
- Transaction costs.
- Out-of-sample performance.
- Dataset and testing period.

Do not optimize parameters only to produce an attractive historical result.

---

# 25. 10 MILLION SCENARIO TESTING

The project target is to support up to 10,000,000 distinct scenarios when executable code, historical data and computing resources permit.

Possible test dimensions:
- Pivot sensitivity.
- Swing definitions.
- BOS confirmation rules.
- CHoCH rules.
- Market regime.
- Timeframe combinations.
- Entry confirmation.
- Stop-loss method.
- Target method.
- Volatility.
- Spread.
- Slippage.
- Session.
- Risk percentage.

Separate:
1. Actual historical trades.
2. Parameter combinations.
3. Monte Carlo simulations.
4. Synthetic scenarios.

Never claim that 10 million scenarios have been tested unless the engine actually ran them and recorded the results.

Record:
- Run ID.
- Dataset.
- Scenario count.
- Failed runs.
- Parameters.
- Execution time.
- Results.
- Validation status.

If not executed, report: NOT YET EXECUTED.

---

# 26. STRUCTURE CONFIDENCE SCORING

Illustrative evidence framework:

| Component | Points |
|---|---:|
| Swing sequence clarity | 20 |
| BOS/CHoCH evidence | 20 |
| Higher timeframe alignment | 20 |
| Displacement | 15 |
| Liquidity context | 10 |
| Volume confirmation | 10 |
| Data quality | 5 |
| Total | 100 |

Rules:
- Missing data receives no invented score.
- Correlated signals must not be double-counted.
- A score is not a win probability.
- Risk failure overrides the score.
- Thresholds must be validated before live use.

---

# 27. FINAL STRUCTURE REPORT

Use natural Hinglish.

## Market Information
- Instrument:
- Market:
- Timeframe:
- Data source:
- Analysis time:

## Structure
- Trend:
- Current swing:
- Previous swing:
- HH/HL/LH/LL:
- External structure:
- Internal structure:

## Structural Events
- BOS:
- CHoCH:
- MSS:
- Displacement:
- Protected high:
- Protected low:

## Important Levels
- Support:
- Resistance:
- Supply:
- Demand:
- Range high:
- Range low:
- Liquidity:

## Confirmation
- Candle evidence:
- Volume:
- Indicator:
- HTF alignment:

## Trading Implication
- Possible direction:
- Confirmation needed:
- Invalidation:
- Risk:
- Final decision: BUY / SELL / WAIT / NO TRADE

## Data Status
- Data quality:
- Closed candle confirmation:
- Missing information:
- Backtest status:

Unknown values must be labelled NOT PROVIDED or NOT VERIFIED.

---

# 28. FINAL RULES

1. Structure must be based on actual price data.
2. Major and minor swings must be distinguished.
3. Pivot confirmation delay must be respected.
4. BOS must use a clearly defined swing.
5. CHoCH is not a guaranteed reversal.
6. MSS terminology must be explained.
7. Wick breaks and candle-close breaks must be distinguished.
8. Higher-timeframe context must be considered.
9. Liquidity sweeps need confirmation.
10. Support and resistance are zones, not guaranteed turning points.
11. Invalidation must be defined.
12. No look-ahead bias.
13. No repainting claims without verification.
14. No fabricated prices or volume.
15. No fabricated backtest results.
16. No guaranteed profit.
17. WAIT and NO TRADE are valid outcomes.

**The purpose of market structure analysis is to understand what price has actually done, identify what could happen next, and define exactly where the current idea becomes invalid.**

---

# END OF MARKET STRUCTURE MASTER ENCYCLOPEDIA
