# Automated-E-Commerce-Executive-Dashboard
## Overview
This project demonstrates a clean and automated Excel-based reporting system designed for executive-level monitoring of e-commerce performance.
Raw transactional data is processed behind the scenes using Power Query and Data Modeling, then presented through a single, user-friendly dashboard sheet.

### Key idea:
Users only see insights.
All complexity stays hidden.

## Architecture Design
```
Raw Data (CSV / Excel)
        ↓
[DATA Sheet] (Hidden - Raw Storage)
        ↓
Power Query (Cleaning & Transformation)
        ↓
[CALC Sheet] (Hidden - Data Model & Measures)
        ↓
DAX Measures (KPIs & Logic)
        ↓
[DASHBOARD Sheet] (Visible - UI Layer)
```

## Dashboard Preview
![Dashboard Preview](/assets/dashboard_preview.png)

## Tech Stack
- Power Query (M) → Data cleaning & transformation
- Power Pivot → Data modeling & relationships
- DAX → KPI calculations & dynamic logic
- Excel Dashboards → Final presentation layer

## Key Features
### 1. Clean UI (Executive-Friendly)
    - Single-page dashboard
    - Minimalist layout (no clutter, no nonsense)
    - Focused only on key business metrics

    Visible components:
    - Total Sales
    - Total Transactions
    - Refund Rate
    Sales breakdown by:
        - Location
        - Product
### 2. Hidden Processing Layers (Important)
To maintain usability, all technical layers are hidden:
| Sheet       | Purpose                   |
| ----------- | ------------------------- |
| `DATA`      | Raw imported dataset      |
| `CALC`      | Data model & calculations |
| `DASHBOARD` | Final visual interface    |

This separation ensures:
- Cleaner user experience
- Better maintainability
- Safer interaction (no accidental edits)

### 3. KPI Calculations (DAX)
```
Total Sales := SUM(dirty_ecommerce_data_2026[Sales_Amount])

Total Transaction := COUNTROWS(dirty_ecommerce_data_2026)

Refund Rate = DIVIDE([Total Refund],[Total Transaction])

```

### 4. Interactive Filtering (Slicers)
Users can filter data dynamically by:
- Location
- Product

All visuals update instantly.
Because static reports are basically PDFs pretending to be useful.

### 5. Automated Data Refresh
To update the dashboard:
1. Replace or update raw data
2. Click:
    `` Data → Refresh All ``
3. Dashboard updates automatically

No manual recalculation. No copy-paste rituals.