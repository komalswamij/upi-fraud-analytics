# UPI Transaction Fraud Detection

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-yellow?logo=powerbi)
![Excel](https://img.shields.io/badge/Excel-Power%20Query-green?logo=microsoft-excel)
![Random Forest](https://img.shields.io/badge/ML-Random%20Forest-orange)
![AUC](https://img.shields.io/badge/AUC-0.905-brightgreen)

**Author:** Komal Swami | **Project ID:** 24CRD02538 | **Domain:** Financial Fraud Detection

---

## 🎯 Project Overview

End-to-end analytics pipeline on **1,00,000 UPI transactions** to detect fraudulent activity using machine learning, visualize patterns across multiple dimensions, and deliver business-ready reports for stakeholders.

**Problem Statement:** Identify high-risk UPI transactions using behavioral, device, geographic, and temporal patterns — and build a reusable fraud-scoring pipeline with 4-tier risk classification (CRITICAL / HIGH / MEDIUM / LOW).

---

## 🔑 Key Findings

| Finding | Value |
|---------|-------|
| Overall Fraud Rate | 2.00% |
| Rooted Device Fraud Rate | **20.69%** — 15× higher than non-rooted |
| Alert Resolution Rate | 87.60% |
| CRITICAL Risk Transactions | 8,010 (18% fraud rate) |
| Electronics Merchant Fraud Rate | 2.24% — above 2.2% threshold |
| Random Forest AUC | **0.905** |
| Fraud Recall | ~94% |

---

## 🔄 Pipeline

```
Raw CSV Data (7 files, 1,00,000 rows)
        ↓
0_Data_Prep  → Project flowchart & planning
        ↓
1_datasets   → Raw source data (7 CSV files)
        ↓
2_Excel      → Power Query cleaning
               (deduplication, null handling, type fixing)
        ↓
3_Python     → EDA + Feature Engineering (36 columns)
             → Random Forest Model (AUC 0.905, ~94% recall)
             → 4-tier Risk Scoring Engine
             → 8 visualization exports (PNG)
        ↓
4_PowerBI    → 2-page interactive dashboard
             → Executive Overview + Fraud Analysis
             → 10 DAX measures, Drillthrough, Tooltip page
        ↓
5_report_ppt → Complexity analysis + Stakeholder report + PPT
```

---

## 📁 Project Structure

```
UPI_Fraud/
│
├── README.md
├── LICENSE
│
├── 0_Data_Prep/
│   └── UPI_Fraud_Project_Flowchart.png      ← Full pipeline flowchart
│
├── 1_datasets/                               ← 7 raw CSV source files
│   ├── upi_transaction_history.csv
│   ├── customer_master.csv
│   ├── device_info.csv
│   ├── upi_account_details.csv
│   ├── merchant_info.csv
│   ├── fraud_alert_history.csv
│   └── customer_feedback_surveys.csv
│
├── 2_Excel/
│   └── power_query_final.xlsx               ← Cleaned data via Power Query
│
├── 3_Python/
│   ├── UPI_fraud_detection.ipynb            ← Main Jupyter notebook
│   ├── upi_fraud_optimized.xls              ← Feature engineered dataset (36 cols)
│   ├── upi_scored_transactions.xls          ← 4-tier risk scored output
│   ├── 01_kpi_summary.png
│   ├── 02_fraud_by_device.png
│   ├── 03_fraud_by_region.png
│   ├── 04_fraud_by_channel.png
│   ├── 05_fraud_by_merchant.png
│   ├── 06_monthly_trends.png
│   ├── 07_model_performance.png
│   └── 08_risk_scoring.png
│
├── 4_PowerBI/
│   ├── dashboard_first.pbix                 ← Interactive Power BI dashboard
│   └── dashboard_first.pdf                  ← PDF export for reviewers
│
└── 5_report_ppt/
    ├── complexity_analysis.md               ← Time & Space complexity
    ├── overall_time_space_complexity.png    ← Complexity visual
    ├── UPI_Fraud_Detection_Stakeholder_Report.docx
    └── UPI_Fraud_KomalSwami_Stakeholder.pptx
```

---

## 📊 Power BI Dashboard

**Page 1 — Executive Overview**
- 5 KPI cards: Total Transactions, Fraud Rate %, Failure Rate %, Avg Amount, Alert Resolution %
- Monthly trend line chart (transactions + fraud rate)
- Transaction type donut chart
- Fraud Rate % by region bar chart
- 5 slicers: Region, Transaction Type, Status, Month, Channel
- Drillthrough page + Tooltip page

**Page 2 — Fraud Analysis**
- 3 KPI cards: Rooted Device Fraud Rate, Blocked Account Txns, Channel Mismatch Txns
- Fraud Rate % by device type bar chart
- Risk tier distribution donut (CRITICAL / HIGH / MEDIUM / LOW)
- Fraud Rate % by merchant type bar chart
- Alert resolution stacked bar chart

---

## 🤖 ML Model Details

| Parameter | Value |
|-----------|-------|
| Algorithm | Random Forest Classifier |
| Features used | 36 engineered columns |
| AUC-ROC | 0.905 |
| Fraud Recall | ~94% |
| Risk tiers | CRITICAL / HIGH / MEDIUM / LOW |
| n_estimators | 100 |
| max_depth | 10 |
| Train/Test split | 80/20 |

**Top fraud predictors:**
- `is_rooted` — strongest signal (20.69% fraud rate)
- `customer_risk_score`
- `merchant_risk_score`
- `channel_device_mismatch_flag`
- `blocked_account_flag`
- `amount_vs_avg_ratio`

---

## ⏱️ Complexity Summary

| Type | Complexity | Actual |
|------|------------|--------|
| Time | O(T·n·d·log n) | ≈ 3.39 billion ops |
| Space | O(n·d) | ≈ 2.6 million cells |

See [`5_report_ppt/complexity_analysis.md`](5_report_ppt/complexity_analysis.md) for full breakdown.

---

## 🐍 Python Setup

```bash
pip install pandas numpy scikit-learn matplotlib seaborn openpyxl jupyter
```

**Run notebook:**
```bash
jupyter notebook UPI_fraud_detection.ipynb
```

---

## 📄 Reports

| File | Audience |
|------|----------|
| `UPI_Fraud_Detection_Stakeholder_Report.docx` | Technical reviewers |
| `UPI_Fraud_KomalSwami_Stakeholder.pptx` | Management / evaluators |

> 💡 **No Power BI Desktop?** Open `4_PowerBI/dashboard_first.pdf` for dashboard screenshots.

---

## 📬 Contact

**Komal Swami**
- LinkedIn: https://www.linkedin.com/in/komal-swami-ds/
- Project ID: 24CRD02538
