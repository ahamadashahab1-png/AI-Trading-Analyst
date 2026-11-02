
# TRADE MANAGEMENT MASTER ENCYCLOPEDIA
## Complete A-to-Z Trade Execution, Monitoring, Adjustment and Exit System
### Version 1.0 | AI Trading Analyst

---

# 1. PURPOSE AND SCOPE

Trade management is the complete process of controlling a trade from the moment an order is prepared until the position is fully closed and reviewed.

It includes:

1. Pre-entry preparation.
2. Order placement.
3. Entry execution.
4. Initial position protection.
5. Live position monitoring.
6. Stop-loss management.
7. Take-profit management.
8. Partial exits.
9. Position additions and reductions.
10. Re-entry decisions.
11. Unexpected market event handling.
12. Portfolio-level coordination.
13. Final exit.
14. Trade recording.
15. Performance analysis.

The AI Trading Analyst must distinguish between:

- Trade analysis.
- Trade planning.
- Trade execution.
- Open-position management.
- Trade closure.
- Post-trade evaluation.

A technically valid entry does not guarantee a successful trade.

The primary rule is:

**Manage the trade according to predefined rules, not fear, greed or random price movement.**

---

# 2. TRADE MANAGEMENT CORE PRINCIPLES

The system MUST:

- Preserve the original trade thesis.
- Identify the exact condition that invalidates the thesis.
- Never widen a stop merely to avoid accepting a loss.
- Never move a stop based only on emotional discomfort.
- Never add to a losing position without an explicitly tested strategy.
- Never increase exposure beyond the risk budget.
- Never assume a target will be reached.
- Never ignore spread, fees, slippage or funding.
- Never treat unrealized profit as guaranteed profit.
- Never report an order as executed without execution evidence.
- Distinguish open orders from filled positions.
- Track actual fills and partial fills.
- Recalculate risk after every position adjustment.
- Consider the entire portfolio, not just one trade.
- Prefer safety when data or execution status is uncertain.

If essential live information is unavailable, explain the limitation and request updated data.

---

# 3. COMPLETE TRADE LIFECYCLE

The system must follow this lifecycle:

1. Market research.
2. Setup identification.
3. Trade thesis.
4. Entry confirmation.
5. Risk approval.
6. Position sizing.
7. Order preparation.
8. Order submission, if authorized.
9. Fill confirmation.
10. Initial protection.
11. Position monitoring.
12. Management adjustments.
13. Partial or full exit.
14. Position reconciliation.
15. Final P&L calculation.
16. Trade journal entry.
17. Performance review.

At every stage, store the current trade state.

Do not confuse an order being submitted with an order being filled.

---

# 4. TRADE STATE MACHINE

Every trade must have a defined state.

Possible states:

- DRAFT
- ANALYZING
- PLANNED
- APPROVED
- REJECTED
- PENDING_ENTRY
- PARTIALLY_FILLED
- OPEN
- PARTIALLY_CLOSED
- MODIFY_PENDING
- EXIT_PENDING
- CLOSED
- CANCELLED
- EXPIRED
- ERROR
- RECONCILIATION_REQUIRED

## 4.1 State Transition Rules

DRAFT -> ANALYZING

ANALYZING -> PLANNED or REJECTED

PLANNED -> APPROVED or REJECTED

APPROVED -> PENDING_ENTRY

PENDING_ENTRY -> PARTIALLY_FILLED, OPEN, CANCELLED or EXPIRED

PARTIALLY_FILLED -> OPEN, PARTIALLY_CLOSED or CANCELLED

OPEN -> MODIFY_PENDING, PARTIALLY_CLOSED or EXIT_PENDING

MODIFY_PENDING -> OPEN or RECONCILIATION_REQUIRED

EXIT_PENDING -> PARTIALLY_CLOSED, CLOSED or RECONCILIATION_REQUIRED

PARTIALLY_CLOSED -> OPEN or CLOSED

CLOSED -> Final reporting and review

A failed API request must not automatically change the actual exchange position state.

The system must reconcile its internal state with broker or exchange records.

---

# 5. PRE-TRADE MANAGEMENT PLAN

Before entry, create a complete trade management plan.

Required fields:

- Trade ID.
- Instrument.
- Exchange or broker.
- Market.
- Trading direction.
- Strategy.
- Timeframe.
- Entry type.
- Entry zone or exact price.
- Initial stop.
- Target levels.
- Risk amount.
- Position size.
- Contract specifications.
- Estimated fees.
- Expected slippage.
- Maximum holding time.
- Invalidation conditions.
- Partial-exit plan.
- Trailing-stop rules.
- News-event risk.
- Portfolio exposure.
- Emergency exit rules.

## 5.1 Trade Thesis

A trade thesis must explain:

- Why the trade exists.
- Which market condition supports it.
- What confirmation is required.
- What price behavior invalidates it.
- What target is realistic.
- What risks could interrupt it.

## 5.2 Management Plan Lock

Once the trade is approved, preserve its original plan.

Any modification must be recorded with:
- Previous value.
- New value.
- Reason.
- Timestamp.
- Market evidence.
- Updated risk.

The AI must not silently rewrite the original plan.

---

# 6. ENTRY EXECUTION MASTER SYSTEM

## 6.1 Market Order

A market order attempts immediate execution at available market prices.

Advantages:
- Usually faster execution.
- Useful when immediate participation matters.

Risks:
- Slippage.
- Spread.
- Poor fills in illiquid markets.
- Price impact.

Never assume a market order fills at the displayed last price.

## 6.2 Limit Order

A limit order specifies the worst acceptable purchase or sale price.

Advantages:
- Price control.
- May reduce adverse execution.

Risks:
- May not fill.
- May partially fill.
- Market may move away.

## 6.3 Stop Order

A stop order becomes active after a trigger condition.

Trigger behavior depends on broker and exchange rules.

## 6.4 Stop-Limit Order

A stop-limit order combines a trigger with a limit price.

It may fail to execute during rapid market movement.

## 6.5 Stop-Market Order

After triggering, it seeks market execution.

It may fill significantly beyond the trigger price.

## 6.6 OCO Orders

One-Cancels-the-Other orders link two orders so that execution or cancellation of one affects the other according to platform rules.

Verify the exact broker implementation.

## 6.7 Bracket Orders

A bracket structure may include:
- Entry order.
- Stop-loss order.
- Profit-taking order.

Verify whether protective orders are actually active after entry fills.

## 6.8 Conditional Orders

Examples:
- Price-triggered order.
- Indicator-triggered order.
- Time-triggered order.
- Volume-triggered order.
- Linked order.
- Trailing stop.

The AI must distinguish native exchange conditions from application-side conditions.

---

# 7. ENTRY QUALITY AND FILL ANALYSIS

After execution, record:

- Planned entry.
- Actual average fill.
- Fill quantity.
- Remaining quantity.
- Number of fills.
- Entry timestamp.
- Spread at entry.
- Estimated slippage.
- Actual slippage.
- Fees.
- Execution venue.

## 7.1 Entry Slippage

For a BUY:

Slippage = Actual Fill Price - Expected Entry Price

For a SELL:

Slippage = Expected Entry Price - Actual Fill Price

Positive values represent adverse slippage under these definitions.

## 7.2 Entry Deviation

Entry Deviation = Absolute (Actual Average Fill - Planned Entry)

Evaluate whether the actual fill changes:
- Stop distance.
- Risk amount.
- Risk-to-reward.
- Trade validity.
- Target feasibility.

If the actual fill makes the original setup invalid, the system must not pretend the original plan remains unchanged.

---

# 8. INITIAL STOP-LOSS MANAGEMENT

Immediately after a position is confirmed, verify the protective stop.

Check:

1. Stop exists.
2. Stop quantity matches the protected position.
3. Stop direction is correct.
4. Stop price is valid.
5. Stop order is accepted.
6. Stop is not accidentally cancelled.
7. Stop is not duplicated.
8. Stop complies with tick-size requirements.
9. Stop remains within the risk policy.
10. Stop behavior is understood.

## 8.1 Long Position

The initial protective stop is normally below the entry price.

## 8.2 Short Position

The initial protective stop is normally above the entry price.

## 8.3 Missing Stop

If a stop is rejected or missing:

- Mark the trade as UNPROTECTED.
- Notify the user immediately.
- Do not claim the trade is safely protected.
- Follow the preauthorized emergency policy.
- Do not create additional exposure.
- Reconcile the actual position and orders.

A missing stop is a critical execution issue.

---

# 9. STOP-LOSS ADJUSTMENT RULES

Stop adjustments must follow predefined strategy rules.

Possible methods:

- Structure-based.
- ATR-based.
- Swing-based.
- Moving-average-based.
- Fixed-R-based.
- Time-based.
- Volatility-based.
- Trailing-based.

## 9.1 Long Position Stop Improvement

Moving the stop upward may reduce planned loss.

## 9.2 Short Position Stop Improvement

Moving the stop downward may reduce planned loss.

## 9.3 Stop Widening

Moving the stop farther from entry increases exposure.

Default policy: reject stop widening.

Any exception requires:
- Explicit strategy rule.
- Recalculated risk.
- Available risk budget.
- User authorization where relevant.
- Complete audit record.

Never widen a stop solely because price is approaching it.

## 9.4 Structural Stop Adjustment

Update the stop only after the relevant market structure has been confirmed according to the strategy.

Do not use unconfirmed swing points.

## 9.5 ATR-Based Adjustment

A strategy may update the stop using a new ATR value.

The ATR timeframe, lookback and multiplier must remain consistent with the tested rules.

Do not automatically use every new ATR value if that would loosen protection.

---

# 10. BREAK-EVEN MANAGEMENT

Break-even management moves the protective stop toward the entry price.

## 10.1 Basic Break-Even

For a long position:

Break-Even Stop = Entry Price

For a short position:

Break-Even Stop = Entry Price

However, actual net break-even must account for:
- Entry fees.
- Exit fees.
- Spread.
- Funding.
- Swap.
- Expected slippage.
- Other applicable charges.

## 10.2 Net Break-Even

Calculate the exit price required for the trade to cover all costs.

For complex contracts, use the actual contract P&L function rather than a simplified price formula.

## 10.3 Break-Even Triggers

Possible triggers:
- Reaching a predefined R multiple.
- Confirmed market structure.
- Reaching a target zone.
- Strategy-specific indicator confirmation.
- Volatility-adjusted movement.

Do not move every trade to break-even at an arbitrary universal percentage.

## 10.4 Break-Even Risks

- Price may return to entry before the main move.
- Fees can create a net loss.
- Tight stops may be triggered by normal volatility.
- Execution can occur beyond the stop.

Evaluate break-even rules using historical and out-of-sample testing.

---

# 11. TRAILING STOP MASTER ENCYCLOPEDIA

A trailing stop follows favorable movement while attempting to preserve gains.

## 11.1 Fixed-Distance Trailing

The stop follows price at a predefined distance.

## 11.2 Percentage Trailing

The stop follows price at a predefined percentage distance.

## 11.3 ATR Trailing

For long positions:

Stop = Highest Favorable Price - (ATR × Multiplier)

For short positions:

Stop = Lowest Favorable Price + (ATR × Multiplier)

The highest or lowest favorable price must be maintained from the defined activation point.

## 11.4 Swing Trailing

For long positions:
- Trail below confirmed higher lows.

For short positions:
- Trail above confirmed lower highs.

## 11.5 Moving Average Trailing

The stop or exit may depend on a selected moving average.

Specify:
- Indicator type.
- Period.
- Timeframe.
- Confirmation candle.
- Buffer.
- Execution rule.

## 11.6 Chandelier Exit

Common structure:

Long Stop = Highest High over lookback - ATR × Multiplier

Short Stop = Lowest Low over lookback + ATR × Multiplier

Parameters must be strategy-tested.

## 11.7 Parabolic SAR Trailing

Use SAR values according to the indicator's exact calculation and update rules.

## 11.8 Trailing Stop Restrictions

- Never move a protective stop in the wrong direction without a validated exception.
- Do not use incomplete candles as confirmed signals.
- Avoid repeated unnecessary stop modifications.
- Respect tick size and broker modification limits.
- Check whether the stop is native or simulated by the application.

---

# 12. TAKE-PROFIT MANAGEMENT

Targets must be connected to the trade thesis.

Possible target methods:

- Fixed R multiples.
- Support and resistance.
- Liquidity pools.
- Swing highs and lows.
- Fibonacci extensions.
- Measured moves.
- ATR projections.
- Volume profile levels.
- Previous day high/low.
- Weekly high/low.
- Range boundaries.
- Strategy-specific projections.

## 12.1 TP1

The first target may be used for:
- Partial booking.
- Risk reduction.
- Structural reassessment.
- Stop adjustment if predefined.

## 12.2 TP2

The second target may capture a larger move.

## 12.3 TP3

The final target may be used for the remaining position.

These targets are optional planning levels, not mandatory exits.

## 12.4 Target Reassessment

Reassess when:
- Market structure changes.
- Original thesis is invalidated.
- A major liquidity level is reached.
- Volatility changes significantly.
- A high-impact event occurs.
- Execution conditions deteriorate.

Do not move a target farther merely because the trade is profitable.

---

# 13. PARTIAL PROFIT BOOKING

Partial exit closes a portion of an open position.

Example:

Initial quantity = 100 units.

- TP1 closes 30 units.
- TP2 closes 30 units.
- TP3 closes remaining 40 units.

Total closed quantity must never exceed the filled position quantity.

## 13.1 Partial Exit Validation

Check:
- Current open quantity.
- Requested close quantity.
- Minimum quantity.
- Quantity step.
- Fees.
- Available liquidity.
- Remaining stop quantity.
- Remaining target quantity.

## 13.2 Remaining Quantity

Remaining Quantity = Filled Quantity - Total Closed Quantity

## 13.3 Weighted Average Exit

Weighted Average Exit Price =
Sum of (Exit Fill Price × Closed Quantity) / Total Closed Quantity

Track every partial fill separately.

## 13.4 Partial Booking Evaluation

Partial booking may:
- Reduce exposure.
- Realize some profit.
- Reduce psychological pressure.

It may also:
- Reduce average winning trade.
- Increase transaction costs.
- Limit participation in large moves.

Use evidence, not assumptions.

---

# 14. SCALING IN AND ADDING TO POSITIONS

Scaling in means increasing position size after an initial entry.

Methods:
- Add after breakout confirmation.
- Add after successful retest.
- Add after pullback.
- Add at predefined structure levels.
- Add after volatility confirmation.

## 14.1 Scaling-In Rules

Before adding:
1. Check current open quantity.
2. Calculate current unrealized P&L.
3. Calculate new total exposure.
4. Recalculate combined stop risk.
5. Check portfolio risk.
6. Check margin.
7. Check correlated exposure.
8. Verify strategy authorization.

## 14.2 Add-to-Winner

Adding to a profitable position may be valid under a tested strategy.

However, the additional quantity creates new risk.

Do not assume existing profit automatically protects the new position.

## 14.3 Averaging Down

Adding to a losing position increases exposure.

Default policy: reject unless the strategy explicitly defines:
- Maximum number of additions.
- Total risk limit.
- Average entry calculation.
- Final stop.
- Maximum adverse movement.
- Margin requirements.
- Exit conditions.

Never average down to avoid admitting a mistake.

## 14.4 Pyramiding

Pyramiding adds exposure in stages.

Every stage must have a separate:
- Entry record.
- Fill record.
- Risk contribution.
- Stop allocation.
- Exit allocation.

The combined position must remain within the total approved risk budget.

---

# 15. SCALING OUT AND POSITION REDUCTION

Scaling out reduces an open position in stages.

Possible reasons:
- Target reached.
- Risk limit reached.
- Volatility increases.
- Market structure weakens.
- Event risk increases.
- Portfolio exposure needs reduction.
- Strategy-defined exit condition appears.

After every reduction:
- Recalculate remaining quantity.
- Reconcile protective orders.
- Recalculate total open risk.
- Recalculate margin.
- Update target quantities.

Do not leave oversized exit orders after a partial fill.

---

# 16. EARLY EXIT MANAGEMENT

An early exit may occur before the original target.

Valid reasons include:

1. Trade thesis invalidation.
2. Confirmed opposite market structure.
3. Unexpected high-impact event.
4. Severe liquidity deterioration.
5. Abnormal spread.
6. Data integrity failure.
7. Exchange or broker instability.
8. Strategy-defined time stop.
9. Portfolio risk breach.
10. Margin danger.
11. Unexpected execution problem.
12. Explicit user decision.

## 16.1 Early Exit Discipline

The system must distinguish:
- Strategy exit.
- Risk-control exit.
- Emergency exit.
- Discretionary exit.
- Execution-related exit.

Record the exact reason.

Do not exit solely because a small temporary candle moves against the position unless the strategy requires it.

---

# 17. TRADE INVALIDATION

A trade becomes invalid when its predefined thesis conditions fail.

Examples:
- Support breaks on a confirmed basis.
- Resistance is reclaimed.
- Breakout fails.
- Liquidity sweep setup fails.
- FVG or order-block condition is invalidated under the strategy.
- Trend structure changes.
- Fundamental thesis changes.
- A required catalyst disappears.

An invalidated trade must not remain active merely because it has unrealized profit.

The system must distinguish between:
- Temporary adverse movement.
- Normal volatility.
- Confirmed invalidation.
- Stop-loss execution.

---

# 18. RE-ENTRY MANAGEMENT

Re-entry means entering again after a previous position has been closed.

Before re-entry, require:
- New setup or valid continuation.
- Fresh confirmation.
- New entry.
- New stop.
- New risk calculation.
- Updated daily loss.
- Updated portfolio exposure.
- Strategy authorization.

Do not automatically re-enter because the stop was hit.

## 18.1 Same-Day Re-entry

Check:
- Daily loss limit.
- Number of previous attempts.
- Market regime.
- Whether the original thesis remains valid.
- Whether the new entry is genuinely different.

## 18.2 Re-entry After Profit

A profitable exit does not justify immediate revenge-like re-entry.

Require a fresh setup.

## 18.3 Re-entry After Loss

Do not increase risk to recover the previous loss.

---

# 19. MULTI-TIMEFRAME TRADE MANAGEMENT

Trade management may use several timeframes.

Example:
- Higher timeframe: trend and major levels.
- Middle timeframe: structure and setup.
- Lower timeframe: execution and monitoring.

## 19.1 Timeframe Roles

Higher timeframe:
- Market regime.
- Major support/resistance.
- Macro structure.

Middle timeframe:
- Trade thesis.
- Setup confirmation.
- Invalidation.

Lower timeframe:
- Entry execution.
- Short-term management.
- Microstructure.

## 19.2 Conflict Handling

If timeframes disagree:
- Identify the strategy's priority timeframe.
- Do not arbitrarily select the favorable signal.
- Reduce confidence if appropriate.
- Avoid management changes based on noisy lower-timeframe movements.

## 19.3 Candle Confirmation

Specify whether decisions require:
- Intrabar price.
- Candle close.
- Multiple candle confirmation.
- Volume confirmation.

Never describe an unfinished candle as a confirmed close.

---

# 20. PRICE ACTION AND MARKET STRUCTURE MANAGEMENT

Track:
- Higher highs.
- Higher lows.
- Lower highs.
- Lower lows.
- BOS.
- CHoCH.
- MSS.
- Range boundaries.
- Breakout.
- Retest.
- Failed breakout.
- Reversal.
- Trend exhaustion.

## 20.1 Long Management

Possible hold conditions:
- Higher-low structure remains intact.
- Bullish continuation is confirmed.
- Support holds.
- No defined invalidation condition appears.

Possible exit conditions:
- Confirmed structural breakdown.
- Strategy invalidation.
- Stop execution.
- Risk-control trigger.

## 20.2 Short Management

Possible hold conditions:
- Lower-high structure remains intact.
- Bearish continuation is confirmed.
- Resistance holds.

Possible exit conditions:
- Confirmed structural breakout.
- Strategy invalidation.
- Stop execution.
- Risk-control trigger.

---

# 21. ICT AND SMART MONEY CONCEPTS MANAGEMENT

The system may manage trades using:

- BOS.
- CHoCH.
- MSS.
- BSL.
- SSL.
- Equal highs.
- Equal lows.
- Liquidity sweep.
- Inducement.
- FVG.
- IFVG.
- BPR.
- Order Block.
- Breaker Block.
- Mitigation Block.
- Premium and Discount.
- OTE.
- Displacement.
- Judas Swing.
- Kill Zones.
- SMT Divergence.
- Power of Three.
- Draw on Liquidity.

Rules:

1. Identify the exact entry model.
2. Define the invalidation point.
3. Distinguish confirmed from unconfirmed structure.
4. Avoid treating every FVG or order block as valid.
5. Check market context.
6. Verify session and timeframe.
7. Record whether the target liquidity was reached.
8. Do not change the model after entry merely to justify holding.

ICT/SMC concepts must be tested as specific rule sets rather than treated as guaranteed institutional behavior.

---

# 22. INDICATOR-BASED TRADE MANAGEMENT

Indicators may assist trade management.

## 22.1 Moving Averages

Use predefined:
- SMA.
- EMA.
- VWMA.
- HMA.
- Other validated averages.

Possible rules:
- Close below a selected average.
- Confirmed crossover.
- Retest failure.
- Trend alignment.

## 22.2 RSI

Possible uses:
- Momentum weakening.
- Divergence.
- Trend regime.
- Predefined threshold exits.

Overbought does not automatically mean SELL.
Oversold does not automatically mean BUY.

## 22.3 MACD

Possible uses:
- Momentum reversal.
- Signal-line cross.
- Histogram contraction.
- Trend confirmation.

## 22.4 ATR

Use for:
- Volatility monitoring.
- Trailing stops.
- Stop-distance analysis.
- Position sizing.

## 22.5 Supertrend

Use only with confirmed indicator values and tested parameters.

## 22.6 VWAP

Use:
- Session trend.
- Mean-reversion conditions.
- Institutional execution context where supported by data.

## 22.7 Volume Indicators

Use:
- OBV.
- MFI.
- CMF.
- Volume Profile.
- Relative Volume.

Do not treat indicator divergence as guaranteed reversal evidence.

---

# 23. VOLUME AND ORDER FLOW MANAGEMENT

Monitor when reliable data exists:

- Bid volume.
- Ask volume.
- Volume delta.
- Cumulative Volume Delta.
- Footprint.
- Absorption.
- Imbalance.
- Open interest.
- Liquidation data.
- Order-book depth.
- Volume profile.
- Point of Control.
- Value Area High.
- Value Area Low.

Important limitations:

- Order books change rapidly.
- Displayed liquidity may disappear.
- Exchange data may be incomplete.
- Aggregated volume may differ between venues.
- Futures and spot volume are not interchangeable.

Use these inputs as supporting evidence, not guaranteed directional signals.

---

# 24. FOREX TRADE MANAGEMENT

Forex-specific factors:

- Currency pair.
- Base currency.
- Quote currency.
- Pip size.
- Pip value.
- Lot size.
- Contract size.
- Account currency.
- Spread.
- Swap.
- Rollover.
- Trading session.
- Broker execution.
- Weekend gap risk.

## 24.1 Forex Open Trade Checks

Monitor:
- London session.
- New York session.
- Asian session.
- Session overlap.
- Central bank events.
- Inflation.
- Employment.
- Interest rates.
- Currency correlation.

## 24.2 Rollover

Check applicable swap and rollover charges.

Do not assume all brokers charge the same amount.

## 24.3 Weekend Exposure

Before market closure:
- Check open risk.
- Check weekend news.
- Check gap exposure.
- Follow predefined holding policy.

---

# 25. CRYPTO TRADE MANAGEMENT

Crypto-specific risks:

- 24/7 trading.
- Exchange outages.
- Weekend volatility.
- Funding rates.
- Liquidation cascades.
- Thin liquidity.
- Token unlocks.
- Exchange-specific price differences.
- Stablecoin depegging.
- Network interruptions.
- Regulatory announcements.

## 25.1 Spot

Monitor:
- Quantity.
- Average entry.
- Fees.
- Exchange custody risk.
- Withdrawal restrictions.
- Liquidity.

## 25.2 Perpetual Futures

Monitor:
- Mark price.
- Index price.
- Funding.
- Maintenance margin.
- Liquidation price.
- Margin mode.
- Contract multiplier.

## 25.3 Cross Margin

Other positions and account collateral may affect liquidation risk.

## 25.4 Isolated Margin

Risk is isolated according to the exchange's rules, but additional margin may still alter liquidation conditions.

## 25.5 Exchange Risk

If the exchange becomes unavailable:
- Do not assume orders remain modifiable.
- Preserve the last verified position state.
- Warn about operational risk.
- Avoid claiming that an order was cancelled or closed without confirmation.

---

# 26. INDIAN STOCKS TRADE MANAGEMENT

Monitor:

- NSE or BSE instrument.
- Trading segment.
- Delivery or intraday.
- Quantity.
- Tick size.
- Brokerage.
- Taxes and charges.
- Liquidity.
- Circuit limits.
- Corporate actions.
- Results.
- Exchange announcements.
- Settlement rules.

## 26.1 Intraday

Follow the broker's square-off and risk policies.

Do not assume all brokers use the same auto-square-off time or charges.

## 26.2 Delivery

Consider:
- Overnight gaps.
- Corporate events.
- Earnings.
- Sector changes.
- Market-wide risk.

## 26.3 Short Selling

Follow current exchange and regulatory rules.

Never assume an intraday short position can be held overnight.

## 26.4 F&O

Monitor:
- Contract expiry.
- Lot size.
- Margin.
- SPAN and exposure requirements where applicable.
- Expiry settlement.
- Option Greeks.
- Assignment and exercise rules.

Verify current contract specifications rather than hardcoding outdated values.

---

# 27. GLOBAL STOCKS TRADE MANAGEMENT

Monitor:
- Exchange trading hours.
- Earnings.
- Guidance.
- Dividends.
- Corporate actions.
- Currency conversion.
- Overnight sessions.
- Pre-market and after-hours liquidity.
- Trading halts.
- Country-specific restrictions.

A price shown during extended hours may not represent executable liquidity during regular trading.

---

# 28. FUTURES TRADE MANAGEMENT

Monitor:
- Contract expiry.
- Rollover.
- Contract multiplier.
- Tick size.
- Tick value.
- Initial margin.
- Maintenance margin.
- Settlement.
- Delivery requirements.
- Overnight margin changes.
- Limit moves.

Do not hold a deliverable contract into a delivery period without understanding the relevant obligations.

---

# 29. OPTIONS TRADE MANAGEMENT

Options require nonlinear payoff analysis.

Monitor:
- Premium.
- Quantity.
- Contract multiplier.
- Strike.
- Expiry.
- Underlying price.
- Implied volatility.
- Delta.
- Gamma.
- Theta.
- Vega.
- Rho.
- Bid-ask spread.
- Open interest.
- Liquidity.
- Margin.
- Assignment risk.

## 29.1 Long Call and Long Put

Monitor:
- Premium decay.
- Volatility changes.
- Delta changes.
- Time to expiry.
- Underlying movement.

## 29.2 Short Options

Monitor:
- Margin.
- Tail risk.
- Gamma exposure.
- Volatility expansion.
- Gap risk.
- Assignment.
- Expiry settlement.

## 29.3 Spreads

Manage each leg and the total payoff together.

Do not assume each leg will execute at its displayed price.

## 29.4 Expiry Management

Define:
- Exit before expiry.
- Exercise conditions.
- Assignment handling.
- Settlement handling.
- Broker-specific cutoffs.

Never invent an expiry rule.

---

# 30. SCALPING TRADE MANAGEMENT

Scalping uses short holding periods.

Monitor:
- Spread.
- Execution speed.
- Order-book depth.
- Slippage.
- Microstructure.
- Short-term volatility.
- Fees.
- Trading latency.

A small expected profit can be eliminated by transaction costs.

Avoid scalping when data or execution latency is too high for the strategy.

Do not use higher-timeframe assumptions to justify a failed short-term scalp.

---

# 31. INTRADAY TRADE MANAGEMENT

Monitor:
- Session structure.
- Opening range.
- VWAP.
- Previous day high/low.
- Intraday volume.
- News events.
- Daily loss limits.
- Broker square-off rules.

Before market close:
- Check open positions.
- Check pending orders.
- Follow holding restrictions.
- Record final exposure.

---

# 32. SWING TRADE MANAGEMENT

Monitor:
- Daily and weekly structure.
- Overnight gaps.
- Earnings.
- Macroeconomic events.
- Funding or swap.
- Corporate actions.
- Multi-day volatility.

Use stop and target rules designed for the holding period.

Do not manage a swing trade using every small intraday candle unless the strategy explicitly requires it.

---

# 33. POSITIONAL TRADE MANAGEMENT

Monitor:
- Weekly and monthly trends.
- Fundamental thesis.
- Valuation changes.
- Macro conditions.
- Major support/resistance.
- Corporate developments.
- Long-term portfolio concentration.

Reassess the thesis when material information changes.

Do not keep a losing position indefinitely just because it was originally intended as a long-term trade.

---

# 34. NEWS AND ECONOMIC EVENT MANAGEMENT

For open positions, track:

- Event name.
- Country.
- Currency or asset exposure.
- Scheduled time.
- Forecast.
- Previous result.
- Actual result.
- Source.
- Publication timestamp.

Important events:
- Interest rate decisions.
- Inflation.
- Employment.
- GDP.
- Central bank speeches.
- Earnings.
- Regulatory decisions.
- Token unlocks.
- Major network upgrades.
- Geopolitical events.

## 34.1 Before Event

Evaluate:
- Existing open risk.
- Potential gap.
- Spread expansion.
- Liquidity.
- Stop reliability.
- Position size.

## 34.2 During Event

Avoid interpreting the first price spike as a confirmed trend.

Wait for reliable data and strategy confirmation.

## 34.3 After Event

Reassess:
- Actual result.
- Market reaction.
- Volatility.
- Structure.
- Original trade thesis.

Never invent news results or timestamps.

---

# 35. CORRELATED TRADES AND PORTFOLIO MANAGEMENT

Manage positions as a portfolio.

Track:
- Total open risk.
- Gross exposure.
- Net exposure.
- Asset correlation.
- Currency concentration.
- Sector concentration.
- Strategy concentration.
- Margin usage.
- Liquidity risk.

A new trade may be individually acceptable but unacceptable at portfolio level.

## 35.1 Portfolio Adjustment

Possible actions:
- Reduce a correlated position.
- Reject a new trade.
- Reduce quantity.
- Close a position.
- Hedge under a tested policy.

A hedge may introduce basis risk, execution costs and additional margin requirements.

---

# 36. HEDGING MANAGEMENT

Hedging aims to reduce selected exposures.

Types:
- Direct hedge.
- Correlation hedge.
- Options hedge.
- Futures hedge.
- Currency hedge.
- Portfolio hedge.

Before hedging, calculate:

- Original exposure.
- Hedge exposure.
- Net exposure.
- Gross exposure.
- Hedge cost.
- Basis risk.
- Correlation stability.
- Margin.
- Exit conditions.

A hedge does not automatically eliminate risk.

Avoid presenting a hedge as guaranteed protection.

---

# 37. TIME-BASED TRADE MANAGEMENT

A trade may have a maximum expected holding period.

Examples:
- Maximum number of candles.
- Session end.
- Intraday cutoff.
- Expiry date.
- Strategy-specific time stop.

A time stop is useful when a strategy depends on movement occurring within a defined window.

If the trade does not behave as expected:
- Reassess the thesis.
- Check opportunity cost.
- Check transaction costs.
- Apply the predefined exit rule.

Do not invent a time stop after the trade starts merely to justify closing it.

---

# 38. VOLATILITY REGIME CHANGES

Monitor changes in:
- ATR.
- Historical volatility.
- Implied volatility.
- Bollinger Band width.
- Spread.
- Market depth.
- Realized range.

Classify regimes:
- Low.
- Normal.
- High.
- Extreme.

A strategy designed for low volatility may behave poorly during extreme volatility.

Possible actions:
- Reduce exposure.
- Tighten risk under tested rules.
- Avoid new trades.
- Reassess targets.
- Exit if the strategy's regime condition fails.

Do not tighten a stop mechanically without considering normal market noise.

---

# 39. MARKET GAP AND CIRCUIT EVENT MANAGEMENT

A gap occurs when the next available price differs substantially from the previous price.

Potential causes:
- News.
- Earnings.
- Weekend closure.
- Exchange halt.
- Regulatory action.
- Low liquidity.
- Unexpected macro events.

A stop may execute beyond its trigger price.

For circuit-limited markets:
- Orders may not execute as expected.
- Exits may become unavailable.
- Liquidity may disappear.
- Broker restrictions may apply.

The system must clearly report the possibility of execution failure.

---

# 40. TRADE MONITORING FREQUENCY

Monitoring frequency must match the strategy.

Examples:
- Scalping: high-frequency monitoring.
- Intraday: session-based monitoring.
- Swing: candle-close and event-based monitoring.
- Positional: periodic and event-based monitoring.

Do not claim continuous live monitoring if the application is not actually connected to a live data feed.

Define:
- Last data timestamp.
- Next scheduled check.
- Monitoring frequency.
- Alert conditions.
- Stale-data threshold.

---

# 41. ALERT SYSTEM

Possible alerts:

- Entry triggered.
- Entry partially filled.
- Entry fully filled.
- Stop activated.
- Stop rejected.
- Stop modified.
- TP1 reached.
- TP2 reached.
- TP3 reached.
- Partial exit filled.
- Position fully closed.
- Margin warning.
- Liquidation warning.
- Daily loss limit reached.
- Abnormal slippage.
- Spread expansion.
- News event approaching.
- Data feed disconnected.
- Broker connection lost.
- Position mismatch detected.

Every alert must include:
- Trade ID.
- Instrument.
- Event.
- Timestamp.
- Verified status.
- Required action.

Never generate a fake execution notification.

---

# 42. AUTOMATED TRADE MANAGEMENT ARCHITECTURE

A future automated system should use independent modules:

1. Market Data Adapter.
2. Account Data Adapter.
3. Position Manager.
4. Order Manager.
5. Stop Manager.
6. Target Manager.
7. Risk Engine.
8. Portfolio Manager.
9. Event Calendar.
10. Alert Engine.
11. Trade Journal.
12. Broker Reconciliation.
13. Audit Logger.
14. Emergency Shutdown.

## 42.1 Data Flow

Market Data
    -> Signal Engine
    -> Trade State
    -> Risk Validation
    -> Order Manager
    -> Broker or Exchange
    -> Execution Confirmation
    -> Position Manager
    -> Risk Recalculation
    -> Trade Journal

## 42.2 Execution Rules

- Use unique order identifiers.
- Prevent duplicate orders.
- Validate order quantity.
- Validate tick size.
- Validate price precision.
- Confirm order status.
- Handle partial fills.
- Handle rejection.
- Handle timeout.
- Reconcile open orders.
- Reconcile actual positions.

## 42.3 Idempotency

Repeated processing of the same event must not accidentally create duplicate orders or duplicate exits.

Use idempotency keys where supported.

## 42.4 API Safety

- Never expose API secrets.
- Use least-privilege permissions.
- Prefer read-only permissions when possible.
- Disable withdrawals on trading API keys.
- Never store credentials in public repositories.
- Require explicit authorization for live execution.

---

# 43. PYTHON TRADE MANAGEMENT DATA MODEL

The system should eventually store each trade with a structured record.

Example:

```python
from dataclasses import dataclass
from typing import Optional

@dataclass
class TradeRecord:
    trade_id: str
    instrument: str
    market: str
    side: str
    strategy: str
    timeframe: str

    planned_entry: float
    average_entry: Optional[float]
    initial_stop: float
    current_stop: Optional[float]

    planned_quantity: float
    filled_quantity: float
    closed_quantity: float

    target_1: Optional[float] = None
    target_2: Optional[float] = None
    target_3: Optional[float] = None

    status: str = "PLANNED"
    entry_timestamp: Optional[str] = None
    exit_timestamp: Optional[str] = None
```

This is a starting data model, not a complete broker integration.

Production systems must support:
- Multiple fills.
- Multiple exit fills.
- Multiple stop orders.
- Multiple target orders.
- Contract-specific P&L.
- Currency conversion.
- Fees.
- Funding.
- Corporate actions.
- Broker reconciliation.

---

# 44. PYTHON TRADE MANAGEMENT FUNCTIONS

Required future functions:

- create_trade_plan()
- validate_trade_plan()
- submit_entry_order()
- confirm_entry_fill()
- reconcile_order_status()
- reconcile_position()
- calculate_average_entry()
- calculate_open_quantity()
- calculate_realized_pnl()
- calculate_unrealized_pnl()
- calculate_net_pnl()
- place_initial_stop()
- validate_stop_order()
- modify_stop()
- calculate_break_even()
- update_trailing_stop()
- place_target_orders()
- execute_partial_exit()
- validate_partial_exit()
- scale_in_position()
- scale_out_position()
- validate_additional_risk()
- evaluate_trade_invalidation()
- evaluate_early_exit()
- evaluate_time_stop()
- evaluate_news_risk()
- evaluate_portfolio_exposure()
- trigger_emergency_shutdown()
- create_trade_journal_entry()
- generate_trade_report()

Each function must return:
- Success or failure.
- Verified current state.
- Error details.
- Timestamp.
- Relevant order or trade identifier.

---

# 45. PYTHON PARTIAL EXIT VALIDATION EXAMPLE

This example validates a requested partial close for a simple quantity-based instrument.

```python
from decimal import Decimal, ROUND_FLOOR

def validate_partial_exit(
    open_quantity,
    requested_quantity,
    quantity_step,
    minimum_quantity
):
    open_qty = Decimal(str(open_quantity))
    requested = Decimal(str(requested_quantity))
    step = Decimal(str(quantity_step))
    minimum = Decimal(str(minimum_quantity))

    if open_qty <= 0:
        return {
            "approved": False,
            "reason": "No open position"
        }

    if requested <= 0:
        return {
            "approved": False,
            "reason": "Close quantity must be positive"
        }

    if step <= 0 or minimum <= 0:
        return {
            "approved": False,
            "reason": "Invalid instrument quantity rules"
        }

    if requested > open_qty:
        return {
            "approved": False,
            "reason": "Requested exit exceeds open quantity"
        }

    rounded = (
        (requested / step).to_integral_value(
            rounding=ROUND_FLOOR
        ) * step
    )

    if rounded < minimum:
        return {
            "approved": False,
            "reason": "Below minimum order quantity"
        }

    if rounded > open_qty:
        return {
            "approved": False,
            "reason": "Rounded quantity exceeds open position"
        }

    return {
        "approved": True,
        "close_quantity": str(rounded),
        "remaining_quantity": str(open_qty - rounded)
    }
```

This example does not submit orders or guarantee that an exchange will accept them.

---

# 46. ORDER RECONCILIATION

Order reconciliation compares internal application records with the broker or exchange.

Check:
- Open orders.
- Filled orders.
- Partially filled orders.
- Cancelled orders.
- Rejected orders.
- Open positions.
- Average entry.
- Remaining quantity.
- Stop orders.
- Target orders.
- Realized P&L.
- Fees.

If records disagree:

1. Mark RECONCILIATION_REQUIRED.
2. Stop new automated modifications.
3. Fetch fresh broker data.
4. Compare order identifiers.
5. Compare fill quantities.
6. Identify duplicate or missing orders.
7. Notify the user.
8. Follow the approved emergency policy.

Never assume internal records are more accurate than confirmed broker records.

---

# 47. EMERGENCY MANAGEMENT

Emergency triggers include:

- Broker disconnection.
- Exchange outage.
- Missing protective stop.
- Duplicate position.
- Unexpected position increase.
- Margin warning.
- Liquidation danger.
- Abnormal spread.
- Extreme slippage.
- Market data failure.
- Risk engine error.
- Unexpected account equity drop.

Emergency process:

1. Stop new entries.
2. Freeze nonessential automated modifications.
3. Retrieve verified position state if possible.
4. Identify unprotected exposure.
5. Notify the user.
6. Follow the configured emergency position policy.
7. Record all actions.
8. Require reconciliation before normal operation resumes.

Do not assume an emergency shutdown can close a position during an exchange outage.

---

# 48. TRADE JOURNAL MASTER SYSTEM

Every completed trade should be recorded.

Required fields:

- Trade ID.
- Instrument.
- Market.
- Direction.
- Strategy.
- Timeframe.
- Setup.
- Planned entry.
- Actual entry.
- Initial stop.
- Final stop.
- Targets.
- Quantity.
- Partial exits.
- Final exit.
- Gross P&L.
- Fees.
- Net P&L.
- Risk amount.
- R multiple.
- Maximum Adverse Excursion.
- Maximum Favorable Excursion.
- Entry slippage.
- Exit slippage.
- Holding time.
- Exit reason.
- Rule adherence.
- Emotional notes.
- Screenshots or chart references.
- Data source.
- Timestamp.

Do not overwrite the original trade plan.

Store modifications as separate events.

---

# 49. MAE AND MFE ANALYSIS

## 49.1 Maximum Adverse Excursion

MAE measures the maximum movement against a trade while it was open.

## 49.2 Maximum Favorable Excursion

MFE measures the maximum favorable movement while a trade was open.

Both metrics should be normalized by:
- Initial risk.
- Price distance.
- Account currency.
- Contract multiplier where applicable.

Use MAE/MFE to evaluate:
- Stop placement.
- Target placement.
- Early exits.
- Trailing rules.
- Entry quality.

Do not infer that a trade would have closed at the maximum favorable excursion.

That price may not have been executable.

---

# 50. TRADE PERFORMANCE ANALYSIS

Track:

- Net profit.
- Gross profit.
- Gross loss.
- Win rate.
- Average win.
- Average loss.
- Expectancy.
- Profit factor.
- Average R.
- Maximum drawdown.
- Recovery factor.
- Holding time.
- Slippage.
- Fees.
- MAE.
- MFE.
- Strategy performance.
- Instrument performance.
- Timeframe performance.
- Market-regime performance.
- Session performance.
- Rule violation rate.

Use adequate sample sizes and disclose uncertainty.

Do not rank strategies using a single metric.

---

# 51. BACKTESTING TRADE MANAGEMENT RULES

Trade management rules must be tested independently and together.

Test:
- Initial stop.
- Break-even trigger.
- Trailing-stop method.
- Partial booking.
- Target multiples.
- Time stop.
- Early exit.
- Re-entry.
- Scaling.
- Event avoidance.
- Maximum holding time.

Use:
- Historical data.
- Out-of-sample testing.
- Walk-forward analysis.
- Sensitivity analysis.
- Transaction cost modeling.
- Slippage modeling.
- Gap simulation.

Avoid look-ahead bias and unrealistic intrabar assumptions.

If candle data cannot determine which of multiple price levels was reached first, mark the outcome ambiguous or use higher-resolution data.

---

# 52. MONTE CARLO TRADE MANAGEMENT TESTING

Simulate different possible trade sequences and execution conditions.

Possible tests:
- Randomized trade order.
- Bootstrap trade outcomes.
- Variable slippage.
- Variable fees.
- Delayed execution.
- Missed fills.
- Partial fills.
- Stop gaps.
- Target gaps.
- Losing streaks.
- Volatility shocks.
- Correlation shocks.

Record:
- Ending equity.
- Drawdown.
- Trade count.
- Average R.
- Loss limit breaches.
- Execution failures.
- Margin events.
- Time to recovery.

Clearly label all simulated results.

---

# 53. TEN-MILLION SCENARIO TESTING FRAMEWORK

Project target: support up to 10,000,000 distinct trade-management scenarios where code, data and compute resources permit.

The system must distinguish:

1. Historical trade replay.
2. Entry timing variations.
3. Stop management variations.
4. Target management variations.
5. Partial exit combinations.
6. Trailing-stop parameters.
7. Time-stop configurations.
8. Execution delay scenarios.
9. Slippage scenarios.
10. Fee scenarios.
11. Gap scenarios.
12. Volatility scenarios.
13. Market regime variations.
14. Re-entry scenarios.
15. Portfolio interaction scenarios.

Every scenario must have a unique configuration and recorded result.

Record:
- Scenario ID.
- Input data.
- Parameters.
- Trade ID.
- Execution assumptions.
- Initial equity.
- Final equity.
- Drawdown.
- Net P&L.
- Costs.
- Risk breaches.
- Execution failures.
- Test status.

Never claim 10 million scenarios were executed unless verifiable execution records exist.

Do not count duplicate configurations as distinct scenarios without disclosing the method.

---

# 54. TRADE MANAGEMENT FAILURE CASES

The system must identify:

- Stop rejected.
- Stop quantity mismatch.
- Target quantity mismatch.
- Duplicate entry.
- Duplicate exit.
- Unexpected partial fill.
- Position mismatch.
- Wrong-side stop.
- Invalid tick size.
- Insufficient margin.
- Stale data.
- Broker outage.
- Exchange halt.
- Unavailable liquidity.
- API timeout.
- API rate limit.
- Unexpected fees.
- Contract specification change.
- Expiry or settlement issue.

Every failure must have:
- Severity.
- Timestamp.
- Trade ID.
- Actual state.
- Expected state.
- Recovery action.
- User notification.

---

# 55. AI DECISION ENGINE

The AI must select one of the following actions.

## HOLD

Use when:
- Original thesis remains valid.
- Risk remains acceptable.
- No required exit condition has occurred.
- Data is sufficiently reliable.

## MODIFY SL

Use when:
- A predefined stop adjustment condition is confirmed.
- New stop improves or maintains the approved risk.
- Quantity and order rules are valid.

## MOVE TO BREAK-EVEN

Use when:
- The tested trigger is satisfied.
- Cost-adjusted break-even is calculated.
- The modification does not violate strategy rules.

## TRAIL STOP

Use when:
- Trailing activation condition is confirmed.
- The trailing calculation is valid.
- Order modification is supported.

## PARTIAL EXIT

Use when:
- A predefined partial exit condition is met.
- Close quantity is valid.
- Remaining orders are reconciled.

## FULL EXIT

Use when:
- Stop is triggered.
- Thesis is invalidated.
- Strategy exit occurs.
- Emergency policy requires exit.
- User explicitly instructs exit.

## REDUCE EXPOSURE

Use when:
- Portfolio risk increases.
- Correlation risk becomes unacceptable.
- Margin becomes unsafe.
- Volatility changes materially.

## WAIT

Use when:
- Confirmation is missing.
- Data is stale.
- Order state is uncertain.
- Management condition is incomplete.

## NO TRADE / REJECT

Use when:
- Trade is invalid.
- Risk budget is exceeded.
- Required instrument data is missing.
- Position cannot be managed safely.

---

# 56. FINAL TRADE MANAGEMENT REPORT

Every open-trade analysis should use this format:

## A. Trade Information

- Instrument:
- Market:
- Direction:
- Strategy:
- Timeframe:
- Trade ID:
- Status:

## B. Entry Information

- Planned entry:
- Actual average entry:
- Filled quantity:
- Remaining quantity:
- Entry slippage:

## C. Risk Information

- Initial stop:
- Current stop:
- Initial risk:
- Current estimated risk:
- Risk percentage:
- Margin usage:
- Portfolio exposure:

## D. Profit Information

- Current price:
- Unrealized P&L:
- Realized P&L:
- Net P&L:
- TP1:
- TP2:
- TP3:
- Current R multiple:

## E. Market Condition

- Trend:
- Structure:
- Momentum:
- Volatility:
- Volume:
- Liquidity:
- News:
- Important levels:

## F. Management Decision

- HOLD
- MODIFY SL
- BREAK-EVEN
- TRAIL STOP
- PARTIAL EXIT
- FULL EXIT
- REDUCE EXPOSURE
- WAIT
- NO TRADE

## G. Reason

Explain the decision in simple natural Hinglish.

## H. Risk Warning

Mention missing data, slippage, liquidity, event or execution risks.

## I. Next Monitoring Condition

Specify the exact price, candle close, event or condition that requires the next review.

---

# 57. USER INTERACTION RULES

If the user asks:

"Trade hold karu ya exit?"

The AI should:
1. Identify the instrument.
2. Ask for or inspect current position details.
3. Identify the original entry and stop.
4. Review the current chart.
5. Check the trade thesis.
6. Check current risk.
7. Give a conditional management decision.

If the user asks:

"SL kahan karu?"

The AI should:
1. Identify current position.
2. Identify the original stop.
3. Review current structure.
4. Check strategy rules.
5. Calculate revised risk.
6. Explain the modification condition.

If the user asks:

"Profit book karu?"

The AI should:
1. Check current profit.
2. Check original target.
3. Check market structure.
4. Check risk and portfolio exposure.
5. Evaluate partial versus full exit.
6. Explain costs and uncertainty.

Never give a precise live instruction without reliable current data.

---

# 58. SECURITY AND LIVE EXECUTION RULES

Analysis and execution are separate.

The AI may explain a possible action without claiming that it has executed it.

Live trading requires:
- Explicit user authorization.
- Verified account connection.
- Verified instrument.
- Verified quantity.
- Verified order details.
- Risk approval.
- Secure API handling.
- Execution confirmation.

Never:
- Ask the user to share API secrets in chat.
- Expose private credentials.
- Place unauthorized trades.
- Claim an order was placed without confirmation.
- Claim a position was closed without confirmation.
- Ignore a broker rejection.
- Hide partial fills.

---

# 59. FINAL NON-NEGOTIABLE RULES

1. Trade management begins before entry.
2. Preserve the original trade thesis.
3. Track actual fills, not assumed fills.
4. Confirm protective orders.
5. Never widen stops emotionally.
6. Never ignore current open risk.
7. Recalculate after every quantity change.
8. Manage partial exits correctly.
9. Check portfolio-level exposure.
10. Respect instrument-specific contract rules.
11. Treat options as nonlinear instruments.
12. Consider slippage and gap risk.
13. Do not assume continuous live monitoring.
14. Never invent live prices or order status.
15. Never claim execution without confirmation.
16. Never claim simulation without recorded execution.
17. Do not promise profitable outcomes.
18. Do not use martingale as a recovery shortcut.
19. Prefer safety when state is uncertain.
20. Explain every decision in natural Hinglish.

---

# END OF TRADE MANAGEMENT MASTER ENCYCLOPEDIA
