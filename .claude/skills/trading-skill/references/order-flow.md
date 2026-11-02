
# ORDER FLOW ANALYSIS MASTER ENCYCLOPEDIA
## AI Trading Analyst — Complete A to Z Order Flow Research & Trading System
### Version 1.0

---

# 1. MISSION AND OBJECTIVE

This module defines a complete Order Flow Analysis system for understanding buying pressure, selling pressure, executed transactions, resting liquidity, market participation and auction behavior.

The objective is to determine:

- Who is aggressively buying?
- Who is aggressively selling?
- Where are orders being executed?
- Where is liquidity available?
- Is buying or selling pressure increasing?
- Is aggressive activity producing price movement?
- Is the market absorbing aggressive orders?
- Is a breakout supported by actual participation?
- Is the market showing exhaustion?
- Is price accepting or rejecting a particular level?
- Is there evidence supporting continuation or reversal?

Supported markets:

- Forex
- Cryptocurrency
- Indian equities
- Global equities
- Indices
- Futures
- Commodities
- Options

The system must distinguish actual market data from inferred institutional activity.

**Important:** Order flow data cannot reliably identify the exact identity of every buyer, seller, institution or market maker.

---

# 2. ORDER FLOW FUNDAMENTALS

## 2.1 What is Order Flow?

Order Flow is the study of orders and transactions entering and interacting with the market.

It examines:

- Executed buy transactions
- Executed sell transactions
- Bid-side activity
- Ask-side activity
- Resting limit orders
- Market depth
- Volume
- Trade intensity
- Liquidity
- Order-book changes
- Price response

Traditional technical analysis mainly studies price and derived indicators.

Order Flow attempts to examine the activity behind price movement.

## 2.2 Three important market components

### Aggressive buyers

Buyers who execute against available ask liquidity.

### Aggressive sellers

Sellers who execute against available bid liquidity.

### Passive liquidity providers

Participants placing resting limit orders that may be executed by aggressive orders.

Do not automatically classify every aggressive buyer as an institution or every limit order as institutional activity.

## 2.3 Market auction process

Markets continuously match buyers and sellers.

Important concepts:

- Price discovery
- Auction acceptance
- Auction rejection
- Value area
- Fair value
- Liquidity
- Volume concentration
- Market imbalance

A price level with heavy trading may indicate acceptance, but context is essential.

---

# 3. ORDER TYPES

Understand these order types:

1. Market Buy
2. Market Sell
3. Limit Buy
4. Limit Sell
5. Stop Buy
6. Stop Sell
7. Stop-Limit
8. Stop-Market
9. Iceberg Order
10. Hidden Order
11. Post-Only Order
12. Immediate-or-Cancel
13. Fill-or-Kill
14. Good-Till-Cancelled
15. Good-Till-Date
16. Reduce-Only
17. Bracket Order
18. One-Cancels-the-Other

Availability and execution rules depend on the exchange and broker.

## 3.1 Market orders

A market order seeks immediate execution against available opposite-side liquidity.

Risks:

- Slippage
- Spread
- Partial execution
- Market impact
- Price gaps

## 3.2 Limit orders

A limit order specifies the maximum buying price or minimum selling price.

Risks:

- No execution
- Partial execution
- Queue position
- Adverse selection

A limit order touching a price does not guarantee a fill.

## 3.3 Stop orders

Stop orders become active after a trigger condition.

A stop-market order can execute beyond its trigger during fast movement.

A stop-limit order may remain unfilled.

---

# 4. BID, ASK AND SPREAD

## 4.1 Bid

The highest displayed price a buyer is currently willing to pay.

## 4.2 Ask

The lowest displayed price a seller is currently willing to accept.

## 4.3 Spread

Spread is the difference between ask and bid.

Formula:

Spread = Ask - Bid

Example:

Bid = 100.00

Ask = 100.05

Spread = 0.05

## 4.4 Mid-price

Mid-price:

Mid = (Bid + Ask) / 2

Mid-price is a reference calculation, not necessarily an executable price.

## 4.5 Spread analysis

Study:

- Average spread
- Maximum spread
- Minimum spread
- Spread expansion
- Spread contraction
- Spread during news
- Spread during market opening
- Spread during low liquidity
- Spread by instrument

A sudden spread increase may indicate reduced liquidity or increased uncertainty.

It is not automatically a buy or sell signal.

---

# 5. LEVEL 1, LEVEL 2 AND LEVEL 3 DATA

## 5.1 Level 1 Market Data

Usually includes:

- Best Bid
- Best Ask
- Bid Size
- Ask Size
- Last Traded Price
- Last Traded Quantity
- Volume
- Timestamp

Level 1 data gives a limited view of the market.

## 5.2 Level 2 Market Data

May include multiple price levels:

- Bid prices
- Bid quantities
- Ask prices
- Ask quantities
- Number of displayed levels
- Order-book updates

It helps analyze visible market depth.

## 5.3 Level 3 Market Data

Where available, may provide order-level information such as:

- Individual displayed orders
- Order identifiers
- Additions
- Modifications
- Cancellations
- Executions

Level 3 access is exchange-specific and may require licensed data.

Not every market provides Level 3 information.

## 5.4 Important limitations

Displayed order-book liquidity can disappear.

Orders can be cancelled, modified or replaced.

Hidden liquidity may not appear in displayed depth.

A snapshot of the order book does not reveal the full sequence of market events.

Never treat visible order-book size as guaranteed executable liquidity.

---

# 6. MARKET DEPTH

Market Depth represents available displayed liquidity at different price levels.

Analyze:

- Bid depth
- Ask depth
- Total bid quantity
- Total ask quantity
- Depth imbalance
- Depth concentration
- Depth changes
- Liquidity gaps
- Order-book stability

## 6.1 Depth Imbalance

One possible formula:

Depth Imbalance = (Bid Depth - Ask Depth) / (Bid Depth + Ask Depth)

If bid depth is 1,000 units and ask depth is 600 units:

Depth Imbalance = 400 / 1,600 = 0.25

This indicates greater displayed bid quantity in the measured depth.

It does not guarantee that price will rise.

## 6.2 Weighted Depth Imbalance

Give greater weight to prices closer to the best bid and ask.

Possible weighting:

Weight at level n = 1 / n

Weighted Bid Depth = Sum of weighted bid quantities.

Weighted Ask Depth = Sum of weighted ask quantities.

Weighted Imbalance:

(Bid Weighted Depth - Ask Weighted Depth) /
(Bid Weighted Depth + Ask Weighted Depth)

The weighting model must be documented and tested.

---

# 7. TIME AND SALES

Time and Sales is a chronological record of executed trades.

Common fields:

- Timestamp
- Trade Price
- Trade Quantity
- Trade Direction Classification
- Exchange
- Trade ID
- Execution Type, if supplied

Analyze:

- Large transactions
- Repeated executions
- Trade frequency
- Trade size distribution
- Aggressive buying
- Aggressive selling
- Sudden activity
- Price response

## 7.1 Trade direction classification

A trade may be classified using:

- Exchange-provided aggressor flag
- Bid/ask comparison
- Tick rule
- Quote rule

If a trade occurs at or near the ask, it may be classified as buyer-initiated.

If it occurs at or near the bid, it may be classified as seller-initiated.

Classification can be uncertain, especially with delayed quotes, midpoint executions or fragmented data.

Always record the classification method.

---

# 8. VOLUME ANALYSIS

Volume represents the amount of activity during a period.

Study:

- Total volume
- Relative volume
- Volume acceleration
- Volume contraction
- Volume distribution
- Buy-initiated volume
- Sell-initiated volume
- Volume by price
- Session volume
- Abnormal volume

## 8.1 Relative Volume

Relative Volume compares current volume with a historical reference.

Example:

RVOL = Current Volume / Average Reference Volume

Current volume = 20,000

Average reference volume = 10,000

RVOL = 2.0

This means current volume is twice the selected reference average.

Comparison must use equivalent time windows when intraday volume patterns vary by session.

## 8.2 Volume confirmation

A breakout with elevated volume may have stronger participation than a breakout with unusually low volume.

However:

- High volume does not guarantee continuation.
- Low volume does not guarantee reversal.
- Volume must be interpreted with price response and market context.

## 8.3 Volume exhaustion

Possible exhaustion clues:

- Very high volume after an extended move
- Reduced price progress
- Large rejection wick
- Repeated failure to advance
- Divergence between volume and price movement

These are clues, not automatic reversal signals.

---

# 9. VOLUME DELTA

Volume Delta measures the difference between buyer-initiated and seller-initiated executed volume.

Formula:

Delta = Aggressive Buy Volume - Aggressive Sell Volume

Example:

Aggressive Buy Volume = 8,000

Aggressive Sell Volume = 5,000

Delta = +3,000

Positive delta indicates greater classified aggressive buying.

Negative delta indicates greater classified aggressive selling.

Zero delta indicates equal classified volumes.

## 9.1 Delta limitations

Delta depends on accurate trade classification.

Different providers can produce different results.

A positive delta does not guarantee a bullish candle.

A negative delta does not guarantee a bearish candle.

---

# 10. CUMULATIVE VOLUME DELTA (CVD)

CVD accumulates volume delta over time.

Formula:

CVD(t) = CVD(t-1) + Delta(t)

Analyze:

- Rising CVD
- Falling CVD
- Flat CVD
- Price-CVD divergence
- Session CVD
- Daily CVD
- Weekly CVD
- Anchored CVD

## 10.1 Bullish CVD divergence

Possible condition:

- Price makes a lower low.
- CVD makes a higher low.

This may suggest selling aggression is weakening.

Confirmation is still required.

## 10.2 Bearish CVD divergence

Possible condition:

- Price makes a higher high.
- CVD makes a lower high.

This may suggest buying aggression is weakening.

It is not sufficient alone to enter a short position.

## 10.3 CVD interpretation

Always examine:

- Timeframe
- Data source
- Session boundary
- Trade classification
- Exchange coverage
- Price structure
- Volume conditions

Crypto CVD from one exchange is not necessarily representative of the entire cryptocurrency market.

Forex CVD from one broker is not centralized global Forex volume.

---

# 11. FOOTPRINT CHARTS

Footprint charts show traded volume at individual price levels within a candle or bar.

Possible fields:

- Price level
- Bid volume
- Ask volume
- Total volume
- Delta
- Number of trades

## 11.1 Footprint types

- Bid x Ask Footprint
- Volume Footprint
- Delta Footprint
- Imbalance Footprint
- Stacked Imbalance Footprint

## 11.2 Footprint interpretation

Look for:

- Strong buying at higher prices
- Strong selling at lower prices
- Absorption
- Exhaustion
- Imbalance
- Rejection
- Acceptance
- Failed auction

## 11.3 Footprint imbalance

A buy imbalance compares ask volume at one price with bid volume at a lower price.

A sell imbalance compares bid volume at one price with ask volume at a higher price.

The exact comparison and ratio depend on the platform's footprint settings.

Do not mix different footprint definitions without documenting them.

## 11.4 Stacked imbalance

Several consecutive price levels may show directional imbalance.

Potential interpretations:

- Aggressive buying pressure
- Aggressive selling pressure
- Momentum
- Breakout participation

Require price confirmation and context.

---

# 12. ORDER FLOW IMBALANCE

Order Flow Imbalance can refer to imbalance in executed trades or changes in displayed order-book liquidity.

Keep these two concepts separate.

### Executed-volume imbalance

Difference between aggressive buy and sell volume.

### Order-book imbalance

Difference between visible bid and ask liquidity.

### Order-book event imbalance

A measure of changes caused by:

- New limit orders
- Cancellations
- Modifications
- Executions

Never treat all three as the same measurement.

---

# 13. ABSORPTION

Absorption occurs when aggressive trading activity is met by passive liquidity and price makes limited progress.

Example:

- Buyers aggressively purchase.
- Ask-side liquidity continues to replenish.
- Price struggles to move higher.

Possible interpretation: buying pressure is being absorbed.

Opposite example:

- Sellers aggressively hit bids.
- Bid liquidity replenishes.
- Price struggles to move lower.

Possible interpretation: selling pressure is being absorbed.

## 13.1 Absorption detection clues

- High executed volume
- Limited price movement
- Repeated transactions near a level
- Replenishing displayed liquidity
- Repeated failed attempts to break a level

## 13.2 Absorption limitations

A candle alone cannot prove absorption.

Accurate analysis may require trade and order-book event data.

Do not automatically call every rejection candle absorption.

---

# 14. ICEBERG ORDERS AND HIDDEN LIQUIDITY

An iceberg order displays only part of a larger order.

Possible clues:

- Repeated executions at the same price
- Displayed quantity replenishment
- Large executed volume
- Limited price movement

However, these clues do not conclusively prove an iceberg order.

Hidden orders may be invisible.

Use labels such as:

- Possible Replenishment
- Potential Hidden Liquidity
- Suspected Iceberg Activity
- Unconfirmed

Never claim to know the exact identity or intention of the participant.

---

# 15. LIQUIDITY ANALYSIS

Liquidity describes how easily an asset can be bought or sold without causing substantial price movement.

Analyze:

- Bid/ask spread
- Market depth
- Trading volume
- Turnover
- Execution quality
- Price impact
- Order-book stability
- Liquidity concentration

## 15.1 Liquidity zones

Study:

- Previous Day High
- Previous Day Low
- Previous Week High
- Previous Week Low
- Equal Highs
- Equal Lows
- Session Highs
- Session Lows
- Swing Highs
- Swing Lows
- Round Numbers
- Volume Profile Nodes

These levels may attract trading interest.

Do not assume all stop orders are located at obvious technical levels.

## 15.2 Liquidity sweep

A liquidity sweep describes price moving through a reference level and then potentially reversing.

Analyze:

- Level breached
- Volume
- Delta
- Price rejection
- Closing location
- Subsequent structure
- Market regime

A sweep is not confirmed merely because a wick crosses a previous high or low.

## 15.3 Liquidity vacuum

A liquidity vacuum occurs when available liquidity becomes thin.

Potential effects:

- Rapid price movement
- Increased slippage
- Gaps between executed prices
- Unstable spreads

---

# 16. DEPTH OF MARKET (DOM)

DOM displays resting buy and sell liquidity at different prices.

Analyze:

- Best bid
- Best ask
- Quantity at each level
- Changes in depth
- Large displayed orders
- Replenishment
- Cancellation
- Spread
- Order-book pressure

## 16.1 DOM limitations

Large displayed orders may be cancelled.

Displayed liquidity can be misleading.

DOM does not show every hidden or off-book transaction.

A DOM snapshot is less informative than a complete time-ordered event stream.

## 16.2 DOM trading principles

Do not buy solely because bid quantity is larger.

Do not sell solely because ask quantity is larger.

Confirm with:

- Actual executions
- Price response
- Spread
- Market structure
- Volume
- Risk conditions

---

# 17. ORDER BOOK DYNAMICS

Study the lifecycle of orders:

1. New order.
2. Displayed order.
3. Modification.
4. Partial execution.
5. Cancellation.
6. Complete execution.

Possible analytical features:

- Order arrival rate
- Cancellation rate
- Execution rate
- Queue imbalance
- Depth changes
- Spread changes
- Price impact

Order-book event data must be timestamped and ordered correctly.

## 17.1 Spoofing and layering

Spoofing and layering refer to manipulative order-book behaviors subject to applicable laws and exchange rules.

Do not assume a large cancelled order proves manipulation.

Do not provide unsupported accusations against specific traders or institutions.

This system is for analysis and detection of suspicious patterns, not market manipulation.

---

# 18. VOLUME PROFILE

Volume Profile shows how much volume traded at different price levels over a selected period.

Important concepts:

- POC: Point of Control
- VAH: Value Area High
- VAL: Value Area Low
- HVN: High Volume Node
- LVN: Low Volume Node
- Value Area
- Developing POC
- Session Profile
- Composite Profile
- Fixed Range Profile
- Visible Range Profile

## 18.1 Point of Control

POC is the price level with the highest traded volume within the selected profile.

## 18.2 Value Area

Value Area is a selected range containing a specified proportion of volume.

Many platforms use approximately 70%, but the setting can vary.

Do not assume every platform calculates it identically.

## 18.3 HVN

High Volume Nodes are areas with relatively concentrated traded volume.

Possible interpretation:

- Acceptance
- Balance
- Consolidation
- Potential support/resistance

## 18.4 LVN

Low Volume Nodes are areas with relatively low traded volume.

Possible interpretation:

- Rejection
- Rapid price movement
- Low acceptance

Context determines the actual meaning.

---

# 19. VWAP AND ANCHORED VWAP

VWAP:

VWAP = Sum(Price x Volume) / Sum(Volume)

The exact price input may be based on trade prices or candle-derived approximations.

Study:

- Session VWAP
- Anchored VWAP
- VWAP deviation
- VWAP reclaim
- VWAP rejection
- VWAP slope
- Price-VWAP relationship

Anchoring examples:

- Session open
- Earnings announcement
- Major swing high
- Major swing low
- Important news event

Do not use a future event to anchor historical analysis before that event occurred.

---

# 20. ORDER FLOW AND PRICE ACTION

Combine executed activity with market structure.

Study:

- Higher High
- Higher Low
- Lower High
- Lower Low
- Break of Structure
- Change of Character
- Breakout
- Breakdown
- Pullback
- Retest
- Rejection
- Consolidation
- Range expansion

## 20.1 Bullish confirmation

Possible combination:

1. Price reaches a meaningful support or liquidity zone.
2. Selling aggression increases.
3. Price makes limited downside progress.
4. Bid liquidity appears to replenish.
5. CVD or delta behavior improves.
6. Price reclaims a key level.
7. Market structure confirms a bullish shift.

Only enter if the complete strategy rules and risk conditions are satisfied.

## 20.2 Bearish confirmation

Possible combination:

1. Price reaches resistance or a liquidity zone.
2. Buying aggression increases.
3. Price makes limited upside progress.
4. Ask liquidity appears to replenish.
5. CVD or delta behavior weakens.
6. Price loses a key level.
7. Market structure confirms a bearish shift.

These are research templates, not guaranteed trading signals.

---

# 21. ORDER FLOW DIVERGENCE

Study divergences between:

- Price and Delta
- Price and CVD
- Price and Volume
- Price and Open Interest
- Price and Market Depth
- Price and Trade Frequency

## 21.1 Bullish divergence

Price weakens while a selected order-flow measurement improves.

## 21.2 Bearish divergence

Price strengthens while a selected order-flow measurement weakens.

## 21.3 Confirmation rules

Check:

- Trend
- Timeframe
- Session
- Data quality
- Liquidity
- Price structure
- Volatility
- Execution costs

A divergence can continue for a long time before price reverses.

---

# 22. OPEN INTEREST ANALYSIS

Open Interest represents outstanding derivative contracts that have not been closed, exercised or otherwise settled.

Study:

- Price increase with OI increase
- Price decrease with OI increase
- Price increase with OI decrease
- Price decrease with OI decrease

These combinations can provide context about positioning and participation.

But OI alone does not reveal exact long and short identities or predict direction.

Always consider contract structure, expiry, exchange and data timestamp.

---

# 23. FUNDING RATE AND LIQUIDATION DATA

Particularly relevant to cryptocurrency derivatives.

Study:

- Funding rate
- Funding history
- Open interest
- Liquidation volume
- Long liquidation
- Short liquidation
- Exchange differences
- Basis
- Premium or discount

A funding rate can indicate positioning pressure, but it is not a direct buy or sell signal.

Liquidation feeds may be incomplete or exchange-specific.

Do not treat a public liquidation feed as a complete record of all market liquidations.

---

# 24. SESSION-BASED ORDER FLOW

Analyze market sessions:

- Asian Session
- London Session
- New York Session
- London-New York Overlap
- Exchange-specific opening and closing periods

For each session, record:

- Opening price
- High
- Low
- Volume
- Delta
- CVD
- Spread
- Volatility
- Liquidity
- VWAP
- Session profile

Use correct daylight-saving and exchange calendar rules.

Forex and crypto do not share the same centralized trading-session structure.

---

# 25. NEWS AND ORDER FLOW

News can produce:

- Sudden volume increase
- Spread expansion
- Liquidity withdrawal
- Fast repricing
- Stop triggering
- Order-book instability
- Volatility spikes

Before interpreting news-related order flow:

1. Verify event time.
2. Verify news source.
3. Check actual versus forecast.
4. Check instrument sensitivity.
5. Examine pre-event liquidity.
6. Examine post-event execution.
7. Account for spread and slippage.
8. Check whether the data feed is delayed.

Do not assume a large transaction after news reveals institutional positioning.

---

# 26. ORDER FLOW STRATEGY LIBRARY

The following are research templates. Each requires objective entry, exit, risk and validation rules.

## Strategy 1: Delta Confirmation Breakout

Conditions:

- A meaningful resistance or support level exists.
- Price approaches the level.
- Executed volume increases.
- Delta confirms directional aggression.
- Price closes beyond the level.
- Spread and execution conditions are acceptable.

Invalidation:

- Failed breakout
- Immediate level reclaim
- Excessive slippage
- Risk limit violation

## Strategy 2: CVD Divergence Reversal

Conditions:

- Price reaches a predefined extreme.
- CVD divergence is present.
- Market structure shows a shift.
- Price confirms the reversal.

Invalidation:

- Price continues the original trend.
- Divergence disappears.
- Stop-loss is reached.

## Strategy 3: Absorption Reversal

Conditions:

- Aggressive trading volume increases near a meaningful level.
- Price progress becomes limited.
- Replenishment or repeated rejection is observed.
- Subsequent price action confirms reversal.

Do not use candle appearance alone as proof of absorption.

## Strategy 4: Footprint Imbalance Continuation

Conditions:

- Market is trending.
- Footprint shows directional imbalance.
- Price structure supports continuation.
- Pullback holds a defined level.
- Risk/reward meets the predefined requirement.

## Strategy 5: VWAP Reclaim

Conditions:

- Price moves below session VWAP.
- Price reclaims VWAP.
- Volume and order flow confirm the move.
- Market structure supports the trade.

## Strategy 6: Liquidity Sweep with Delta Shift

Conditions:

- A predefined liquidity level is breached.
- Price fails to maintain acceptance beyond the level.
- Delta behavior changes.
- Structure confirms a shift.

## Strategy 7: Volume Profile Acceptance

Conditions:

- Price interacts with POC, VAH or VAL.
- Volume profile behavior is documented.
- Price acceptance or rejection is confirmed.
- Risk is defined.

## Strategy 8: Failed Auction

Conditions:

- Price attempts to establish value beyond a reference extreme.
- Acceptance fails.
- Price returns into the previous range.
- Execution and risk conditions remain valid.

## Strategy 9: Order Book Imbalance with Execution Confirmation

Conditions:

- Measured depth imbalance is present.
- Actual trades support the direction.
- Liquidity is stable enough.
- Spread and slippage are acceptable.

Do not trade based on a static DOM snapshot alone.

## Strategy 10: CVD Trend Continuation

Conditions:

- Price trend is established.
- CVD supports the trend.
- Pullbacks show weakening countertrend aggression.
- Price confirms continuation.

---

# 27. MULTI-TIMEFRAME ORDER FLOW

Support:

- Tick level
- 1-minute
- 3-minute
- 5-minute
- 15-minute
- 30-minute
- 1-hour
- 4-hour
- Daily
- Weekly

Higher timeframe:

- Overall structure
- Major liquidity
- Important volume zones
- Trend and regime

Lower timeframe:

- Execution
- Delta
- Footprint
- Absorption
- Entry confirmation

Never use an unfinished higher-timeframe candle as if it were finalized.

Different data frequencies can produce different delta and volume measurements.

---

# 28. MARKET-SPECIFIC ORDER FLOW RULES

## 28.1 Forex

Important limitations:

- Forex is decentralized.
- There is no single complete global order book.
- Broker volume may represent tick activity rather than centralized traded volume.
- Broker-specific order flow is not necessarily representative of the whole market.

Use:

- Broker bid/ask data
- Tick volume
- Verified futures proxy data where appropriate
- Currency futures volume
- Spread
- Session liquidity

Label proxy data clearly.

## 28.2 Cryptocurrency

Consider:

- Exchange-specific order books
- Exchange fragmentation
- Spot and derivatives differences
- Perpetual funding
- Liquidations
- Open interest
- Exchange outages
- Wash trading concerns
- Stablecoin liquidity

Do not combine exchange data without normalization and source documentation.

## 28.3 Indian equities

Consider:

- NSE/BSE data
- Exchange depth
- Lot and tick specifications
- Trading sessions
- Market-wide circuit limits
- Intraday liquidity
- Corporate actions
- Broker data limitations

Use only authorized market data.

## 28.4 Global equities

Consider:

- Exchange fragmentation
- Lit and off-exchange trading
- Auctions
- Trading halts
- Market data entitlements
- Corporate actions
- Time-zone differences

## 28.5 Futures and commodities

Consider:

- Contract expiry
- Rollover
- Contract multiplier
- Tick value
- Centralized exchange volume
- Delivery rules
- Open interest
- Spread between contracts

## 28.6 Options

Consider:

- Option-specific volume
- Open interest
- Bid/ask spread
- Implied volatility
- Greeks
- Strike liquidity
- Expiry
- Exercise and assignment

High option volume does not automatically reveal whether the buyer or seller opened a position.

---

# 29. DATA REQUIREMENTS AND API INTEGRATION

The system may connect to:

- Exchange market data APIs
- Broker APIs
- Licensed tick data
- Order-book feeds
- Historical trade feeds
- Volume profile data
- Options chain APIs

Every connection must define:

- API provider
- Endpoint
- Authentication method
- Permissions
- Rate limits
- Data fields
- Timestamp format
- Update frequency
- Error handling
- Licensing restrictions

Never invent API endpoints, credentials or available data fields.

Never expose API keys in public repositories.

Use environment variables or a secure secret manager.

## 29.1 Data freshness

Display:

- Data timestamp
- Last update time
- Data delay
- Feed status
- Missing updates
- Source

If the feed is stale, the system must not present the result as live order flow.

---

# 30. ORDER FLOW CALCULATION ENGINE

Implement separate calculation modules for:

- Bid/ask spread
- Mid-price
- Depth imbalance
- Weighted depth imbalance
- Volume delta
- Cumulative volume delta
- Relative volume
- Trade intensity
- Order arrival rate
- Cancellation rate
- Execution rate
- Volume profile
- VWAP
- Anchored VWAP
- Footprint imbalance
- Absorption candidates
- Price impact

Each calculation must define:

- Input data
- Formula
- Time window
- Sampling frequency
- Data source
- Missing-data behavior
- Limitations

Do not calculate a metric when required fields are unavailable.

Return INSUFFICIENT DATA instead.

---

# 31. PYTHON DATA MODEL EXAMPLE

Educational example:

```python
from dataclasses import dataclass
from datetime import datetime

@dataclass
class Trade:
    timestamp: datetime
    price: float
    quantity: float
    aggressor_side: str | None
    exchange: str | None = None

@dataclass
class OrderBookLevel:
    price: float
    quantity: float

@dataclass
class OrderBookSnapshot:
    timestamp: datetime
    bids: list[OrderBookLevel]
    asks: list[OrderBookLevel]
    source: str
```

The actual production model must validate all fields, units, timestamps and instrument specifications.

---

# 32. PYTHON DELTA CALCULATION EXAMPLE

```python
def calculate_delta(trades):
    buy_volume = 0.0
    sell_volume = 0.0
    unknown_volume = 0.0

    for trade in trades:
        side = trade.aggressor_side
        quantity = trade.quantity

        if quantity < 0:
            raise ValueError(
                "Trade quantity cannot be negative"
            )

        if side == "BUY":
            buy_volume += quantity

        elif side == "SELL":
            sell_volume += quantity

        else:
            unknown_volume += quantity

    return {
        "buy_volume": buy_volume,
        "sell_volume": sell_volume,
        "unknown_volume": unknown_volume,
        "delta": buy_volume - sell_volume
    }
```

Only use reliable aggressor-side classifications.

Do not silently classify unknown trades as buys or sells.

---

# 33. PYTHON CVD CALCULATION EXAMPLE

```python
def calculate_cvd(deltas, starting_value=0.0):
    cvd = []
    current = starting_value

    for delta in deltas:
        current += float(delta)
        cvd.append(current)

    return cvd
```

Ensure the input deltas are chronologically ordered and use a consistent session or anchoring rule.

---

# 34. PYTHON ORDER BOOK IMBALANCE EXAMPLE

```python
def calculate_depth_imbalance(
    bids,
    asks
):
    bid_total = sum(
        level.quantity for level in bids
    )

    ask_total = sum(
        level.quantity for level in asks
    )

    total = bid_total + ask_total

    if total <= 0:
        return None

    return (
        bid_total - ask_total
    ) / total
```

This is a simple displayed-depth measure.

It does not account for hidden liquidity, queue priority or future cancellations.

---

# 35. PYTHON VWAP EXAMPLE

```python
def calculate_vwap(trades):
    total_value = 0.0
    total_volume = 0.0

    for trade in trades:
        if trade.quantity < 0:
            raise ValueError(
                "Negative quantity"
            )

        total_value += (
            trade.price * trade.quantity
        )

        total_volume += trade.quantity

    if total_volume == 0:
        return None

    return total_value / total_volume
```

For production VWAP, use actual executed trades when available and apply a clearly defined session reset.

---

# 36. PYTHON RELATIVE VOLUME EXAMPLE

```python
def calculate_rvol(
    current_volume,
    average_volume
):
    if current_volume < 0:
        raise ValueError(
            "Volume cannot be negative"
        )

    if average_volume <= 0:
        return None

    return current_volume / average_volume
```

The reference average should be calculated using comparable historical time windows.

---

# 37. ORDER FLOW BACKTESTING

Backtest order flow strategies using data appropriate to the strategy.

Required data may include:

- Historical trades
- Bid/ask quotes
- Order-book updates
- Depth snapshots
- Tick timestamps
- Exchange events

Test:

1. Signal generation.
2. Signal timestamp.
3. Execution delay.
4. Spread.
5. Slippage.
6. Queue assumptions.
7. Partial fills.
8. Order cancellations.
9. Market impact.
10. Position sizing.
11. Stop execution.
12. Take-profit execution.
13. Trading fees.
14. Data quality.
15. Out-of-sample results.

## 37.1 Backtesting limitations

OHLCV candles cannot reliably reconstruct a full historical order book.

A current order book cannot be used as historical evidence.

A static snapshot cannot reproduce historical order arrival and cancellation sequences.

If historical order-book data is unavailable, label the test as a proxy or candle-based approximation.

Never present approximate results as full order-book backtesting.

---

# 38. ORDER FLOW PERFORMANCE METRICS

Evaluate:

- Net P&L
- Gross P&L
- Win rate
- Profit factor
- Expectancy
- Average R
- Maximum drawdown
- Sharpe ratio
- Sortino ratio
- Slippage
- Spread cost
- Fill rate
- Partial fill rate
- Market impact
- Execution latency
- Trade count
- MAE
- MFE
- Strategy stability

Also measure signal quality:

- Delta confirmation success
- CVD divergence outcome
- Absorption setup outcome
- Footprint imbalance outcome
- Liquidity sweep outcome
- Failed auction outcome

Define every outcome window and success criterion before testing.

---

# 39. ORDER FLOW SCORING ENGINE

A future scoring engine may combine:

- Price structure
- Delta
- CVD
- Volume
- Footprint imbalance
- Market depth
- VWAP
- Liquidity
- Spread
- Volatility
- Session context

Illustrative scoring model:

| Component | Example Weight |
|---|---:|
| Market structure | 20 |
| Delta | 15 |
| CVD | 15 |
| Volume | 10 |
| Footprint | 10 |
| Liquidity | 10 |
| VWAP | 10 |
| Execution quality | 10 |

These weights are research defaults only, not validated predictive values.

Requirements:

- Normalize component scores.
- Avoid double-counting correlated features.
- Handle missing data.
- Record confidence separately.
- Validate weights out of sample.
- Compare against simpler baselines.

A high score must never override a hard risk rejection.

---

# 40. SIGNAL CONFIDENCE AND DATA QUALITY

Separate three concepts:

### Data quality

How reliable and complete is the underlying information?

### Signal strength

How strongly do the observed measurements support the setup?

### Statistical confidence

How much evidence supports the strategy's historical performance?

These are not interchangeable.

A visually strong signal with poor data quality must not be described as high confidence.

Do not generate fake percentage probabilities.

If a model is not calibrated, use qualitative descriptions:

- Weak
- Moderate
- Strong
- Insufficient Evidence

---

# 41. RISK MANAGEMENT INTEGRATION

Before an order flow trade is approved:

- Confirm entry.
- Define invalidation.
- Calculate Stop Loss.
- Calculate position size.
- Calculate maximum loss.
- Include spread.
- Include slippage.
- Include fees.
- Check leverage.
- Check available margin.
- Check portfolio exposure.
- Check daily loss limit.

Order flow strength does not justify increasing risk beyond the declared limit.

Never move a stop further away merely because order flow still appears favorable.

---

# 42. FAILURE CONDITIONS

Reject or downgrade analysis when:

- Market data is stale.
- Bid/ask data is missing.
- Trade classification is unreliable.
- Order-book updates are incomplete.
- Exchange coverage is unknown.
- Spread is abnormal.
- Liquidity is insufficient.
- Market is halted.
- Timestamp synchronization fails.
- Required instrument specifications are missing.
- Historical data is not available.
- Signal rules are ambiguous.
- Execution cannot be simulated realistically.

Return:

INSUFFICIENT ORDER FLOW DATA — NO RELIABLE CONCLUSION.

---

# 43. AUTOMATED ALERT SYSTEM

Potential alerts:

- Delta spike
- CVD divergence
- Abnormal volume
- Depth imbalance
- Spread expansion
- Liquidity withdrawal
- Potential absorption
- Footprint imbalance
- VWAP reclaim
- Volume Profile level interaction
- Open Interest change
- Funding rate extreme

Every alert must include:

- Instrument
- Timestamp
- Timeframe
- Data source
- Measurement
- Threshold
- Explanation
- Data quality
- Invalidation
- Risk warning

Alerts must not automatically become trading orders without a separate authorization and risk-control system.

---

# 44. ORDER FLOW REPORT FORMAT

Every analysis should use this structure:

## A. Instrument Details

- Market
- Symbol
- Exchange or broker
- Timeframe
- Session
- Timestamp

## B. Data Quality

- Data source
- Data type
- Feed status
- Delay
- Missing fields
- Classification method

## C. Market Structure

- Trend
- Key levels
- Support
- Resistance
- Liquidity zones

## D. Order Flow Measurements

- Bid
- Ask
- Spread
- Delta
- CVD
- Volume
- Relative volume
- Market depth
- Footprint
- VWAP
- Volume Profile
- Open Interest, if available

## E. Interpretation

- Aggressive buying
- Aggressive selling
- Absorption evidence
- Imbalance
- Liquidity behavior
- Price response
- Confirmation
- Contradictions

## F. Trading Plan

- BUY / SELL / WAIT / NO TRADE
- Entry
- Stop Loss
- TP1
- TP2
- TP3
- Risk-to-reward
- Position size

Only provide exact trade levels when supported by available data.

## G. Confidence and Limitations

- Data quality
- Signal strength
- Statistical evidence
- Missing information
- Invalidation

---

# 45. FINAL DECISION ENGINE

Possible decisions:

BUY:
Only when the defined bullish strategy conditions are satisfied and risk checks pass.

SELL:
Only when the defined bearish strategy conditions are satisfied and risk checks pass.

WAIT:
When a setup is developing but confirmation is missing.

NO TRADE:
When data is unreliable, liquidity is poor, risk is unacceptable or no valid setup exists.

Order Flow must not override:

- Higher timeframe risk
- Major news risk
- Portfolio limits
- Execution constraints
- Data integrity
- Stop-loss requirements

---

# 46. HONESTY AND MARKET DATA RULES

Never:

- Invent order-book quantities.
- Invent institutional activity.
- Invent buyer or seller identities.
- Invent volume delta.
- Invent CVD.
- Invent footprint data.
- Invent live market depth.
- Claim hidden liquidity was confirmed without evidence.
- Claim an iceberg order was identified from a candle alone.
- Present broker-specific Forex data as global market data.
- Present one crypto exchange as the entire market.
- Claim an order flow backtest was completed without execution.
- Guarantee a trading outcome.

Clearly label:

- VERIFIED DATA
- CALCULATED METRIC
- ESTIMATED VALUE
- DATA PROXY
- HYPOTHESIS
- INSUFFICIENT DATA

---

# 47. FUTURE ADVANCED DEVELOPMENT

Future implementation may add:

- Real-time order-book ingestion
- Historical tick database
- Exchange WebSocket integrations
- Multi-exchange CVD
- Footprint visualization
- DOM visualization
- Order-book heatmaps
- Liquidity event detection
- Absorption detection models
- Queue position estimation
- Market impact models
- Smart execution simulation
- Order flow machine learning
- Strategy optimization
- Multi-market research
- Distributed scenario testing

Every integration must use documented and authorized data sources.

Do not claim a feature is operational merely because its documentation exists.

---

# 48. MANDATORY HINGLISH COMMUNICATION

All user-facing order flow explanations must be in natural Hinglish.

Example:

"Is level par aggressive buying dikh rahi hai, lekin price abhi resistance ke upar accept nahi hua. Isliye breakout confirm nahi hai. Filhaal WAIT better hai."

Explain technical terms in simple language.

Do not respond in pure Hindi or unnecessarily complicated English.

---

# 49. FINAL PRINCIPLES

1. Order flow is evidence, not certainty.
2. Aggressive buying does not guarantee a bullish move.
3. Aggressive selling does not guarantee a bearish move.
4. Visible liquidity can disappear.
5. Delta requires reliable trade classification.
6. CVD depends on data coverage and methodology.
7. Absorption requires more than a rejection candle.
8. Forex order flow is fragmented.
9. One exchange does not represent every market.
10. Historical order flow does not guarantee future behavior.
11. Risk management remains mandatory.
12. Missing data must never be invented.
13. Every strategy requires independent validation.
14. Every signal must have an invalidation condition.
15. NO TRADE is a valid decision.

**NO RELIABLE DATA = NO RELIABLE ORDER FLOW CONCLUSION.**

**NO VALIDATION = NO STRATEGY APPROVAL.**

**NO GUARANTEED PROFIT.**
