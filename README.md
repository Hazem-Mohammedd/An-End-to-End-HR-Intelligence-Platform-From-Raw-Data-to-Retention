# From Raw Data to Retention: An End-to-End HR Intelligence Platform
Built an automated, end-to-end HR intelligence platform designed to maximize workforce retention and optimize strategic planning by integrating Python ETL, SQL Star Schemas, Power BI dashboards, and XGBoost machine learning. This unified solution empowers executives to proactively predict attrition, monitor data governance, and run interactive "What-If" retention simulations via a custom Streamlit web app.

# Project excerpt
Architected a full-stack HR Command Center integrating SQL warehousing with a Streamlit application. Features automated ETL, Power BI dashboard, data quality governance, XGBoost attrition prediction, and an interactive What-If retention simulator.

# Business Case

The company’s HR data was fragmented across disconnected CSV files, leading to slow reporting cycles, poor data governance, and a reactive approach to workforce management. Without a centralized data system, HR leadership lacked real-time visibility into workforce metrics and could not anticipate employee turnover. This reactive environment meant the company was losing high-performing talent simply because they could not identify flight risks early enough to intervene effectively.

Project Goal

The objective was to architect and deploy a robust, end-to-end HR intelligence web application combining Data Engineering and Machine Learning. The system was designed to:

- Automate the extraction, cleaning, and loading (ETL) of raw HR data.
- Enforce strict data quality and governance standards.
- Transition HR from reactive reporting to proactive planning using ML-based flight risk predictions.
- Provide executives with a dynamic "What-If" simulator to test retention strategies and calculate intervention costs before making business decisions.

# Process & Methodology

## 1. Data Ingestion & Quality Automation

Engineered a dynamiac Python-based ETL pipeline via a Streamlit interface. The system automates the ingestion of raw CSVs, performs programmatic data cleansing (handling missing records using business logic rather than blind statistical means), removes duplicates, and ensures structural integrity before pushing data to the database.

## 2. Enterprise Data Warehousing (SQL Server)

Architected a scalable Data Warehouse (HR_DW) using MS SQL Server. Designed a dimensional Star Schema topology, centralizing transactional data within a Fact_HR table, surrounded by conformed dimensions (Dim_Job, Dim_Employee). Engineered robust T-SQL Merge (Upsert) logic to handle slowly changing dimensions and prevent data duplication during live updates.

## 3. Business Intelligence & Dashboards (Power BI)

Integrated Power BI with the SQL Data Warehouse to democratize descriptive analytics. Engineered a dynamic Dim_Date table using M-Language to enable robust, highly flexible time-intelligence analysis across the dataset. Developed complex DAX measures to track critical KPIs (Headcount, Turnover Rate, Average Tenure) and delivered an interactive suite of enterprise dashboards capable of independently addressing ~80% of recurring managerial reporting needs.

## 4. Predictive Analytics Engine (XGBoost)

Transitioned the platform to predictive analytics by addressing the classic "Imbalanced Classification" problem in HR data. Conducted offline model evaluation comparing Random Forest, SVM, and Logistic Regression. Overcame the "Accuracy Paradox" of Random Forest by selecting XGBoost as the champion model, heavily weighting it to optimize for Recall. This ensures the model accurately catches actual flight risks without overwhelming HR with false positive alarms.

## 5. Interactive Web Application (Streamlit)

Replaced static BI tools with a fully interactive, Python-based Streamlit web application. The platform features an Executive Command Center structured into three core modules:

- Ingestion & ETL: One-click data uploads with live processing summaries.
- Predictive Engine: Real-time ML scoring to identify top at-risk employees.
- Retention 'What-If' Simulator & Governance: A strategic tool allowing HR to simulate how specific interventions (e.g., PayZone promotions or $2000 Leadership Training) mathematically reduce an employee's flight risk probability. It also features a live Data Quality Monitor comparing Staging vs. Fact tables to guarantee 100% data integrity.

# Key Insights

- The Accuracy Trap in HR ML: Discovered that standard accuracy metrics are highly misleading for attrition data. Random Forest achieved 81% accuracy but failed to identify real risks, proving that strategic model selection based on Recall is crucial for HR interventions.
- Attrition Drivers: Uncovered that specific combinations of low pay scales (PayZones) and lack of professional training are the strongest predictors of employee turnover.
- Intervention ROI: Demonstrated that offering premium leadership training is mathematically as effective as a minor salary bump in reducing flight risk, offering HR cost-effective retention alternatives.
- Workforce Optimization: Identified distinct workforce distribution bottlenecks within critical business units through Power BI interactive cross-filtering, highlighting inefficiencies in the hiring pipeline.

# Impact

- Massive Time Savings for HR: Automated 100% of routine data cleaning and ad-hoc reporting, freeing up dozens of hours monthly for HR business partners.
- Proactive Risk Mitigation: Empowered HR to identify at-risk employees months in advance, shifting the department from exit interviews to preventive retention strategies.
- Strategic Decision-Making: The What-If Simulator allowed executives to immediately view the estimated success rate of their retention budget, optimizing HR spending.
- Zero-Defect Data Governance: The integrated live monitoring system ensures perfect referential integrity and instantly flags orphaned records.

# Tools & Technologies Used

- Data Engineering: Python (Pandas), MS SQL Server, T-SQL (Stored Procedures, MERGE), ODBC.
- Business Intelligence: Power BI, DAX, M-Language (Power Query), Data Modeling.
- Machine Learning: XGBoost, Scikit-Learn (Model Selection, Scaling, Evaluation), Predictive Modeling.
- Web Application: Streamlit, Custom CSS.
