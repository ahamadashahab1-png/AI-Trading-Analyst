
# MARKET REGIME ANALYSIS ENGINE
## Complete A-Z Professional Market Regime Classification, Detection, Transition, Strategy Selection, Machine Learning, Backtesting and Risk Framework

Version: 1.0  
Module: Trading Analyst  
Category: Advanced Quantitative Market Analysis  
Primary Language: User-facing Hinglish  
Decision Outputs: BULLISH / BEARISH / SIDEWAYS / TRANSITIONAL / HIGH VOLATILITY / LOW VOLATILITY / UNCERTAIN

---

# 1. PURPOSE AND CORE OBJECTIVE

Market Regime Analysis ka objective identify karna hai ki market iss waqt kis environment mein trade kar raha hai.

Ek hi strategy har market condition mein kaam nahi karti. Trend-following strategy strong trend mein useful ho sakti hai, lekin sideways market mein repeated false entries de sakti hai. Mean-reversion strategy range mein useful ho sakti hai, lekin strong breakout ke waqt dangerous ho sakti hai.

Is module ko:

1. Current market regime identify karna hai.
2. Regime ki strength measure karni hai.
3. Regime change ke early signals detect karne hain.
4. Market regime ke according strategy select karni hai.
5. False regime classification avoid karni hai.
6. Different timeframes ke regimes compare karne hain.
7. Historical data se regime behaviour test karna hai.
8. Uncertainty aur conflicting signals report karne hain.
9. Regime-based risk aur position sizing calculate karni hai.
10. BUY / SELL / WAIT / NO TRADE decision mein regime information provide karni hai.

IMPORTANT:
Market regime prediction certainty nahi hoti. Regime classification probabilistic estimate hai. Market kisi bhi waqt apna behaviour change kar sakta hai.

---

# 2. MARKET REGIME CLASSIFICATION SYSTEM

Market ko ek single label dene ke bajay multiple dimensions par classify karo.

## 2.1 Directional Regime

- Bullish Trend
- Bearish Trend
- Sideways / Neutral
- Weak Uptrend
- Weak Downtrend
- Directional Transition
- Unclear / Unclassified

## 2.2 Volatility Regime

- Very Low Volatility
- Low Volatility
- Normal Volatility
- High Volatility
- Extreme Volatility
- Volatility Expansion
- Volatility Contraction

## 2.3 Momentum Regime

- Strong Positive Momentum
- Weak Positive Momentum
- Neutral Momentum
- Weak Negative Momentum
- Strong Negative Momentum
- Momentum Exhaustion
- Momentum Divergence

## 2.4 Market Structure Regime

- Higher High / Higher Low
- Lower High / Lower Low
- Range-Bound Structure
- Compression
- Expansion
- Breakout
- Failed Breakout
- Structural Transition

## 2.5 Liquidity Regime

- Normal Liquidity
- High Liquidity
- Low Liquidity
- Thin Order Book
- Liquidity Sweep
- Liquidity Vacuum
- Unusual Spread
- Potential Liquidity Event

## 2.6 Combined Regime

Final output ek multidimensional classification ho:

```text
Direction: Bullish
Volatility: Normal
Momentum: Strong Positive
Structure: Higher High / Higher Low
Liquidity: Normal
Trend Strength: Strong
Regime Stability: High
Transition Risk: Low
```

Agar dimensions conflict karte hain to ek misleading single label mat do. Conflict clearly explain karo.

---

# 3. TRENDING MARKET REGIME

## 3.1 Bullish Trending Market

Bullish trend ke possible characteristics:

- Higher Highs (HH)
- Higher Lows (HL)
- Price important moving averages ke upar
- Moving averages upward slope mein
- Positive directional movement
- Pullbacks ke baad buying interest
- Breakouts par participation increase
- Support zones hold karna
- Strong bullish displacement

Confirmation checklist:

1. HTF structure bullish ho.
2. Recent swing structure HH/HL support kare.
3. Price action bullish continuation show kare.
4. ADX trend strength support kare.
5. Momentum indicators contradictory na hon.
6. Volume available ho to breakout participation confirm kare.
7. Market kisi major resistance par exhausted na ho.

Sirf RSI above 50 hone se bullish trend confirm nahi hota.

## 3.2 Bearish Trending Market

Possible characteristics:

- Lower Highs (LH)
- Lower Lows (LL)
- Price declining moving averages ke neeche
- Negative directional movement
- Rally attempts weak
- Resistance rejection
- Breakdown participation
- Selling pressure

Confirmation checklist:

1. HTF structure bearish ho.
2. Recent swing structure LH/LL support kare.
3. Price action bearish continuation show kare.
4. Trend strength sufficient ho.
5. Momentum negative ho ya bearish shift show kare.
6. Important support ke paas breakdown risk assess karo.

## 3.3 Trend Strength

Trend strength ko direction se alag assess karo.

Example:

- Bullish + Strong
- Bullish + Weak
- Bearish + Strong
- Bearish + Weak

Strong bullish direction ka matlab guaranteed BUY nahi hai. Entry, valuation, liquidity, risk aur resistance bhi assess karna hoga.

## 3.4 Trend Quality

Trend quality ke factors:

- Swing consistency
- Pullback depth
- Breakout follow-through
- Trend duration
- Volatility stability
- Volume confirmation
- Moving average alignment
- HTF/LTF agreement
- Failed breakout frequency
- Price efficiency

Trend quality ko numerical score tabhi do jab scoring model defined aur validated ho.

---

# 4. SIDEWAYS AND RANGING REGIME

Sideways market mein price defined upper aur lower boundaries ke beech move kar sakta hai.

Possible characteristics:

- Repeated resistance rejection
- Repeated support reaction
- Weak directional movement
- Flat moving averages
- Frequent mean reversion
- False breakouts
- Overlapping candles
- Low directional efficiency

## 4.1 Range Identification

Identify:

- Range High
- Range Low
- Range Midpoint
- Range Width
- Range Duration
- Number of Boundary Tests
- Failed Breakouts
- Volume Distribution
- Volatility Contraction or Expansion

Range ko identify karte waqt arbitrary two-point trendlines par depend mat karo.

Multiple independent swing reactions aur meaningful price acceptance assess karo.

## 4.2 Range Quality

High-quality range ke possible signs:

- Clearly defined boundaries
- Repeated reactions
- Reasonable duration
- No sustained directional acceptance outside range
- Sufficient liquidity
- Consistent price rotation

## 4.3 Range Strategies

Possible strategies:

1. Support rejection trading.
2. Resistance rejection trading.
3. Mean reversion.
4. Range midpoint avoidance.
5. False breakout reversal.
6. Confirmed range breakout.

Range ke middle mein entry avoid karna useful ho sakta hai jab risk-reward poor ho.

## 4.4 Range Breakout Confirmation

Check:

- Candle close outside range.
- Breakout distance relative to ATR.
- Relative volume, if available.
- Retest and acceptance.
- Momentum expansion.
- HTF structure.
- Liquidity above or below range.
- News or event risk.

Wick outside range alone confirmed breakout nahi hai.

---

# 5. MARKET CYCLE: ACCUMULATION, MARKUP, DISTRIBUTION, MARKDOWN

Wyckoff-style market cycle ko possible analytical framework ke roop mein use karo, guaranteed institutional activity detector ke roop mein nahi.

## 5.1 Accumulation

Possible characteristics:

- Extended decline ke baad range formation.
- Selling pressure reduce hona.
- Support reactions.
- Spring-like liquidity sweep.
- Sign of Strength.
- Last Point of Support.

Assess:

- Volume behaviour.
- Range structure.
- Demand response.
- Failed downside continuation.
- HTF context.

Accumulation ko sirf sideways range dekhkar declare mat karo.

## 5.2 Markup

Possible characteristics:

- HH/HL structure.
- Strong bullish displacement.
- Breakout acceptance.
- Pullbacks holding above previous structure.
- Positive momentum.
- Demand participation.

## 5.3 Distribution

Possible characteristics:

- Extended uptrend ke baad range.
- Repeated resistance tests.
- Weak upside follow-through.
- Potential buying climax.
- Upthrust-like behaviour.
- Sign of Weakness.

Distribution confirm karne ke liye breakdown aur structural evidence chahiye.

## 5.4 Markdown

Possible characteristics:

- LH/LL structure.
- Bearish displacement.
- Support breakdown.
- Weak recovery attempts.
- Negative momentum.
- Supply dominance.

## 5.5 Cycle Classification Rules

Har phase ke saath:

- Supporting evidence.
- Contradictory evidence.
- Confidence.
- Timeframe.
- Invalidation.
- Alternative interpretation.

Historical chart par phase ko hindsight se label karke real-time predictive accuracy claim mat karo.

---

# 6. TREND DETECTION INDICATORS

## 6.1 Moving Averages

Common indicators:

- SMA
- EMA
- WMA
- VWMA
- HMA

Assess:

- Price versus MA.
- Fast MA versus slow MA.
- MA slope.
- MA separation.
- MA compression.
- Crossovers.
- Distance from MA relative to ATR.

Example:

```text
EMA 20 > EMA 50 > EMA 200
```

Yeh bullish alignment suggest kar sakta hai, lekin standalone trade signal nahi hai.

MA periods market aur timeframe ke hisaab se validate karo.

## 6.2 ADX

Average Directional Index trend strength estimate karta hai, direction nahi.

Use:

- ADX level.
- ADX slope.
- +DI versus -DI.
- Trend persistence.
- Market-specific thresholds.

Common interpretation:

- ADX below 20: weak trend conditions possible.
- ADX 20–25: developing trend possible.
- ADX above 25: stronger trend conditions possible.
- ADX above 40: strong trend conditions possible.

Ye universal rules nahi hain. Instrument, timeframe aur calculation settings ke hisaab se test karo.

## 6.3 RSI

Use RSI for:

- Momentum regime.
- Bullish/bearish range behaviour.
- Divergence.
- Momentum shifts.
- Overextension.

RSI above 70 ka matlab automatic SELL nahi.
RSI below 30 ka matlab automatic BUY nahi.

Strong trends mein RSI extended readings maintain kar sakta hai.

## 6.4 MACD

Assess:

- MACD line versus signal line.
- Histogram expansion/contraction.
- Zero-line position.
- Momentum crossover.
- Divergence.

MACD lagging indicator hai. Price structure ke saath combine karo.

## 6.5 Bollinger Bands

Use:

- Bandwidth.
- Squeeze.
- Expansion.
- Price position.
- Band walking.
- Mean-reversion conditions.

Bollinger squeeze future breakout ki direction guarantee nahi karta.

## 6.6 ATR

Use:

- Absolute volatility.
- Relative volatility.
- Stop distance.
- Range expansion.
- Volatility shock.
- Position sizing.

ATR direction nahi batata.

---

# 7. VOLATILITY REGIME CLASSIFICATION

Volatility ko absolute aur relative dono tarike se assess karo.

## 7.1 Historical Volatility

Returns ke standard deviation se historical volatility calculate ki ja sakti hai.

```python
import numpy as np
import pandas as pd

def historical_volatility(
    close: pd.Series,
    window: int = 20,
    periods_per_year: int = 252
):
    returns = np.log(close / close.shift(1))
    return returns.rolling(window).std() * np.sqrt(periods_per_year)
```

Annualization factor instrument aur timeframe ke according choose karo.

Crypto 24/7 market aur exchange trading hours ko alag handle karo.

## 7.2 ATR-Based Volatility

```python
def calculate_atr(df, period=14):
    high = df["high"]
    low = df["low"]
    close = df["close"]

    previous_close = close.shift(1)

    true_range = pd.concat(
        [
            high - low,
            (high - previous_close).abs(),
            (low - previous_close).abs()
        ],
        axis=1
    ).max(axis=1)

    return true_range.rolling(period).mean()
```

## 7.3 Normalized ATR

```python
def normalized_atr(df, period=14):
    atr = calculate_atr(df, period)
    return atr / df["close"] * 100
```

Normalization different-priced instruments ko compare karne mein help kar sakti hai.

## 7.4 Volatility Percentile

Current volatility ko historical distribution ke against compare karo.

Possible categories:

- Below 10th percentile: exceptionally low.
- 10th–30th: low.
- 30th–70th: normal.
- 70th–90th: elevated.
- Above 90th: extreme.

Percentile boundaries configurable aur backtested honi chahiye.

## 7.5 Volatility Expansion

Signals:

- ATR rising.
- Bollinger bandwidth increasing.
- Larger candle ranges.
- Realized volatility increasing.
- Breakout participation.
- Wider intraday movement.

## 7.6 Volatility Contraction

Signals:

- ATR falling.
- Narrowing ranges.
- Bollinger bandwidth declining.
- Reduced directional movement.
- Price compression.

Contraction ke baad expansion aa sakta hai, lekin direction unknown hoti hai.

---

# 8. MOMENTUM REGIME ANALYSIS

Momentum ko direction, strength aur persistence ke basis par classify karo.

Measure:

- Rate of Change.
- RSI.
- MACD histogram.
- Candle body expansion.
- Relative price performance.
- Momentum divergence.
- Volume participation.
- Trend slope.

## 8.1 Momentum Acceleration

Possible signs:

- Increasing positive returns.
- Rising MACD histogram.
- Higher momentum peaks.
- Increasing directional movement.

## 8.2 Momentum Deceleration

Possible signs:

- Smaller candle bodies.
- Falling momentum peaks.
- Divergence.
- Weak breakout continuation.
- Reduced relative volume.

Momentum slowdown alone trend reversal confirm nahi karta.

## 8.3 Divergence

Bullish divergence:

- Price lower low.
- Momentum higher low.

Bearish divergence:

- Price higher high.
- Momentum lower high.

Divergence ko structure, timeframe aur confirmation ke saath assess karo.

---

# 9. MARKET EFFICIENCY AND CHOP ANALYSIS

## 9.1 Efficiency Ratio

Kaufman-style Efficiency Ratio:

```python
def efficiency_ratio(close, period=10):
    net_change = (close - close.shift(period)).abs()

    path_length = (
        close.diff().abs()
        .rolling(period)
        .sum()
    )

    return net_change / path_length.replace(0, np.nan)
```

Interpretation:

- Higher value: more directional movement.
- Lower value: more back-and-forth movement.

Thresholds empirically validate karo.

## 9.2 Choppiness Index

Use Choppiness Index to estimate whether price is more directional or rotational.

Common interpretation:

- Higher readings: choppier conditions.
- Lower readings: more directional conditions.

Formula, period and thresholds consistent rakho.

## 9.3 Trend Efficiency

Measure:

- Net movement.
- Total movement.
- Pullback depth.
- Trend persistence.
- Reversal frequency.

---

# 10. MARKET REGIME DETECTION USING PRICE STRUCTURE

Price structure primary evidence sources mein se ek hona chahiye.

Detect:

- HH/HL.
- LH/LL.
- BOS.
- CHoCH.
- MSS.
- Range formation.
- Compression.
- Expansion.
- Failed breakout.
- Swing failure.
- Structural invalidation.

Rules:

1. Swing detection algorithm clearly define karo.
2. Confirmed swing aur developing swing ko distinguish karo.
3. Future candles use karke past signal ko repaint mat karo.
4. Structure break candle close ya selected confirmation rule par define karo.
5. Timeframe ke according swing sensitivity adjust karo.

---

# 11. LIQUIDITY AND ORDER FLOW REGIME

Available data ke according assess karo:

- Bid-ask spread.
- Market depth.
- Order-book imbalance.
- Volume delta.
- Cumulative Volume Delta.
- Absorption.
- Liquidity sweep.
- Large trade activity.
- Open interest.
- Funding rate.
- Liquidations.

Important limitations:

- Forex spot market decentralized hai.
- Ek exchange ka order book complete global liquidity nahi dikhata.
- Reported volume aur actual traded volume mein differences ho sakte hain.
- Spoofing ya hidden orders ka certainty ke saath inference mat karo.

Liquidity regime:

- Deep and stable.
- Normal.
- Thin.
- Unstable.
- Event-distorted.

---

# 12. HIDDEN MARKOV MODEL (HMM)

HMM market regimes ko latent states ke roop mein model kar sakta hai.

Possible hidden states:

- Low volatility trend.
- High volatility trend.
- Low volatility range.
- High volatility range.

Observable features:

- Returns.
- Realized volatility.
- ATR percentage.
- Momentum.
- Trend efficiency.
- Volume features.

## 12.1 HMM Requirements

- Historical observations.
- Feature scaling.
- Training and test separation.
- State stability checks.
- Transition matrix.
- Probability output.
- Out-of-sample validation.

HMM state numbers ka direct economic meaning nahi hota. States ko unke statistical characteristics ke basis par interpret karo.

## 12.2 Example Architecture

```python
# Optional dependency:
# pip install hmmlearn scikit-learn

import numpy as np
from sklearn.preprocessing import StandardScaler
from hmmlearn.hmm import GaussianHMM

def prepare_hmm_features(df):
    returns = np.log(df["close"] / df["close"].shift(1))

    features = pd.DataFrame({
        "returns": returns,
        "volatility": returns.rolling(20).std(),
        "range_pct": (
            (df["high"] - df["low"]) / df["close"]
        ),
        "momentum": (
            df["close"] / df["close"].shift(10) - 1
        )
    })

    return features.replace(
        [np.inf, -np.inf],
        np.nan
    ).dropna()

def train_hmm(features, states=4):
    scaler = StandardScaler()
    X = scaler.fit_transform(features)

    model = GaussianHMM(
        n_components=states,
        covariance_type="diag",
        n_iter=500,
        random_state=42
    )

    model.fit(X)

    return model, scaler
```

IMPORTANT:

Yeh demonstration architecture hai, production-ready validated trading model nahi.

Production use mein scaler sirf training data par fit karo. Test data par dobara fit mat karo. Chronological separation maintain karo.

## 12.3 HMM Transition Matrix

Transition matrix estimate karti hai ki model ke states ke beech historical transition probabilities kya rahi hain.

```python
def get_transition_matrix(model):
    return model.transmat_
```

Transition probability historical model estimate hai, guaranteed future probability nahi.

---

# 13. MACHINE LEARNING REGIME DETECTION

Possible models:

- Logistic Regression.
- Random Forest.
- Gradient Boosting.
- XGBoost.
- LightGBM.
- Support Vector Machine.
- Hidden Markov Model.
- Gaussian Mixture Model.
- K-Means.
- Temporal Neural Networks.

## 13.1 Feature Engineering

Features:

- Returns.
- ATR percentage.
- Historical volatility.
- RSI.
- ADX.
- MA slope.
- MA distance.
- Bollinger bandwidth.
- Efficiency ratio.
- Volume percentile.
- Relative volume.
- Drawdown.
- Trend persistence.
- Range width.
- Spread.
- Market session.

## 13.2 Label Design

Possible labels:

- Bullish trend.
- Bearish trend.
- Sideways.
- High volatility.
- Low volatility.
- Transition.

Labels create karte waqt future information ka leakage avoid karo.

Agar future return threshold se labels banaye ja rahe hain, label horizon clearly define karo.

## 13.3 Data Leakage Prevention

Never:

- Randomly shuffle time-series observations for ordinary trading validation.
- Fit scalers on full dataset.
- Use future candle high/low for earlier signal.
- Use revised fundamentals unavailable at historical date.
- Ignore publication timestamps.
- Use future regime labels as present-time features.

Use chronological train, validation and test splits.

## 13.4 Model Evaluation

Evaluate:

- Accuracy.
- Precision.
- Recall.
- F1 Score.
- Confusion Matrix.
- Balanced Accuracy.
- Calibration.
- Regime Duration Error.
- Transition Detection Delay.
- False Transition Rate.
- Downstream strategy performance.

Classification accuracy alone profitability prove nahi karti.

---

# 14. REGIME TRANSITION DETECTION

Regime transition tab hota hai jab market behaviour materially change hota hai.

Examples:

- Bullish to Sideways.
- Sideways to Bullish.
- Bullish to Bearish.
- Low Volatility to High Volatility.
- Trending to Ranging.
- High Liquidity to Thin Liquidity.

## 14.1 Early Warning Signals

- ADX decline.
- MA slope flattening.
- Momentum divergence.
- ATR expansion.
- Range compression.
- Structure failure.
- Failed breakout.
- Volume behaviour change.
- HMM state probability shift.
- Order-book instability.

## 14.2 Transition Confirmation

Transition tabhi classify karo jab multiple independent observations support karein.

Possible confirmation:

1. Structure change.
2. Momentum change.
3. Volatility behaviour change.
4. Breakout acceptance.
5. HTF agreement.

## 14.3 Change Point Detection

Statistical tools:

- CUSUM.
- Bayesian Online Change Point Detection.
- Rolling distribution comparison.
- Variance shift detection.
- Mean shift detection.

Change point signal market regime change ki possibility batata hai, guaranteed reversal nahi.

---

# 15. REGIME STABILITY AND DURATION

Calculate:

- Current regime duration.
- Average historical duration.
- Median duration.
- Transition frequency.
- State persistence.
- Confidence change.
- Recent classification instability.

Do not assume regime will continue merely because it has existed for a long time.

Duration statistics instrument and timeframe specific honi chahiye.

---

# 16. MULTI-TIMEFRAME REGIME ANALYSIS

Use:

- Higher Timeframe (HTF).
- Intermediate Timeframe.
- Lower Timeframe (LTF).

Example:

```text
Weekly: Bullish trend
Daily: Bullish trend
4H: Sideways pullback
1H: Bearish short-term momentum
15M: Potential bullish reversal
```

Interpretation:

HTF bullish hai, lekin LTF correction chal raha hai. Immediate BUY automatically valid nahi hai.

## 16.1 MTF Rules

- HTF regime = directional context.
- ITF regime = setup environment.
- LTF regime = entry timing.
- Conflicting signals = lower confidence.
- HTF invalidation = setup reassessment.
- Different sessions = volatility and liquidity adjustment.

Timeframe combination user ke trading style ke according select karo.

---

# 17. REGIME ANALYSIS BY TRADING STYLE

## 17.1 Scalping

Focus:

- Spread.
- Execution latency.
- Short-term volatility.
- Order-book liquidity.
- Session activity.
- Microstructure noise.

Avoid trading when spread and slippage consume expected edge.

## 17.2 Intraday

Focus:

- Opening range.
- Session trend.
- Intraday VWAP.
- Relative volume.
- News calendar.
- Intraday volatility.
- Previous day high/low.

## 17.3 Swing

Focus:

- Daily and 4H structure.
- Weekly regime.
- Trend strength.
- Major support/resistance.
- Overnight gap risk.
- Earnings and macro events.

## 17.4 Positional

Focus:

- Weekly/monthly trend.
- Fundamental environment.
- Long-term volatility.
- Economic cycle.
- Sector strength.
- Portfolio concentration.

---

# 18. MARKET-SPECIFIC REGIME ANALYSIS

## 18.1 Forex

Assess:

- Central bank policy.
- Interest-rate differential.
- Inflation and employment data.
- Economic calendar.
- Currency strength.
- Session overlap.
- Spread and rollover.
- Geopolitical risk.

Forex spot volume fragmented hota hai. Ek broker ka volume entire market represent nahi karta.

## 18.2 Cryptocurrency

Assess:

- Exchange-specific liquidity.
- 24/7 volatility.
- Funding rate.
- Open interest.
- Liquidation clusters.
- Exchange inflows/outflows if reliable.
- BTC market regime.
- Altcoin correlation.
- Stablecoin and regulatory events.

Crypto regime exchange aur asset ke according different ho sakta hai.

## 18.3 Indian Stocks

Assess:

- NSE/BSE trading hours.
- Nifty and Bank Nifty context.
- Sector performance.
- Corporate earnings.
- RBI policy.
- SEBI/regulatory events.
- FII/DII flows where reliable.
- India VIX.
- Circuit limits.
- Corporate actions.

Use adjusted historical data where required.

## 18.4 Global Stocks

Assess:

- Earnings.
- Index regime.
- Sector rotation.
- Interest rates.
- Inflation.
- Liquidity.
- Market breadth.
- Volatility indices.

## 18.5 Indices

Assess:

- Breadth.
- Constituents contribution.
- Futures basis.
- Volatility.
- Macro calendar.
- Market opening gaps.
- Major index levels.

## 18.6 Futures and Commodities

Assess:

- Contract expiry.
- Roll dates.
- Term structure.
- Contango/backwardation.
- Inventory reports.
- Seasonality.
- Delivery specifications.
- Contract liquidity.

Different expiry contracts ko blindly combine mat karo.

## 18.7 Options

Assess:

- Implied volatility.
- Realized volatility.
- IV percentile.
- Skew.
- Term structure.
- Gamma exposure where reliable.
- Expiry.
- Open interest.
- Bid-ask spread.

Options ka regime analysis underlying price aur volatility surface dono ko consider kare.

---

# 19. STRATEGY SELECTION BY REGIME

| Regime | Potential Strategy | Main Risk |
|---|---|---|
| Strong Bullish Trend | Trend following, pullback | Late entry |
| Strong Bearish Trend | Short trend following | Short squeeze |
| Sideways | Range trading | Breakout |
| Low Volatility | Compression watch | False breakout |
| High Volatility | Reduced size, selective setups | Large slippage |
| Transition | Wait for confirmation | Whipsaw |
| Uncertain | No trade / observation | False confidence |
| Extreme Event | Risk reduction | Gap and execution risk |

Strategy selection automatic trade approval nahi hai.

Har setup ko separate entry, invalidation aur risk checks pass karne honge.

---

# 20. REGIME-BASED ENTRY RULES

## Bullish Trend

Potential setups:

- Pullback to support.
- Higher-low formation.
- Bullish breakout and retest.
- Momentum continuation.
- Demand-zone reaction.

## Bearish Trend

Potential setups:

- Rally into resistance.
- Lower-high formation.
- Bearish breakdown and retest.
- Momentum continuation.
- Supply-zone rejection.

## Sideways

Potential setups:

- Support rejection.
- Resistance rejection.
- Confirmed false breakout.
- Range expansion breakout.

## Transition

Default approach:

- Reduce aggressiveness.
- Wait for structure confirmation.
- Avoid forcing directional trades.
- Reassess volatility and liquidity.

## High Volatility

- Reduce position size.
- Widen stop only when structurally justified and recalculate size.
- Check spread and slippage.
- Avoid chasing extended candles.
- Assess event risk.

---

# 21. STOP LOSS AND TAKE PROFIT BY REGIME

Stop loss placement must depend on trade invalidation, not arbitrary fixed percentages.

Possible SL references:

- Swing low/high.
- Structure invalidation.
- ATR distance.
- Support/resistance.
- Liquidity boundary.
- Volatility-adjusted stop.

Take-profit references:

- Next structure level.
- Range boundary.
- Previous high/low.
- Liquidity pool.
- ATR-based projection.
- Risk-reward target.
- Trailing stop.

Regime-based adjustment:

- Strong trend: trailing may help capture continuation.
- Range: opposite boundary may be a target.
- High volatility: size reduction and realistic execution assumptions.
- Transition: tighter decision discipline, not automatically tighter stops.

Never widen stop simply to avoid accepting a loss.

---

# 22. REGIME-BASED POSITION SIZING

Position size should be based on:

- Account equity.
- Risk percentage.
- Stop distance.
- Contract multiplier.
- Tick value.
- Currency conversion.
- Fees.
- Expected slippage.
- Instrument specifications.

Basic formula:

```text
Risk Amount = Account Equity × Risk Percentage

Position Size =
Risk Amount / Estimated Loss Per Unit
```

For a volatility-adjusted strategy:

```text
Adjusted Risk =
Base Risk × Validated Regime Risk Multiplier
```

Risk multiplier must be based on historical out-of-sample evidence.

Do not increase risk merely because model confidence is high.

---

# 23. REGIME CONFIDENCE SCORE

Build a transparent scoring framework.

Possible dimensions:

| Dimension | Example Weight |
|---|---:|
| Price Structure | 25% |
| Trend Strength | 15% |
| Momentum | 15% |
| Volatility | 10% |
| Volume / Participation | 10% |
| Multi-Timeframe Agreement | 15% |
| Liquidity | 10% |

Weights are initial design examples, not validated optimal values.

Missing data ko neutral confirmation mat samjho.

## 23.1 Score Interpretation

Example configurable bands:

- 80–100: Strong evidence.
- 65–79: Moderate-to-strong evidence.
- 50–64: Mixed evidence.
- Below 50: Weak or uncertain evidence.

A score is not a probability unless calibrated against historical outcomes.

## 23.2 Confidence Output

Always report:

- Score.
- Evidence.
- Missing inputs.
- Conflicting signals.
- Calibration status.
- Model version.

---

# 24. REGIME DETECTION PIPELINE

Recommended processing sequence:

1. Fetch market data.
2. Validate timestamps.
3. Detect missing candles.
4. Validate OHLC relationships.
5. Calculate returns.
6. Calculate volatility.
7. Calculate trend indicators.
8. Detect market structure.
9. Assess momentum.
10. Assess volume and liquidity.
11. Calculate timeframe-specific features.
12. Run regime classifier.
13. Estimate transition probability.
14. Apply uncertainty checks.
15. Produce regime report.
16. Pass output to strategy-selection module.
17. Apply independent risk approval.
18. Log result.

Agar critical data unavailable hai to result ko incomplete mark karo.

---

# 25. PYTHON DATA VALIDATION

```python
import pandas as pd
import numpy as np

REQUIRED_COLUMNS = [
    "open",
    "high",
    "low",
    "close",
    "volume"
]

def validate_ohlcv(df):
    errors = []

    missing = [
        col for col in REQUIRED_COLUMNS
        if col not in df.columns
    ]

    if missing:
        return {
            "valid": False,
            "errors": [f"Missing columns: {missing}"]
        }

    if df.empty:
        errors.append("Dataset is empty")

    if not isinstance(df.index, pd.DatetimeIndex):
        errors.append("DatetimeIndex required")

    if df.index.has_duplicates:
        errors.append("Duplicate timestamps detected")

    if not df.index.is_monotonic_increasing:
        errors.append("Timestamps are not sorted")

    for col in REQUIRED_COLUMNS:
        if not np.isfinite(df[col]).all():
            errors.append(f"Invalid values in {col}")

    if (df["high"] < df["low"]).any():
        errors.append("High is below Low")

    if (df["high"] < df["open"]).any():
        errors.append("High below Open")

    if (df["high"] < df["close"]).any():
        errors.append("High below Close")

    if (df["low"] > df["open"]).any():
        errors.append("Low above Open")

    if (df["low"] > df["close"]).any():
        errors.append("Low above Close")

    if (df["volume"] < 0).any():
        errors.append("Negative volume")

    return {
        "valid": len(errors) == 0,
        "errors": errors
    }
```

Production system mein missing candles, exchange timezone, daylight saving, market holidays aur session gaps separately validate karo.

---

# 26. PYTHON FEATURE ENGINEERING

```python
def build_regime_features(df):
    data = df.copy()

    close = data["close"]
    high = data["high"]
    low = data["low"]

    data["return_1"] = close.pct_change()

    data["ema_20"] = close.ewm(
        span=20,
        adjust=False
    ).mean()

    data["ema_50"] = close.ewm(
        span=50,
        adjust=False
    ).mean()

    data["ema_200"] = close.ewm(
        span=200,
        adjust=False
    ).mean()

    data["ema_20_slope"] = (
        data["ema_20"] -
        data["ema_20"].shift(5)
    ) / close

    previous_close = close.shift(1)

    tr = pd.concat(
        [
            high - low,
            (high - previous_close).abs(),
            (low - previous_close).abs()
        ],
        axis=1
    ).max(axis=1)

    data["atr_14"] = tr.rolling(14).mean()

    data["atr_pct"] = (
        data["atr_14"] / close * 100
    )

    data["realized_vol_20"] = (
        data["return_1"]
        .rolling(20)
        .std()
    )

    data["momentum_10"] = (
        close / close.shift(10) - 1
    )

    data["range_pct"] = (
        (high - low) / close * 100
    )

    data["volume_ma_20"] = (
        data["volume"].rolling(20).mean()
    )

    data["relative_volume"] = (
        data["volume"] /
        data["volume_ma_20"].replace(0, np.nan)
    )

    return data
```

Indicator warm-up period ke liye sufficient history required hai.

NaN values ko blindly zero se replace mat karo.

---

# 27. BASIC RULE-BASED REGIME CLASSIFIER

```python
def classify_basic_regime(row):
    required = [
        "close",
        "ema_20",
        "ema_50",
        "ema_20_slope",
        "atr_pct",
        "momentum_10"
    ]

    if any(pd.isna(row.get(k)) for k in required):
        return "UNCERTAIN"

    bullish = (
        row["close"] > row["ema_20"]
        and row["ema_20"] > row["ema_50"]
        and row["ema_20_slope"] > 0
        and row["momentum_10"] > 0
    )

    bearish = (
        row["close"] < row["ema_20"]
        and row["ema_20"] < row["ema_50"]
        and row["ema_20_slope"] < 0
        and row["momentum_10"] < 0
    )

    if bullish:
        return "BULLISH"

    if bearish:
        return "BEARISH"

    return "SIDEWAYS_OR_UNCERTAIN"
```

This is a basic educational classifier.

It does not use a validated ADX threshold, market structure, transaction costs or out-of-sample performance.

Do not use it as a standalone live trading system.

---

# 28. ADVANCED CLASSIFIER ARCHITECTURE

Advanced engine mein separate modules hone chahiye:

```text
MarketRegimeEngine
    |
    |-- DataValidator
    |-- FeatureBuilder
    |-- TrendDetector
    |-- VolatilityDetector
    |-- MomentumDetector
    |-- StructureDetector
    |-- LiquidityDetector
    |-- MultiTimeframeAnalyzer
    |-- RuleBasedClassifier
    |-- StatisticalClassifier
    |-- MLClassifier
    |-- TransitionDetector
    |-- ConfidenceCalibrator
    |-- StrategySelector
    |-- RiskApproval
    |-- ReportGenerator
    |-- AuditLogger
```

Rule-based, statistical aur ML outputs ko separately preserve karo.

Ensemble disagreement ko report karo, hide mat karo.

---

# 29. BACKTESTING REGIME CLASSIFIERS

Test these questions:

1. Regime labels kitni frequently change hote hain?
2. False transition rate kya hai?
3. Regime detection mein delay kitna hai?
4. Strong trends identify hue ya miss hue?
5. Range classification reliable hai?
6. High-volatility events detect hue?
7. Different market conditions mein performance kaisi hai?
8. Different timeframes par stability kaisi hai?
9. Transaction costs ke baad strategy useful hai?
10. Out-of-sample performance stable hai?

## 29.1 Chronological Testing

Use:

- Training period.
- Validation period.
- Out-of-sample test.
- Walk-forward windows.

Future data ka leakage avoid karo.

## 29.2 Strategy-Level Testing

Classifier ke output par based strategy ko independently test karo.

Metrics:

- Net Return.
- CAGR where applicable.
- Maximum Drawdown.
- Sharpe Ratio.
- Sortino Ratio.
- Profit Factor.
- Expectancy.
- Trade Count.
- Turnover.
- Win Rate.
- Average Win/Loss.
- Exposure.
- Slippage Sensitivity.

## 29.3 Regime-Specific Results

Performance ko regime ke according break down karo.

Example:

```text
Bullish Regime:
Trades: 120
Net P&L: Calculated from actual test
Max Drawdown: Calculated from actual test

Bearish Regime:
Trades: 95
Net P&L: Calculated from actual test
Max Drawdown: Calculated from actual test

Sideways Regime:
Trades: 140
Net P&L: Calculated from actual test
Max Drawdown: Calculated from actual test
```

Yeh output format example hai, actual performance claim nahi.

---

# 30. WALK-FORWARD VALIDATION

Walk-forward process:

1. Historical training window choose karo.
2. Model train karo.
3. Next unseen period par test karo.
4. Window forward shift karo.
5. Model retrain karo.
6. Results combine karo.
7. Stability assess karo.

Avoid:

- Repeatedly tuning on test data.
- Selecting only favourable periods.
- Ignoring regime changes.
- Optimizing hundreds of parameters without correction.

---

# 31. MONTE CARLO AND SCENARIO TESTING

Monte Carlo testing possible trade outcomes ki distribution study kar sakta hai.

Methods:

- Trade return resampling.
- Block bootstrap.
- Randomized execution delay.
- Slippage variation.
- Fee variation.
- Parameter perturbation.
- Volatility shocks.
- Gap scenarios.
- Regime transition stress.
- Correlation shocks.

Trade sequence dependence important hai. Simple random shuffling market path behaviour ko destroy kar sakta hai. Appropriate bootstrap method select karo.

---

# 32. 10 MILLION SCENARIO TESTING FRAMEWORK

Target: up to 10,000,000 distinct scenarios.

IMPORTANT:
10 million scenarios ka target framework hai. Jab tak executable code actual scenarios run karke results save nahi karta, tab tak "1 crore tests complete" claim forbidden hai.

## 32.1 Scenario Dimensions

Possible dimensions:

- Asset.
- Timeframe.
- Market regime.
- Volatility level.
- Momentum state.
- Trend strength.
- Entry type.
- Stop method.
- Exit method.
- Slippage.
- Fees.
- Spread.
- Parameter variation.
- Execution delay.
- News shock.
- Liquidity condition.
- Market session.
- Position size.
- Regime transition.

## 32.2 Scenario Categories

1. Historical replay.
2. Parameter combinations.
3. Synthetic price paths.
4. Monte Carlo sequences.
5. Execution stress tests.
6. Volatility stress tests.
7. Liquidity stress tests.
8. Regime transition simulations.
9. Walk-forward model tests.
10. Cross-asset tests.

Different categories ko separately report karo.

Synthetic scenarios historical market evidence ka replacement nahi hain.

## 32.3 Scenario Result Storage

Each run must record:

```text
scenario_id
model_version
asset
timeframe
data_period
regime_label
feature_version
parameter_set
entry_rule
exit_rule
transaction_cost
slippage
execution_assumption
result
drawdown
validation_status
timestamp
```

## 32.4 Testing Completion Report

```text
Target Scenarios: 10,000,000
Executed Scenarios: Actual Count
Successful Runs: Actual Count
Failed Runs: Actual Count
Skipped Runs: Actual Count
Unique Scenarios: Verified Count
Data Coverage: Actual Period
Out-of-Sample Status: Actual Status
Results File: Actual Location
```

Never invent any number.

---

# 33. REGIME CHANGE STRESS TESTS

Test:

- Bullish to bearish reversal.
- Bearish to bullish reversal.
- Trend to range.
- Range to breakout.
- Low to extreme volatility.
- Sudden liquidity reduction.
- Major economic announcement.
- Exchange outage.
- Market gap.
- Data feed interruption.

System should be able to return UNCERTAIN or NO TRADE when evidence becomes unreliable.

---

# 34. REGIME-BASED RISK RULES

1. Strong regime classification does not remove trading risk.
2. High volatility may require smaller position size.
3. Thin liquidity may make stop execution unreliable.
4. Transition regimes require additional caution.
5. Conflicting timeframes reduce conviction.
6. Correlated positions increase portfolio risk.
7. Event risk must be assessed separately.
8. Risk per trade must respect account-level limits.
9. Never increase size to recover losses.
10. Stop trading when data or execution becomes unreliable.

Risk approval independent module hona chahiye.

---

# 35. NO TRADE CONDITIONS

NO TRADE or WAIT prefer karo when:

- Data incomplete.
- Price structure unclear.
- Indicators conflict.
- Regime rapidly switching.
- Spread unusually wide.
- Liquidity too low.
- Extreme event risk.
- Stop placement invalid.
- Risk-reward inadequate.
- No confirmed setup.
- Model out of distribution.
- Model confidence uncalibrated.
- Historical validation insufficient.
- Entry would require chasing an extended move.

No trade bhi valid analytical decision hai.

---

# 36. FINAL REGIME DECISION ENGINE

Decision sequence:

```text
DATA VALID?
    |
    |-- NO --> UNCERTAIN / NO TRADE
    |
    YES
    |
STRUCTURE CLEAR?
    |
    |-- NO --> SIDEWAYS / TRANSITION / UNCERTAIN
    |
    YES
    |
TREND DIRECTION?
    |
    |-- Bullish --> Bullish candidate
    |-- Bearish --> Bearish candidate
    |-- Neutral --> Range candidate
    |
VOLATILITY AND LIQUIDITY SAFE?
    |
    |-- NO --> WAIT / NO TRADE
    |
    YES
    |
MTF CONFIRMATION?
    |
    |-- Conflict --> Reduce confidence
    |
    YES
    |
SETUP VALID?
    |
    |-- NO --> WAIT
    |
    YES
    |
RISK APPROVED?
    |
    |-- NO --> NO TRADE
    |
    YES
    |
TRADE PLAN MAY BE GENERATED
```

Regime classification aur trade execution approval separate decisions rahenge.

---

# 37. STANDARD HINGLISH REGIME REPORT

Har analysis mein ye format use karo:

## Market Regime Report

**Asset:**  
**Exchange / Broker:**  
**Current Price:**  
**Data Timestamp:**  
**Timeframe:**  

### 1. Current Regime
- Direction:
- Trend Strength:
- Volatility:
- Momentum:
- Structure:
- Liquidity:

### 2. Evidence
- Bullish Evidence:
- Bearish Evidence:
- Neutral Evidence:
- Conflicting Signals:

### 3. Multi-Timeframe Regime
- Higher Timeframe:
- Intermediate Timeframe:
- Lower Timeframe:

### 4. Transition Risk
- Current Regime Stability:
- Possible Transition:
- Early Warning Signals:
- Invalidation:

### 5. Suitable Strategies
- Primary Strategy:
- Alternative Strategy:
- Strategies to Avoid:

### 6. Trading Decision
- BUY / SELL / WAIT / NO TRADE:
- Reason:
- Required Confirmation:

### 7. Risk
- Volatility Risk:
- Liquidity Risk:
- News Risk:
- Execution Risk:

### 8. Model Reliability
- Data Quality:
- Historical Validation:
- Out-of-Sample Status:
- Confidence Calibration:
- Known Limitations:

### 9. Final Explanation
Simple Hinglish mein explain karo ki market kis condition mein hai aur trader ko kis cheez ka wait karna chahiye.

---

# 38. SCREENSHOT-BASED REGIME ANALYSIS

Agar user chart screenshot provide kare:

1. Visible symbol identify karo.
2. Visible timeframe identify karo.
3. Visible price scale inspect karo.
4. Trend structure assess karo.
5. Range boundaries identify karo.
6. Volatility behaviour assess karo.
7. Momentum evidence inspect karo.
8. Visible indicators read karo.
9. Possible transition signals identify karo.
10. Missing information disclose karo.

Screenshot limitations:

- Hidden candles available nahi.
- Exact historical OHLCV unavailable ho sakta hai.
- Indicators ke values unreadable ho sakte hain.
- Live market state verify nahi hoti.
- Exchange and timezone unknown ho sakte hain.

Exact numeric classification tabhi do jab chart data sufficient ho.

---

# 39. AUTOMATION AND ALERTS

Possible alerts:

- Bullish regime detected.
- Bearish regime detected.
- Range detected.
- Volatility expansion.
- Volatility contraction.
- Regime transition warning.
- HMM state probability change.
- Trend strength deterioration.
- Liquidity deterioration.
- Model disagreement.
- Data feed failure.

Alert mein:

- Timestamp.
- Asset.
- Timeframe.
- Previous regime.
- New regime.
- Supporting evidence.
- Confidence.
- Data source.
- Model version.

Alerts automatic orders place nahi karenge unless separately authorized, risk-controlled execution system exists.

---

# 40. SYSTEM TESTING AND QUALITY ASSURANCE

Test cases:

1. Empty dataset.
2. Missing columns.
3. Duplicate timestamps.
4. Unsorted timestamps.
5. Missing candles.
6. Zero volume.
7. Negative volume.
8. Invalid OHLC.
9. Flat market.
10. Strong bullish trend.
11. Strong bearish trend.
12. Sideways market.
13. Volatility shock.
14. Sudden gap.
15. Regime transition.
16. Conflicting timeframes.
17. Extreme spread.
18. Insufficient history.
19. NaN indicators.
20. Model failure.
21. Out-of-distribution data.
22. Exchange timezone change.
23. Corporate action.
24. Futures contract rollover.

Expected result for unreliable inputs: controlled failure, UNCERTAIN or NO TRADE.

---

# 41. COMMON REGIME ANALYSIS MISTAKES

Avoid:

- One indicator se regime declare karna.
- ADX ko direction indicator samajhna.
- RSI 70 ko automatic SELL samajhna.
- RSI 30 ko automatic BUY samajhna.
- Every range ko accumulation kehna.
- Every breakout ko real breakout kehna.
- HMM states ko fixed market meanings dena.
- ML accuracy ko profitability samajhna.
- Future data use karna.
- Repainting swing detection.
- Overfitting thresholds.
- Different assets ke liye identical thresholds assume karna.
- News risk ignore karna.
- Spread and slippage ignore karna.
- Uncalibrated score ko probability kehna.
- Synthetic tests ko historical evidence kehna.
- Unexecuted 10M scenarios ko completed batana.

---

# 42. SECURITY AND DATA INTEGRITY

- API keys source code mein hardcode mat karo.
- Secrets environment variables mein rakho.
- User account details logs mein expose mat karo.
- External model output ko verified fact mat samjho.
- Third-party data source timestamps preserve karo.
- Data revisions record karo.
- Model versioning maintain karo.
- Backtest results reproducible rakho.
- Failed tests ko delete karke hide mat karo.
- Audit logs preserve karo.

---

# 43. REFERENCE INTEGRATION

Is module ko existing trading skill references ke saath coordinate karna hai:

- technical-indicators.md
- volatility-analysis.md
- market-structure.md
- support-resistance.md
- price-action-strategies.md
- volume-analysis.md
- liquidity-analysis.md
- order-flow.md
- multi-timeframe-analysis.md
- ict-smc.md
- risk-management.md
- trade-management.md
- backtesting.md
- news-analysis.md
- fundamental-analysis.md
- candlestick-patterns.md
- chart-patterns.md

Integration rules:

1. Regime module market environment classify karega.
2. Structure module swing and structure evidence provide karega.
3. Indicator module technical measurements provide karega.
4. Volatility module volatility estimates provide karega.
5. Liquidity and order-flow modules execution environment assess karenge.
6. News module event risk provide karega.
7. Strategy module suitable setups select karega.
8. Risk module trade approval dega.
9. Backtesting module historical validation karega.
10. Trade management module approved position manage karega.

Duplicate calculations avoid karo. Shared definitions and consistent timestamps use karo.

---

# 44. FINAL OPERATING RULES

1. User ko natural Hinglish mein jawab do.
2. Market regime aur trade signal ko alag rakho.
3. Data ke bina live regime invent mat karo.
4. Bullish regime ka matlab automatic BUY nahi.
5. Bearish regime ka matlab automatic SELL nahi.
6. Sideways regime mein trend-following signal force mat karo.
7. Transition regime mein extra caution rakho.
8. Volatility ko direction mat samjho.
9. HMM/ML predictions ko certainty mat bolo.
10. Confidence ko calibrated probability tabhi bolo jab evidence available ho.
11. Backtest results tabhi report karo jab actual execution hui ho.
12. 10 million scenarios complete hone ka claim tabhi karo jab verified execution records hon.
13. User ko supporting evidence aur opposing evidence dono batao.
14. Invalid data par controlled failure do.
15. Risk approval ke bina trade recommend mat karo.
16. Setup unclear ho to WAIT / NO TRADE prefer karo.
17. Entry, SL aur TP ko available data se justify karo.
18. Historical classification ko future guarantee mat banao.
19. Market-specific rules apply karo.
20. Har result reproducible aur auditable banane ki koshish karo.

**CORE PRINCIPLE:**

Market regime analysis ka kaam market ko forcefully predict karna nahi, balki current market environment ko objectively classify karna, regime change ko monitor karna aur us environment ke according risk-aware trading decisions support karna hai.
