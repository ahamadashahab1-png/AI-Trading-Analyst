
# PORTFOLIO MANAGEMENT & ALLOCATION ENGINE
## Professional A-Z Multi-Asset Portfolio Construction, Capital Allocation, Risk Optimization, Hedging, Rebalancing and Monitoring System

**Version:** 1.0  
**Module:** AI Trading Analyst  
**Category:** Advanced Portfolio Intelligence  
**User-facing language:** Natural Hinglish  
**Supported markets:** Forex, Crypto, Indian Stocks, Global Stocks, Indices, Futures, Commodities and Options  
**Supported portfolio types:** Long-only, Long/Short, Multi-Asset, Multi-Strategy and Derivatives  
**Decision outputs:** ADD / REDUCE / HOLD / REBALANCE / HEDGE / CLOSE / WAIT

---

# 1. CORE PURPOSE

Portfolio Management Engine ka objective poore trading account ko ek integrated system ki tarah manage karna hai.

Individual trade profitable ho sakta hai, lekin multiple positions ko combine karne par portfolio ka risk excessive ho sakta hai.

Example:

- Long Nifty.
- Long Bank Nifty.
- Long multiple banking stocks.
- Long an ETF with similar exposure.

Ye alag positions hain, lekin inka underlying risk kaafi correlated ho sakta hai.

Portfolio Engine ko sirf individual trades nahi, balki combined exposure analyse karna hoga.

## Main Responsibilities

1. Account equity calculate karna.
2. Available capital aur free margin calculate karna.
3. Portfolio exposure measure karna.
4. Asset allocation determine karna.
5. Position sizes calculate karna.
6. Correlated positions identify karna.
7. Concentration risk control karna.
8. Portfolio volatility measure karna.
9. Maximum drawdown monitor karna.
10. Risk limits enforce karna.
11. Hedging opportunities evaluate karna.
12. Portfolio rebalancing decisions generate karna.
13. Multiple strategies ke combined risk ko analyse karna.
14. Portfolio performance attribution karna.
15. Stress scenarios simulate karna.
16. Capital protection rules enforce karna.

**Core principle:** Portfolio ka objective maximum return chase karna nahi, balki acceptable risk ke andar sustainable capital allocation aur risk-adjusted performance achieve karna hai.

---

# 2. PORTFOLIO ENGINE ARCHITECTURE

```text
PORTFOLIO MANAGEMENT ENGINE
|
|-- 1. Account Data
|     |-- Equity
|     |-- Balance
|     |-- Cash
|     |-- Margin
|     |-- P&L
|
|-- 2. Portfolio Data Validation
|
|-- 3. Position Management
|     |-- Open Positions
|     |-- Pending Orders
|     |-- Closed Positions
|
|-- 4. Exposure Engine
|     |-- Gross Exposure
|     |-- Net Exposure
|     |-- Asset Exposure
|     |-- Currency Exposure
|     |-- Sector Exposure
|
|-- 5. Correlation Engine
|
|-- 6. Allocation Engine
|     |-- Equal Weight
|     |-- Risk-Based
|     |-- Volatility Targeting
|     |-- Risk Parity
|     |-- Mean Variance
|
|-- 7. Portfolio Risk Engine
|
|-- 8. Hedging Engine
|
|-- 9. Rebalancing Engine
|
|-- 10. Performance Attribution
|
|-- 11. Stress Testing
|
|-- 12. Monitoring and Alerts
|
|-- 13. Final Portfolio Decision
```

Har component independently testable hona chahiye.

Agar account data incomplete hai, engine ko capital allocation approve nahi karna chahiye.

---

# 3. PORTFOLIO DATA MODEL

Portfolio analysis se pehle account aur holdings ki structured information collect karo.

## 3.1 Account Information

Required fields:

- Account ID: internal identifier only.
- Base currency.
- Account balance.
- Current equity.
- Available cash.
- Used margin.
- Free margin.
- Unrealized P&L.
- Realized P&L.
- Deposit and withdrawal history.
- Broker or exchange.
- Account type.
- Leverage settings.
- Account permissions.

Sensitive credentials ko portfolio database mein store mat karo.

## 3.2 Position Information

Har position ke liye:

- Position ID.
- Instrument.
- Asset class.
- Exchange.
- Direction.
- Quantity.
- Average entry.
- Current mark price.
- Market value.
- Unrealized P&L.
- Stop loss.
- Target.
- Contract multiplier.
- Tick size.
- Currency.
- Margin requirement.
- Fees.
- Holding period.
- Strategy ID.
- Strategy version.

## 3.3 Pending Order Information

- Order ID.
- Instrument.
- Side.
- Order type.
- Quantity.
- Limit price.
- Stop price.
- Expiry.
- Estimated margin.
- Estimated risk.
- Execution status.

Pending orders ko ignore karke allocation calculate mat karo. Unke fill hone ki possibility ko portfolio exposure mein include karo.

## 3.4 Data Quality

Validate:

1. Duplicate positions.
2. Missing quantities.
3. Invalid prices.
4. Incorrect currencies.
5. Stale market prices.
6. Missing contract multipliers.
7. Incorrect corporate actions.
8. Missing open orders.
9. Broker position mismatch.
10. Incorrect margin calculations.

Critical data missing ho to allocation status `BLOCKED` rakho.

---

# 4. PORTFOLIO ACCOUNTING

## 4.1 Account Balance

Balance generally realized cash movements aur realized P&L reflect karta hai. Exact broker definition verify karo.

## 4.2 Equity

Simplified formula:

```text
Equity = Account Balance + Unrealized P&L
```

Broker-specific adjustments, financing, accrued charges aur other account entries include ho sakte hain.

## 4.3 Available Capital

```text
Available Capital =
Equity - Required Reserves
```

Required reserves mein margin buffer, pending obligations aur risk reserve include ho sakte hain.

## 4.4 Free Margin

Simplified leveraged account formula:

```text
Free Margin = Equity - Used Margin
```

Broker ke exact margin rules verify karo.

## 4.5 Net Asset Value

Portfolio NAV:

```text
NAV = Total Assets - Total Liabilities
```

Different currencies ki holdings ko consistent base currency mein convert karo.

## 4.6 Deposits and Withdrawals

Performance calculation mein deposits aur withdrawals ko account returns se separate karo.

Cash flow ko ignore karne se performance misleading ho sakti hai.

---

# 5. PORTFOLIO CLASSIFICATION

Portfolio ko multiple dimensions mein classify karo.

## 5.1 Asset Class

- Cash.
- Equities.
- Bonds.
- Forex.
- Crypto.
- Commodities.
- Indices.
- Futures.
- Options.
- ETFs.
- Other permitted instruments.

## 5.2 Strategy Allocation

- Trend Following.
- Momentum.
- Mean Reversion.
- Breakout.
- Pullback.
- Arbitrage.
- Statistical Trading.
- Long-Term Investment.
- Event-Driven.
- Hedging.

## 5.3 Time Horizon

- Scalping.
- Intraday.
- Swing.
- Positional.
- Long-Term.

## 5.4 Geography

- India.
- United States.
- Europe.
- Asia-Pacific.
- Other regions.

## 5.5 Currency

- INR.
- USD.
- EUR.
- GBP.
- JPY.
- Other currencies.

Exposure classification actual economic risk ke basis par honi chahiye, sirf instrument ke naam par nahi.

---

# 6. PORTFOLIO EXPOSURE ENGINE

Exposure engine portfolio ka actual market risk measure karega.

## 6.1 Gross Exposure

Long aur short exposure ka absolute total:

```text
Gross Exposure =
Sum(Absolute Position Market Values)
```

## 6.2 Net Exposure

```text
Net Exposure =
Long Exposure - Short Exposure
```

Net exposure low hone ka matlab automatically low risk nahi hai.

Long-short portfolio mein basis risk, correlation breakdown aur short squeeze possible hain.

## 6.3 Gross Leverage

Simplified measure:

```text
Gross Leverage = Gross Exposure / Portfolio Equity
```

## 6.4 Net Leverage

```text
Net Leverage = Net Exposure / Portfolio Equity
```

Definitions ko report mein clearly state karo.

## 6.5 Exposure by Asset

Example:

| Asset | Market Value | Portfolio Weight |
|---|---:|---:|
| Equity A | Actual data | Calculated |
| Equity B | Actual data | Calculated |
| Crypto A | Actual data | Calculated |
| Cash | Actual data | Calculated |

Formula:

```text
Portfolio Weight =
Position Value / Portfolio NAV
```

## 6.6 Currency Exposure

Currency risk calculate karte waqt:

- Asset currency.
- Funding currency.
- Revenue currency where relevant.
- Derivative currency exposure.
- Currency hedge.

INR-based portfolio mein USD-denominated assets ka currency exposure separately monitor karo.

## 6.7 Sector Exposure

Possible sectors:

- Banking.
- IT.
- Energy.
- Healthcare.
- Consumer.
- Industrials.
- Financial Services.
- Materials.
- Utilities.
- Real Estate.

Sector classification source and date record karo.

## 6.8 Look-Through Exposure

ETF, mutual fund aur fund holdings ke underlying exposures ko available data ke according break down karo.

Agar holdings unavailable hain, look-through exposure ko `UNKNOWN` label karo.

---

# 7. CAPITAL ALLOCATION METHODS

Engine multiple allocation methods support karega.

## 7.1 Equal Weight Allocation

Har selected asset ko equal portfolio weight.

```text
Weight per Asset = 1 / Number of Assets
```

Example:

5 assets:

```text
Each Weight = 20%
```

Advantages:
- Simple.
- Transparent.
- Easy to rebalance.

Limitations:
- Risk contribution equal nahi hota.
- High-volatility assets portfolio risk dominate kar sakte hain.

## 7.2 Fixed Weight Allocation

User-defined allocation.

Example:

```text
Cash: 20%
Equities: 40%
Forex: 10%
Crypto: 10%
Commodities: 10%
Other: 10%
```

Ye sirf illustrative allocation hai, universal recommendation nahi.

Allocation constraints:

- Minimum weight.
- Maximum weight.
- Cash reserve.
- Asset restrictions.
- Liquidity.
- Risk budget.

## 7.3 Market-Capitalization Weighting

Market capitalization ke basis par portfolio weight.

Risks:

- Largest companies dominate kar sakti hain.
- Valuation risk ignore ho sakta hai.
- Sector concentration develop ho sakti hai.

## 7.4 Risk-Based Allocation

Capital ke bajay risk contribution ke according allocation.

Example:

Low-volatility asset ko larger weight aur high-volatility asset ko smaller weight mil sakta hai.

## 7.5 Volatility Targeting

Portfolio ya individual asset volatility ko defined target ke around manage karo.

Simplified asset weight:

```text
Raw Weight = Target Volatility / Estimated Asset Volatility
```

Then normalize and apply constraints.

Volatility estimate stable aur relevant hona chahiye.

## 7.6 Inverse Volatility Allocation

```text
Raw Weight_i = 1 / Volatility_i

Final Weight_i =
Raw Weight_i / Sum(All Raw Weights)
```

Ye volatility-based allocation hai, complete risk parity nahi.

## 7.7 Risk Parity

Risk parity mein portfolio risk contributions ko balance karne ka objective hota hai.

General form:

```text
Portfolio Variance = w' Σ w
```

Where:

- `w` = Portfolio weight vector.
- `Σ` = Covariance matrix.

Marginal contribution to risk:

```text
MRC_i = (Σw)_i / Portfolio Volatility
```

Risk contribution:

```text
RC_i = w_i × MRC_i
```

Risk parity ka objective selected assets ke risk contributions ko target ke according balance karna hai.

Leverage aur asset correlations ki wajah se risk parity portfolio high gross exposure create kar sakta hai. Risk limits mandatory hain.

## 7.8 Kelly Criterion

Kelly sizing expected growth maximize karne ka mathematical framework hai.

Simple binary-outcome form:

```text
f* = (b × p - q) / b
```

Where:

- `b` = Net payoff ratio.
- `p` = Win probability.
- `q` = Loss probability.
- `f*` = Theoretical optimal fraction.

Limitations:

- Probabilities uncertain hoti hain.
- Returns non-stationary ho sakte hain.
- Estimation errors large impact daal sakte hain.
- Full Kelly severe drawdowns create kar sakta hai.

Fractional Kelly ya capped risk use karne par bhi independent risk approval required hai.

Kelly output ko guaranteed optimal sizing mat samjho.

## 7.9 Mean-Variance Allocation

Objective:

```text
Maximize:
Expected Portfolio Return
- Risk Penalty
```

Standard form:

```text
Maximize:
μ'w - λ(w'Σw)
```

Subject to:

- Weight constraints.
- Long/short restrictions.
- Cash constraints.
- Leverage limits.
- Liquidity limits.
- Turnover limits.

Expected returns aur covariance estimation errors ko account karo.

## 7.10 Minimum Variance Portfolio

Objective:

```text
Minimize w'Σw
```

Subject to portfolio constraints.

Low estimated variance future losses se protection guarantee nahi karta.

## 7.11 Maximum Diversification

Portfolio diversification ratio:

```text
Diversification Ratio =
Weighted Average Asset Volatility
/
Portfolio Volatility
```

Optimization mein practical constraints include karo.

## 7.12 Black-Litterman Framework

Possible inputs:

- Market equilibrium returns.
- Investor views.
- Confidence in views.
- Covariance matrix.
- Prior assumptions.

Investor views uncertain ho sakte hain. Confidence levels explicitly document karo.

---

# 8. ALLOCATION CONSTRAINT ENGINE

Portfolio optimizer ko unrestricted weights generate karne ki permission nahi honi chahiye.

Possible constraints:

- Minimum cash allocation.
- Maximum single-asset weight.
- Maximum sector weight.
- Maximum currency exposure.
- Maximum gross leverage.
- Maximum net leverage.
- Maximum portfolio volatility.
- Maximum expected drawdown.
- Maximum daily loss.
- Minimum liquidity.
- Maximum turnover.
- Restricted instruments.
- User-specific prohibited assets.

Every constraint ka source record karo:

- User-defined.
- Broker-defined.
- Regulatory.
- Strategy-defined.
- System safety rule.

Conflicting constraints hone par optimization fail ya require manual review karna chahiye.

---

# 9. CORRELATION ENGINE

Correlation portfolio diversification ka important component hai.

## 9.1 Pearson Correlation

Linear relationship measure karta hai.

```text
ρ = Cov(X,Y) / (σX × σY)
```

Range:

```text
-1 to +1
```

Interpretation:

- +1: Perfect positive linear relationship.
- 0: No linear correlation.
- -1: Perfect negative linear relationship.

Zero correlation ka matlab independence nahi hota.

## 9.2 Spearman Correlation

Rank-based monotonic relationship measure karta hai.

Nonlinear monotonic relationships identify karne mein useful ho sakta hai.

## 9.3 Kendall Correlation

Rank concordance measure karta hai.

Small samples aur rank relationships ke liye useful ho sakta hai.

## 9.4 Rolling Correlation

Different time windows par correlation calculate karo.

Example:

- 20 periods.
- 60 periods.
- 120 periods.
- 252 periods.

Windows strategy aur data frequency ke according select karo.

## 9.5 Covariance Matrix

Portfolio variance calculate karne ke liye covariance matrix use karo.

Check:

- Matrix symmetry.
- Missing values.
- Positive semidefinite properties.
- Estimation stability.
- Timestamp alignment.

## 9.6 Correlation Breakdown

Stress periods mein historical correlation relationships change ho sakte hain.

Monitor:

- Rolling correlation.
- Tail dependence.
- Volatility spikes.
- Liquidity stress.
- Common macro exposure.

Hedging ke liye stable negative correlation assume mat karo.

## 9.7 Correlation Clustering

Assets ko similarity ke basis par groups mein classify kar sakte ho.

Methods:

- Hierarchical clustering.
- K-means.
- Distance correlation.
- Dynamic correlation models.

Clusters statistical estimates hain, permanent economic relationships nahi.

---

# 10. CONCENTRATION RISK ENGINE

Concentration risk portfolio ke ek asset, sector, currency ya theme mein excessive allocation ko identify karta hai.

## 10.1 Single Asset Concentration

```text
Single Asset Weight =
Asset Exposure / Portfolio NAV
```

## 10.2 Sector Concentration

Total exposure by sector calculate karo.

## 10.3 Currency Concentration

Base currency aur foreign currency exposures aggregate karo.

## 10.4 Top Holdings

Report:

- Top 5 holdings.
- Top 10 holdings.
- Top sector.
- Top currency.
- Top strategy.
- Top correlated cluster.

## 10.5 Herfindahl-Hirschman Index

```text
HHI = Sum(Weight_i²)
```

Weights ko decimal ya percentage convention mein consistently use karo.

Higher HHI generally greater concentration indicate karta hai.

HHI ko standalone risk measure mat samjho.

## 10.6 Effective Number of Holdings

```text
Effective Holdings = 1 / Sum(Weight_i²)
```

Equal-weighted portfolio ke case mein ye actual number of holdings ke equal hota hai.

---

# 11. PORTFOLIO RISK ENGINE

Portfolio risk engine individual position risk ke saath combined portfolio risk calculate karega.

## 11.1 Trade Risk

```text
Trade Risk =
Estimated Loss at Stop
+ Estimated Fees
+ Estimated Slippage
```

## 11.2 Total Open Risk

Simple stop-based approximation:

```text
Total Open Risk =
Sum(Estimated Loss at Each Position Stop)
```

Ye worst-case portfolio loss guarantee nahi karta.

Gaps, slippage, correlation and execution failure actual losses ko larger bana sakte hain.

## 11.3 Portfolio Volatility

```text
σp = sqrt(w'Σw)
```

Returns, weights aur covariance same units aur compatible time horizon mein hone chahiye.

## 11.4 Maximum Drawdown

```text
Drawdown_t =
(Current NAV / Previous Peak NAV) - 1
```

Maximum drawdown = series ka minimum drawdown.

## 11.5 Drawdown Duration

Peak se recovery tak elapsed time measure karo.

## 11.6 Value at Risk

Historical VaR, parametric VaR ya Monte Carlo VaR use kar sakte ho.

VaR specified confidence level aur horizon ke andar loss threshold estimate karta hai.

VaR maximum possible loss nahi hota.

## 11.7 Expected Shortfall

Expected Shortfall, VaR threshold exceed hone par average tail loss estimate karta hai.

Method, confidence level aur horizon report karo.

## 11.8 Stress Risk

Stress testing mein:

- Market crash.
- Volatility spike.
- Correlation convergence.
- Currency shock.
- Liquidity collapse.
- Spread widening.
- Gap risk.
- Exchange outage.
- Broker failure.

Include karo.

---

# 12. RISK BUDGETING

Portfolio ko total risk budget ke according manage karo.

Risk budgets define ho sakte hain:

- Per trade.
- Per asset.
- Per sector.
- Per strategy.
- Per currency.
- Per asset class.
- Daily.
- Weekly.
- Portfolio-wide.

## 12.1 Risk Budget Allocation

Example structure:

```text
Total Portfolio Risk Budget
|
|-- Equity Risk Budget
|-- Forex Risk Budget
|-- Crypto Risk Budget
|-- Commodity Risk Budget
|-- Options Risk Budget
```

Actual percentages user ke risk profile aur verified account data se determine honge.

## 12.2 Risk Budget Consumption

```text
Risk Budget Utilization =
Current Allocated Risk / Allowed Risk Budget
```

## 12.3 Risk Budget Breach

Breach hone par:

- New positions block.
- Existing exposure review.
- Risk reduction candidates identify.
- Alert generate.
- Manual review when required.

Risk budget ko automatically increase mat karo.

---

# 13. MARGIN AND LEVERAGE MANAGEMENT

## 13.1 Margin Utilization

```text
Margin Utilization =
Used Margin / Equity
```

## 13.2 Leverage

```text
Effective Leverage =
Gross Exposure / Equity
```

Broker ka stated maximum leverage aur actual portfolio leverage alag concepts hain.

## 13.3 Margin Buffer

Free margin ko monitor karo.

Stress scenarios mein:

- Price gap.
- Volatility increase.
- Margin requirement increase.
- Currency conversion changes.
- Forced liquidation.

## 13.4 Liquidation Risk

Crypto, futures aur leveraged products mein liquidation thresholds identify karo.

Do not assume stop-loss orders always prevent liquidation.

## 13.5 Emergency Rules

If margin risk exceeds configured safety thresholds:

1. Stop new exposure.
2. Notify user.
3. Recalculate portfolio risk.
4. Identify risk reduction options.
5. Require appropriate approval for live actions.

Automatic forced liquidation actions should not be executed without an explicitly authorized and tested system.

---

# 14. HEDGING ENGINE

Hedging ka objective specific risk reduce karna hai.

Hedge cost, basis risk aur imperfect relationships ko evaluate karna mandatory hai.

## 14.1 Direct Hedge

Same or closely related instrument ke opposite exposure se risk reduce karna.

## 14.2 Cross-Asset Hedge

Related instrument ke through exposure hedge karna.

Cross-asset relationship unstable ho sakta hai.

## 14.3 Currency Hedge

Foreign currency exposure ko forward, futures ya other permitted instruments se manage karna.

## 14.4 Futures Hedge

Underlying portfolio exposure ko index ya commodity futures se partially hedge karna.

Consider:

- Contract multiplier.
- Expiry.
- Basis.
- Rollover.
- Margin.
- Tracking error.

## 14.5 Options Hedge

Possible structures:

- Protective Put.
- Collar.
- Put Spread.
- Call Spread.
- Other defined-risk structures.

Calculate:

- Premium.
- Greeks.
- Expiry.
- Strike.
- Breakeven.
- Maximum loss.
- Assignment risk.

## 14.6 Hedge Ratio

Basic minimum-variance hedge ratio:

```text
h* = Cov(Spot Change, Hedge Change)
     /
     Var(Hedge Change)
```

Actual hedge quantity requires instrument contract specifications and currency conversion.

## 14.7 Hedge Effectiveness

Compare:

- Unhedged risk.
- Hedged risk.
- Hedge cost.
- Residual risk.
- Basis risk.
- Tail behaviour.

A hedge can reduce some risks while creating new risks.

## 14.8 Over-Hedging

Net exposure reverse direction mein ja sakta hai.

Always calculate resulting portfolio exposure after hedge.

---

# 15. PORTFOLIO REBALANCING ENGINE

Rebalancing ka purpose portfolio ko target allocation ke paas maintain karna hai.

## 15.1 Calendar Rebalancing

- Daily.
- Weekly.
- Monthly.
- Quarterly.

Frequency asset liquidity, transaction costs aur strategy horizon ke according choose karo.

## 15.2 Threshold Rebalancing

Rebalance when actual weight target se defined tolerance exceed kare.

Example:

```text
Target Weight: 20%
Allowed Deviation: 5 Percentage Points
```

Ye illustrative threshold hai.

## 15.3 Drift Calculation

```text
Weight Drift =
Actual Weight - Target Weight
```

## 15.4 Volatility-Based Rebalancing

Volatility changes ke basis par target risk adjust karo.

## 15.5 Risk-Based Rebalancing

Risk contribution target se significantly deviate hone par review karo.

## 15.6 Rebalancing Costs

Calculate:

- Brokerage.
- Exchange charges.
- Taxes.
- Spread.
- Slippage.
- Market impact.
- Funding cost.
- Currency conversion cost.

India-specific statutory charges and applicable taxes ko current verified rules ke according calculate karo.

## 15.7 Tax-Aware Rebalancing

When relevant, include:

- Holding period.
- Capital gains.
- Tax lots.
- Realized gains.
- Loss harvesting restrictions.
- Applicable tax rules.

Tax calculations ke liye current jurisdiction-specific rules verify karna mandatory hai.

## 15.8 Rebalancing Decision

Possible actions:

- BUY.
- SELL.
- REDUCE.
- HOLD.
- REBALANCE.
- WAIT.

Do not rebalance only because a target weight changed by a tiny amount if costs outweigh the benefit.

---

# 16. PORTFOLIO PERFORMANCE ATTRIBUTION

Portfolio performance ko meaningful sources mein break down karo.

## 16.1 Asset Attribution

Asset-wise contribution.

## 16.2 Sector Attribution

Sector-wise returns and risk contribution.

## 16.3 Strategy Attribution

Strategy-wise P&L.

## 16.4 Currency Attribution

Underlying asset return aur FX translation impact separate karo.

## 16.5 Allocation Attribution

Allocation decisions se performance contribution.

## 16.6 Selection Attribution

Asset selection se contribution.

## 16.7 Trading Cost Attribution

Fees, spread, slippage and financing.

## 16.8 Benchmark Comparison

Benchmark select karo jo portfolio objective ke saath relevant ho.

Example:

- Indian equity portfolio: suitable Indian equity benchmark.
- Global equity portfolio: relevant global index.
- Crypto portfolio: appropriate crypto benchmark.

Benchmark mismatch se misleading performance conclusions avoid karo.

---

# 17. PORTFOLIO PERFORMANCE METRICS

Calculate:

### Return
- Total Return.
- Time-Weighted Return.
- Money-Weighted Return.
- CAGR.
- Annualized Return.
- Monthly Return.
- Rolling Return.

### Risk
- Standard Deviation.
- Maximum Drawdown.
- Drawdown Duration.
- VaR.
- Expected Shortfall.
- Downside Deviation.
- Beta.

### Risk-Adjusted Performance
- Sharpe Ratio.
- Sortino Ratio.
- Calmar Ratio.
- Information Ratio.
- Treynor Ratio.

### Trading Performance
- Win Rate.
- Profit Factor.
- Expectancy.
- Average R.
- Turnover.
- Trade Frequency.

### Stability
- Rolling Performance.
- Regime-Specific Performance.
- Asset Contribution.
- Strategy Contribution.
- Out-of-Sample Results.

Har metric ka calculation method, timeframe aur return frequency state karo.

---

# 18. PORTFOLIO STRATEGY TYPES

## 18.1 Long-Only Portfolio

Only long positions.

Consider:

- Market beta.
- Sector concentration.
- Cash allocation.
- Drawdown.
- Benchmark tracking.

## 18.2 Long/Short Portfolio

Long and short positions.

Consider:

- Gross exposure.
- Net exposure.
- Borrow availability.
- Borrow costs.
- Short squeeze.
- Margin.
- Rebate.
- Hedge mismatch.

## 18.3 Multi-Asset Portfolio

Combine:

- Equity.
- Bonds.
- Cash.
- Commodities.
- Forex.
- Crypto.
- Other instruments.

Cross-asset correlations and risk units must be compatible.

## 18.4 Multi-Strategy Portfolio

Multiple trading strategies combine karo.

Check:

- Signal correlation.
- Return correlation.
- Drawdown overlap.
- Execution overlap.
- Shared risk factors.

## 18.5 Tactical Allocation

Market conditions ke according portfolio weights change karna.

Requires:

- Defined rules.
- Validated signals.
- Turnover controls.
- Risk constraints.

## 18.6 Strategic Allocation

Long-term target weights maintain karna.

---

# 19. MARKET-SPECIFIC PORTFOLIO RULES

## 19.1 Indian Stocks

Consider:

- NSE/BSE.
- Cash and F&O exposure.
- Sector concentration.
- Market lot.
- Circuit limits.
- Liquidity.
- Corporate actions.
- Earnings.
- INR exposure.
- Brokerage and statutory charges.
- Applicable regulations.

## 19.2 Global Stocks

Consider:

- Country exposure.
- Currency risk.
- Sector allocation.
- Earnings concentration.
- Market hours.
- Overnight gaps.
- Custody and settlement.

## 19.3 Forex

Consider:

- Currency pairs.
- Currency factor exposure.
- USD concentration.
- Interest-rate sensitivity.
- Rollover.
- Broker margin.
- Session liquidity.
- Correlated currency positions.

Currency exposure ko pair-wise positions se aggregate karo.

Example:

Multiple USD pairs ek common USD exposure create kar sakte hain.

## 19.4 Crypto

Consider:

- Exchange concentration.
- Stablecoin exposure.
- Token concentration.
- Exchange counterparty risk.
- Custody risk.
- Funding.
- Open interest.
- Liquidation.
- 24/7 market.
- Chain and protocol risks.

Different tokens ko automatically diversified assets mat samjho.

## 19.5 Indices

Consider:

- Constituent overlap.
- Sector concentration.
- Futures basis.
- Index options.
- Tracking error.
- Market breadth.

## 19.6 Futures

Consider:

- Expiry.
- Rollover.
- Contract multiplier.
- Tick value.
- Initial margin.
- Maintenance margin.
- Delivery.
- Contango/backwardation.

## 19.7 Commodities

Consider:

- Supply-demand.
- Inventory.
- Seasonal exposure.
- Futures curve.
- Storage.
- Delivery.
- Currency exposure.
- Geopolitical shocks.

## 19.8 Options

Consider:

- Delta exposure.
- Gamma exposure.
- Vega exposure.
- Theta decay.
- Rho.
- Expiry concentration.
- Strike concentration.
- Open interest.
- Assignment risk.
- Exercise style.

Option positions ko sirf premium value se measure mat karo. Underlying exposure aur Greeks bhi aggregate karo.

---

# 20. OPTIONS PORTFOLIO GREEKS

## 20.1 Delta

Underlying price ke change ke against approximate option price sensitivity.

## 20.2 Gamma

Delta ki sensitivity to underlying price.

## 20.3 Vega

Implied volatility sensitivity.

## 20.4 Theta

Time decay sensitivity.

## 20.5 Rho

Interest-rate sensitivity.

Portfolio-level Greeks aggregate karo.

Different expiries, currencies aur contract multipliers ko correctly normalize karo.

## 20.6 Scenario Greeks

Large price moves aur volatility changes ke liye Greeks approximate results de sakte hain.

Nonlinear options exposure ke liye full repricing stress tests use karo.

---

# 21. PORTFOLIO STRESS TESTING

Stress test portfolio ko extreme conditions mein evaluate karta hai.

## 21.1 Historical Stress

Relevant historical episodes replay karo.

## 21.2 Hypothetical Stress

Examples:

- Equity index falls sharply.
- INR depreciates.
- USD strengthens.
- Crypto falls sharply.
- Oil prices spike.
- Volatility doubles.
- Correlations increase.
- Liquidity falls.
- Spreads widen.
- Broker margin rises.

Stress magnitudes illustrative assumptions hain, forecasts nahi.

## 21.3 Combined Stress

Simultaneously multiple shocks apply karo.

Example:

- Equity down.
- Currency adverse.
- Volatility up.
- Correlation converges.
- Liquidity down.

## 21.4 Reverse Stress Test

Find karo ki kaunsa shock portfolio ko defined loss or margin threshold breach tak le ja sakta hai.

## 21.5 Stress Test Report

```text
Scenario:
Assumptions:
Positions Affected:
Estimated Portfolio P&L:
Estimated Drawdown:
Margin Impact:
Liquidity Impact:
Largest Risk Contributor:
Model Limitations:
```

---

# 22. MONTE CARLO PORTFOLIO SIMULATION

Possible approaches:

- Historical return bootstrap.
- Block bootstrap.
- Parametric simulation.
- Multivariate simulation.
- Regime-switching simulation.
- Volatility model simulation.
- Correlation stress.
- Randomized execution costs.

Preserve temporal dependence where necessary.

Report:

- Median outcome.
- Percentile outcomes.
- Drawdown distribution.
- Loss probability under model.
- Expected Shortfall.
- Margin breach frequency.
- Ruin assumptions.

Simulation results are conditional on model assumptions, not future guarantees.

---

# 23. 10 MILLION SCENARIO TESTING FRAMEWORK

Target: 10,000,000 distinct portfolio scenarios.

This is an engineering target. It is not a claim that 10 million scenarios have already been executed.

## 23.1 Scenario Dimensions

- Asset allocation.
- Asset universe.
- Portfolio weights.
- Strategy mix.
- Correlation matrix.
- Volatility.
- Market regime.
- Return distribution.
- Currency shock.
- Interest-rate shock.
- Liquidity shock.
- Spread.
- Slippage.
- Fees.
- Leverage.
- Margin.
- Rebalancing frequency.
- Hedge ratio.
- Position sizing.
- Drawdown.
- Market gap.
- Execution delay.
- Tail events.

## 23.2 Scenario Categories

1. Historical portfolio replay.
2. Asset allocation combinations.
3. Correlation stress scenarios.
4. Volatility stress scenarios.
5. Currency shock scenarios.
6. Interest-rate shock scenarios.
7. Liquidity stress scenarios.
8. Leverage and margin scenarios.
9. Rebalancing scenarios.
10. Hedging scenarios.
11. Monte Carlo portfolio paths.
12. Regime-switching simulations.
13. Transaction cost scenarios.
14. Cross-asset scenarios.
15. Options Greek scenarios.
16. Portfolio drawdown scenarios.
17. Risk budget scenarios.
18. Reverse stress scenarios.

## 23.3 Scenario Integrity

Every scenario should have:

- Unique ID.
- Unique hash.
- Input parameters.
- Random seed if applicable.
- Model version.
- Data version.
- Scenario type.
- Execution status.
- Result.
- Validation status.

## 23.4 Scenario Record

```text
scenario_id
scenario_hash
portfolio_id
portfolio_version
asset_universe
weights
market_regime
volatility_assumption
correlation_assumption
currency_shocks
liquidity_assumptions
execution_costs
leverage
margin
hedge_ratio
rebalancing_rule
scenario_type
random_seed
portfolio_return
maximum_drawdown
margin_breach
execution_status
timestamp
```

## 23.5 Completion Report

```text
Target Scenarios: 10,000,000
Executed: Actual Count
Unique: Verified Count
Failed: Actual Count
Skipped: Actual Count
Historical: Actual Count
Synthetic: Actual Count
Monte Carlo: Actual Count
Stress: Actual Count
Completed: Actual Status
Model Version: Actual Version
Results Location: Actual Location
```

Never fabricate executed counts.

A parameter combination is not automatically an independent historical observation.

Synthetic returns are not real historical performance.

---

# 24. PYTHON PORTFOLIO DATA MODEL

```python
from dataclasses import dataclass, field
from typing import Optional, List

@dataclass
class Position:
    instrument: str
    asset_class: str
    side: str
    quantity: float
    mark_price: float
    currency: str
    multiplier: float = 1.0
    strategy_id: Optional[str] = None

@dataclass
class Portfolio:
    portfolio_id: str
    base_currency: str
    equity: float
    cash: float
    positions: List[Position] = field(
        default_factory=list
    )

@dataclass
class AllocationResult:
    weights: dict
    method: str
    constraints_passed: bool
    warnings: List[str] = field(
        default_factory=list
    )
```

Production implementation mein currency conversion, contract specifications, liabilities, fees and margin separately model karo.

---

# 25. PYTHON PORTFOLIO EXPOSURE CALCULATOR

```python
def position_market_value(position, fx_rate=1.0):
    if position.quantity < 0:
        raise ValueError("Use side to represent direction")

    if position.mark_price <= 0:
        raise ValueError("Invalid mark price")

    if position.multiplier <= 0:
        raise ValueError("Invalid contract multiplier")

    return (
        position.quantity
        * position.mark_price
        * position.multiplier
        * fx_rate
    )


def calculate_exposure(positions, fx_rates):
    long_exposure = 0.0
    short_exposure = 0.0

    for position in positions:
        fx = fx_rates.get(position.currency)

        if fx is None or fx <= 0:
            raise ValueError(
                f"Missing or invalid FX rate: {position.currency}"
            )

        value = position_market_value(
            position,
            fx
        )

        if position.side.upper() == "LONG":
            long_exposure += value

        elif position.side.upper() == "SHORT":
            short_exposure += value

        else:
            raise ValueError("Invalid position side")

    gross = long_exposure + short_exposure
    net = long_exposure - short_exposure

    return {
        "long_exposure": long_exposure,
        "short_exposure": short_exposure,
        "gross_exposure": gross,
        "net_exposure": net
    }
```

Production system mein futures, options, swaps aur nonlinear exposures ke liye instrument-specific risk models required hain.

---

# 26. PYTHON PORTFOLIO WEIGHT CALCULATOR

```python
def calculate_weights(position_values, nav):
    if nav <= 0:
        raise ValueError("NAV must be positive")

    weights = {}

    for asset, value in position_values.items():
        weights[asset] = value / nav

    return weights
```

Short positions ke signed weights separately represent karo.

Gross absolute weights aur net signed weights ko confuse mat karo.

---

# 27. PYTHON CORRELATION ENGINE

```python
import pandas as pd

def calculate_correlation(returns):
    if returns.empty:
        raise ValueError("Returns data is empty")

    if returns.isna().any().any():
        raise ValueError(
            "Missing return observations"
        )

    return {
        "pearson": returns.corr(
            method="pearson"
        ),
        "spearman": returns.corr(
            method="spearman"
        ),
        "covariance": returns.cov()
    }


def rolling_correlation(
    returns,
    asset_a,
    asset_b,
    window=60
):
    if window <= 1:
        raise ValueError("Window must exceed 1")

    return (
        returns[asset_a]
        .rolling(window)
        .corr(returns[asset_b])
    )
```

All assets ka timestamp alignment aur return frequency consistent hona chahiye.

Missing data ko silently forward-fill mat karo.

---

# 28. PYTHON PORTFOLIO VOLATILITY

```python
import numpy as np

def portfolio_volatility(weights, covariance):
    weights = np.asarray(
        weights,
        dtype=float
    )

    covariance = np.asarray(
        covariance,
        dtype=float
    )

    if covariance.shape != (
        len(weights),
        len(weights)
    ):
        raise ValueError(
            "Covariance dimension mismatch"
        )

    variance = weights @ covariance @ weights

    if variance < -1e-10:
        raise ValueError(
            "Invalid negative portfolio variance"
        )

    return float(np.sqrt(max(variance, 0.0)))
```

Annualization ke liye data frequency ke according correct scaling apply karo.

---

# 29. PYTHON RISK CONTRIBUTION

```python
import numpy as np

def risk_contributions(weights, covariance):
    weights = np.asarray(
        weights,
        dtype=float
    )

    covariance = np.asarray(
        covariance,
        dtype=float
    )

    variance = weights @ covariance @ weights

    if variance <= 0:
        raise ValueError(
            "Portfolio variance must be positive"
        )

    volatility = np.sqrt(variance)

    marginal = (
        covariance @ weights
    ) / volatility

    contributions = weights * marginal

    return {
        "portfolio_volatility": float(volatility),
        "marginal_contributions": marginal.tolist(),
        "risk_contributions": contributions.tolist()
    }
```

Short positions ke negative risk contributions possible hain. Interpretation carefully karo.

---

# 30. PYTHON DRAWDOWN ENGINE

```python
import pandas as pd

def calculate_drawdown(nav_series):
    if nav_series.empty:
        raise ValueError("NAV series is empty")

    if (nav_series <= 0).any():
        raise ValueError(
            "NAV must be positive"
        )

    running_peak = nav_series.cummax()

    drawdown = (
        nav_series / running_peak
    ) - 1

    return {
        "drawdown_series": drawdown,
        "maximum_drawdown": float(
            drawdown.min()
        )
    }
```

NAV series ko external cash flows ke liye appropriately adjust karo.

---

# 31. PYTHON ALLOCATION VALIDATION

```python
def validate_weights(
    weights,
    minimum=0.0,
    maximum=1.0,
    tolerance=1e-8
):
    if not weights:
        return False, ["No weights supplied"]

    errors = []

    for asset, weight in weights.items():
        if not minimum <= weight <= maximum:
            errors.append(
                f"Weight out of range: {asset}"
            )

    total = sum(weights.values())

    if abs(total - 1.0) > tolerance:
        errors.append(
            "Weights do not sum to 1"
        )

    return len(errors) == 0, errors
```

Long-only portfolio ke liye ye simplified validator hai. Long/short portfolios ko separate constraints chahiye.

---

# 32. PYTHON PORTFOLIO RISK LIMITS

```python
def check_portfolio_limits(
    equity,
    gross_exposure,
    daily_loss,
    max_gross_leverage,
    max_daily_loss
):
    if equity <= 0:
        return {
            "approved": False,
            "reason": "Invalid equity"
        }

    leverage = gross_exposure / equity

    if leverage > max_gross_leverage:
        return {
            "approved": False,
            "reason": "Gross leverage limit exceeded"
        }

    if daily_loss >= max_daily_loss:
        return {
            "approved": False,
            "reason": "Daily loss limit reached"
        }

    return {
        "approved": True,
        "leverage": leverage
    }
```

Ye educational example hai. Production risk approval ko pending orders, open risk, margin, gaps and instrument-specific exposures bhi evaluate karne honge.

---

# 33. PYTHON REBALANCING ENGINE

```python
def calculate_rebalance_orders(
    current_weights,
    target_weights,
    nav,
    tolerance=0.05
):
    if nav <= 0:
        raise ValueError("NAV must be positive")

    orders = []

    all_assets = set(current_weights) | set(
        target_weights
    )

    for asset in all_assets:
        current = current_weights.get(asset, 0.0)
        target = target_weights.get(asset, 0.0)

        drift = target - current

        if abs(drift) >= tolerance:
            orders.append({
                "asset": asset,
                "current_weight": current,
                "target_weight": target,
                "drift": drift,
                "estimated_value_change": drift * nav
            })

    return orders
```

Real execution se pehle transaction costs, minimum order size, taxes, liquidity and portfolio constraints apply karo.

---

# 34. PORTFOLIO OPTIMIZATION ENGINE

Possible optimization methods:

1. Equal Weight.
2. Inverse Volatility.
3. Risk Parity.
4. Minimum Variance.
5. Mean-Variance.
6. Maximum Sharpe.
7. Maximum Diversification.
8. Black-Litterman.
9. Risk Budgeting.
10. Volatility Targeting.

Optimization requirements:

- Valid covariance matrix.
- Expected return assumptions.
- Weight constraints.
- Leverage constraints.
- Turnover constraints.
- Transaction costs.
- Liquidity constraints.
- Currency conversion.
- Minimum cash.
- Position restrictions.

## 34.1 Optimization Failure

If:

- Matrix invalid.
- Data insufficient.
- Constraints infeasible.
- Solver fails.
- Output contains invalid weights.
- Expected return assumptions missing.

Then do not silently use optimizer output.

Return `OPTIMIZATION_FAILED` and explain the reason.

## 34.2 Parameter Stability

Test whether small changes in:

- Expected returns.
- Covariance.
- Volatility.
- Constraints.

Cause large allocation changes.

Unstable solutions require caution.

---

# 35. PERFORMANCE ATTRIBUTION IMPLEMENTATION

Build attribution at:

- Asset level.
- Sector level.
- Strategy level.
- Currency level.
- Allocation level.
- Trading cost level.

Use consistent return attribution methods.

For multi-period attribution, compounding effects must be handled correctly.

Do not simply add incompatible percentage returns across periods.

---

# 36. PORTFOLIO MONITORING ENGINE

Monitor:

- NAV.
- Equity.
- Cash.
- Gross exposure.
- Net exposure.
- Leverage.
- Margin utilization.
- Free margin.
- Portfolio volatility.
- Maximum drawdown.
- Risk budget consumption.
- Concentration.
- Correlation.
- Open positions.
- Pending orders.
- Liquidity.
- Currency exposure.
- Strategy performance.

## 36.1 Alert Levels

Possible alert categories:

- INFO.
- WARNING.
- HIGH RISK.
- CRITICAL.
- DATA FAILURE.

Thresholds must be configured and tested.

## 36.2 Alert Examples

- Single asset concentration exceeded.
- Sector exposure too high.
- Gross leverage exceeded.
- Daily loss limit reached.
- Correlation breakdown.
- Margin buffer reduced.
- Market data stale.
- Broker positions mismatch.
- Portfolio drawdown exceeded.
- Hedge effectiveness deteriorated.

---

# 37. PORTFOLIO EMERGENCY PROTECTION

Emergency conditions:

1. Account data mismatch.
2. Broker API unavailable.
3. Duplicate orders.
4. Margin risk critical.
5. Daily loss limit breached.
6. Unexpected leverage.
7. Uncontrolled exposure.
8. Price feed failure.
9. Currency conversion failure.
10. Portfolio reconciliation failure.

Possible system actions:

- Block new orders.
- Disable automated allocation.
- Generate critical alert.
- Reconcile broker positions.
- Recalculate exposure.
- Require manual review.
- Activate pre-authorized risk controls.

**Important:** Emergency liquidation or live order cancellation must follow explicitly configured permissions and broker-specific procedures. Never assume an order was cancelled without confirmation.

---

# 38. PORTFOLIO RECONCILIATION

Regularly compare internal portfolio records with broker/exchange records.

Reconcile:

- Positions.
- Quantities.
- Average prices.
- Open orders.
- Executed trades.
- Fees.
- Funding.
- Dividends.
- Corporate actions.
- Margin.
- Cash.
- Realized P&L.
- Unrealized P&L.

Unresolved mismatch hone par new allocation decisions block karo.

---

# 39. DATABASE AND AUDIT ARCHITECTURE

Suggested tables:

```text
accounts
portfolios
positions
pending_orders
closed_trades
assets
asset_metadata
market_prices
fx_rates
corporate_actions
portfolio_weights
target_allocations
risk_limits
risk_measurements
correlation_snapshots
allocation_runs
rebalance_orders
hedges
stress_tests
monte_carlo_runs
performance_attribution
alerts
audit_logs
model_versions
```

Every important decision should record:

- Timestamp.
- Portfolio version.
- Input snapshot.
- Data source.
- Calculation version.
- Risk constraints.
- Output.
- Warnings.
- Approval status.

Sensitive credentials and secrets should never appear in audit logs.

---

# 40. DATA SOURCES AND INTEGRATION

Possible data categories:

- Broker account data.
- Exchange market data.
- Historical OHLCV.
- Corporate actions.
- FX rates.
- Futures specifications.
- Options chains.
- Interest rates.
- Economic calendar.
- Portfolio benchmarks.
- Liquidity information.

Before use, verify:

- Source identity.
- Update frequency.
- Data licensing.
- Market coverage.
- Timestamp.
- Timezone.
- Missing observations.
- Reliability.

Never claim live portfolio access unless a connector is actually connected and verified.

---

# 41. API AND AUTOMATION SECURITY

Security requirements:

1. API keys environment variables mein store karo.
2. Credentials GitHub repository mein commit mat karo.
3. Read-only permissions prefer karo for analysis.
4. Trading permissions separately control karo.
5. Withdrawal permissions avoid karo.
6. Test and live environments separate rakho.
7. Rate limits respect karo.
8. Validate all API responses.
9. Use secure transport.
10. Keep audit logs.
11. Rotate credentials when required.
12. Apply least-privilege access.
13. Require explicit authorization for live trading actions.
14. Reconcile every order response.
15. Handle retries without duplicate orders.

---

# 42. PORTFOLIO DECISION ENGINE

Portfolio decisions:

- ADD.
- REDUCE.
- HOLD.
- REBALANCE.
- HEDGE.
- CLOSE.
- WAIT.
- BLOCKED.

## 42.1 ADD

Add exposure only when:

- Target allocation permits.
- Strategy or investment thesis remains valid.
- Risk budget is available.
- Concentration remains acceptable.
- Liquidity is sufficient.
- Execution costs are acceptable.

## 42.2 REDUCE

Reduce when:

- Exposure exceeds limits.
- Risk contribution becomes excessive.
- Thesis weakens.
- Correlation rises.
- Drawdown rules trigger.
- Margin buffer becomes inadequate.

## 42.3 HOLD

Hold when:

- Portfolio remains within constraints.
- Existing exposure is justified.
- Rebalancing benefit does not exceed cost.

## 42.4 REBALANCE

Rebalance when:

- Target drift exceeds threshold.
- Risk contribution deviates.
- Strategic allocation changes.
- Constraints require adjustment.

## 42.5 HEDGE

Hedge only when:

- Specific risk is identified.
- Hedge instrument is suitable.
- Hedge cost is understood.
- Residual basis risk is acceptable.
- Portfolio-level benefit is demonstrated.

## 42.6 CLOSE

Close when:

- Position thesis invalidated.
- Risk limit requires exit.
- Instrument is no longer suitable.
- Portfolio rules require removal.

## 42.7 WAIT

Wait when:

- Data is incomplete.
- Market conditions are uncertain.
- Allocation benefit is unclear.
- Execution is poor.

## 42.8 BLOCKED

Block portfolio action when:

- Risk controls fail.
- Account reconciliation fails.
- Critical data is missing.
- Permissions are unavailable.
- Constraints are infeasible.

---

# 43. PORTFOLIO APPROVAL GATE

Before generating an actionable allocation recommendation:

```text
1. IS ACCOUNT DATA VALID?
   NO -> BLOCKED

2. ARE ALL POSITIONS RECONCILED?
   NO -> BLOCKED

3. ARE MARKET PRICES CURRENT?
   NO -> BLOCKED

4. IS CURRENCY CONVERSION VALID?
   NO -> BLOCKED

5. ARE EXPOSURES CALCULATED?
   NO -> BLOCKED

6. ARE CORRELATIONS AVAILABLE?
   NO -> WARN / BLOCKED AS REQUIRED

7. ARE RISK LIMITS DEFINED?
   NO -> BLOCKED

8. DOES ALLOCATION SATISFY CONSTRAINTS?
   NO -> REJECT

9. ARE MARGIN AND LIQUIDITY ACCEPTABLE?
   NO -> BLOCKED

10. ARE COSTS ESTIMATED?
    NO -> WARN / BLOCKED

11. DOES PORTFOLIO STRESS TEST PASS?
    NO -> REVIEW / REJECT

12. IS ACTION AUTHORIZED?
    NO -> RECOMMENDATION ONLY

13. ALL REQUIRED CHECKS PASS?
    YES -> ACTION CANDIDATE
```

An allocation recommendation is not authorization to execute a live order.

---

# 44. STANDARD PORTFOLIO REPORT

Every complete portfolio analysis should use this format.

## A. Account Overview

- Base Currency:
- Account Balance:
- Equity:
- Cash:
- Used Margin:
- Free Margin:
- Unrealized P&L:
- Realized P&L:
- Data Timestamp:

### B. Portfolio Allocation

| Asset | Current Weight | Target Weight | Drift |
|---|---:|---:|---:|
| Actual asset | Calculated | Configured | Calculated |

### C. Exposure

- Gross Exposure:
- Net Exposure:
- Gross Leverage:
- Net Leverage:
- Currency Exposure:
- Sector Exposure:
- Strategy Exposure:

### D. Risk

- Portfolio Volatility:
- Maximum Drawdown:
- Open Risk:
- Margin Utilization:
- VaR:
- Expected Shortfall:
- Largest Risk Contributor:

### E. Correlation

- Highest Correlated Positions:
- Correlation Clusters:
- Correlation Changes:
- Diversification Concerns:

### F. Performance

- Total Return:
- Benchmark Return:
- Sharpe:
- Sortino:
- Profit Factor:
- Strategy Contribution:
- Trading Costs:

### G. Recommended Actions

| Instrument | Action | Reason | Risk Impact |
|---|---|---|---|
| Actual instrument | ADD / REDUCE / HOLD / HEDGE | Evidence | Calculated |

### H. Final Decision

- ADD / REDUCE / HOLD / REBALANCE / HEDGE / CLOSE / WAIT / BLOCKED
- Reason:
- Key Risk:
- Required Confirmation:
- Data Limitations:

### I. Simple Hinglish Explanation

Explain:

- Portfolio ki current condition.
- Sabse bada risk.
- Capital kahan concentrated hai.
- Diversification sufficient hai ya nahi.
- Kya change recommended hai.
- Recommendation ke peeche reasoning.

---

# 45. USER INTERACTION RULES

## User: "Mera portfolio analyse karo"

Ask for or use connected account data. If unavailable, request holdings and relevant account information.

Never assume holdings.

## User: "Mere paise kahan invest karun?"

Clarify:

- Investment horizon.
- Risk tolerance.
- Capital.
- Liquidity requirements.
- Relevant market and jurisdiction.

Do not promise returns.

## User: "Portfolio ko diversify karo"

Analyse actual underlying risk, not just number of holdings.

## User: "Best allocation batao"

Explain assumptions and compare multiple methods.

Do not present optimizer output as guaranteed best allocation.

## User: "Risk kam karo"

Identify largest risk contributors and evaluate reduction, hedging and reallocation.

## User: "Hedge kar do"

Explain hedge instrument, cost, residual risk and required authorization. Do not execute without explicit permission.

## User: "1 crore baar test karo"

Explain actual compute and data availability. Report executed scenario counts only after verified execution.

---

# 46. TESTING AND QUALITY ASSURANCE

Test the following:

1. Empty portfolio.
2. Invalid NAV.
3. Negative asset quantity.
4. Invalid mark price.
5. Missing FX rate.
6. Incorrect contract multiplier.
7. Duplicate positions.
8. Missing asset metadata.
9. Stale market price.
10. Inconsistent timestamps.
11. Incorrect position direction.
12. Invalid allocation weights.
13. Weights not summing correctly.
14. Correlation matrix mismatch.
15. Singular covariance matrix.
16. Non-positive-semidefinite covariance.
17. Excessive leverage.
18. Margin breach.
19. Risk budget breach.
20. Concentration breach.
21. Missing open orders.
22. Incorrect pending-order exposure.
23. Rebalancing cost error.
24. Hedge overexposure.
25. Currency conversion failure.
26. Corporate action mismatch.
27. Options Greek aggregation error.
28. Futures expiry mismatch.
29. Portfolio reconciliation failure.
30. API timeout.
31. Duplicate API response.
32. Optimizer infeasible constraints.
33. Monte Carlo reproducibility.
34. Stress test failure.
35. Drawdown calculation error.

Invalid input ko silently accept mat karo.

---

# 47. REFERENCE INTEGRATION

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
- strategy-selection-engine.md

Responsibilities:

- Strategy Selection Engine identifies trade candidates.
- Risk Management Engine calculates individual trade risk.
- Portfolio Engine combines exposures and portfolio-level risk.
- Backtesting Engine validates portfolio strategies.
- Trade Management Engine monitors approved positions.
- Market Regime Engine identifies changing market conditions.
- News and Fundamental modules supply event and asset context.

Portfolio-level risk approval must not be replaced by individual trade approval.

---

# 48. FINAL OPERATING RULES

1. Always use current, validated account data.
2. Never invent holdings.
3. Never invent portfolio equity.
4. Never invent market prices.
5. Never assume broker margin rules.
6. Never assume currency conversion rates.
7. Never ignore pending orders.
8. Never ignore transaction costs.
9. Never ignore correlated exposure.
10. Never assume different tickers mean diversification.
11. Never confuse net exposure with total risk.
12. Never treat VaR as maximum possible loss.
13. Never treat historical correlation as permanent.
14. Never assume hedges are perfect.
15. Never ignore leverage.
16. Never ignore liquidation risk.
17. Never optimize without constraints.
18. Never hide optimization failures.
19. Never hide negative stress results.
20. Never fabricate Monte Carlo results.
21. Never claim 10 million scenarios were executed without evidence.
22. Always distinguish historical and synthetic scenarios.
23. Always document allocation assumptions.
24. Always track strategy and model versions.
25. Always monitor concentration.
26. Always monitor portfolio drawdown.
27. Always reconcile broker positions.
28. Always use least-privilege API access.
29. Require explicit authorization for live actions.
30. Prefer WAIT when data is insufficient.
31. Prefer BLOCKED when critical controls fail.
32. Explain portfolio recommendations in natural Hinglish.
33. Explain complex financial terms in simple language.
34. Never guarantee returns.
35. Capital protection and honest risk reporting take priority over return targets.

---

# 49. CORE PRINCIPLE

Portfolio Management Engine ka purpose maximum number of trades open karna nahi hai.

Iska purpose hai:

- Capital ka disciplined allocation.
- Risk ka measurement.
- Concentration ka control.
- Correlated exposures ki identification.
- Diversification ka assessment.
- Portfolio volatility ka management.
- Margin aur leverage control.
- Hedging aur rebalancing decisions.
- Realistic stress testing.
- Performance attribution.
- Capital protection.

**FINAL RULE:**

Agar portfolio data unreliable hai, constraints fail hain, margin unsafe hai ya risk accurately measure nahi ho raha, to system ko allocation approve nahi karna chahiye.

Best portfolio decision kabhi-kabhi koi nayi position na lena bhi hota hai.
