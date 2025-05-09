# 🚀 Space Mission Dashboard  

📌 **Business Problem**  
As global interest in space exploration intensifies, stakeholders—including governments, aerospace firms, and analysts—need a reliable, interactive tool to assess mission success, costs, and organizational performance. This end-to-end business intelligence solution transforms raw space mission data into a refined, actionable Power BI dashboard.

**Key Objectives:**

- Analyze global space missions across time, countries, and organizations  
- Measure and compare mission success rates and costs  
- Identify high-performing companies and countries in the space sector  
- Provide data-driven insights through visual storytelling  

---

🗂️ **Data Structure**  
The project uses a **star schema** model to support efficient reporting and scalability:

| Table Name     | Purpose                                                                 |
|----------------|-------------------------------------------------------------------------|
| `FactMission`  | Core mission data (costs, outcomes, associations to dimensions)         |
| `DimDate`      | Standard calendar table for time-based analysis                         |
| `DimCompany`   | Cleaned company names and affiliations                                  |
| `DimLocation`  | Country and launch site mapping                                         |
| `DimRocket`    | Rocket types and specifications                                         |

**Repository Structure:**
Additional folder structure from the repository:

/data → Contains the original and cleaned Excel data files
/reports → Power BI dashboard file (Space Mission.pbix)
/docs → Supporting documentation and analysis summary
README.md → Project overview and usage guide

# 📈 Executive Summary
The Power BI dashboard provides a comprehensive overview of the global space mission landscape. It includes:

- **Total Missions and Success Rates**
- **Country-wise mission outcomes**
- **Company-level mission trends**
- **Year-over-Year analysis**
- **Mission cost summaries**
- **Filterable visuals with drill-through capability**

### 🛠 Tools Used:

- **Microsoft Excel** – Data collection and cleaning  
- **Power Query** – ETL processes  
- **Power BI** – Data modeling and dashboard creation  
- **DAX** – Custom KPIs and time intelligence functions  

---

# 🔍 Insights Deep Dive

### 📅 Mission Trends by Year  
Clear growth in launch activity from private companies since the 2000s, with economic or political instability causing dips in some years.

### 🌍 Top Performing Countries  
- The **USA** leads in both mission volume and success rate.  
- **USSR/Russia** shows a strong historical footprint with consistent missions.

### 🏢 Company-Level Analysis  
- A few companies dominate launch volume and maintain high success rates.  
- Newer players exhibit varied outcomes, suggesting learning curves or innovation gaps.

### 💰 Cost vs. Outcome  
- High-cost missions don’t always guarantee success.  
- Some firms deliver successful missions with lean budgets.

### 🌐 Geopolitical Impact  
Mission trends shift during key global events, e.g., Cold War tensions or the post-2008 financial crisis period.

---

# 🧮 Key DAX Measures Implemented

```DAX
Total Missions = COUNTROWS(FactMission)

Successful Missions = 
CALCULATE([Total Missions], FactMission[Status] = "Success")

Success Rate = 
DIVIDE([Successful Missions], [Total Missions])

Mission Cost Summary = 
SUM(FactMission[Cost])

Total Mission YoY% = 
DIVIDE([Total Missions] - [LY Missions], [LY Missions])
```

# ✅ Recommendations

### ✅ Support Efficient Companies  
Promote partnerships with firms consistently delivering successful, cost-effective missions.

### ❗ Enhance Failure Review  
Deep dive into high failure rates in some companies to reduce risk and improve outcomes.

### 📊 Invest in Data-Driven Forecasting  
Use time-based patterns and cost-performance ratios to guide future planning and funding.

### 🤝 Foster International Collaboration  
Encourage global cooperation to reduce redundancy and optimize launch infrastructure sharing.

---

# 💡 Project Value

## 📋 Summary Table

| Attribute             | Details                                                          |
|------------------------|------------------------------------------------------------------|
| **End-to-End Workflow** | From raw Excel to a live, filterable dashboard                   |
| **Data Model**         | Star schema with a clean, scalable structure                      |
| **Power BI Proficiency** | Advanced use of Power Query and DAX                            |
| **Visualization**      | User-friendly interface with drill-throughs and slicers           |
| **Business Value**     | Real insights for government, private sector, and academia        |

## 📦 Project Metadata

| Item              | Description                              |
|-------------------|------------------------------------------|
| **Tools Used**    | Excel, Power Query, Power BI, DAX        |
| **Duration**      | 1–2 weeks                                |
| **Target Audience** | Aerospace Analysts, Government, BI Teams |

