# VOLATILITY ANALYSIS — COMPLETE A–Z MASTER ENGINE

Version: 1.0  
Category: Volatility Research, Statistical Modeling, Risk, Derivatives and Trading  
Parent Skill: AI Trading Analyst  
Output Language: Natural Hinglish

---

# 1. PURPOSE AND OBJECTIVES

This reference defines a comprehensive volatility analysis and research framework for financial markets.

The system must understand, calculate, interpret, forecast, test and apply volatility across:

- Forex.
- Cryptocurrency.
- Indian stocks.
- Global stocks.
- Indices.
- Commodities.
- Futures.
- Options.
- Scalping.
- Intraday.
- Swing trading.
- Positional trading.
- Portfolio risk management.
- Algorithmic trading.

The system must cover:

1. Historical Volatility.
2. Realized Volatility.
3. Implied Volatility.
4. Forecast Volatility.
5. Conditional Volatility.
6. Intraday Volatility.
7. Overnight Volatility.
8. Volatility Regimes.
9. Volatility Clustering.
10. Volatility Expansion.
11. Volatility Contraction.
12. Volatility Breakouts.
13. Statistical Models.
14. GARCH Family.
15. ATR and Range-Based Estimators.
16. Options Volatility.
17. Volatility Surface.
18. VIX and Volatility Indices.
19. Volatility-Based Position Sizing.
20. Stop-Loss and Target Optimization.
21. Portfolio Volatility.
22. Monte Carlo Simulation.
23. Backtesting.
24. Ten-million-scenario testing framework.

**Core rule:** Volatility measures price variability. It does not independently determine market direction.

High volatility does not automatically mean BUY or SELL.

Low volatility does not automatically mean that a breakout is imminent.

Every interpretation must include timeframe, instrument, data source, market conditions and measurement method.

---

# 2. WHAT IS VOLATILITY?

Volatility measures how much an asset's price or returns vary over a specified period.

High volatility:

- Larger price fluctuations.
- Greater uncertainty in price movement.
- Potentially higher execution risk.
- Potentially wider stop requirements.
- Increased possibility of rapid gains and losses.

Low volatility:

- Smaller price fluctuations.
- Narrower trading ranges.
- Potentially lower immediate price variability.
- Possible consolidation.
- No guarantee of an upcoming breakout.

## 2.1 Volatility is not direction

Example:

An instrument moves from 100 to 105 and later falls to 98.

The movement may be highly volatile even though the final return is negative.

Volatility measures variability, not bullishness or bearishness.

## 2.2 Volatility units

Volatility may be expressed as:

- Absolute price units.
- Percentage.
- Daily standard deviation.
- Annualized percentage.
- ATR points.
- Basis points.
- Implied volatility percentage.

Always state the unit.

---

# 3. VOLATILITY CLASSIFICATION

The system must distinguish:

```text
HISTORICAL_VOLATILITY
REALIZED_VOLATILITY
IMPLIED_VOLATILITY
FORECAST_VOLATILITY
CONDITIONAL_VOLATILITY
INTRADAY_VOLATILITY
OVERNIGHT_VOLATILITY
RANGE_BASED_VOLATILITY
PARKINSON_VOLATILITY
GARMAN_KLASS_VOLATILITY
ROGERS_SATCHELL_VOLATILITY
YANG_ZHANG_VOLATILITY
GARCH_VOLATILITY
STOCHASTIC_VOLATILITY
LOCAL_VOLATILITY
FORWARD_VOLATILITY
PORTFOLIO_VOLATILITY
```

These measurements are related but not interchangeable.

---

# 4. HISTORICAL VOLATILITY (HV)

Historical volatility measures the variability of past returns.

A common method uses the standard deviation of logarithmic returns.

Log return:

```text
r(t) = ln(P(t) / P(t-1))
```

Historical volatility:

```text
HV = Standard Deviation of Returns
```

Annualized historical volatility:

```text
Annualized HV = Daily Return Std Dev × √Annualization Factor
```

Common approximate annualization factors:

- US and Indian stock trading days: 252.
- Calendar-day crypto markets: 365.
- Forex: use an explicitly documented convention.

The correct factor depends on the data frequency and market calendar.

## 4.1 HV calculation rules

Specify:

- Lookback period.
- Return type.
- Sampling frequency.
- Annualization factor.
- Missing-data treatment.
- Price adjustment method.

Common lookbacks:

- 5 periods.
- 10 periods.
- 20 periods.
- 30 periods.
- 60 periods.
- 90 periods.
- 120 periods.
- 252 periods.

Do not assume a 20-period HV is universally optimal.

## 4.2 Interpretation

Compare current HV with:

- Its own historical distribution.
- Previous periods.
- Similar market regimes.
- Other instruments in the same asset class.

A high HV relative to its own history indicates elevated realized variability, not guaranteed future movement.

---

# 5. REALIZED VOLATILITY (RV)

Realized volatility estimates volatility from observed returns over a specific period.

For intraday returns:

```text
RV = √(Σ r(i)²)
```

Where:

- r(i) = individual intraday return.
- The sum covers the chosen measurement period.

Annualization depends on sampling and time conventions.

## 5.1 Intraday RV

Use:

- One-minute returns.
- Five-minute returns.
- Fifteen-minute returns.
- Thirty-minute returns.
- Hourly returns.

High-frequency data requires careful treatment of:

- Bid-ask bounce.
- Microstructure noise.
- Missing observations.
- Irregular timestamps.
- Exchange outages.

## 5.2 Overnight and intraday decomposition

Separate:

- Previous close to current open.
- Current open to current close.
- Intraday realized movement.

Gap movement and intraday volatility should not be treated as identical.

## 5.3 Realized variance

```text
Realized Variance = Σ r(i)²
```

Realized volatility is the square root of realized variance.

---

# 6. IMPLIED VOLATILITY (IV)

Implied volatility is the volatility input implied by an option's market price under a selected pricing model.

It is not directly observed as a guaranteed future volatility value.

It depends on:

- Option price.
- Underlying price.
- Strike.
- Time to expiry.
- Interest rates.
- Dividends.
- Option type.
- Pricing model.
- Exercise style.
- Market liquidity.

## 6.1 IV interpretation

Higher IV generally means the option market price reflects greater expected variability under the model.

Lower IV generally means the opposite.

IV is not a directional prediction.

## 6.2 IV versus HV

Compare:

- Current IV.
- Historical volatility.
- Realized volatility.
- IV rank.
- IV percentile.
- Expiry-specific IV.
- Strike-specific IV.

The comparison must use consistent periods and units.

## 6.3 IV limitations

IV may be distorted by:

- Wide bid-ask spreads.
- Illiquid options.
- Stale quotes.
- Event premiums.
- Incorrect interest-rate inputs.
- Incorrect dividend assumptions.
- Model limitations.

Do not treat a single option quote as a reliable volatility forecast.

---

# 7. IV RANK AND IV PERCENTILE

## 7.1 IV Rank

A common calculation:

```text
IV Rank =
(Current IV - Lowest IV in Lookback) /
(Highest IV - Lowest IV) × 100
```

If highest IV equals lowest IV, the result is undefined.

## 7.2 IV Percentile

IV percentile measures the percentage of observations in the lookback period that are below current IV.

Example:

An IV percentile of 80 means approximately 80% of the sampled historical IV observations were below the current observation.

The exact methodology must be stated.

IV Rank and IV Percentile are different metrics.

---

# 8. TRUE RANGE AND ATR

Average True Range measures average price range, including gaps.

True Range:

```text
TR = max(
    High - Low,
    abs(High - Previous Close),
    abs(Low - Previous Close)
)
```

ATR is a smoothed average of True Range.

## 8.1 ATR methods

Common approaches:

- Wilder's RMA.
- Simple Moving Average.
- Exponential Moving Average.

Wilder smoothing is widely used in the standard ATR indicator.

## 8.2 ATR interpretation

ATR measures absolute price movement.

ATR does not indicate direction.

ATR should be interpreted relative to:

- Instrument price.
- Timeframe.
- Historical ATR.
- Volatility regime.
- Contract specifications.

## 8.3 Normalized ATR

```text
Normalized ATR = ATR / Current Price × 100
```

This helps compare instruments with different price levels.

## 8.4 ATR-based stop-loss

Example:

```text
Stop Distance = ATR × Multiplier
```

Possible multipliers must be strategy-specific and tested.

Do not use a universal ATR multiplier for every market.

---

# 9. RANGE-BASED VOLATILITY ESTIMATORS

Range-based estimators use OHLC data rather than closing prices alone.

## 9.1 Parkinson estimator

Uses high-low range.

Conceptual form:

```text
Variance ≈
(1 / 4 ln 2) × Average[ln(High / Low)²]
```

Useful when intraperiod range contains information not captured by close-to-close returns.

Assumptions and limitations must be considered, especially when gaps or drift are significant.

## 9.2 Garman-Klass estimator

Uses:

- Open.
- High.
- Low.
- Close.

It can be more efficient than a simple close-to-close estimator under its assumptions.

## 9.3 Rogers-Satchell estimator

Designed to accommodate nonzero drift under its assumptions.

## 9.4 Yang-Zhang estimator

Combines overnight and intraday components.

It is useful when opening gaps are relevant.

## 9.5 Estimator selection

Choose based on:

- Available data.
- Sampling frequency.
- Market gaps.
- Trading hours.
- Data quality.
- Estimator assumptions.

Never compare estimators without documenting their methodology.

---

# 10. VOLATILITY CLUSTERING

Volatility clustering means periods of large movements tend to be followed by periods of relatively large movements, while quiet periods may be followed by quiet periods.

This is a common empirical characteristic of financial returns.

Potential implications:

- Yesterday's high volatility may matter for today's risk.
- Stop distances may need regime adjustment.
- Fixed position sizes may create inconsistent risk.
- Volatility models may improve risk estimates.

Volatility clustering does not imply exact price direction.

---

# 11. VOLATILITY EXPANSION

Volatility expansion occurs when measured variability increases.

Possible evidence:

- ATR rises.
- Bollinger Band width expands.
- Realized volatility increases.
- Candle ranges increase.
- High-low ranges expand.
- Intraday movement accelerates.
- Implied volatility rises.

## 11.1 Expansion confirmation

Check:

- Price direction.
- Volume.
- Market structure.
- Breakout acceptance.
- News.
- Spread.
- Order-book conditions.

Expansion can occur during both bullish and bearish movements.

---

# 12. VOLATILITY CONTRACTION

Volatility contraction occurs when price variability decreases.

Possible evidence:

- Falling ATR.
- Narrowing Bollinger Bands.
- Reduced true range.
- Lower realized volatility.
- Narrower intraday ranges.

Contraction can indicate consolidation.

It does not guarantee an imminent breakout.

A market can remain quiet for an extended period.

---

# 13. VOLATILITY SQUEEZE

A squeeze identifies unusually compressed volatility according to a defined indicator or statistical threshold.

Possible tools:

- Bollinger Bands.
- Keltner Channels.
- ATR.
- Historical percentile.
- Standard deviation.
- Range compression.

## 13.1 Bollinger-Keltner squeeze

A common squeeze definition occurs when Bollinger Bands lie inside Keltner Channels.

Exact indicator settings must be documented.

## 13.2 Squeeze release

Potential release evidence:

- Band expansion.
- ATR increase.
- Price breakout.
- Volume expansion.
- Structure confirmation.

Squeeze release does not guarantee that price will continue in the breakout direction.

---

# 14. VOLATILITY BREAKOUTS

A volatility breakout occurs when price moves beyond a defined range or threshold with increased variability.

Possible methods:

- ATR breakout.
- Opening range breakout.
- Donchian breakout.
- Bollinger Band breakout.
- Historical range breakout.
- Standard deviation breakout.

Confirm:

1. Defined range.
2. Breakout threshold.
3. Close or acceptance rule.
4. Volume.
5. Market structure.
6. Execution conditions.
7. Risk and invalidation.

Distinguish between:

- Initial breakout.
- Confirmed breakout.
- Failed breakout.
- Volatility expansion without directional breakout.

---

# 15. VOLATILITY REGIME DETECTION

Classify market volatility into regimes.

Possible labels:

```text
VERY_LOW
LOW
NORMAL
ELEVATED
HIGH
EXTREME
UNKNOWN
```

These labels must be defined using historical thresholds.

## 15.1 Percentile-based regime

Example framework:

- Below 10th percentile: Very Low.
- 10th–30th percentile: Low.
- 30th–70th percentile: Normal.
- 70th–90th percentile: Elevated.
- Above 90th percentile: High.

These are example research thresholds, not universal trading rules.

## 15.2 Regime persistence

Measure:

- Number of consecutive periods.
- Transition frequency.
- Average regime duration.
- Regime transition probability.

## 15.3 Regime transition

Watch for:

- Low to normal.
- Normal to high.
- High to extreme.
- High to low.

Transitions should be confirmed using more than one observation where appropriate.

---

# 16. VOLATILITY INDICATORS

## 16.1 Bollinger Bands

Uses a moving average and standard deviation bands.

Common interpretation:

- Wider bands: greater recent variability.
- Narrower bands: lower recent variability.
- Band touches: price interaction, not automatic reversal signals.
- Band walking: sustained directional movement can occur.

## 16.2 Bollinger Band Width

A common calculation:

```text
Band Width =
(Upper Band - Lower Band) / Middle Band
```

Define handling when the middle band is zero or invalid.

## 16.3 ATR

Measures smoothed True Range.

## 16.4 Keltner Channels

Uses a moving average and ATR-based channel width.

## 16.5 Donchian Channels

Uses highest high and lowest low over a selected lookback.

## 16.6 Standard Deviation

Measures dispersion around the mean.

## 16.7 Historical Volatility

Measures past return variability.

## 16.8 Chaikin Volatility

Measures changes in high-low range.

## 16.9 Choppiness Index

Attempts to measure whether price movement is more trend-like or range-like.

It is not a direct volatility forecast.

## 16.10 Ulcer Index

Measures downside drawdown depth and duration rather than conventional two-sided volatility.

## 16.11 VIX

VIX represents option-implied expected volatility for the S&P 500 over a specified forward horizon, calculated using Cboe's methodology.

It is not:

- A directional indicator.
- A guaranteed future realized volatility value.
- A universal volatility measure for every asset.

For Indian markets, use the appropriate India volatility index and verify its current methodology and availability.

---

# 17. GARCH FAMILY

GARCH models estimate conditional variance from historical returns and prior variance estimates.

## 17.1 ARCH

Autoregressive Conditional Heteroskedasticity.

Models variance using past squared shocks.

## 17.2 GARCH(1,1)

A common model:

```text
h(t) = omega
     + alpha × epsilon(t-1)²
     + beta × h(t-1)
```

Where:

- h(t): Conditional variance.
- omega: Constant.
- alpha: Response to recent shocks.
- beta: Persistence of previous variance.
- epsilon: Previous return shock.

## 17.3 GARCH interpretation

- Higher alpha: stronger reaction to recent shocks.
- Higher beta: greater persistence.
- alpha + beta near one: potentially persistent volatility under the model.

Model constraints and stationarity conditions must be checked.

## 17.4 EGARCH

Models log variance and can capture asymmetric volatility responses.

## 17.5 GJR-GARCH

Allows negative and positive shocks to affect volatility differently.

## 17.6 TGARCH

Threshold GARCH models capture asymmetric conditional volatility effects.

## 17.7 IGARCH

Used when volatility persistence is modeled as extremely high.

## 17.8 APARCH

Allows more flexible power and asymmetry specifications.

## 17.9 Model evaluation

Check:

- Parameter validity.
- Convergence.
- Residuals.
- Standardized residuals.
- Remaining ARCH effects.
- Forecast errors.
- Out-of-sample performance.
- Stability across regimes.

Do not choose a GARCH model only because it fits historical data well.

---

# 18. STOCHASTIC VOLATILITY MODELS

Stochastic volatility models treat variance as a latent random process.

They can be used to model volatility dynamics that are not fully captured by simple GARCH models.

Consider:

- Latent volatility.
- State-space representation.
- Parameter estimation.
- Filtering.
- Forecasting.
- Model uncertainty.

These models can be computationally intensive.

Never present a latent volatility estimate as directly observed market data.

---

# 19. VOLATILITY FORECASTING

Potential forecasting methods:

- Historical average.
- Rolling standard deviation.
- Exponentially weighted moving average.
- ATR forecast.
- GARCH.
- EGARCH.
- GJR-GARCH.
- Realized volatility models.
- HAR-RV.
- Stochastic volatility.
- Machine learning.

## 19.1 EWMA volatility

```text
Variance(t) =
lambda × Variance(t-1)
+ (1 - lambda) × Return(t-1)²
```

Lambda must be specified and validated.

## 19.2 HAR-RV

Uses realized volatility at different horizons, such as:

- Daily.
- Weekly.
- Monthly.

The exact model and scaling must be documented.

## 19.3 Forecast evaluation

Use:

- MAE.
- RMSE.
- QLIKE.
- Forecast bias.
- Out-of-sample loss.
- Regime-specific performance.

A forecast must include its horizon and uncertainty.

---

# 20. VOLATILITY AND OPTIONS

Options are highly sensitive to volatility.

Important concepts:

- Implied Volatility.
- Historical Volatility.
- Realized Volatility.
- IV Rank.
- IV Percentile.
- Volatility Smile.
- Volatility Skew.
- Term Structure.
- Forward Volatility.
- Vega.
- Volga/Vomma.
- Vanna.
- Gamma.
- Theta.

## 20.1 Volatility smile

Implied volatility varies across strikes.

## 20.2 Volatility skew

Implied volatility may differ between lower and higher strikes.

## 20.3 Volatility term structure

Implied volatility varies by expiry.

## 20.4 Forward volatility

A model-derived estimate of volatility over a future period implied by two maturities.

The calculation requires consistent variance and time conventions.

## 20.5 Vega

Measures an option's theoretical sensitivity to changes in implied volatility.

## 20.6 Gamma

Measures the rate of change of delta with respect to underlying price.

## 20.7 Theta

Measures sensitivity to time decay under the selected pricing convention.

## 20.8 Volatility risk

Option positions can lose value due to:

- IV decline.
- Time decay.
- Underlying movement.
- Spread widening.
- Liquidity reduction.
- Model error.

Do not recommend an option trade based on IV alone.

---

# 21. VOLATILITY CRUSH

Volatility crush refers to a decline in implied volatility that reduces option premium, other factors held constant.

Common contexts:

- Earnings.
- Major economic announcements.
- Central bank decisions.
- Scheduled events.
- Expiry-related repricing.

The actual option price also depends on underlying price, time, rates and other Greeks.

A volatility crush is not guaranteed after every news event.

---

# 22. EVENT AND NEWS VOLATILITY

Monitor:

- Central bank announcements.
- Inflation data.
- Employment reports.
- GDP.
- Interest rate decisions.
- Earnings.
- Corporate announcements.
- Geopolitical events.
- Government policy.
- Commodity inventories.
- Token unlocks.
- Regulatory announcements.

Before an event:

- Check scheduled time.
- Check timezone.
- Check expected volatility.
- Check current spread.
- Check overnight and gap exposure.
- Check position size.

After an event:

- Compare actual and forecast data.
- Evaluate price reaction.
- Evaluate spread normalization.
- Evaluate realized volatility.
- Reassess invalidation.

Never invent event dates or outcomes.

---

# 23. VOLATILITY ACROSS TRADING SESSIONS

Analyze volatility by:

- Asian session.
- London session.
- New York session.
- Indian market opening.
- Indian market closing.
- Pre-market.
- After-hours.
- Futures sessions.

Use actual exchange schedules.

Account for:

- Daylight-saving changes.
- Exchange holidays.
- Early closes.
- Instrument-specific trading hours.

Session volatility is empirical and can change over time.

---

# 24. VOLATILITY AND MARKET STRUCTURE

Combine volatility with:

- Trend.
- Range.
- BOS.
- CHoCH.
- MSS.
- Support and resistance.
- Liquidity.
- Breakouts.
- Failed breakouts.

Examples:

### Trend with expanding volatility

Potential strong directional movement, but execution risk may also rise.

### Trend with contracting volatility

Potential pause or consolidation.

### Range with low volatility

Potential compression.

### Range with expanding volatility

Potential range expansion or breakout.

Always verify actual direction and structure.

---

# 25. VOLATILITY AND ICT/SMC

Use with `ict-smc.md`.

Evaluate:

- Displacement.
- Fair Value Gap.
- Order Block.
- Liquidity sweep.
- Expansion leg.
- Retracement.
- Premium/discount.
- Session volatility.

Do not interpret a large candle as proof of institutional participation.

Displacement definitions should include objective size and structure rules.

---

# 26. VOLATILITY AND ORDER FLOW

Use with `order-flow.md`.

Evaluate:

- Bid/ask spread.
- Market depth.
- Volume delta.
- CVD.
- Footprint.
- Absorption.
- Order-book imbalance.
- Slippage.
- Market impact.

Volatility can rise while order-book depth falls.

This combination may create difficult execution conditions.

Displayed liquidity is not guaranteed liquidity.

---

# 27. VOLATILITY AND VOLUME

Use with `volume-analysis.md`.

Evaluate:

- Relative volume.
- Volume expansion.
- Volume contraction.
- Price range.
- Volume per price movement.
- Volume profile.
- VWAP.
- Delta.

High volume and high volatility are not the same thing.

High volume may occur in a narrow range due to absorption or two-way trading.

---

# 28. MARKET-SPECIFIC VOLATILITY FRAMEWORK

## 28.1 Forex

Analyze:

- Pair-specific volatility.
- Session behavior.
- Interest rate decisions.
- Inflation.
- Employment.
- Currency correlations.
- Rollover.
- Spread.
- Weekend gaps.

Forex volatility estimates depend on the data feed because the market is fragmented.

## 28.2 Cryptocurrency

Analyze:

- 24/7 returns.
- Exchange-specific data.
- Weekend volatility.
- Funding rates.
- Open interest.
- Liquidations.
- Token unlocks.
- Regulatory news.
- Exchange failures.
- Spot/futures basis.

Use appropriate calendar-day annualization.

## 28.3 Indian Stocks

Analyze:

- NSE/BSE trading sessions.
- Opening gaps.
- Corporate earnings.
- Results announcements.
- Corporate actions.
- Sector volatility.
- Circuit limits.
- Market-wide volatility.
- Stock-specific liquidity.

## 28.4 Global Stocks

Analyze:

- Earnings gaps.
- Pre-market trading.
- After-hours trading.
- Index conditions.
- Sector volatility.
- Trading halts.

## 28.5 Indices

Analyze:

- Index-level realized volatility.
- Futures volatility.
- Constituent contributions.
- Correlation.
- Rebalancing.
- Expiry.
- Market-wide event risk.

## 28.6 Commodities

Analyze:

- Inventory.
- Weather.
- Supply disruption.
- Demand.
- Seasonality.
- Contract expiry.
- Delivery.
- Geopolitics.

## 28.7 Futures

Account for:

- Contract multiplier.
- Tick value.
- Expiry.
- Rollover.
- Price limits.
- Margin.
- Overnight risk.

## 28.8 Options

Account for:

- IV.
- Skew.
- Term structure.
- Greeks.
- Strike liquidity.
- Expiry.
- Gamma exposure.
- Volatility crush.
- Exercise and settlement rules.

---

# 29. VOLATILITY-BASED TRADING STRATEGIES

Every strategy must have objective entry, exit, invalidation and risk rules.

## Strategy 1: ATR Trend Continuation

Conditions:

- Valid trend.
- ATR behavior supports the setup.
- Pullback is controlled.
- Structure remains intact.
- Risk is acceptable.

## Strategy 2: Volatility Squeeze Breakout

Conditions:

- Defined squeeze.
- Defined range.
- Confirmed breakout.
- Volume or structure confirmation.
- Acceptable spread and slippage.

## Strategy 3: Volatility Expansion Continuation

Conditions:

- Range expansion.
- Directional structure.
- Follow-through.
- Entry after a defined trigger.

## Strategy 4: Volatility Contraction Pullback

Conditions:

- Established trend.
- Reduced countertrend movement.
- Structure intact.
- Confirmation of continuation.

## Strategy 5: ATR-Based Stop Management

- Calculate ATR.
- Define initial stop.
- Set maximum risk.
- Recalculate according to strategy rules.
- Never widen stops without explicit risk approval.

## Strategy 6: Bollinger Band Expansion

- Identify band compression.
- Confirm band expansion.
- Confirm price direction.
- Avoid automatic reversal assumptions.

## Strategy 7: Realized Volatility Regime Strategy

- Calculate rolling RV.
- Classify regime.
- Select validated strategy parameters.
- Monitor regime transitions.

## Strategy 8: IV-HV Relative Value Research

Compare implied and realized volatility.

This is research, not an automatic option-selling signal.

Account for:

- Forecast error.
- Risk premium.
- Skew.
- Term structure.
- Transaction costs.
- Tail risk.

## Strategy 9: Event Volatility Strategy

- Verify event schedule.
- Evaluate IV.
- Evaluate expected move.
- Evaluate option liquidity.
- Define maximum loss.
- Avoid unsupported directional assumptions.

## Strategy 10: Range Expansion Strategy

- Define prior range.
- Define breakout threshold.
- Confirm acceptance.
- Evaluate risk and liquidity.

## Strategy 11: Volatility-Adjusted Trend Following

- Adjust exposure according to validated volatility estimates.
- Apply portfolio risk limits.
- Monitor volatility spikes.

## Strategy 12: Volatility Mean Reversion Research

- Identify extreme volatility relative to history.
- Test whether reversion exists.
- Include transaction costs.
- Avoid assuming that extreme volatility must fall.

---

# 30. VOLATILITY-BASED STOP-LOSS

Potential methods:

- ATR multiple.
- Swing-based stop.
- Standard deviation distance.
- Range boundary.
- Structure-based stop.
- Option-specific maximum loss.

A stop must respect:

- Market structure.
- Instrument tick size.
- Spread.
- Volatility.
- Execution conditions.
- Maximum account risk.

A wider stop requires smaller position size if account risk is unchanged.

Never choose a stop solely because it produces an attractive R:R.

---

# 31. VOLATILITY-BASED POSITION SIZING

Basic risk model:

```text
Risk Amount = Account Balance × Risk Percentage
```

```text
Position Size =
Risk Amount / Monetary Risk Per Unit
```

Monetary risk per unit must include:

- Entry-to-stop distance.
- Contract multiplier.
- Tick or pip value.
- Currency conversion.
- Expected fees.
- Spread.
- Slippage.

## 31.1 Volatility targeting

A portfolio or strategy may target a defined volatility level by adjusting exposure.

A simplified relationship:

```text
Exposure ∝ Target Volatility / Estimated Volatility
```

This must be constrained by:

- Maximum leverage.
- Minimum liquidity.
- Margin.
- Risk limits.
- Correlation.
- Gap risk.

Volatility targeting does not eliminate losses.

## 31.2 Position sizing warning

During extreme volatility, smaller positions may be appropriate.

However, estimated volatility can lag sudden shocks.

Use additional stress limits.

---

# 32. PORTFOLIO VOLATILITY

Portfolio volatility depends on individual asset volatility and correlations.

For weights vector w and covariance matrix Sigma:

```text
Portfolio Variance = w' × Sigma × w
```

```text
Portfolio Volatility = √Portfolio Variance
```

Analyze:

- Asset weights.
- Return covariance.
- Correlation.
- Concentration.
- Currency exposure.
- Sector exposure.
- Leverage.
- Liquidity.
- Tail risk.

Correlation can increase during market stress.

Historical covariance is not a guarantee of future diversification.

---

# 33. VOLATILITY RISK METRICS

Monitor:

- Standard deviation.
- ATR.
- Normalized ATR.
- Historical volatility.
- Realized volatility.
- Implied volatility.
- Maximum drawdown.
- Value at Risk.
- Expected Shortfall.
- Tail loss.
- Gap risk.
- Stress loss.
- Volatility of volatility.

## 33.1 Value at Risk

VaR estimates a loss threshold over a specified horizon and confidence level under a model.

## 33.2 Expected Shortfall

Expected Shortfall estimates average loss beyond the VaR threshold under a defined methodology.

## 33.3 Risk limitations

VaR and Expected Shortfall depend on:

- Data.
- Distribution assumptions.
- Horizon.
- Confidence level.
- Model.
- Portfolio composition.

Neither metric guarantees a maximum possible loss.

---

# 34. PYTHON VOLATILITY ENGINE

Recommended architecture:

```text
DATA INPUT
    |
    v
DATA VALIDATION
    |
    v
RETURN CALCULATION
    |
    v
OHLC RANGE METRICS
    |
    v
ATR / HV / RV / IV
    |
    v
VOLATILITY REGIME
    |
    v
FORECAST MODELS
    |
    v
MARKET STRUCTURE
    |
    v
RISK MODEL
    |
    v
BACKTEST / VALIDATION
    |
    v
BUY / SELL / WAIT / NO TRADE
```

## 34.1 Input data requirements

```text
timestamp
open
high
low
close
volume
instrument
exchange
timeframe
timezone
source
```

For options:

```text
underlying_price
option_type
strike
expiry
bid
ask
last_price
implied_volatility
volume
open_interest
interest_rate
dividend_assumption
```

## 34.2 Basic log returns

```python
import math

def calculate_log_return(previous_price, current_price):
    if previous_price is None or current_price is None:
        return None

    if previous_price <= 0 or current_price <= 0:
        return None

    return math.log(current_price / previous_price)
```

## 34.3 Historical volatility

```python
import math
import statistics

def historical_volatility(
    prices,
    annualization_factor=252
):
    if annualization_factor <= 0:
        raise ValueError("Annualization factor must be positive")

    if len(prices) < 3:
        return None

    returns = []

    for previous, current in zip(prices[:-1], prices[1:]):
        if previous is None or current is None:
            return None

        if previous <= 0 or current <= 0:
            return None

        returns.append(math.log(current / previous))

    if len(returns) < 2:
        return None

    daily_std = statistics.stdev(returns)

    return daily_std * math.sqrt(annualization_factor)
```

This function assumes equally spaced observations. Irregular or missing intervals require proper resampling and validation.

## 34.4 True Range

```python
def true_range(high, low, previous_close):
    if high is None or low is None or previous_close is None:
        return None

    if high < low:
        raise ValueError("High cannot be below low")

    return max(
        high - low,
        abs(high - previous_close),
        abs(low - previous_close)
    )
```

## 34.5 Simple ATR

```python
def simple_atr(true_ranges, period=14):
    if period <= 0:
        raise ValueError("Period must be positive")

    if len(true_ranges) < period:
        return None

    values = true_ranges[-period:]

    if any(value is None for value in values):
        return None

    return sum(values) / period
```

This is a simple moving-average ATR, not Wilder's smoothing.

## 34.6 Normalized ATR

```python
def normalized_atr(atr, price):
    if atr is None or price is None or price <= 0:
        return None

    return (atr / price) * 100
```

## 34.7 Rolling volatility regime

```python
def volatility_regime(
    current_value,
    historical_values
):
    values = [
        value for value in historical_values
        if value is not None
    ]

    if current_value is None or len(values) < 20:
        return "UNKNOWN"

    lower = sum(values) / len(values)

    sorted_values = sorted(values)

    index = int(0.9 * (len(sorted_values) - 1))
    upper = sorted_values[index]

    if current_value < lower * 0.5:
        return "LOW"

    if current_value > upper:
        return "HIGH"

    return "NORMAL"
```

This example is a basic illustration, not a production percentile engine. Production logic must calculate the current observation's empirical percentile without leakage and use validated regime thresholds.

---

# 35. VOLATILITY ENGINE TESTING

Test:

- Invalid prices.
- Zero prices.
- Negative prices.
- Missing values.
- Duplicate timestamps.
- Out-of-order data.
- Incorrect OHLC.
- Missing candles.
- Irregular intervals.
- Incorrect annualization.
- Exchange holidays.
- Corporate actions.
- Futures rollover.
- Timezone errors.
- Extreme outliers.

Test expected outputs against independently calculated reference values.

Record:

- Code version.
- Input dataset.
- Parameters.
- Execution timestamp.
- Test status.
- Results.

Never mark unexecuted tests as passed.

---

# 36. BACKTESTING VOLATILITY STRATEGIES

Every backtest must define:

- Instrument.
- Exchange.
- Historical data.
- Sampling frequency.
- Volatility estimator.
- Lookback.
- Entry.
- Exit.
- Stop.
- Target.
- Position sizing.
- Spread.
- Commission.
- Slippage.
- Funding or financing.
- Margin.
- Execution model.

Measure:

- Win rate.
- Expectancy.
- Profit factor.
- Net return.
- Maximum drawdown.
- Sharpe.
- Sortino.
- Calmar.
- MAE.
- MFE.
- Average holding time.
- Exposure.
- Turnover.
- Cost sensitivity.

Use:

- In-sample testing.
- Out-of-sample testing.
- Walk-forward testing.
- Cross-validation where appropriate.
- Parameter stability.
- Regime-specific evaluation.

Prevent:

- Look-ahead bias.
- Data leakage.
- Survivorship bias.
- Overfitting.
- Repainting.
- Unrealistic fills.

---

# 37. TEN-MILLION-SCENARIO RESEARCH FRAMEWORK

Research target: Up to 10,000,000 executable and auditable scenarios.

Possible scenario dimensions:

- ATR period.
- ATR multiplier.
- HV lookback.
- RV sampling frequency.
- IV threshold.
- IV Rank.
- IV Percentile.
- Bollinger settings.
- Keltner settings.
- Squeeze threshold.
- Regime boundaries.
- GARCH parameters.
- Entry method.
- Stop method.
- Target method.
- Timeframe.
- Instrument.
- Session.
- Spread.
- Slippage.
- Volatility shock.
- Market regime.
- Position size.
- Risk limit.

## 37.1 Scenario categories

Report separately:

1. Historical trade simulations.
2. Parameter combinations.
3. Forecast-model comparisons.
4. Bootstrap simulations.
5. Monte Carlo simulations.
6. Synthetic stress scenarios.

Do not combine these into one misleading scenario count.

## 37.2 Scenario record

```python
scenario_record = {
    "scenario_id": None,
    "strategy_version": None,
    "dataset_id": None,
    "instrument": None,
    "timeframe": None,
    "parameters": None,
    "simulation_type": None,
    "execution_status": "NOT_RUN",
    "trade_count": None,
    "net_return": None,
    "max_drawdown": None,
    "expectancy": None,
    "forecast_error": None
}
```

## 37.3 Execution states

```text
NOT_RUN
PLANNED
RUNNING
PARTIALLY_COMPLETED
COMPLETED
FAILED
```

Never claim that ten million scenarios have been completed without execution logs.

A target is not an executed result.

---

# 38. MONTE CARLO AND STRESS TESTING

Simulate:

- Randomized trade sequences.
- Bootstrap returns.
- Volatility spikes.
- Gap events.
- Spread expansion.
- Slippage expansion.
- Liquidity reduction.
- Delayed entries.
- Missed exits.
- Exchange outages.
- Parameter perturbations.
- Correlation shocks.
- News shocks.
- Regime transitions.

Report:

- Median outcome.
- Return distribution.
- Drawdown distribution.
- Tail losses.
- Risk of ruin under stated assumptions.
- Stress-case losses.
- Sensitivity to transaction costs.

Monte Carlo outputs depend on the assumptions and input data.

They are not guarantees of future outcomes.

---

# 39. VOLATILITY ALERT SYSTEM

Potential alerts:

```text
ATR_SPIKE
ATR_CONTRACTION
HV_EXTREME
RV_SPIKE
IV_SPIKE
IV_CRUSH
VOLATILITY_SQUEEZE
SQUEEZE_RELEASE
VOLATILITY_EXPANSION
VOLATILITY_CONTRACTION
REGIME_CHANGE
GAP_RISK_WARNING
SPREAD_EXPANSION
LIQUIDITY_REDUCTION
VOLATILITY_FORECAST_CHANGE
OPTIONS_SKEW_CHANGE
TERM_STRUCTURE_CHANGE
DATA_QUALITY_WARNING
```

Every alert must contain:

- Instrument.
- Exchange.
- Timeframe.
- Timestamp.
- Metric.
- Current value.
- Reference value.
- Threshold.
- Source.
- Confidence.
- Relevant risk.

Alerts must not automatically generate live trades.

---

# 40. VOLATILITY AND TRADE MANAGEMENT

Use with `trade-management.md`.

Monitor:

- Initial ATR.
- Current ATR.
- Entry volatility.
- Stop distance.
- Realized movement.
- Current risk.
- Trailing stop.
- Partial exits.
- Gap risk.
- Spread changes.

## 40.1 Stop adjustment

A stop should not be widened simply because volatility increases.

Any stop modification must preserve the approved maximum risk or explicitly request a new risk decision.

## 40.2 Trailing stop

Possible approaches:

- ATR trailing.
- Swing trailing.
- Structure trailing.
- Chandelier Exit.
- Time-based exit.

Each must be backtested with realistic execution.

## 40.3 Partial booking

Evaluate whether partial exits improve the strategy after costs.

Do not assume they always improve results.

---

# 41. COMMON VOLATILITY MISTAKES

Avoid:

1. Assuming high volatility means BUY.
2. Assuming low volatility means SELL.
3. Treating ATR as directional.
4. Confusing IV and HV.
5. Confusing volatility and volume.
6. Ignoring overnight gaps.
7. Using incorrect annualization.
8. Comparing different sampling frequencies directly.
9. Ignoring market-specific trading calendars.
10. Using stale option quotes.
11. Treating VIX as a universal volatility indicator.
12. Assuming a squeeze guarantees a breakout.
13. Assuming every volatility spike will mean-revert.
14. Using future data in volatility forecasting.
15. Overfitting GARCH parameters.
16. Ignoring transaction costs.
17. Ignoring liquidity during high volatility.
18. Using fixed position sizes across all volatility regimes.
19. Ignoring volatility-of-volatility.
20. Claiming forecasts are certain.
21. Reporting simulations that were not run.
22. Treating VaR as a maximum possible loss.

---

# 42. PROFESSIONAL VOLATILITY ANALYSIS REPORT

All user-facing reports must be in natural Hinglish.

## Market Information

- Instrument:
- Exchange:
- Current price:
- Timeframe:
- Data timestamp:
- Timezone:
- Data source:

## Volatility Measurements

- ATR:
- Normalized ATR:
- Historical volatility:
- Realized volatility:
- Implied volatility:
- IV Rank:
- IV Percentile:
- Bollinger Band Width:
- Range-based volatility:

## Volatility Regime

- Current regime:
- Historical percentile:
- Regime duration:
- Recent change:
- Forecast horizon:

## Market Structure

- Trend:
- Range:
- Support:
- Resistance:
- Liquidity:
- Breakout status:

## Event Risk

- Upcoming event:
- Event timestamp:
- Gap risk:
- News risk:
- Session conditions:

## Options Analysis

- Expiry:
- Strike:
- IV:
- Skew:
- Term structure:
- Vega:
- Gamma:
- Theta:
- Liquidity:

## Trade Plan

- BUY / SELL / WAIT / NO TRADE:
- Entry trigger:
- Entry:
- Stop-loss:
- TP1:
- TP2:
- TP3:
- R:R:
- Position size:
- Maximum account risk:

## Execution Risk

- Spread:
- Slippage:
- Market depth:
- Gap risk:
- Liquidity:
- Data quality:

## Research Validation

- Backtest status:
- Out-of-sample status:
- Forecast accuracy:
- Monte Carlo status:
- Scenario count:
- Model version:

## Final Decision

- Decision:
- Evidence:
- Confidence category:
- What must happen next:
- Invalidation:

---

# 43. FINAL DECISION ENGINE

## BUY

Only when:

- Directional setup is valid.
- Market structure supports it.
- Volatility is suitable for the strategy.
- Entry is actionable.
- Stop and targets are defined.
- Execution conditions are acceptable.
- Risk checks pass.

## SELL

Only when:

- Directional setup is valid.
- Market structure supports it.
- Volatility is suitable for the strategy.
- Entry is actionable.
- Stop and targets are defined.
- Execution conditions are acceptable.
- Risk checks pass.

## WAIT

Use when:

- Volatility regime is changing.
- Breakout confirmation is missing.
- Price is inside an unclear range.
- Forecast uncertainty is high.
- Entry trigger has not occurred.

## NO TRADE

Use when:

- Data is unreliable.
- Spread is excessive.
- Liquidity is insufficient.
- Volatility is too unstable for the strategy.
- Risk exceeds limits.
- Entry and invalidation cannot be defined.
- Reward-to-risk is inadequate.
- Event risk makes execution unacceptable.

A volatility score cannot override a hard risk failure.

---

# 44. SECURITY AND AUTOMATION

Protect:

- API keys.
- Broker credentials.
- Exchange secrets.
- Private keys.
- Account information.

For automated execution:

1. Validate market data.
2. Validate volatility calculations.
3. Validate instrument specifications.
4. Validate order quantity.
5. Validate stop-loss.
6. Validate maximum risk.
7. Check duplicate orders.
8. Check margin.
9. Confirm broker response.
10. Reconcile actual positions.

An analytical signal must not silently become a live order.

Require explicit authorization and independent execution safeguards.

---

# 45. FINAL OPERATING RULES

1. Volatility is not direction.
2. Always state the measurement method.
3. Always state the timeframe.
4. Always state the data source.
5. Distinguish HV, RV and IV.
6. Use correct annualization.
7. Include gaps and session effects.
8. Consider market-specific conditions.
9. Verify option quote quality.
10. Use out-of-sample testing.
11. Prevent look-ahead bias.
12. Include spread and slippage.
13. Adjust position size to actual risk.
14. Never widen stops without risk approval.
15. Never invent live volatility values.
16. Never invent option IV.
17. Never invent VIX values.
18. Never fabricate model forecasts.
19. Never claim unexecuted backtests.
20. Never claim ten million completed scenarios without logs.
21. Explain uncertainty clearly.
22. Prefer WAIT when confirmation is missing.
23. Prefer NO TRADE when risk is unacceptable.
24. Explain every user-facing result in natural Hinglish.
25. Never guarantee profit.

---

# 46. REFERENCE INTEGRATION

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
- `liquidity-analysis.md`

Load relevant references according to the user's request.

---

# END OF VOLATILITY ANALYSIS MASTER REFERENCE
