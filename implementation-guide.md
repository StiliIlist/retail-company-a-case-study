# Implementation Guide
**Retail Company A – Demand Planning Excel Dashboard Setup & Usage Instructions**

## 1. Overview
This guide explains how to configure, populate, and maintain the Retail Company A Demand Planning Excel Dashboard, ensuring seamless integration with your data sources and alignment with SOP processes.

## 2. File Structure
```
excel-dashboard/
├── Retail-Company-A-Dashboard.xlsx  # Main workbook
└── data/
    ├── sales_data.csv               # Daily/weekly sales
    ├── inventory_snapshot.csv       # Current stock levels
    ├── marketing_calendar.csv       # Campaign schedule & lift factors
    └── supplier_performance.csv     # Lead times & OTIF
```

### Data Refresh Workflow
1. **Extract** raw data from ERP/e-commerce platform (as CSV).
2. **Replace** existing CSVs in `data/` folder (must keep filenames).
3. **Open** Excel workbook and **Refresh All** (Data tab > Refresh All).
4. **Review** dashboards for updated KPIs and alerts.

## 3. Initial Configuration
### 3.1 Sales Data Mapping
- **Required Columns:** `date`, `sku`, `units_sold`, `revenue`
- Ensure date format = `YYYY-MM-DD`
- Save as `sales_data.csv` in data folder

### 3.2 Inventory Snapshot
- **Required Columns:** `sku`, `on_hand_units`, `warehouse`, `updated_at`
- Populate daily before 08:00 for dashboard accuracy

### 3.3 Marketing Calendar
- **Required Columns:** `start_date`, `end_date`, `campaign_name`, `lift_factor`
- Lift factor example: 1.3 = 30% sales lift during campaign

### 3.4 Supplier Performance
- **Required Columns:** `supplier`, `avg_lead_time_days`, `otif_pct`, `last_delivery`

## 4. Dashboard Components
### 4.1 Executive Summary Tab
- **KPIs:** Inventory Value, WOS avg, Forecast Accuracy, Low Stock Count, Excess Stock Count
- **Conditional Formatting:** Traffic lights for KPI thresholds

### 4.2 Historical Sales Tab
- 104-week weekly aggregation
- Trend charts auto-update after data refresh

### 4.3 Demand Forecast Tab
- **FORECAST.ETS** function generates 26-week projection
- Confidence intervals shown as shaded area on line chart

### 4.4 Current Inventory Tab
- Reorder Point calculation = `ROUNDUP((Avg Weekly Demand*Lead Time Weeks)+(1.65*StdDev),0)`
- Conditional formatting highlights reorder needs

### 4.5 Supplier Management Tab
- OTIF trends, average lead times, and supplier ranking

## 5. Updating Formulas
- **Forecast Parameters:** Located in hidden sheet `Parameters` (seasonality, dampening factor)
- **Safety Stock Z-Score:** Default 1.65 (95% service), adjust if needed
- **Campaign Lift Range:** Editable cells with Data Validation dropdown

## 6. Scenario Planning
- Use `Scenario_Manager` sheet to model demand shocks (e.g., +20% promo lift)
- Select scenario in dropdown to apply across dashboards

## 7. Troubleshooting
| Issue | Cause | Fix |
|-------|-------|-----|
| #N/A errors in forecast | Missing dates in sales data | Fill missing dates with zero sales |
| Dashboard charts blank | Data not refreshed | Data > Refresh All |
| Conditional formatting gone | Workbook copied without formats | Copy from template or reapply rules |
| Slow performance | Large data sets | Archive older data (>104 weeks) |

## 8. Maintenance Schedule
| Frequency | Task |
|-----------|------|
| Daily | Refresh data, review alerts |
| Weekly | Demand & Supply Review meetings |
| Monthly | S&OP process, clean old data |
| Quarterly | Forecast model parameter tuning |
| Semi-Annual | SOP review & dashboard enhancements |

## 9. Security & Version Control
- Store workbook in version-controlled repository (GitHub/GitLFS if >100MB)
- Tag releases matching SOP approvals (`v2025.07-demand-plan`) 
- Access: read-only for most users, write access for planning team

## 10. Support & Contacts
- **Demand Planner:** Primary owner and first-line support
- **IT Analytics:** Technical support for data pipelines
- **Finance Analyst:** For margin & cash flow alignment queries

---

*Follow this guide to ensure accurate, reliable demand planning insights that align with Retail Company A’s operational goals.*