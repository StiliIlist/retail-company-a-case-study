# Standard Operating Procedure (SOP)
**Demand Planning & Inventory Management - Retail Company A**

## Document Control
- **Version:** 2.0
- **Effective Date:** Current
- **Review Cycle:** Semi-Annual
- **Owner:** Demand Planning Function
- **Approved By:** Operations Leadership

---

## 1. Purpose & Scope

This SOP establishes standardized procedures for demand planning and inventory management across all product categories for Retail Company A's direct-to-consumer apparel business. The scope includes:

- All finished-goods SKUs sold through e-commerce, retail partners, and physical locations
- Forecast horizons from tactical (weekly) to strategic (18-month)
- Cross-functional coordination across Planning, Marketing, Finance, and Operations
- Integration with third-party logistics (3PL) and supplier networks

### Objectives
- Maintain 90%+ forecast accuracy (MAPE ≤ 10%)
- Optimize inventory levels (6-10 weeks of supply target)
- Ensure 95%+ service levels across all channels
- Maximize inventory turn while minimizing stockouts

## 2. Definitions & Key Terms

| Term | Definition |
|------|------------|
| **Demand Plan** | Weekly SKU-level forecast of units and revenue |
| **Consensus Forecast** | Executive-approved demand plan serving as single source of truth |
| **WOS** | Weeks of Supply (On-hand inventory ÷ Average weekly demand) |
| **MAPE** | Mean Absolute Percentage Error (primary forecast accuracy metric) |
| **OTIF** | On-Time-In-Full supplier performance measurement |
| **S&OP** | Sales & Operations Planning monthly consensus process |
| **SKU** | Stock Keeping Unit (unique product-size-color combination) |

## 3. Roles & Responsibilities

### Demand Planner (Primary Role)
- **Core Duties:** Own forecast engine, maintain statistical models, chair demand reviews
- **Time Allocation:** 60% forecasting, 25% analysis, 15% cross-functional coordination
- **Key Deliverables:** Weekly KPI reports, monthly consensus plan, quarterly accuracy reviews

### Inventory Planner
- **Core Duties:** Calculate reorder points, launch purchase orders, monitor stock levels
- **Integration:** Daily coordination with demand forecasts for replenishment decisions
- **Key Metrics:** WOS maintenance, stockout prevention, excess inventory minimization

### Marketing Team
- **Input Responsibilities:** Campaign calendars, promotional lift factors, new product launches
- **Coordination:** Weekly demand review participation, campaign impact validation
- **Data Requirements:** 4-week advance notice for promotional activities

### Finance Team
- **Planning Role:** Convert unit forecasts to revenue/margin projections
- **Constraints:** Validate cash flow limitations, approve high-value purchase orders
- **Reporting:** Monthly financial impact analysis of inventory decisions

### Operations/3PL Liaison
- **Capacity Management:** Confirm warehouse capacity, inbound scheduling, labor constraints
- **Performance Tracking:** Monitor supplier OTIF, lead time performance, quality metrics
- **Escalation:** Flag capacity constraints and supply chain disruptions

## 4. Data Architecture & Systems

### Primary Data Sources
- **Sales Data:** E-commerce platform (daily transaction feeds)
- **Inventory Data:** ERP system (real-time stock levels and movements)
- **Marketing Data:** Campaign management system (promotional calendars and performance)
- **Supplier Data:** 3PL feeds (inbound receipts, lead times, quality metrics)

### Forecasting Engine
- **Platform:** Excel-based model with Power Query automation
- **Methodology:** FORECAST.ETS exponential smoothing with seasonal decomposition
- **Enhancements:** Marketing lift factors, new product introduction curves
- **Validation:** Statistical significance testing, confidence interval calculation

### Reporting Infrastructure
- **Dashboard Platform:** Excel with embedded charts and conditional formatting
- **KPI Monitoring:** Automated variance alerts, exception reporting
- **Distribution:** Weekly stakeholder reports, monthly executive summaries
- **Version Control:** Date-stamped files with read-only access post-approval

## 5. Process Workflows

### 5.1 Daily Operations (Monday-Thursday)
**07:30 - Data Validation**
- Automated script validates sales data completeness
- Exception reporting for missing data, negative inventory, duplicate records
- Data quality issues resolved before 09:00 dashboard refresh

**09:00 - Dashboard Update**
- KPI scorecards refresh with latest performance metrics
- Inventory alerts generated for items below reorder points
- Variance analysis updated with actual vs. forecast performance

### 5.2 Weekly Demand Review (Wednesday 10:00 AM)
**Participants:** Demand Planner, Marketing, Merchandising
**Duration:** 60 minutes
**Agenda:**
1. **Performance Review (15 min):** Prior week variance analysis, accuracy metrics
2. **Forecast Updates (30 min):** Statistical baseline review, marketing input integration
3. **Exception Management (15 min):** Items with WOS < 4 or > 16, override approvals

**Outputs:**
- Updated demand forecasts with documented overrides
- Marketing campaign impact validations
- Risk/opportunity identification for supply planning

### 5.3 Weekly Supply Review (Thursday 2:00 PM)
**Participants:** Supply Planner, Finance, Demand Planner
**Duration:** 45 minutes
**Focus Areas:**
- Capacity validation against demand plan
- Purchase order recommendations and cash flow impact
- Supplier performance review and escalation needs

### 5.4 Monthly S&OP Process

**Week 1 - Data Collection**
- Historical performance analysis
- Market intelligence gathering
- Preliminary forecast generation

**Week 2 - Demand Review**
- Cross-functional demand plan validation
- Marketing campaign integration
- Risk assessment and mitigation planning

**Week 3 - Supply Review**
- Capacity planning and constraint identification
- Financial impact modeling
- Pre-S&OP consensus building

**Week 4 - Executive S&OP**
- Leadership approval of consensus plan
- Resource allocation decisions
- Performance target setting

## 6. Key Performance Indicators (KPIs)

### Primary Metrics
| KPI | Calculation | Target | Review Frequency |
|-----|-------------|--------|------------------|
| **Forecast Accuracy (MAPE)** | Avg(\|Actual-Forecast\|/Actual) | ≤ 15% | Weekly |
| **Forecast Bias** | Σ(Forecast-Actual)/ΣActual | ±5% | Weekly |
| **Weeks of Supply** | On-hand / Avg weekly demand | 6-10 weeks | Daily |
| **Service Level** | Orders fulfilled / Total orders | ≥ 95% | Daily |
| **Inventory Turnover** | COGS / Average inventory | ≥ 6× annually | Monthly |
| **Supplier OTIF** | On-time & in-full receipts / Total POs | ≥ 90% | Weekly |

### Dashboard Formatting
- **Green:** Performance within target range
- **Yellow:** Performance 5-10% outside target (caution zone)
- **Red:** Performance >10% outside target (action required)

### Alert Thresholds
- **Critical:** MAPE > 20%, Service Level < 90%, WOS < 3 or > 20
- **Warning:** MAPE 15-20%, Service Level 90-95%, WOS 3-4 or 16-20
- **Informational:** New product launches, promotional periods, supplier changes

## 7. Exception Management

### Forecast Override Governance
- **Authority:** Only Demand Planner authorized to override statistical forecasts
- **Documentation:** All overrides logged with reason codes and approval
- **Validation:** Monthly review of override accuracy vs. statistical baseline
- **Threshold:** Overrides >10% of baseline require marketing/merchandising sign-off

### Inventory Alert Response
**Critical Stock Situations (WOS < 3)**
1. Immediate escalation to inventory planner and operations
2. Expedite options evaluation (air freight, alternative suppliers)
3. Customer communication preparation for potential stockouts
4. Executive notification within 4 hours

**Excess Inventory (WOS > 20)**
1. Merchandising consultation for promotional opportunities
2. Secondary channel evaluation (outlet, wholesale)
3. Markdown scenarios and margin impact analysis
4. Long-term demand pattern reassessment

### Supplier Performance Issues
**OTIF < 85% (Individual Supplier)**
1. Immediate supplier communication and root cause analysis
2. Alternative sourcing evaluation and capacity assessment
3. Customer impact assessment and mitigation planning
4. Supplier improvement plan development with timelines

## 8. Training & Competency

### New Hire Onboarding
- **Week 1:** SOP overview, system access, shadow experienced planner
- **Week 2:** Hands-on forecasting practice with sample data sets
- **Week 3:** Cross-functional meeting participation and stakeholder introductions
- **Week 4:** Independent operation with mentor oversight and feedback

### Ongoing Development
- **Quarterly:** Forecast accuracy deep-dives and methodology refinements
- **Semi-Annual:** Industry best practice research and system enhancement evaluation
- **Annual:** Advanced analytics training and statistical modeling updates

### Competency Validation
- **Monthly:** KPI performance review against individual and team targets
- **Quarterly:** Cross-functional feedback collection and development planning
- **Annual:** Formal performance evaluation with career development discussions

## 9. Quality Assurance & Compliance

### Data Quality Controls
- **Automated Validation:** Daily data integrity checks with exception reporting
- **Manual Verification:** Weekly sample audits of key data sources
- **Reconciliation:** Monthly variance analysis between systems and actual results

### Process Audits
- **Internal Review:** Quarterly SOP compliance assessment
- **Cross-Functional Audit:** Semi-annual review with Finance and Operations
- **External Validation:** Annual third-party assessment (if applicable)

### Documentation Standards
- **Version Control:** All forecasts and plans maintained with date stamps
- **Change Management:** SOP updates require stakeholder review and approval
- **Retention Policy:** Historical data and decisions retained for 3 years minimum

## 10. Continuous Improvement

### Improvement Identification
- **Performance Metrics:** Regular analysis of KPI trends and variance patterns
- **Stakeholder Feedback:** Quarterly surveys and improvement suggestions
- **Industry Benchmarking:** Annual comparison with retail industry standards

### Implementation Process
- **Idea Evaluation:** Monthly review of improvement opportunities
- **Pilot Testing:** Controlled testing of changes before full implementation
- **Performance Validation:** Pre/post implementation comparison with statistical significance
- **Standardization:** Successful improvements incorporated into SOP updates

### Innovation Pipeline
- **Technology Evaluation:** Ongoing assessment of advanced analytics and AI tools
- **Process Optimization:** Lean Six Sigma methodology for workflow improvements
- **Skill Development:** Training programs for advanced forecasting techniques

## 11. Emergency Procedures

### Supply Chain Disruptions
1. **Immediate Assessment:** Impact evaluation on inventory and service levels
2. **Alternative Sourcing:** Activation of backup suppliers and expedite options
3. **Communication Plan:** Internal stakeholder updates and customer notifications
4. **Recovery Planning:** Timeline development for normal operations restoration

### System Failures
1. **Manual Backup:** Activation of offline processes and manual calculations
2. **IT Escalation:** Priority support request with estimated restoration timeline
3. **Stakeholder Notification:** Communication of limited functionality and workarounds
4. **Post-Recovery:** System validation and data reconciliation procedures

---

## Document Revision History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | Initial | Demand Planning | Initial SOP creation |
| 2.0 | Current | Demand Planning | Process improvements, KPI updates |

## Approval Signatures

- **Operations Manager:** [Signature Required]
- **Finance Director:** [Signature Required] 
- **IT Systems:** [Signature Required]
- **Quality Assurance:** [Signature Required]

---

*This SOP is reviewed semi-annually and updated as business requirements evolve. All users must acknowledge receipt and understanding before operational deployment.*