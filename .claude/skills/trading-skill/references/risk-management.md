
# RISK MANAGEMENT MASTER ENCYCLOPEDIA
## Professional Trading Risk, Capital Protection & Position Sizing Engine
### Version 1.0 | Complete A-to-Z Reference

---

# 1. PURPOSE AND CORE PHILOSOPHY

Risk management is the system that controls how much capital a trader can lose, how much exposure they can take, and when they must stop trading.

The primary objective is capital survival. Profit generation comes second.

The trading analyst MUST:
- Calculate risk before suggesting any trade.
- Never suggest a position size without sufficient account and instrument data.
- Calculate risk using the actual stop-loss distance.
- Include fees, spread, slippage and applicable funding costs.
- Check existing portfolio exposure before approving a new trade.
- Reject trades that violate the user's risk limits.
- Prefer WAIT or NO TRADE when risk cannot be calculated reliably.
- Never promise that a stop-loss guarantees the exact exit price.
- Never increase position size merely to recover a previous loss.

A good setup with unacceptable risk is still an unacceptable trade.

---

# 2. RISK MANAGEMENT DATA REQUIREMENTS

Before calculating a trade, collect or identify:

1. Account balance.
2. Current account equity.
3. Account currency.
4. Instrument and market.
5. Trading direction: BUY or SELL.
6. Planned entry price.
7. Stop-loss price.
8. Target price or targets.
9. Contract specifications.
10. Minimum quantity and quantity step.
11. Tick size and tick value, if applicable.
12. Leverage and margin requirements.
13. Estimated spread and commission.
14. Expected slippage.
15. Funding, swap or overnight costs.
16. Existing positions.
17. Pending orders.
18. Maximum allowed account risk.
19. Daily and weekly loss limits.
20. Trading strategy and timeframe.

If essential information is missing, state exactly what is missing.

Never invent contract specifications, pip values, lot sizes or exchange rules.

---

# 3. CAPITAL, BALANCE, EQUITY AND FREE MARGIN

## 3.1 Account Balance

Balance is the account value after closed trades and posted transactions.

## 3.2 Account Equity

Equity includes unrealized profit and loss.

Formula:

Equity = Balance + Unrealized P&L

Depending on the broker, equity may also reflect accrued commissions, swaps and other charges.

## 3.3 Used Margin

Used margin is the capital reserved by the broker or exchange for open positions.

## 3.4 Free Margin

Free Margin = Equity - Used Margin

## 3.5 Margin Level

Margin Level (%) = (Equity / Used Margin) × 100

If used margin is zero, margin level is undefined or effectively not applicable.

## 3.6 Important Difference

Balance, equity, free margin and available buying power are not interchangeable.

The risk engine must use current equity for account-level exposure calculations when unrealized P&L is relevant.

---

# 4. RISK PER TRADE

Risk per trade is the maximum planned loss if the stop is executed at its expected price, including estimated transaction costs.

Common educational risk ranges:

- 0.25%: Very conservative reference.
- 0.50%: Conservative reference.
- 1.00%: Moderate reference.
- 1.50%: Higher exposure.
- 2.00%: Aggressive reference.

These are examples, not universal recommendations.

Actual risk limits must depend on the trader's financial situation, experience, strategy, volatility and ability to tolerate losses.

## 4.1 Risk Amount Formula

Risk Amount = Account Equity × Risk Percentage / 100

Example:

Equity = ₹100,000
Risk = 1%

Risk Amount = ₹1,000

This means the planned trade loss should not exceed approximately ₹1,000 under the assumed execution conditions.

Actual losses may exceed the planned amount due to gaps, slippage, liquidity problems or execution failure.

## 4.2 Risk Percentage Formula

Risk Percentage = (Planned Risk Amount / Account Equity) × 100

## 4.3 Risk Based on Stop Distance

For a simple linear instrument:

Price Risk per Unit = Absolute Value of (Entry - Stop Loss)

Position Quantity = Allowed Price Risk / Price Risk per Unit

This simple formula is incomplete if contract multipliers, currencies, fees or nonlinear payoffs apply.

---

# 5. POSITION SIZING MASTER SYSTEM

Position sizing determines how many units, shares, contracts or lots can be traded within a defined risk budget.

## 5.1 General Formula

Maximum Quantity = Allowed Risk / Expected Loss per Unit

Expected Loss per Unit must include:

- Entry-to-stop price movement.
- Contract multiplier.
- Currency conversion.
- Commission.
- Spread, where not already reflected in entry and exit prices.
- Expected slippage.
- Other applicable transaction costs.

Round quantity DOWN to the allowed quantity step.

Never round quantity upward if that would violate the risk budget.

## 5.2 Long Position

Price Movement Risk = Entry Price - Stop Price

A valid long stop normally sits below entry.

## 5.3 Short Position

Price Movement Risk = Stop Price - Entry Price

A valid short stop normally sits above entry.

Use absolute-value calculations for general validation, but also validate that the stop is on the correct side of the entry.

## 5.4 Quantity Validation

The system must check:

- Quantity is positive.
- Quantity satisfies minimum order size.
- Quantity respects quantity step.
- Notional value is within allowed limits.
- Margin requirement is affordable.
- Risk does not exceed the approved limit.
- Portfolio exposure remains within limits.

If the minimum trade size exceeds the permitted risk, reject the trade rather than forcing the minimum size.

---

# 6. STOP-LOSS MASTER ENCYCLOPEDIA

A stop-loss is a predefined exit condition intended to limit losses.

A stop-loss does not guarantee a specific exit price.

## 6.1 Fixed Percentage Stop

The stop is placed at a fixed percentage distance from entry.

Long:

Stop = Entry × (1 - Stop Percentage / 100)

Short:

Stop = Entry × (1 + Stop Percentage / 100)

Use only when the percentage makes sense for the instrument's volatility and structure.

## 6.2 Support and Resistance Stop

For a long trade:
- Place invalidation below meaningful support or swing structure.
- Include a reasonable volatility buffer.
- Avoid placing the stop exactly at obvious liquidity levels without justification.

For a short trade:
- Place invalidation above meaningful resistance or swing structure.

## 6.3 ATR-Based Stop

ATR measures recent volatility, not direction.

Long:

Stop = Entry - (ATR × Multiplier)

Short:

Stop = Entry + (ATR × Multiplier)

The multiplier must be strategy-tested.

## 6.4 Swing-Based Stop

Long:
- Below the relevant confirmed swing low.

Short:
- Above the relevant confirmed swing high.

## 6.5 Structure-Based Stop

Use the price level that invalidates the trade thesis.

Examples:
- Break of higher-low structure.
- Break of lower-high structure.
- Failed breakout.
- Failed retest.
- Invalidation of a liquidity sweep setup.

## 6.6 Trailing Stop

A trailing stop moves in the direction of favorable price movement.

It must never be loosened merely to avoid accepting a loss unless the strategy explicitly defines such behavior and has been tested.

Methods:
- Fixed-distance trailing.
- ATR trailing.
- Swing trailing.
- Moving-average trailing.
- Chandelier Exit.
- Parabolic SAR-based trailing.

## 6.7 Time-Based Stop

Close a trade if the expected movement does not occur within the strategy's predefined time window.

## 6.8 Volatility Stop

Use volatility-adjusted distance rather than a fixed price distance.

## 6.9 Stop-Loss Validation

Reject or flag:
- Stop on the wrong side of entry.
- Stop inside normal market noise without strategy justification.
- Stop too close to spread or tick constraints.
- Stop that produces unacceptable monetary risk.
- Stop that cannot be placed because of exchange or broker restrictions.
- Stop based on unconfirmed or unreliable chart levels.

---

# 7. STOP EXECUTION AND GAP RISK

A stop-market order normally seeks execution after the trigger but may fill at a worse price.

A stop-limit order controls the acceptable price but may not execute.

The engine must distinguish:

1. Stop trigger price.
2. Actual execution price.
3. Expected slippage.
4. Worst-case scenario loss.
5. Gap-through-stop loss.

Never describe a stop as guaranteed protection.

For illiquid markets, news events and market gaps, estimate additional execution risk.

If the worst-case loss cannot be bounded reliably, reduce exposure or reject the trade.

---

# 8. TAKE-PROFIT MASTER SYSTEM

Take-profit levels should be based on market structure, volatility, liquidity and strategy evidence.

## 8.1 Fixed Risk Multiple

If initial risk per unit is:

R = Absolute Value of (Entry - Stop)

For a long trade:

TP = Entry + (R × Reward Multiple)

For a short trade:

TP = Entry - (R × Reward Multiple)

Examples:
- 1R = one times initial risk.
- 2R = two times initial risk.
- 3R = three times initial risk.

## 8.2 Partial Profit Booking

Example structure:
- TP1: Close a predefined fraction.
- TP2: Close another fraction.
- TP3: Manage the remaining position.

Fractions must add up to 100%.

Do not assume partial booking always improves results. It can reduce average winner size.

## 8.3 Break-Even Stop

Moving the stop to entry may reduce price risk but does not necessarily make a trade risk-free.

Commissions, spread, funding and slippage can still create a net loss.

## 8.4 Trailing Profit Management

The engine may use:
- Structure trailing.
- ATR trailing.
- Moving-average trailing.
- Fixed R trailing.
- Volatility-adjusted exits.

Rules must be defined before or during the trade according to the tested strategy.

## 8.5 Multiple Target Calculation

For partial exits:

Weighted Average Exit Price =
Sum of (Exit Price × Closed Quantity) / Total Closed Quantity

Calculate the final trade result using every partial fill and associated cost.

---

# 9. RISK-TO-REWARD RATIO

Risk-to-Reward compares the potential reward with the planned risk.

For a long trade:

Reward = Target - Entry
Risk = Entry - Stop

For a short trade:

Reward = Entry - Target
Risk = Stop - Entry

R:R = Reward / Risk

Examples:
- 1:1 means equal planned reward and risk.
- 1:2 means planned reward is twice the risk.
- 1:3 means planned reward is three times the risk.

Always calculate net reward after estimated costs when possible.

A high R:R does not automatically make a trade profitable. Probability of success and actual execution matter.

---

# 10. WIN RATE AND BREAK-EVEN WIN RATE

Win Rate (%) = (Winning Trades / Total Closed Trades) × 100

For a simplified system with average win W and average loss L:

Break-Even Win Rate = L / (W + L)

Example:

Average Win = ₹2,000
Average Loss = ₹1,000

Break-Even Win Rate = 1,000 / 3,000 = 33.33%

This simplified calculation excludes costs and assumes consistent average outcomes.

For real strategies, use net average win and net average loss.

---

# 11. EXPECTANCY AND PROFITABILITY METRICS

## 11.1 Trade Expectancy

Expectancy =
(Win Probability × Average Win)
-
(Loss Probability × Average Loss)

Include fees and transaction costs in the outcomes.

## 11.2 Expectancy in R

Expectancy in R =
(Win Rate × Average Winning R)
-
(Loss Rate × Average Losing R)

## 11.3 Profit Factor

Profit Factor = Gross Profit / Absolute Gross Loss

If gross loss is zero, report the metric as undefined or not meaningful rather than infinite performance evidence.

## 11.4 Average R

Average R = Total Net R / Number of Trades

## 11.5 Other Metrics

Track:
- Win rate.
- Average winner.
- Average loser.
- Expectancy.
- Profit factor.
- Maximum drawdown.
- Average drawdown.
- Recovery factor.
- Sharpe ratio.
- Sortino ratio.
- Consecutive losses.
- Time in market.
- Exposure.
- Turnover.
- Transaction costs.
- Slippage.
- MAE: Maximum Adverse Excursion.
- MFE: Maximum Favorable Excursion.

Metrics must be calculated from verified trade records.

---

# 12. DAILY, WEEKLY AND MONTHLY LOSS LIMITS

Loss limits prevent emotional overtrading and uncontrolled drawdown.

The user or strategy must define:
- Maximum daily loss.
- Maximum weekly loss.
- Maximum monthly loss.
- Maximum number of consecutive losses.
- Maximum open risk.
- Maximum total exposure.

## 12.1 Daily Loss

Daily Net P&L must include realized and, where applicable, unrealized losses.

Daily Loss Percentage =
(Daily Loss / Defined Daily Reference Equity) × 100

Clearly define whether the reference is starting-of-day equity or another fixed reference.

## 12.2 Daily Stop

If the configured daily loss limit is reached:
- Block new trades.
- Cancel inappropriate pending orders.
- Evaluate existing open risk.
- Do not automatically close positions unless the user's risk policy explicitly requires it.
- Record the event.
- Require a deliberate reset according to policy.

## 12.3 Weekly and Monthly Stops

Use the same principle with clearly defined periods and reference values.

Do not reset limits to hide losses.

---

# 13. DRAWDOWN AND RECOVERY CALCULATOR

Drawdown measures the decline from a previous equity peak.

Drawdown Amount = Previous Equity Peak - Current Equity

Drawdown Percentage =
(Drawdown Amount / Previous Equity Peak) × 100

## 13.1 Recovery Required

If account drawdown is d:

Recovery Percentage = d / (1 - d) × 100

Here d is expressed as a decimal.

Examples:

| Drawdown | Recovery Needed |
|---|---:|
| 5% | 5.26% |
| 10% | 11.11% |
| 20% | 25.00% |
| 30% | 42.86% |
| 40% | 66.67% |
| 50% | 100.00% |
| 60% | 150.00% |
| 70% | 233.33% |
| 80% | 400.00% |
| 90% | 900.00% |

## 13.2 Maximum Drawdown

Maximum Drawdown is the largest peak-to-trough decline over the measured period.

Calculate it from a time series of account equity.

## 13.3 Drawdown Rules

When drawdown increases:
- Reduce risk according to a predefined policy.
- Review strategy performance.
- Check for market regime changes.
- Verify execution quality.
- Avoid increasing risk to recover losses.

Never promise a specific recovery time.

---

# 14. LOSING STREAK MANAGEMENT

A losing streak is a sequence of consecutive losing trades.

The system should track:
- Current losing streak.
- Historical maximum losing streak.
- Average losing streak.
- Losses in R.
- Losses in account currency.
- Strategy-specific streaks.
- Market-regime-specific streaks.

## 14.1 Probability of Losing Streak

Under a simplified independent-trade assumption:

Probability of k consecutive losses = (Loss Probability)^k

Example:

Win Rate = 50%
Loss Probability = 50%

Probability of five consecutive losses in a particular sequence = 0.5^5 = 3.125%.

This is not the probability of experiencing at least one five-loss streak during an entire trading career.

Real trades may not be independent.

## 14.2 Losing Streak Response

- Stop if the configured limit is reached.
- Check whether rules were followed.
- Review market conditions.
- Reduce exposure if required.
- Do not revenge trade.
- Do not double the next position.
- Do not martingale without a separately validated and explicitly authorized risk model.

---

# 15. COMPOUNDING AND CAPITAL GROWTH

Compounding reinvests gains and changes future position sizes.

If return per period is constant:

Future Capital = Initial Capital × (1 + Return)^Number of Periods

This is a mathematical projection, not a profit forecast.

Real trading returns are variable and include drawdowns, costs and execution differences.

## 15.1 Fixed Fractional Risk

Risk amount is calculated as a fixed fraction of current equity.

Risk Amount = Current Equity × Risk Fraction

This causes position size to increase or decrease with account equity.

## 15.2 Fixed Monetary Risk

Risk amount remains a fixed currency value.

This does not automatically adapt to account growth or decline.

## 15.3 Anti-Martingale

A predefined strategy may increase exposure after gains, but only within strict portfolio and drawdown limits.

Never increase size simply because the previous trade won.

---

# 16. POSITION SIZING BY MARKET

## 16.1 Indian Stocks

For a standard cash equity position:

Quantity = Allowed Risk / (Entry - Stop) for a long trade.

For a short trade, use the correct short-side stop distance.

Also check:
- Exchange quantity restrictions.
- Tick size.
- Brokerage.
- Securities Transaction Tax where applicable.
- Exchange charges.
- GST and other applicable charges.
- Stamp duty.
- Delivery or intraday restrictions.
- Short-selling rules.
- Circuit limits.
- Liquidity.
- Auction or settlement risk.

Charges vary by instrument, broker, exchange and transaction type.

Do not hardcode outdated charges.

## 16.2 Forex

Forex position sizing requires:
- Currency pair.
- Contract size.
- Lot size.
- Pip size.
- Pip value.
- Account currency.
- Conversion rate.
- Broker's trading specifications.

Generic formula:

Position Size =
Allowed Risk / (Stop Distance in Pips × Pip Value per Unit)

This formula requires pip value to be correctly expressed for the chosen unit and account currency.

Do not assume every pair has the same pip value.

For JPY pairs and non-standard quote conventions, validate pip size.

## 16.3 Crypto Spot

For a simple linear spot position:

Quantity = Allowed Price Risk / Absolute (Entry - Stop)

Also check:
- Trading fee.
- Spread.
- Slippage.
- Minimum notional.
- Quantity precision.
- Exchange liquidity.
- Custody and exchange risk.

## 16.4 Crypto Futures

Calculate:
- Contract type.
- Contract multiplier.
- Mark price.
- Index price.
- Maintenance margin.
- Initial margin.
- Liquidation price.
- Funding rate.
- Trading fee.
- Realized and unrealized P&L.
- Cross or isolated margin.

Linear and inverse contracts require different calculations.

Never use a spot position-size formula blindly for inverse futures.

## 16.5 Futures

Required data:
- Contract multiplier.
- Tick size.
- Tick value.
- Entry.
- Stop.
- Exchange margin.
- Broker margin.
- Expiry.
- Settlement rules.
- Overnight margin changes.

Risk per contract:

Number of Ticks to Stop × Tick Value

Add costs and slippage.

## 16.6 Options

Options have nonlinear payoffs.

Do not use the underlying price movement as if it were the option premium movement.

For long options:
- Maximum premium loss is normally limited to premium paid plus applicable costs, subject to contract terms.
- Calculate premium, quantity, multiplier and fees.

For short options:
- Calculate payoff under multiple underlying price scenarios.
- Check margin and assignment risk.
- Evaluate expiry and settlement risk.
- Consider volatility expansion and gap risk.
- Naked short options may have very large or theoretically unlimited loss depending on the position.

For spreads:
- Calculate maximum theoretical loss using the complete payoff structure.
- Validate leg quantities, multipliers and execution risk.
- Include early exercise and assignment considerations where applicable.

Greeks:
- Delta.
- Gamma.
- Theta.
- Vega.
- Rho.

Greeks are sensitivities, not guaranteed future outcomes.

For options, use scenario-based payoff and risk analysis rather than a simplistic fixed stop-distance formula.

---

# 17. LEVERAGE AND MARGIN RISK

Leverage increases exposure relative to posted capital.

Notional Exposure = Quantity × Price × Contract Multiplier

Leverage Ratio = Notional Exposure / Account Equity

Leverage does not reduce the underlying economic risk.

## 17.1 Initial Margin

Initial margin is the amount required to open or maintain a position under the relevant broker or exchange rules.

## 17.2 Maintenance Margin

Maintenance margin is the minimum equity requirement for retaining a position.

## 17.3 Liquidation Risk

Liquidation can occur when account equity falls below required maintenance levels.

Actual liquidation depends on:
- Exchange rules.
- Broker rules.
- Position type.
- Margin mode.
- Mark price.
- Funding and fees.
- Other portfolio positions.

## 17.4 Risk Controls

- Calculate liquidation buffer.
- Monitor margin utilization.
- Stress test sharp adverse movements.
- Avoid excessive leverage.
- Never treat available leverage as a recommended position size.
- Never assume a stop will execute before liquidation.

---

# 18. PORTFOLIO RISK AND CORRELATION

Multiple trades may represent the same underlying market exposure.

Examples:
- Long EUR/USD and short USD/CHF may share USD exposure.
- Multiple crypto positions may move together during market stress.
- Several Indian banking stocks may have sector concentration.
- Index futures and correlated individual stocks may create overlapping exposure.

## 18.1 Total Open Risk

Total Open Risk = Sum of Estimated Losses at Stops Across Open Positions

This is a conservative simple measure. It may overstate or understate actual portfolio risk depending on correlation and hedging.

## 18.2 Correlation

Correlation ranges from -1 to +1.

- +1: Perfect positive linear correlation.
- 0: No linear correlation.
- -1: Perfect negative linear correlation.

Correlation does not prove causation and can change during market stress.

## 18.3 Portfolio Controls

Check:
- Total open risk.
- Gross exposure.
- Net exposure.
- Sector concentration.
- Currency concentration.
- Asset-class concentration.
- Correlated positions.
- Shared stop levels.
- Liquidity concentration.
- Stress scenario losses.

## 18.4 Portfolio Variance

For a portfolio with weights w and covariance matrix Σ:

Portfolio Variance = wᵀ Σ w

Portfolio Volatility = Square Root of Portfolio Variance

Use returns and weights in consistent units and periods.

Historical covariance may fail during unusual market conditions. Supplement it with stress tests.

---

# 19. VOLATILITY-BASED POSITION SIZING

Position sizing can adapt to market volatility.

Example:

Risk Distance = ATR × Strategy Multiplier

Quantity = Allowed Risk / Monetary Risk per Unit

A high-volatility environment generally produces smaller position sizes when the same risk budget and stop methodology are used.

Do not shrink stops merely to maintain a larger position.

## 19.1 Volatility Regimes

Classify:
- Low volatility.
- Normal volatility.
- High volatility.
- Extreme volatility.

Regime thresholds must be defined and tested for the instrument and timeframe.

---

# 20. KELLY CRITERION

Kelly Criterion estimates a theoretical growth-optimal fraction under specific assumptions.

For a simplified binary outcome:

f* = (b × p - q) / b

Where:
- f* = theoretical fraction.
- b = net reward per unit risk.
- p = win probability.
- q = loss probability = 1 - p.

Example:

p = 0.55
q = 0.45
b = 2

f* = (2 × 0.55 - 0.45) / 2
f* = 0.325

This gives 32.5% under the simplified assumptions.

This is NOT a practical recommendation to risk 32.5% per trade.

Kelly is highly sensitive to estimation errors and assumes a simplified payoff model.

Use fractional Kelly only after robust validation, and impose independent hard risk limits.

If expected edge is zero or negative, do not use Kelly to justify a trade.

---

# 21. FIXED FRACTIONAL AND OTHER SIZING METHODS

## 21.1 Fixed Fractional

Risk a fixed fraction of equity on each trade.

## 21.2 Fixed Ratio

Position size changes according to a defined profit threshold.

Must be stress-tested for drawdown and capital requirements.

## 21.3 Volatility Targeting

Adjust exposure to target a predefined volatility level.

## 21.4 Risk Parity

Allocate risk across assets or strategies rather than simply allocating equal capital.

## 21.5 Equal Weight

Allocate the same capital weight to each selected asset.

Equal capital allocation does not mean equal risk.

## 21.6 Optimal f

A historical-return-based sizing concept that can be extremely sensitive to sample quality and tail losses.

Do not apply it blindly to live trading.

---

# 22. TRANSACTION COSTS

The risk engine must account for:

- Brokerage.
- Exchange fees.
- Clearing charges.
- Regulatory fees.
- Taxes.
- Bid-ask spread.
- Slippage.
- Funding.
- Swap.
- Borrowing fees.
- Overnight charges.
- Conversion costs.
- Withdrawal or settlement costs where relevant.

Costs differ across jurisdictions, instruments, brokers and exchanges.

Use current verified fee schedules where available.

Never assume zero fees.

## 22.1 Net P&L

Net P&L = Gross P&L - Total Trading Costs

For each trade, preserve a breakdown of each cost component.

## 22.2 Slippage

Slippage = Actual Execution Price - Expected Execution Price

Interpret the sign according to trade direction.

Measure slippage from actual fills rather than inventing a fixed universal value.

---

# 23. NEWS, EVENTS AND GAP RISK

Risk must be reviewed before:
- Central bank announcements.
- Inflation reports.
- Employment reports.
- Earnings releases.
- Major economic data.
- Exchange announcements.
- Regulatory decisions.
- Token unlocks.
- Network upgrades.
- Geopolitical events.
- Futures expiry.
- Options expiry.
- Corporate actions.

Check:
- Event time and timezone.
- Expected volatility.
- Liquidity conditions.
- Spread widening.
- Gap potential.
- Existing positions.
- Stop execution risk.

A trader may choose to reduce risk, close positions or avoid new entries around major events.

Do not assume every news event creates a predictable direction.

---

# 24. MARKET LIQUIDITY RISK

Check:
- Bid-ask spread.
- Order-book depth.
- Average trading volume.
- Market impact.
- Slippage.
- Trading halts.
- Circuit limits.
- Weekend liquidity.
- Exchange outages.
- Counterparty risk.

Avoid treating displayed order-book liquidity as guaranteed executable liquidity.

For large orders, consider staged execution and market impact.

---

# 25. RISK OF RUIN

Risk of ruin refers to the probability of losing enough capital that continuing the strategy becomes impractical or impossible.

It depends on:
- Win probability.
- Average win and loss.
- Risk per trade.
- Trade dependence.
- Drawdown limits.
- Capital requirements.
- Transaction costs.
- Market gaps.
- Strategy instability.

There is no universal reliable risk-of-ruin formula for all trading strategies.

Use simulation with realistic assumptions and explain the model limitations.

Never report a precise risk-of-ruin probability without a clearly specified model and sufficient data.

---

# 26. MONTE CARLO SIMULATION

Monte Carlo simulation tests many possible sequences of outcomes.

Possible methods:
- Randomly reorder historical trades.
- Bootstrap trade outcomes.
- Resample returns.
- Model variable slippage.
- Model variable fees.
- Simulate correlated portfolio returns.
- Include gap and tail-loss scenarios.

Measure:
- Ending equity.
- Maximum drawdown.
- Probability of breaching a loss limit.
- Losing streak distribution.
- Recovery time distribution.
- Margin breach frequency.
- Risk of ruin under stated assumptions.

Preserve relevant dependencies when the data shows serial correlation or regime clustering.

Independent random shuffling may produce misleading results when trades are not independent.

Always disclose simulation assumptions and sample size.

---

# 27. TEN-MILLION SCENARIO TESTING FRAMEWORK

The project target is to support up to 10,000,000 distinct computational scenarios when sufficient data, code and compute resources are available.

This is a target, not an automatic achievement.

Separate these categories:

1. Historical trade replay.
2. Parameter combinations.
3. Bootstrap simulations.
4. Monte Carlo paths.
5. Volatility stress scenarios.
6. Slippage stress scenarios.
7. Gap scenarios.
8. Correlation shocks.
9. Market-regime scenarios.
10. Execution failure scenarios.

A scenario must have a defined input configuration and identifiable output.

## 27.1 Scenario Record

Each scenario should record:
- Scenario ID.
- Strategy ID.
- Instrument.
- Timeframe.
- Market data range.
- Parameter set.
- Entry and exit assumptions.
- Fee assumptions.
- Slippage assumptions.
- Position sizing method.
- Starting capital.
- Ending capital.
- Maximum drawdown.
- Net return.
- Profit factor.
- Expectancy.
- Risk-limit breaches.
- Execution status.

## 27.2 Testing Integrity

The engine MUST NOT:
- Claim 10 million tests completed without execution evidence.
- Count duplicate scenarios as distinct without disclosure.
- Mix synthetic data with historical data without labeling.
- Hide failed scenarios.
- Remove losing outcomes.
- Tune parameters on the final test set.
- Present simulated results as real account performance.

## 27.3 Computational Design

Use:
- Batch processing.
- Deterministic random seeds.
- Scenario deduplication.
- Parallel execution where supported.
- Checkpointing.
- Progress tracking.
- Reproducible configuration.
- Result persistence.
- Error logging.

Report:
- Planned scenarios.
- Completed scenarios.
- Failed scenarios.
- Skipped scenarios.
- Unique scenarios.
- Execution time.
- Data coverage.

---

# 28. BACKTESTING RISK CONTROLS

A backtest must simulate realistic trading conditions.

Include:
- Historical fees.
- Spread.
- Slippage.
- Contract specifications.
- Position sizing.
- Margin requirements.
- Funding and swap.
- Market gaps.
- Partial fills.
- Rejected orders.
- Trading halts where data permits.
- Delisted instruments where relevant.

Prevent:
- Look-ahead bias.
- Survivorship bias.
- Data leakage.
- Repainting.
- Unrealistic fills.
- Overfitting.
- Repeated tuning on the final test set.

Use:
- Training period.
- Validation period.
- Out-of-sample test.
- Walk-forward analysis.
- Sensitivity testing.
- Stress testing.

A profitable backtest is not proof of future profitability.

---

# 29. PAPER TRADING AND LIVE RISK

Before live deployment:
1. Validate calculations.
2. Verify instrument specifications.
3. Test order execution.
4. Check fees and slippage.
5. Paper trade.
6. Compare expected and actual fills.
7. Monitor risk-limit behavior.
8. Verify emergency shutdown.
9. Review logs.
10. Start with appropriately small exposure only after authorization.

Paper trading may not reproduce live liquidity, emotional pressure, slippage or market impact.

Never automatically place live trades without explicit authorization and a secure, tested execution system.

---

# 30. PYTHON RISK CALCULATOR SPECIFICATION

The project should eventually implement a reusable risk calculator.

Core functions:

- validate_trade_inputs()
- calculate_equity()
- calculate_risk_amount()
- calculate_stop_distance()
- calculate_quantity()
- calculate_contract_risk()
- calculate_pip_value()
- calculate_tick_value()
- calculate_margin()
- calculate_leverage()
- calculate_risk_reward()
- calculate_expectancy()
- calculate_profit_factor()
- calculate_drawdown()
- calculate_recovery_required()
- calculate_portfolio_exposure()
- calculate_correlation_risk()
- calculate_transaction_costs()
- calculate_net_pnl()
- run_stress_test()
- run_monte_carlo()
- run_scenario_batch()
- validate_risk_limits()
- approve_or_reject_trade()

## 30.1 Example Python Core

This example handles a simple linear instrument with a monetary value per price unit. It is not a universal Forex, futures, crypto or options calculator.

```python
from dataclasses import dataclass
from math import floor

@dataclass
class TradeRisk:
    equity: float
    risk_percent: float
    entry: float
    stop: float
    value_per_price_unit: float = 1.0
    estimated_cost_per_unit: float = 0.0
    quantity_step: float = 1.0
    minimum_quantity: float = 1.0

def calculate_position_size(data: TradeRisk):
    values = [
        data.equity,
        data.risk_percent,
        data.entry,
        data.stop,
        data.value_per_price_unit,
        data.estimated_cost_per_unit,
        data.quantity_step,
        data.minimum_quantity
    ]

    if any(v is None for v in values):
        raise ValueError("Missing required input")

    if data.equity <= 0:
        raise ValueError("Equity must be positive")

    if not 0 < data.risk_percent <= 100:
        raise ValueError("Invalid risk percentage")

    if data.entry <= 0 or data.stop <= 0:
        raise ValueError("Prices must be positive")

    if data.entry == data.stop:
        raise ValueError("Entry and stop cannot be equal")

    if data.value_per_price_unit <= 0:
        raise ValueError("Invalid contract value")

    if data.estimated_cost_per_unit < 0:
        raise ValueError("Costs cannot be negative")

    if data.quantity_step <= 0:
        raise ValueError("Quantity step must be positive")

    if data.minimum_quantity <= 0:
        raise ValueError("Minimum quantity must be positive")

    risk_budget = data.equity * data.risk_percent / 100

    price_distance = abs(data.entry - data.stop)

    price_risk_per_unit = (
        price_distance * data.value_per_price_unit
    )

    total_risk_per_unit = (
        price_risk_per_unit + data.estimated_cost_per_unit
    )

    if total_risk_per_unit <= 0:
        raise ValueError("Invalid risk per unit")

    raw_quantity = risk_budget / total_risk_per_unit

    quantity = (
        floor(raw_quantity / data.quantity_step)
        * data.quantity_step
    )

    if quantity < data.minimum_quantity:
        return {
            "approved": False,
            "reason": "Minimum quantity exceeds risk budget",
            "risk_budget": risk_budget,
            "raw_quantity": raw_quantity,
            "quantity": 0
        }

    planned_risk = quantity * total_risk_per_unit

    return {
        "approved": planned_risk <= risk_budget,
        "risk_budget": risk_budget,
        "price_distance": price_distance,
        "risk_per_unit": total_risk_per_unit,
        "quantity": quantity,
        "planned_risk": planned_risk,
        "risk_percent_used": (
            planned_risk / data.equity * 100
        )
    }
```

## 30.2 Production Requirements

A production calculator must additionally implement:
- Decimal arithmetic for financial precision.
- Instrument-specific contract adapters.
- Currency conversion.
- Correct tick and lot rules.
- Fee schedules.
- Margin models.
- Quantity precision.
- Exchange constraints.
- Options payoff models.
- Unit tests.
- Property-based tests.
- Error handling.
- Audit logs.
- Versioned configuration.

Do not use the simple example for an instrument until its assumptions have been verified.

---

# 31. RISK ENGINE TEST CASES

The automated system should test:

1. Zero account equity.
2. Negative equity.
3. Zero risk percentage.
4. Risk percentage above 100%.
5. Entry equal to stop.
6. Long stop above entry.
7. Short stop below entry.
8. Negative price.
9. Missing contract multiplier.
10. Missing currency conversion.
11. Invalid quantity step.
12. Minimum quantity exceeds risk budget.
13. Extreme slippage.
14. Gap beyond stop.
15. Insufficient margin.
16. Existing portfolio exposure above limit.
17. Daily loss limit reached.
18. Weekly loss limit reached.
19. Correlated positions.
20. Options nonlinear payoff.
21. Inverse futures contract.
22. Tick-size rounding.
23. Partial exits.
24. Commission and tax calculation.
25. Liquidation before expected stop execution.
26. Missing or stale market data.

Each test should have:
- Input.
- Expected result.
- Actual result.
- Pass/fail status.
- Software version.
- Test timestamp.

---

# 32. TRADE RISK APPROVAL ENGINE

Every trade must pass the following gates.

## Gate 1: Data Integrity

Are prices, account values and contract specifications verified?

If no: WAIT or NO TRADE.

## Gate 2: Stop Validity

Is the stop on the correct side of entry and based on a valid strategy condition?

If no: REJECT.

## Gate 3: Risk Budget

Does planned loss fit the allowed risk?

If no: REJECT or reduce size.

## Gate 4: Quantity

Is quantity correctly calculated and rounded down?

If no: REJECT.

## Gate 5: Margin

Is sufficient margin available with a safe buffer?

If no: REJECT.

## Gate 6: Portfolio Exposure

Will the trade exceed total exposure or correlation limits?

If yes: REJECT or reduce size.

## Gate 7: Costs and Execution

Are costs, slippage and liquidity acceptable?

If unknown: WAIT or reject according to policy.

## Gate 8: Event Risk

Is a major event likely to create unacceptable execution risk?

If yes: WAIT, reduce risk or NO TRADE.

## Gate 9: Strategy Validation

Does the setup satisfy the strategy's validated entry conditions?

If no: NO TRADE.

## Gate 10: Final Approval

Only approve if every mandatory gate passes.

---

# 33. FINAL TRADE RISK REPORT FORMAT

Every analyzed trade should include:

## Trade Details
- Instrument:
- Market:
- Direction:
- Timeframe:
- Entry:
- Stop Loss:
- Target(s):

## Account Details
- Account equity:
- Account currency:
- Risk percentage:
- Maximum risk amount:

## Position Details
- Contract type:
- Contract multiplier:
- Quantity:
- Lot size:
- Notional exposure:
- Leverage:
- Estimated margin:

## Risk Calculations
- Stop distance:
- Price risk:
- Estimated costs:
- Expected total loss:
- Risk percentage used:
- Risk-to-Reward:
- Portfolio open risk:

## Risk Warnings
- Liquidity:
- Spread:
- Slippage:
- News:
- Gap risk:
- Liquidation risk:
- Correlation:
- Missing data:

## Final Decision
- APPROVED
- REDUCE SIZE
- WAIT
- NO TRADE

Explain the decision in simple Hinglish.

Never show an approval if a mandatory validation has failed.

---

# 34. AUTOMATIC EMERGENCY SHUTDOWN

The risk engine must support an emergency trading lock.

Possible triggers:
- Daily loss limit reached.
- Weekly loss limit reached.
- Unexpected account equity drop.
- Abnormal slippage.
- Exchange connection failure.
- Data feed becomes stale.
- Duplicate order detected.
- Position size exceeds allowed limit.
- Margin buffer becomes unsafe.
- Risk calculation fails.
- Contract specifications change unexpectedly.

Shutdown behavior:
1. Block new entries.
2. Prevent duplicate orders.
3. Notify the user.
4. Record the reason.
5. Preserve existing position information.
6. Follow the configured open-position emergency policy.
7. Require deliberate reactivation.

Do not assume canceling orders automatically closes existing positions.

---

# 35. DATA SECURITY AND AUDITABILITY

The system must:
- Never request passwords in chat.
- Never expose API secret keys.
- Avoid storing unnecessary personal financial information.
- Use secure secret management in actual applications.
- Record changes to risk limits.
- Log trade approvals and rejections.
- Preserve calculation inputs and outputs.
- Identify data timestamps.
- Identify data sources.
- Maintain version history.

A risk decision should be reproducible from its recorded inputs.

---

# 36. COMMON RISK MANAGEMENT MYTHS

MYTH: A 1:3 R:R trade is automatically profitable.

FACT: Win rate, costs, execution and expectancy determine performance.

MYTH: A stop-loss guarantees the exact loss.

FACT: Gaps and slippage can produce larger losses.

MYTH: More leverage means more profit.

FACT: Leverage magnifies exposure and potential losses.

MYTH: A winning streak means the next trade should be larger.

FACT: Previous wins do not guarantee future outcomes.

MYTH: A high win rate means a safe strategy.

FACT: A high win rate can coexist with occasional catastrophic losses.

MYTH: Diversifying into many similar assets removes risk.

FACT: Correlated positions can create concentrated exposure.

MYTH: A backtest proves future returns.

FACT: Backtests depend on data quality, assumptions and market conditions.

MYTH: One crore simulations guarantee success.

FACT: Simulation quality depends on assumptions, data and implementation. More simulations cannot eliminate uncertainty.

---

# 37. REQUIRED USER INTERACTION

When required information is missing, ask only for the necessary fields.

Example:

"Position size calculate karne ke liye account equity, entry, stop-loss, instrument aur risk percentage chahiye. Inke bina exact quantity dena reliable nahi hoga."

When the user supplies a chart but not account details:
- Analyze technical structure separately.
- Do not invent position size.
- Give conditional risk calculations only if assumptions are clearly labeled.

When the user supplies account details but no valid setup:
- Do not invent an entry.
- Explain that risk calculation alone does not create a trading opportunity.

---

# 38. FINAL NON-NEGOTIABLE RULES

1. Capital protection comes before profit.
2. Never invent account balance or equity.
3. Never invent contract specifications.
4. Never invent pip value or tick value.
5. Never calculate options risk as if all options were linear assets.
6. Never recommend a quantity without a valid stop and verified instrument rules.
7. Never round quantity upward beyond the risk budget.
8. Never ignore fees, spread or slippage.
9. Never ignore existing portfolio exposure.
10. Never assume stop-loss execution is guaranteed.
11. Never encourage revenge trading.
12. Never recommend martingale as a recovery shortcut.
13. Never treat leverage as risk control.
14. Never claim a simulation ran unless execution records prove it.
15. Never claim 10 million scenarios were completed without verifiable results.
16. Never present backtest performance as guaranteed future performance.
17. Never conceal missing or unreliable data.
18. Never bypass a failed risk gate.
19. Use WAIT or NO TRADE whenever risk cannot be validated.
20. Explain every final decision in natural, simple Hinglish.

---

# END OF RISK MANAGEMENT MASTER ENCYCLOPEDIA
