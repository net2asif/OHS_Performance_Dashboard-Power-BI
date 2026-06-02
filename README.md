# 🦺 OHS Performance Dashboard — Power BI
### Occupational Health & Safety Intelligence Report | 2024 – 2026 | Kingdom of Saudi Arabia

---

![Power BI](https://img.shields.io/badge/Power%20BI-Advanced-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-30%20Measures-0078D4?style=for-the-badge)
![Data](https://img.shields.io/badge/Dataset-1%2C000%20Rows-22C55E?style=for-the-badge)
![Sites](https://img.shields.io/badge/KSA%20Sites-8%20Locations-EF4444?style=for-the-badge)

---

## 📌 Project Overview

A fully interactive **5-page Power BI dashboard** built to track, analyze, and present Occupational Health & Safety performance across a 3-year period (2024–2026). The dashboard covers **1,000 incidents**, **10 departments**, and **8 sites across Saudi Arabia**, delivering real-time KPIs, trend analysis, and compliance tracking to support data-driven safety decisions.

> *"This dashboard does not just report on safety — it enables it. When you can see the patterns, you can intervene before the next incident happens."*

---

## 🖥️ Dashboard Pages

| # | Page | Purpose |
|---|------|---------|
| 1 | 🏠 **Introduction** | Project scope, KPI snapshot, navigation |
| 2 | 📈 **Executive Summary** | TRIR, LTIFR, Days Since LTI, Safety Score |
| 3 | 🔍 **Incident Deep Dive** | Root cause, department, shift, location analysis |
| 4 | ✅ **Compliance & CAPA** | Training, investigations, corrective actions |
| 5 | 📖 **3-Year Safety Story** | Year-over-year improvement narrative |

---

## 📐 Data Model

```
┌─────────────────────────────────┐        ┌──────────────────────┐
│   OHS_Incidents_2024_2026       │        │   OHS_Date_Table     │
│   (Fact Table — 1,000 rows)     │ *────1 │   (1,096 rows)       │
│   [Date] ───────────────────────┼────────▶ [Date]               │
└─────────────────────────────────┘        └──────────────────────┘

                    ┌──────────────────────┐
                    │   _OHS Measures      │
                    │   (30 DAX measures)  │
                    │   Disconnected ✅    │
                    └──────────────────────┘
```

---

## 📊 KPIs & Measures (30 Total)

### 🔢 Base Counts
`Total Incidents` · `Recordable Incidents` · `Lost Time Injuries` · `Near Misses` · `Total Days Lost` · `Open CAPAs` · `Overdue CAPAs`

### 📉 Rate KPIs
| Measure | Formula | Benchmark |
|---------|---------|-----------|
| **TRIR** | Recordable × 200,000 ÷ Manhours | < 1.0 = Good |
| **LTIFR** | LTI × 1,000,000 ÷ Manhours | < 1.0 = Good |
| **Severity Rate** | Days Lost × 200,000 ÷ Manhours | Lower = Better |
| **Near Miss Ratio** | Near Misses ÷ Recordable | Higher = Better |

### 📅 Time Intelligence
`YTD Incidents` · `PYTD Incidents` · `YoY % Change` · `Rolling 12M` · `MoM Change %`

### ✅ Compliance
`CAPA Closure Rate` *(Target 85%)* · `Training Compliance %` *(Target 90%)* · `Investigation Completion %` *(Target 95%)* · `Reported Within 24h %`

### 🏆 Advanced
`Days Since Last LTI` · `Safety Score /100` · `TRIR Status` · `Incident Rank by Dept` · `TRIR 2024/2025/2026`

---

## 📋 Dataset Columns

| Column | Description |
|--------|-------------|
| `IncidentID` | Unique ID (INC-0001 format) |
| `Date` | Incident date (2024–2026) |
| `Department` | 10 departments |
| `Location` | 8 KSA sites (Riyadh, Jeddah, Dammam, Mecca, Medina…) |
| `IncidentType` | Near Miss, LTI, MTC, First Aid, Property Damage… |
| `Severity` | Low / Medium / High / Critical |
| `RootCause` | Unsafe Act, Equipment Failure, Human Error… |
| `DaysLost` | Working days lost |
| `CAPAStatus` | Open / In Progress / Closed / Overdue |
| `TrainingCompliant` | Yes / No |
| `Recordable` | Yes / No |
| `NearMiss` | Yes / No |
| `InvestigationComplete` | Yes / No |
| `ReportedWithin24h` | Yes / No |

---

## 🎨 Color Theme — Dark Dashboard

| Element | Hex Code |
|---------|----------|
| Canvas Background | `#12141F` |
| Card Background | `#1E2030` |
| Card Border | `#2A2D3E` |
| KPI Value Text | `#FFFFFF` |
| Label Text | `#9BA3B8` |
| Trend Up ▲ | `#22C55E` |
| Trend Down ▼ | `#EF4444` |
| Line 1 — 2024 | `#3B82F6` |
| Line 2 — 2025 | `#6B7280` |
| Line 3 — 2026 | `#10B981` |

---

## 🚀 How to Use

**1. Load Data**
```
Power BI Desktop → Home → Get Data → Text/CSV
Load: OHS_Incidents_2024_2026.csv + OHS_Date_Table.csv
```

**2. Create Relationship**
```
Model View → Drag OHS_Incidents[Date] → OHS_Date_Table[Date]
Cardinality: Many to One
```

**3. Mark Date Table**
```
Right-click OHS_Date_Table → Mark as Date Table → Select [Date]
```

**4. Create Measures Table**
```
Home → Enter Data → Name: "_OHS Measures" → Load
Right-click table → New Measure → paste DAX from /dax folder
```

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Power BI Desktop** | Dashboard development |
| **DAX** | KPI calculations & time intelligence |
| **Power Query (M)** | Data transformation |
| **Tabular Editor** | Bulk measure creation |
| **Python** | Sample dataset generation |

---

## 📂 Repository Structure

```
OHS-Dashboard-PowerBI/
│
├── 📁 data/
│   ├── OHS_Incidents_2024_2026.csv
│   ├── OHS_Date_Table.csv
│   └── OHS_Measures_Table.csv
│
├── 📁 dax/
│   ├── 01_base_counts.dax
│   ├── 02_rate_kpis.dax
│   ├── 03_time_intelligence.dax
│   ├── 04_compliance.dax
│   └── 05_advanced_kpis.dax
│
├── 📁 docs/
│   ├── OHS_PowerBI_Complete_Guide.md
│   ├── color_palette.md
│   └── data_dictionary.md
│
├── 📁 screenshots/
├── README.md
├── LICENSE
└── .gitignore
```

---

## 📖 OHS Glossary

| Term | Definition |
|------|-----------|
| **TRIR** | Total Recordable Incident Rate per 200,000 hrs |
| **LTIFR** | Lost Time Injury Frequency Rate per 1,000,000 hrs |
| **LTI** | Lost Time Injury — worker misses next scheduled work day |
| **Near Miss** | Unsafe event that caused no injury — this time |
| **CAPA** | Corrective and Preventive Action |
| **RLS** | Row Level Security — role-based data access |
| **ISO 45001** | International OHS management system standard |
| **Heinrich's Triangle** | 1 fatality : 10 serious : 30 minor : 300 near misses |

---

## 👤 Author

**Muhammad Asif**
OHS Coordinator & Reports Specialist
📍 Riyadh, Kingdom of Saudi Arabia

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat&logo=linkedin)](https://linkedin.com)
[![Power BI](https://img.shields.io/badge/Power%20BI-Portfolio-F2C811?style=flat&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com)

---

## 📄 License

This project is open source under the [MIT License](LICENSE).

---

*Built with Power BI · DAX · Python · Saudi Vision 2030 🇸🇦*
