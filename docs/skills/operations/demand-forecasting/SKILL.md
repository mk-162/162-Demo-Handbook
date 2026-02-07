---
name: demand-forecasting
title: Demand Forecasting & Inventory Planning
description: Systematic approach to predicting demand, calculating safety stock, reorder points, and managing supplier lead times
version: 1.0.0
tags: [operations, inventory, forecasting, supply-chain, planning]
---

# Demand Forecasting & Inventory Planning

## Purpose

This skill provides a comprehensive methodology for predicting product demand and managing inventory levels. It covers historical analysis, seasonality modeling, safety stock calculations, and supplier management to ensure optimal stock levels while minimizing carrying costs.

**Use this skill when:**
- Planning inventory for new products
- Reviewing stock levels for existing products
- Preparing for seasonal demand changes
- Setting reorder points and safety stock levels
- Evaluating supplier performance
- Creating annual purchase budgets
- Managing cash flow in inventory

**GTSE Context:** For distributors of trade and industrial products, inventory management directly impacts both customer satisfaction (stockouts = lost sales) and cash flow (overstock = tied-up capital). This skill is optimized for businesses with hundreds to thousands of SKUs and multiple suppliers.

## Inputs

- `product_sku`: Product identifier
- `historical_sales`: Monthly/weekly sales data (minimum 12 months, ideal 24-36 months)
- `lead_time_days`: Supplier lead time in days
- `holding_cost_rate`: Annual cost to hold inventory (% of value)
- `stockout_cost`: Estimated cost per stockout incident
- `service_level_target`: Target in-stock percentage (e.g., 95%)
- `supplier_info`: Supplier reliability and MOQ data

## Prerequisites

Before implementing this skill:

1. **Data Access**
   - ERP/inventory management system
   - Historical sales data by SKU
   - Supplier lead time records
   - Stock level history

2. **Business Parameters**
   - Target service levels defined
   - Holding cost understood
   - Storage capacity known
   - Budget constraints clear

3. **Supplier Information**
   - Lead times documented
   - MOQs known
   - Reliability history
   - Payment terms

---

## Procedure

### Step 1: Historical Sales Analysis

**What:** Analyze past sales data to understand demand patterns and trends.

**How:**

#### 1.1 Data Collection

Gather sales data by SKU:

```markdown
## Sales Data Template

### Product: Cable Ties 300mm Black 100pk
**SKU:** CT300BK100

### Monthly Sales History (Units)
| Month | Year 1 | Year 2 | Year 3 | Avg |
|-------|--------|--------|--------|-----|
| Jan | 280 | 310 | 345 | 312 |
| Feb | 295 | 325 | 360 | 327 |
| Mar | 380 | 420 | 465 | 422 |
| Apr | 350 | 385 | 425 | 387 |
| May | 340 | 375 | 415 | 377 |
| Jun | 320 | 355 | 390 | 355 |
| Jul | 310 | 340 | 380 | 343 |
| Aug | 300 | 330 | 365 | 332 |
| Sep | 360 | 395 | 440 | 398 |
| Oct | 330 | 365 | 405 | 367 |
| Nov | 290 | 320 | 355 | 322 |
| Dec | 250 | 275 | 305 | 277 |
| **Total** | 3,805 | 4,195 | 4,650 | 4,217 |

### Summary Statistics
- Average monthly sales: 351 units
- Standard deviation: 41 units
- Coefficient of variation: 11.7%
- Year-over-year growth: 10.4%
```

#### 1.2 Trend Analysis

Calculate the underlying trend:

```markdown
## Trend Calculation

### Method: Linear Regression

Using least squares method on monthly data:

Sales(t) = Base + (Trend × t)

Where:
- Base = Starting demand level
- Trend = Monthly growth rate
- t = Time period (month number)

### Example Calculation:
Year 3 data regression:
- Base: 290 units
- Trend: +5.2 units/month
- R²: 0.78 (good fit)

### Interpretation:
- Underlying demand growing ~5 units/month
- Expect ~352 units base demand at month 1 of Year 4
- Confidence: 78% of variation explained by trend
```

#### 1.3 Demand Classification (ABC-XYZ Analysis)

Classify products by value and variability:

```markdown
## ABC-XYZ Classification Matrix

### ABC Classification (by revenue/value)
| Class | % of SKUs | % of Revenue | Description |
|-------|-----------|--------------|-------------|
| A | 20% | 80% | High value, critical |
| B | 30% | 15% | Medium value |
| C | 50% | 5% | Low value, many SKUs |

### XYZ Classification (by demand variability)
| Class | CV Range | Description |
|-------|----------|-------------|
| X | 0-20% | Stable, predictable |
| Y | 20-50% | Moderate variability |
| Z | 50%+ | Highly variable, unpredictable |

### Combined Matrix
| | X (Stable) | Y (Variable) | Z (Erratic) |
|---|------------|--------------|-------------|
| **A** | AX: Easy to manage, automate | AY: Important, needs attention | AZ: Critical, manual review |
| **B** | BX: Automate | BY: Standard review | BZ: Watch closely |
| **C** | CX: Automate, consider dropship | CY: Consider consolidation | CZ: Consider elimination |

### Product Classification Example:
| SKU | Annual Revenue | CV | ABC | XYZ | Combined | Strategy |
|-----|----------------|-----|-----|-----|----------|----------|
| CT300BK100 | £45,000 | 12% | A | X | AX | Auto-reorder |
| VDE-SET-8 | £28,000 | 35% | A | Y | AY | Regular review |
| DRILL-RARE | £1,200 | 65% | C | Z | CZ | Make-to-order |
```

#### 1.4 Demand Pattern Recognition

Identify the type of demand pattern:

```markdown
## Demand Pattern Types

### Type 1: Smooth/Regular
- Consistent demand month-to-month
- Low CV (<20%)
- Example: Basic cable ties, standard screws
- Forecasting: Simple moving average

### Type 2: Seasonal
- Clear peaks and troughs
- Pattern repeats annually
- Example: Garden products, heating supplies
- Forecasting: Seasonal decomposition

### Type 3: Trending
- Consistent upward or downward movement
- Growth/decline over time
- Example: New products, declining tech
- Forecasting: Linear regression

### Type 4: Intermittent/Lumpy
- Infrequent, irregular demand
- Long periods of zero demand
- Example: Specialized tools, rare parts
- Forecasting: Croston's method

### Type 5: New/No History
- Insufficient data
- Launch products
- Example: New product lines
- Forecasting: Analogous products, market research

### Pattern Identification Check:
| Pattern | Test | CT300BK100 | Result |
|---------|------|------------|--------|
| Trend | Regression R² | 0.78 | ✅ Trending |
| Seasonal | Seasonal indices vary >20% | Yes (Mar 120, Dec 79) | ✅ Seasonal |
| Variability | CV | 12% | Stable |
| **Classification** | | | Trending + Seasonal |
```

**Tools:** Excel, ERP reports, statistical software

**Output:** Demand profile for each SKU with classification and pattern identification

---

### Step 2: Seasonality Pattern Analysis

**What:** Identify and quantify seasonal patterns to adjust forecasts.

**How:**

#### 2.1 Calculate Seasonal Indices

```markdown
## Seasonal Index Calculation

### Step 1: Calculate Monthly Averages
| Month | 3-Year Total | Monthly Avg | Overall Monthly Avg |
|-------|--------------|-------------|---------------------|
| Jan | 935 | 312 | 351 |
| Feb | 980 | 327 | 351 |
| Mar | 1,265 | 422 | 351 |
| Apr | 1,160 | 387 | 351 |
| May | 1,130 | 377 | 351 |
| Jun | 1,065 | 355 | 351 |
| Jul | 1,030 | 343 | 351 |
| Aug | 995 | 332 | 351 |
| Sep | 1,195 | 398 | 351 |
| Oct | 1,100 | 367 | 351 |
| Nov | 965 | 322 | 351 |
| Dec | 830 | 277 | 351 |

### Step 2: Calculate Seasonal Index
Seasonal Index = Monthly Avg / Overall Monthly Avg

| Month | Seasonal Index | Interpretation |
|-------|----------------|----------------|
| Jan | 0.89 | 11% below average |
| Feb | 0.93 | 7% below average |
| Mar | 1.20 | 20% above average |
| Apr | 1.10 | 10% above average |
| May | 1.07 | 7% above average |
| Jun | 1.01 | Average |
| Jul | 0.98 | 2% below average |
| Aug | 0.95 | 5% below average |
| Sep | 1.13 | 13% above average |
| Oct | 1.04 | 4% above average |
| Nov | 0.92 | 8% below average |
| Dec | 0.79 | 21% below average |

### Validation Check
Sum of indices should ≈ 12.00
Our sum: 12.01 ✅
```

#### 2.2 Visualize Seasonality

```markdown
## Seasonal Pattern Visualization

### Monthly Demand Pattern (ASCII Chart)
```
Units
450 |              *
400 |        *           *
350 |    *      *  *        *
300 | *   *           *  *     *
250 |                             *
    +--+--+--+--+--+--+--+--+--+--+--+--+
     J  F  M  A  M  J  J  A  S  O  N  D
```

### Peak Periods (Index > 1.10):
- **March:** Spring project season (+20%)
- **September:** Back-to-work surge (+13%)

### Trough Periods (Index < 0.90):
- **December:** Holiday slowdown (-21%)
- **January:** Post-holiday recovery (-11%)
```

#### 2.3 Category-Level Seasonality

Different product categories have different patterns:

```markdown
## Seasonality by Product Category

### Cable Ties & Electrical
| Month | Index | Notes |
|-------|-------|-------|
| Mar | 1.20 | Spring projects |
| Sep | 1.15 | Back-to-work |
| Dec | 0.75 | Holiday slow |

### Garden & Outdoor
| Month | Index | Notes |
|-------|-------|-------|
| Mar-Apr | 1.40 | Spring garden prep |
| May-Jul | 1.25 | Peak gardening |
| Nov-Feb | 0.50 | Winter dormancy |

### Hand Tools
| Month | Index | Notes |
|-------|-------|-------|
| Nov-Dec | 1.30 | Christmas gifts |
| Jun | 1.15 | Father's Day |
| Feb-Mar | 0.90 | Post-holiday |

### Safety/PPE
| Month | Index | Notes |
|-------|-------|-------|
| Jan | 1.20 | New year compliance |
| Sep | 1.15 | New projects |
| Jul-Aug | 0.85 | Holiday season |

### B2B/Trade
| Month | Index | Notes |
|-------|-------|-------|
| Sep-Nov | 1.20 | End of year projects |
| Dec | 0.60 | Shutdown period |
| Aug | 0.75 | Holiday slowdown |
```

**Tools:** Excel, charts, statistical analysis

**Output:** Seasonal indices for all products/categories

---

### Step 3: Lead Time Analysis

**What:** Understand and track supplier lead times to inform reorder timing.

**How:**

#### 3.1 Lead Time Measurement

```markdown
## Lead Time Components

### Total Lead Time = Order Processing + Manufacturing + Transit + Receiving

| Component | Description | Typical Duration |
|-----------|-------------|------------------|
| Order Processing | Time from PO to supplier acknowledgment | 1-3 days |
| Manufacturing | Time for supplier to produce/pick | 1-30+ days |
| Transit | Shipping time | 2-45 days |
| Receiving | Goods in, QC, put away | 1-3 days |

### Lead Time by Supplier

| Supplier | Location | Avg Lead Time | Std Dev | Range |
|----------|----------|---------------|---------|-------|
| Supplier A | UK | 5 days | 1.5 days | 3-8 days |
| Supplier B | EU | 12 days | 3 days | 8-18 days |
| Supplier C | China | 42 days | 7 days | 30-60 days |
| Supplier D | UK | 7 days | 2 days | 4-12 days |
```

#### 3.2 Lead Time Tracking Template

```markdown
## Lead Time Tracking Log

| PO Date | Supplier | PO # | Promised | Actual Received | Lead Time | Variance |
|---------|----------|------|----------|-----------------|-----------|----------|
| 01-Jan | Supp A | 1001 | 06-Jan | 06-Jan | 5 days | 0 |
| 03-Jan | Supp B | 1002 | 15-Jan | 17-Jan | 14 days | +2 |
| 05-Jan | Supp C | 1003 | 16-Feb | 22-Feb | 48 days | +6 |
| 08-Jan | Supp A | 1004 | 13-Jan | 12-Jan | 4 days | -1 |
| ... | | | | | | |

### Supplier Performance Summary
| Supplier | Orders | On-Time % | Avg Variance | Max Delay |
|----------|--------|-----------|--------------|-----------|
| Supp A | 45 | 92% | +0.5 days | 3 days |
| Supp B | 28 | 78% | +2.1 days | 6 days |
| Supp C | 12 | 67% | +4.2 days | 12 days |
| Supp D | 36 | 85% | +1.2 days | 5 days |
```

#### 3.3 Lead Time for Planning Purposes

Use worst-case planning for safety stock:

```markdown
## Planning Lead Times

### Lead Time Selection
| Risk Tolerance | Lead Time Used | Formula |
|----------------|----------------|---------|
| Conservative | Maximum | Avg + 3σ |
| Standard | 95th percentile | Avg + 1.65σ |
| Aggressive | Average | Avg |

### Example: Supplier C (China)
- Average: 42 days
- Std Dev: 7 days
- Conservative (Max): 42 + (3 × 7) = 63 days
- Standard (95%): 42 + (1.65 × 7) = 54 days
- Aggressive (Avg): 42 days

### Recommended Planning Lead Times
| Supplier | Avg | Planning LT | Notes |
|----------|-----|-------------|-------|
| Supp A | 5 | 8 days | +3 for buffer |
| Supp B | 12 | 18 days | +6 for variability |
| Supp C | 42 | 56 days | +14 for ocean freight risk |
| Supp D | 7 | 11 days | +4 for buffer |
```

#### 3.4 Seasonal Lead Time Adjustments

Lead times often increase during:

```markdown
## Seasonal Lead Time Factors

| Period | Impact | Adjustment | Reason |
|--------|--------|------------|--------|
| Chinese New Year (Jan/Feb) | +14-28 days | Order 8 weeks early | Factory closures |
| Q4 Peak Season | +5-10 days | Order earlier | Shipping congestion |
| UK Bank Holidays | +1-3 days | Plan around | Local operations |
| Supplier Shutdowns (Aug) | +7-14 days | Pre-order | EU summer holidays |
| Black Friday prep | +5 days | Order early | Everyone ordering |

### Annual Lead Time Calendar
| Month | Supp C Normal LT | Adjusted LT | Note |
|-------|------------------|-------------|------|
| Jan | 42 | 60+ | CNY prep |
| Feb | 42 | 70+ | CNY impact |
| Mar | 42 | 50 | Recovery |
| Apr-Jul | 42 | 45 | Normal |
| Aug | 42 | 50 | Summer slow |
| Sep-Nov | 42 | 50 | Peak prep |
| Dec | 42 | 55 | Peak shipping |
```

**Tools:** ERP system, supplier tracking spreadsheet

**Output:** Lead time database with planning values by supplier

---

### Step 4: Safety Stock Calculation

**What:** Determine optimal safety stock levels to achieve service level targets.

**How:**

#### 4.1 Safety Stock Formula

```markdown
## Safety Stock Calculation

### Basic Formula:
Safety Stock = Z × σDL

Where:
- Z = Service level factor (from normal distribution)
- σDL = Standard deviation of demand during lead time

### Z-Values by Service Level:
| Service Level | Z-Value |
|---------------|---------|
| 90% | 1.28 |
| 95% | 1.65 |
| 97.5% | 1.96 |
| 99% | 2.33 |
| 99.9% | 3.09 |

### Extended Formula (accounts for lead time variability):
Safety Stock = Z × √[(LT × σD²) + (D̄² × σLT²)]

Where:
- LT = Average lead time
- σD = Standard deviation of demand
- D̄ = Average demand
- σLT = Standard deviation of lead time
```

#### 4.2 Calculate Demand Variability

```markdown
## Demand During Lead Time Analysis

### Product: CT300BK100
**Daily Sales:** 12 units (average)
**Daily Std Dev:** 4 units
**Lead Time:** 42 days
**Lead Time Std Dev:** 7 days

### Step 1: Calculate Average Demand During Lead Time
DDLT = Daily Demand × Lead Time
DDLT = 12 × 42 = 504 units

### Step 2: Calculate Variability During Lead Time
σDL = √[(LT × σD²) + (D̄² × σLT²)]
σDL = √[(42 × 4²) + (12² × 7²)]
σDL = √[(42 × 16) + (144 × 49)]
σDL = √[672 + 7,056]
σDL = √7,728
σDL = 88 units

### Step 3: Calculate Safety Stock
Target Service Level: 95% (Z = 1.65)
Safety Stock = 1.65 × 88 = 145 units
```

#### 4.3 Safety Stock Calculator Template

```markdown
## Safety Stock Calculator

### Input Parameters
| Parameter | Value | Source |
|-----------|-------|--------|
| Average daily demand | 12 units | Historical sales |
| Daily demand std dev | 4 units | Historical sales |
| Lead time (days) | 42 days | Supplier average |
| Lead time std dev | 7 days | Supplier variance |
| Target service level | 95% | Business decision |
| Z-value | 1.65 | Service level table |

### Calculation
| Step | Formula | Result |
|------|---------|--------|
| Avg demand during LT | 12 × 42 | 504 units |
| Variance (demand component) | 42 × 4² | 672 |
| Variance (LT component) | 12² × 7² | 7,056 |
| Total variance | 672 + 7,056 | 7,728 |
| Std dev of DDLT | √7,728 | 88 units |
| Safety stock | 1.65 × 88 | **145 units** |

### Validation
- Safety stock represents ~12 days of sales
- Cost: 145 × £2.45 = £355 in inventory
- Risk: 5% chance of stockout per cycle
```

#### 4.4 Category Safety Stock Strategy

```markdown
## Safety Stock Strategy by Classification

| ABC-XYZ | Service Level | Safety Stock Strategy |
|---------|---------------|----------------------|
| AX | 99% | High safety stock, auto-replenish |
| AY | 97% | Substantial safety stock, regular review |
| AZ | 95% | Moderate stock, frequent review |
| BX | 95% | Standard safety stock |
| BY | 95% | Standard with review |
| BZ | 90% | Lower stock, accept some risk |
| CX | 90% | Minimal, quick replenishment |
| CY | 85% | Consider make-to-order |
| CZ | 80% | Make-to-order or drop |

### Adjusted Service Levels (Cost Consideration)
High-cost items: Reduce service level 2-5%
Low-cost/high-volume: Increase service level 2-5%
Strategic items: Override to 99%
New items: 95% until pattern established
```

**Tools:** Excel calculator, inventory management system

**Output:** Safety stock levels for all SKUs

---

### Step 5: Reorder Point Calculation

**What:** Determine when to place orders to maintain stock availability.

**How:**

#### 5.1 Reorder Point Formula

```markdown
## Reorder Point Calculation

### Basic Formula:
Reorder Point = (Daily Demand × Lead Time) + Safety Stock

ROP = D × LT + SS

### Example: CT300BK100
- Daily demand: 12 units
- Lead time: 42 days  
- Safety stock: 145 units

ROP = (12 × 42) + 145
ROP = 504 + 145
ROP = **649 units**

### Interpretation:
When stock reaches 649 units, place a reorder.
This provides:
- 504 units to cover average demand during lead time
- 145 units safety buffer for variability
```

#### 5.2 Seasonal Reorder Point Adjustment

```markdown
## Seasonal ROP Adjustment

### Problem:
Fixed ROP doesn't account for demand changes.
March demand 20% higher than average = potential stockout.

### Solution: Monthly ROP Adjustment

| Month | Seasonal Index | Daily Demand | ROP |
|-------|----------------|--------------|-----|
| Jan | 0.89 | 10.7 | 594 |
| Feb | 0.93 | 11.2 | 615 |
| Mar | 1.20 | 14.4 | **749** |
| Apr | 1.10 | 13.2 | 699 |
| May | 1.07 | 12.8 | 683 |
| Jun | 1.01 | 12.1 | 653 |
| Jul | 0.98 | 11.8 | 640 |
| Aug | 0.95 | 11.4 | 623 |
| Sep | 1.13 | 13.6 | **716** |
| Oct | 1.04 | 12.5 | 670 |
| Nov | 0.92 | 11.0 | 607 |
| Dec | 0.79 | 9.5 | **544** |

### System Implementation:
Option 1: Update ROP monthly in system
Option 2: Use highest ROP year-round (simple but costly)
Option 3: Trigger seasonal review reminders
```

#### 5.3 Reorder Quantity (EOQ)

```markdown
## Economic Order Quantity

### EOQ Formula:
EOQ = √[(2 × D × S) / H]

Where:
- D = Annual demand (units)
- S = Order cost (per order)
- H = Holding cost (per unit per year)

### Example: CT300BK100
- Annual demand: 4,200 units
- Order cost: £25 (admin, receiving, processing)
- Holding cost: £0.49/unit/year (20% of £2.45)

EOQ = √[(2 × 4,200 × 25) / 0.49]
EOQ = √[210,000 / 0.49]
EOQ = √428,571
EOQ = **655 units**

### Practical Adjustment:
| Factor | EOQ | Adjusted Qty | Reason |
|--------|-----|--------------|--------|
| MOQ (min 500) | 655 | 655 | Above MOQ ✓ |
| Case pack (100) | 655 | 700 | Round to case |
| Volume discount | 700 | 1,000 | 10% off at 1,000 |
| Storage limit | 1,000 | 1,000 | Capacity OK ✓ |

**Final Order Qty: 1,000 units** (with volume discount)
```

#### 5.4 Order Cycle Review

Alternative approach for many low-volume items:

```markdown
## Periodic Review System

### Fixed Review Period (Weekly/Monthly)

**Order-Up-To Level:**
S = D × (R + LT) + SS

Where:
- S = Order-up-to level
- D = Average demand per day
- R = Review period (days)
- LT = Lead time (days)
- SS = Safety stock

### Example: Monthly Review
- Daily demand: 12 units
- Review period: 30 days
- Lead time: 42 days
- Safety stock: 145 units

S = 12 × (30 + 42) + 145
S = 12 × 72 + 145
S = 864 + 145
S = **1,009 units**

### On Review Day:
Order = S - Current Stock - On Order
Example: Current stock = 450, On order = 200
Order = 1,009 - 450 - 200 = **359 units**
```

**Tools:** Inventory system, EOQ calculator

**Output:** Reorder points and quantities for all SKUs

---

### Step 6: Supplier Lead Time Management

**What:** Actively manage suppliers to optimize inventory performance.

**How:**

#### 6.1 Supplier Performance Scorecard

```markdown
## Supplier Scorecard Template

### Supplier: [Supplier Name]

**Evaluation Period:** Q4 2024

### Performance Metrics
| Metric | Target | Actual | Score | Weight |
|--------|--------|--------|-------|--------|
| On-Time Delivery | 95% | 87% | 3/5 | 30% |
| Order Accuracy | 99% | 96% | 3/5 | 25% |
| Quality (defect rate) | <1% | 0.5% | 5/5 | 20% |
| Lead Time Consistency | ±2 days | ±4 days | 2/5 | 15% |
| Communication | Response <24h | Avg 36h | 3/5 | 10% |

**Weighted Score: 3.15/5**

### Trend
| Quarter | Score | Trend |
|---------|-------|-------|
| Q1 | 3.4 | - |
| Q2 | 3.5 | ↑ |
| Q3 | 3.0 | ↓ |
| Q4 | 3.15 | ↑ |

### Action Items
1. Review late delivery causes (3 containers delayed in Q4)
2. Request improvement plan for on-time target
3. Consider dual-sourcing for critical items
```

#### 6.2 Supplier Communication Calendar

```markdown
## Supplier Communication Schedule

### Regular Reviews
| Frequency | Activity | Owner |
|-----------|----------|-------|
| Weekly | Order status check | Buyer |
| Monthly | Performance review call | Buyer/Manager |
| Quarterly | Business review meeting | Manager/Director |
| Annually | Contract negotiation | Director |

### Key Dates to Communicate
| Date | Event | Action Required |
|------|-------|-----------------|
| Jan 15 | CNY forecast | Submit 3-month forecast |
| Jul 1 | Summer shutdown dates | Confirm and adjust orders |
| Sep 1 | Q4 peak forecast | Submit Q4 demand plan |
| Nov 1 | Year-end inventory | Agree December deliveries |

### Forecast Sharing
| Horizon | Detail Level | Frequency |
|---------|--------------|-----------|
| 0-4 weeks | Firm orders | Weekly |
| 4-12 weeks | Planned orders | Bi-weekly |
| 12-26 weeks | Forecast range | Monthly |
| 26-52 weeks | Annual outlook | Quarterly |
```

#### 6.3 Dual-Sourcing Strategy

```markdown
## Multi-Supplier Strategy

### When to Dual-Source
| Factor | Threshold | Action |
|--------|-----------|--------|
| Single supplier dependency | >£100k/year | Qualify backup |
| On-time <85% | Persistent | Split orders |
| Critical product | Stockout = significant loss | Backup required |
| Long lead time | >30 days | Consider local backup |

### Dual-Source Split Example
| Supplier | Location | Lead Time | Cost | Split % |
|----------|----------|-----------|------|---------|
| Primary (China) | Shenzhen | 42 days | £2.00 | 70% |
| Backup (UK) | Manchester | 7 days | £2.80 | 30% |

**Rationale:**
- Primary for cost-effective bulk
- Backup for agility and emergency

**Blended Cost:** (0.7 × £2.00) + (0.3 × £2.80) = £2.24
Premium: 12% increase
Risk Reduction: Significant

### Emergency Ordering Rules
| Stock Level | Action | Supplier |
|-------------|--------|----------|
| >ROP | Normal ordering | Primary |
| <ROP, >Safety | Expedite if possible | Primary or Backup |
| <Safety | Emergency order | Backup (any cost) |
```

#### 6.4 Supplier Improvement Initiatives

```markdown
## Supplier Development Actions

### Short-Term (<3 months)
| Issue | Action | Expected Impact |
|-------|--------|-----------------|
| Late deliveries | Weekly order tracking calls | -2 days variance |
| Documentation errors | Provide template | -50% errors |
| MOQ too high | Negotiate based on volume | Lower MOQ |

### Medium-Term (3-6 months)
| Issue | Action | Expected Impact |
|-------|--------|-----------------|
| Lead time too long | Supplier holds buffer stock | -14 days LT |
| No visibility | Implement EDI/API | Real-time updates |
| Quality issues | On-site audit | Quality plan |

### Long-Term (6-12 months)
| Issue | Action | Expected Impact |
|-------|--------|-----------------|
| Cost too high | Value engineering | -5-10% cost |
| Capacity constraints | Supplier expansion | +50% capacity |
| Geographic risk | Alternative source | Resilience |
```

**Tools:** Supplier scorecard, meeting tracker, contract management

**Output:** Supplier management system with scorecards and improvement plans

---

### Step 7: Demand Forecast Generation

**What:** Create actionable demand forecasts for planning purposes.

**How:**

#### 7.1 Forecast Methods by Product Type

```markdown
## Forecasting Method Selection

| Product Type | Method | Formula |
|--------------|--------|---------|
| Stable (AX) | Simple Moving Average | Avg of last N periods |
| Trending | Linear Regression | Base + Trend × t |
| Seasonal | Seasonal Decomposition | Base × Seasonal Index |
| Trending + Seasonal | Holt-Winters | Combines both |
| Intermittent | Croston's Method | Special for sporadic |
| New Product | Analogous + Judgment | Similar product data |

### Method Selection Decision Tree
```
Is there sufficient history (>12 months)?
├── No → Use analogous products or judgment
└── Yes → Is there a clear trend?
    ├── No → Is there seasonality?
    │   ├── No → Simple Moving Average
    │   └── Yes → Seasonal Adjustment
    └── Yes → Is there seasonality?
        ├── No → Linear Regression
        └── Yes → Holt-Winters
```
```

#### 7.2 Forecast Calculation Example

```markdown
## Holt-Winters Forecast Example

### Product: CT300BK100

### Historical Data (Year 3):
| Month | Actual | Trend | Seasonal | Fitted |
|-------|--------|-------|----------|--------|
| Jan | 345 | 333 | 0.89 | 296 |
| Feb | 360 | 337 | 0.93 | 313 |
| Mar | 465 | 341 | 1.20 | 409 |
| ... | | | | |

### Forecast (Year 4):
| Month | Trend | Seasonal | Forecast | 90% Range |
|-------|-------|----------|----------|-----------|
| Jan | 378 | 0.89 | 336 | 295-377 |
| Feb | 382 | 0.93 | 355 | 312-398 |
| Mar | 386 | 1.20 | 463 | 407-519 |
| Apr | 390 | 1.10 | 429 | 377-481 |
| May | 394 | 1.07 | 422 | 371-473 |
| Jun | 398 | 1.01 | 402 | 353-451 |
| Jul | 402 | 0.98 | 394 | 347-441 |
| Aug | 406 | 0.95 | 386 | 339-433 |
| Sep | 410 | 1.13 | 463 | 407-519 |
| Oct | 414 | 1.04 | 431 | 379-483 |
| Nov | 418 | 0.92 | 385 | 338-432 |
| Dec | 422 | 0.79 | 333 | 293-373 |
| **Total** | | | **4,799** | 4,218-5,380 |

### Growth Projection:
- Year 3: 4,650 units
- Year 4 forecast: 4,799 units
- Growth: 3.2%
```

#### 7.3 Forecast Accuracy Tracking

```markdown
## Forecast Accuracy Measurement

### Accuracy Metrics
| Metric | Formula | Target |
|--------|---------|--------|
| MAPE | Σ(|Actual - Forecast| / Actual) / n | <15% |
| Bias | Σ(Actual - Forecast) / n | ±5% |
| Weighted MAPE | MAPE weighted by value | <15% |

### Monthly Accuracy Tracking
| Month | Forecast | Actual | Error | MAPE |
|-------|----------|--------|-------|------|
| Jan | 336 | 352 | -16 | 4.5% |
| Feb | 355 | 340 | +15 | 4.4% |
| Mar | 463 | 488 | -25 | 5.1% |
| Apr | 429 | 410 | +19 | 4.6% |
| May | 422 | 435 | -13 | 3.0% |
| **YTD** | | | | **4.3%** ✅ |

### Accuracy by Category
| Category | MAPE | Bias | Status |
|----------|------|------|--------|
| Cable Ties | 5% | +2% | 🟢 Good |
| Hand Tools | 12% | -5% | 🟡 Acceptable |
| Specialty | 28% | +15% | 🔴 Review method |
```

#### 7.4 Collaborative Forecast Adjustment

```markdown
## Forecast Review Process

### Monthly Forecast Review Meeting
**Attendees:** Sales, Operations, Finance
**Duration:** 1 hour
**Cadence:** First Monday monthly

### Agenda:
1. Last month accuracy review (10 min)
2. Statistical forecast presentation (15 min)
3. Sales intelligence inputs (15 min)
   - New customer pipeline
   - Lost customers
   - Promotions planned
   - Market trends
4. Adjustment discussion (15 min)
5. Final forecast approval (5 min)

### Adjustment Authority
| Adjustment | Authority | Documentation |
|------------|-----------|---------------|
| ±10% | Forecast analyst | Notes in system |
| ±10-25% | Sales Manager | Written justification |
| ±25-50% | Director | Business case |
| >50% | Executive | Full approval |

### Common Adjustment Reasons
| Reason | Typical Impact | Evidence Required |
|--------|----------------|-------------------|
| New customer | +5-20% | Signed contract |
| Lost customer | -5-20% | Confirmed loss |
| Promotion | +20-100% | Marketing plan |
| Competitor action | ±10-30% | Market data |
| Economic conditions | ±10-20% | Macro indicators |
```

**Tools:** Forecasting software, Excel, meeting framework

**Output:** Rolling 12-month forecast by SKU with accuracy tracking

---

## Examples

### Example 1: Full SKU Analysis

**Product:** GTSE Cable Ties 300mm Black 100pk (CT300BK100)

**Historical Analysis (3 years):**
- Total Year 3 sales: 4,650 units
- Average monthly: 388 units
- Standard deviation: 48 units
- CV: 12% (Stable X classification)
- Annual revenue: £41,851
- Classification: A-X (high value, stable)

**Seasonality:**
- Peak months: March (120 index), September (113 index)
- Trough months: December (79 index), January (89 index)
- Pattern: Spring project surge + back-to-work

**Lead Time:**
- Supplier: China manufacturer
- Average lead time: 42 days
- Lead time std dev: 7 days
- Planning lead time: 56 days (conservative)

**Safety Stock:**
- Target service level: 99% (A-item)
- Z-value: 2.33
- σDL: 88 units
- Safety stock: 205 units

**Reorder Point (March - peak month):**
- Daily demand: 14.4 units (seasonally adjusted)
- ROP = (14.4 × 56) + 205 = 1,011 units

**Order Quantity:**
- EOQ: 655 units (calculated)
- MOQ: 1,000 units (supplier)
- Order quantity: 1,000 units

**Inventory Investment:**
- Average inventory: 705 units
- Inventory value: £1,727
- Turns: 6.6x per year

---

### Example 2: New Product Forecast

**Product:** New VDE Screwdriver Set (VDE-SET-PRO)

**No historical data available**

**Approach: Analogous Product Method**

**Step 1: Identify similar product**
- Existing: VDE-SET-8 (8-piece set)
- Year 3 sales: 1,200 units
- Price: £34.99

**Step 2: Estimate new product as ratio**
- New product: 12-piece premium set
- Price: £49.99 (+43%)
- Expected volume: 60-80% of base product
- Estimate: 840 units Year 1

**Step 3: Apply launch curve**
| Quarter | % of Annual | Units |
|---------|-------------|-------|
| Q1 (launch) | 15% | 126 |
| Q2 | 22% | 185 |
| Q3 | 28% | 235 |
| Q4 | 35% | 294 |

**Step 4: Set conservative inventory**
- Safety stock: 30 units (higher due to uncertainty)
- Initial order: 150 units
- Reorder point: 50 units
- Review: Monthly for first 6 months

---

### Example 3: Seasonal Inventory Plan

**Product Category:** Garden Cable Ties (seasonal)

**Problem:** Garden products have 3:1 peak-to-trough ratio

**Current approach:** Fixed safety stock → overstock in winter, stockouts in spring

**Seasonal Inventory Strategy:**

| Month | Index | Monthly Demand | Safety Stock | ROP | Notes |
|-------|-------|----------------|--------------|-----|-------|
| Jan | 0.5 | 100 | 50 | 120 | Build stock |
| Feb | 0.6 | 120 | 60 | 160 | Pre-season prep |
| Mar | 1.4 | 280 | 140 | 420 | Peak begins |
| Apr | 1.6 | 320 | 160 | 480 | Peak |
| May | 1.5 | 300 | 150 | 450 | Peak |
| Jun | 1.2 | 240 | 120 | 360 | Moderate |
| Jul | 1.0 | 200 | 100 | 300 | Normal |
| Aug | 0.8 | 160 | 80 | 240 | Decline |
| Sep | 0.6 | 120 | 60 | 180 | Low |
| Oct | 0.5 | 100 | 50 | 150 | Low |
| Nov | 0.5 | 100 | 50 | 150 | Low |
| Dec | 0.5 | 100 | 50 | 150 | Low |

**Key Actions:**
1. February: Place large order for peak season (3-month supply)
2. March-May: Weekly inventory reviews
3. August: Reduce orders, let stock deplete
4. October-January: Minimal inventory, quick replenishment

---

## Output Format

### SKU Inventory Parameter Card

```markdown
# Inventory Parameters: [SKU]

**Product:** [Name]
**Category:** [Category]
**Classification:** [ABC-XYZ]
**Supplier:** [Name]

## Demand Profile
- Annual demand: [Units]
- Monthly average: [Units]
- Daily average: [Units]
- Seasonality: [Pattern description]
- Peak months: [List]

## Lead Time
- Supplier: [Name]
- Average: [Days]
- Planning: [Days]

## Inventory Parameters
- Service level: [%]
- Safety stock: [Units]
- Reorder point: [Units]
- Order quantity: [Units]

## Financial
- Unit cost: [£]
- Inventory value target: [£]
- Annual turns: [X]

## Review Schedule
- Frequency: [Weekly/Monthly/Quarterly]
- Next review: [Date]

---
Last Updated: [Date]
Analyst: [Name]
```

---

## Related Skills

- [Amazon Product Launch](../../amazon/product-launch/SKILL) - Launch inventory
- [Pricing Strategy](../../ecommerce/pricing-strategy/SKILL) - Margin impact
- [B2B Account Penetration](../../b2b/account-penetration/SKILL) - Customer forecasting
- [Product Photography](../../content/product-photography/SKILL) - New product prep

---

## Appendix

### A: Z-Value Reference Table

| Service Level | Z-Value | Safety Stock Multiple |
|---------------|---------|----------------------|
| 80% | 0.84 | 0.84σ |
| 85% | 1.04 | 1.04σ |
| 90% | 1.28 | 1.28σ |
| 95% | 1.65 | 1.65σ |
| 97.5% | 1.96 | 1.96σ |
| 99% | 2.33 | 2.33σ |
| 99.5% | 2.58 | 2.58σ |
| 99.9% | 3.09 | 3.09σ |

### B: EOQ Sensitivity Analysis

How EOQ changes with different inputs:

| Holding Cost | Order Cost | EOQ Impact |
|--------------|------------|------------|
| ↑ Higher | Same | ↓ Smaller orders |
| Same | ↑ Higher | ↑ Larger orders |
| ↑ Higher | ↑ Higher | → Depends on ratio |

### C: Seasonal Index Calculator

```
Monthly Index = (Avg Month Sales / Avg All Months)

Example:
- March average: 422 units
- Overall monthly average: 351 units
- March index: 422/351 = 1.20

Validation:
Sum of 12 monthly indices should equal 12.0 (±0.1)
```

### D: Key Performance Indicators

| KPI | Formula | Target | Frequency |
|-----|---------|--------|-----------|
| Service Level | Orders shipped complete / Total orders | >95% | Weekly |
| Stockout Rate | SKUs at zero stock / Total SKUs | <2% | Daily |
| Inventory Turns | Annual COGS / Avg Inventory | >4x | Monthly |
| Forecast Accuracy | 1 - MAPE | >85% | Monthly |
| Days of Supply | Inventory / Daily demand | 30-60 days | Weekly |

---

*Version 1.0.0 | Last Updated: 2025*
*For GTSE internal use - Confidential*
