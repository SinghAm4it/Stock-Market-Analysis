# Adani Enterprises Limited Stock Analysis (Power BI Dashboard)

## 📌 Project Overview
This project is an interactive **Power BI dashboard** built using **1-year historical NSE stock data for Adani Enterprises Limited**.  
The objective of this dashboard is to provide **analytics-based insights** using:

- trend indicators (Moving Averages)
- technical signals (Golden Cross & Death Cross)
- volume anomaly detection (Volume Spike Ratio)
- price strength analysis (VWAP vs Close)
- trading activity diagnostics (Volume vs Number of Trades)

This dashboard helps answer key analytical questions such as:
- *Is the stock in an uptrend or downtrend?*
- *When did bullish/bearish trend reversal signals occur?*
- *How does trading activity impact stock price movement?*
- *Which months were most volatile / most active?*
- *When did abnormal volume events occur and what was the price impact?*

---

## 🧾 Dataset Details
The dataset contains daily price and trading activity metrics including:

- `DATE`
- `OPEN`, `HIGH`, `LOW`, `CLOSE`
- `PREV. CLOSE`
- `VWAP` (Volume Weighted Average Price)
- `52W H`, `52W L`
- `VOLUME`
- `VALUE` (turnover / total money traded)
- `NO. OF TRADES`

Time hierarchy fields were also created:
- DAY
- MONTH
- QUARTER
- YEAR

---

## 🎯 Dashboard Features
### Filters / Slicers
The dashboard supports interactive filtering using:
- **DAY**
- **MONTH**
- **QUARTER**
- **YEAR**

This allows user-driven exploration of price movement and trading patterns across multiple time periods.

---

## KPI Summary Cards (Top Insights)
The dashboard displays key headline metrics:

- **Max 52W High**: Highest observed 52-week high value during selected time range  
- **Min 52W Low**: Lowest observed 52-week low value during selected time range  
- **Avg Opening Price**: Average daily open price for selected period  
- **Avg Closing Price**: Average daily close price for selected period  
- **Total Volume**: Total shares traded during selected period  

📌 **Meaning:**  
These KPIs provide a quick “stock health snapshot”:
- whether stock traded closer to its highs or lows
- whether price is stable or fluctuating
- how much market participation existed during the period

---

#  Visual Insights Explained (Chart-by-Chart)

## 1) Avg of Daily Movement by Year and Month
### What it shows
This line chart shows **average daily movement** aggregated month-wise.

### Why it matters
This chart highlights:
- which months had high market fluctuations
- periods of higher uncertainty / volatility

### 💡 Insight we can derive
- months with sharp rise/fall represent **unstable market sentiment**
- stable flat movement months represent **consolidation phase** (range-bound stock)

---

## 2) Golden Cross & Death Cross Signal Chart (MA20 / MA50)
### What it shows
This chart contains:
- **Close Price trend**
- **MA20 (20-day moving average)**
- **MA50 (50-day moving average)**
- Marked **Golden Cross** and **Death Cross** signal events

### Meaning of indicators
#### Moving Average (MA)
- MA smooths price fluctuations
- helps identify overall trend direction

#### Golden Cross (Bullish Signal)
Occurs when:
- MA20 crosses above MA50  
indicates bullish trend reversal / uptrend confirmation

#### Death Cross (Bearish Signal)
Occurs when:
- MA20 crosses below MA50  
indicates bearish trend reversal / downtrend confirmation

### 💡 Insights from the chart
- The stock experienced **trend regime changes** indicated by crossover events
- multiple signals suggest the stock did not remain in one trend direction throughout the year

### What this predicts
- After Golden Cross: probability of upside trend increases
- After Death Cross: probability of downside trend increases
  
---

## 3) Avg No. of Trades and Avg Volume by Year and Month
### What it shows
This chart compares:
- **Avg Volume (shares traded)**
- **Avg No. of Trades (transactions executed)**

### Why it matters
This chart helps detect trading behaviour:
- **High trades + low/moderate volume** → retail-driven activity
- **Low trades + high volume** → institutional/bulk order activity

### 💡 Insights from this visual
- months with high volume spikes represent periods of high market interest
- changes in trade count indicate shifts in participation

**Business Insight:**  
This chart helps understand whether activity is driven by many small buyers/sellers or fewer large participants.

---

## 4) Avg VWAP and Avg Closing Price by Month
### What it shows
This compares:
- Monthly average VWAP
- Monthly average Closing price

### Meaning of VWAP
**VWAP (Volume Weighted Average Price)** reflects the “fair average traded price” because it is weighted by volume.

### Interpretation rules
- **Close > VWAP** → buyers dominated (bullish pressure)
- **Close < VWAP** → sellers dominated (bearish pressure)

### 💡 Insights from this visual
- If close price consistently remains above VWAP across months → strong bullish demand
- frequent close below VWAP → weakness and selling pressure

**Why this is important:**  
VWAP helps validate whether the day/month ended with buying or selling strength.

---

## 5) Daily Volume Spike Ratio (Abnormal Trading Detection)
### What it shows
This chart tracks the **Volume Spike Ratio**, which measures:

> Today's volume ÷ Average volume of last 20 days

### Interpretation
- **Ratio ≈ 1.0** → normal day
- **Ratio ≥ 2.0** → high-volume spike day
- **Ratio ≥ 3.0** → extreme anomaly activity

### Why it matters
Volume spikes often occur during:
- news events
- earnings announcements
- major market sentiment change
- institutional entry/exit

### 💡 Insights from this visual
- spike days correspond to high market attention periods
- spike detection helps identify “significant days” automatically

 **Predictive value:**  
After volume spike, stock often shows increased volatility and sharper price movement.

---

# ✅ Key Insights Answered (From Dashboard)

## Insight 1: What is the overall trend?
Using MA20/MA50 and closing trend:
- The dashboard shows periods of both upward and downward movement
- Trend direction shifts are captured via Golden/Death cross

Conclusion:  
Stock did not remain in a single trend for the entire year; it experienced 2 death crosses and a golden cross in a single year.

---

## Insight 2: When did major trend reversals happen?
Golden and Death Cross markers identify:
- bullish reversal points (Golden Cross)
- bearish reversal points (Death Cross)

Conclusion:  
Crossover events are key “signal dates” and can be treated as turning points.

---

## Insight 3: Do volume spikes affect movement?
Volume spike chart highlights abnormal volume days.

Conclusion:  
Volume spikes are associated with market participation shocks and often increase volatility; these are high-impact trading days. Volume Spike Ratio above 3 was observed multiple times and the daily movement on that day was more than normal days.

---

## Insight 4: How strong is price relative to VWAP?
VWAP vs Close chart indicates buying vs selling pressure.

Conclusion:
If close is often above VWAP, buying strength exists.
If close frequently below VWAP, selling pressure exists.
Here monthyl average close was frequently below monthly average VWAP thus it can concluded that still there is selling pressure.

---

# 🛠 Tools & Techniques Used
- Power BI Desktop
- Power Query (data cleaning, types, derived time fields)
- DAX measures for:
  - MA20, MA50
  - Golden Cross / Death Cross signals
  - Volume Spike Ratio (rolling 20-day avg)
- Interactive filtering with slicers
