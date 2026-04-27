# LeadLens — Ad Performance & Lead Quality Analytics
> *Data-driven insights to evaluate performance and capture the 20% CPL premium*

---

##  Project Overview

LeadLens is an end-to-end data analytics project built to analyze **3,000+ ad leads** for a Debt Settlement advertiser. Using Python, statistical testing, and machine learning models, this project identifies the key drivers of lead quality and delivers a **3-step strategic roadmap** to increase Cost Per Lead (CPL) from **$30 → $33**.

---

## 🧠 Understanding the Business

### Who is Involved?

| Stakeholder | Role |
|-------------|------|
| **Publisher** | Runs ads on Google, Yahoo, AdKnowledge — collects form submissions (leads) |
| **Advertiser (DebtReductionInc)** | Buys leads at $30/lead — calls consumers to sell debt settlement services |
| **Consumer (Lead)** | Person with debt who filled out an online form |

### How It Works
```
Consumer searches "debt help" on Google
        ↓
Publisher's Ad appears → Consumer fills form
        ↓
Lead Created → Publisher sells to Advertiser @ $30
        ↓
Advertiser calls consumer
        ↓
CLOSED (customer) ✅  OR  Wasted ❌
```

---

## 🎯 Business Problem

```
Total Leads Bought    : 3,000
Cost Per Lead (CPL)   : $30
Total Spend           : $90,000

Leads that CLOSED     : ~240 (only 8%!)
Leads WASTED          : ~2,760 (92% waste)
```

**Advertiser's Offer:**
> *"Improve lead quality from 8.0% to 9.6%, and we will increase CPL from $30 to $33"*

---

## 📊 Dataset — 24 Columns

| Column | Description | Used? |
|--------|-------------|-------|
| A — LeadCreated | Date lead was created | ✅ Trend analysis |
| **E — CallStatus** | **Final lead outcome** | ✅ Target variable |
| **F — WidgetName** | **Ad design, size, 1DC vs 2DC** | ✅ Key driver |
| G — PublisherZoneName | Ad placement on page | ✅ Placement |
| H — PublisherCampaignName | Online vs Call Center | ✅ Source |
| I — AddressScore | Name-address match (1-5) | ✅ Data quality |
| J — PhoneScore | Name-phone match (1-5) | ✅ Data quality |
| **M — DebtLevel** | Consumer's debt amount | ✅ Key driver |
| **O — Partner** | Google / Yahoo / AdKnowledge | ✅ Key driver |
| L — State | Consumer's state | ✅ Geography |
| S/T — Keywords | Search keywords | ✅ Intent |

### Lead Quality Classification

| CallStatus | Category |
|-----------|----------|
| Closed, EP Sent/Received/Confirmed | ✅ GOOD |
| Unable to Contact, Invalid Profile, Doesn't Qualify | ❌ BAD |
| All others | ⚪ UNKNOWN |

---

## 🔍 Key Findings

### 1️⃣ Monthly Trend (Chi-Square Test)

| Month | Good Rate | Bad Rate |
|-------|-----------|----------|
| April | 15.3% | 11.0% |
| July | **9.2% ❌** | 20.7% |
| September | **16.9% ✅** | 16.3% |

> **83% swing** — p = 9.15×10⁻¹⁸ → NOT random — operational shifts causing it

---

### 2️⃣ Ad Creative Driver

| Ad Type | Good Rate |
|---------|-----------|
| 1-Page Branded | **23.4% ✅** |
| 1-Page Generic | 16.1% |
| 2-Page Branded | **10.7% ❌** |

---

### 3️⃣ Debt Level Driver

| Debt Range | Good Rate | Verdict |
|-----------|-----------|---------|
| $7,500–$10,000 | 7.0% | ❌ Worst |
| **$10,001–$15,000** | **18.5%** | ✅ Best |
| **$70,001–$90,000** | **19.0%** | ✅ Best |
| >$100,000 | 6.8% | ❌ Avoid |

---

### 4️⃣ Traffic Partner Driver

| Partner | Good Rate |
|---------|-----------|
| **AdKnowledge** | **18.7% 🏆** |
| Call Center | 16.2% ⚠️ |
| Yahoo | 14.1% |
| Google | 11.1% ❌ |

---

## 📈 3-Step Optimization Roadmap

**Step 1 — Optimize UX**
- ✅ Use only 1-page branded forms (23.4% Good rate)
- ❌ Remove all 2-page forms

**Step 2 — Cut Dead Weight**
- ❌ Stop targeting $7.5k–$10k debt segment
- ✅ Focus on $10k–$15k and $70k–$90k

**Step 3 — Reallocate Budget**
- 💸 Shift Google spend → AdKnowledge
- 🚫 Add negative keywords: "student", "default"

### Business Impact
```
Current Quality :  8.0%  →  Target: 9.6%  
Current Revenue : $90,000 → New: $99,000
Extra Revenue   : +$9,000 per 3,000 leads 
```

## 🛠️ Tech Stack

```
Python · Pandas · NumPy · SciPy · Scikit-learn · Matplotlib · Seaborn · Excel
```

---

## 🤖 Models Used

| Model | Purpose |
|-------|---------|
| **Chi-Square Test** | Validate if quality swings are statistically significant |
| **Moving Average** | Smooth monthly quality fluctuations |
| **Linear Regression** | Ad Spend vs Leads relationship |
| **Logistic Regression** | Predict Good/Bad lead |
| **Random Forest** | Feature importance — which factor matters most |

---

## 📁 Project Structure

```
LeadLens/
│
├── SOLUTION.xlsx              ← Raw Data (3,000+ leads, 24 columns)
├── LeadLens_Analysis.py       ← Complete Python Code
├── LeadLens_Notebook.ipynb    ← Jupyter Notebook
├── LeadLens_Code.pdf          ← PDF Version
│
├── charts/
│   ├── chart_1_monthly_trend.png
│   ├── chart_2_segment_analysis.png
│   ├── chart_3_linear_regression.png
│   └── chart_4_feature_importance.png
│
└── README.md                
```

---

## 🚀 How to Run

**Step 1 — Install Dependencies**
```bash
pip install pandas numpy scipy scikit-learn matplotlib seaborn openpyxl
```

**Step 2 — Run Python Script**
```bash
python LeadLens_Analysis.py
```

**OR Run in Jupyter Lab**
```bash
jupyter lab
```
> Open `LeadLens_Notebook.ipynb` → Press `Shift + Enter` cell by cell

> ⚠️ Make sure `SOLUTION.xlsx` is in the **same folder** as the code!

## 👨‍💻 Author

**Vivek Upadhyay**

