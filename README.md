# 🏭 Manufacturing Line Productivity Analysis

> **An end-to-end Power BI dashboard built to monitor manufacturing productivity, evaluate operator performance, identify production bottlenecks, and analyze downtime factors to support data-driven operational decision-making.**

---

## 📌 Project Overview

Manufacturing organizations rely on efficient production processes to maximize output, reduce operational costs, and meet customer demand. Even small inefficiencies in production lines can lead to increased downtime, delayed deliveries, and reduced profitability.

This project analyzes productivity and downtime data from a **soda bottling production line** to evaluate operational performance across multiple dimensions, including production efficiency, operator productivity, downtime causes, and operator-related errors.

Using Power BI, the raw production data was transformed into an interactive dashboard that enables stakeholders to monitor production KPIs, identify operational bottlenecks, and make informed decisions to improve manufacturing performance.

---

# 🎯 Business Objectives

This dashboard was developed to answer the following business questions:

- 📈 What is the current production line efficiency?
- 👷 Which operators are performing efficiently and which require improvement?
- ⛔ What are the primary causes of production downtime?
- ⚠️ How much downtime is caused by operator-related errors?
- 🥤 Which products experience the highest downtime?
- 📅 How does production efficiency change over time?
- 🔍 Which operators struggle with specific types of production errors?

---

# 📂 Dataset Overview

The project consists of **four related tables** forming a Star Schema data model.

| Table | Description |
|--------|-------------|
| **Line Productivity** | Production records including date, batch, product, operator, start time and end time |
| **Products** | Product details including flavour, bottle size and minimum expected production time |
| **Line Downtime** | Downtime minutes recorded against each production batch |
| **Downtime Factors** | Downtime descriptions and classification of operator-related errors |

### Dataset Summary

| Metric | Value |
|---------|------:|
| Production Batches | **38** |
| Products | **6** |
| Operators | **4** |
| Downtime Factors | **12** |

---

# 🧹 Data Preparation

Data preparation was completed in **Power Query** before building the dashboard.

### Transformations Performed

- ✔ Removed unnecessary records
- ✔ Validated data types
- ✔ Unpivoted downtime matrix into a normalized fact table
- ✔ Created relationships between tables
- ✔ Built a Star Schema data model
- ✔ Optimized the model for reporting and filtering

---

# ⭐ Data Model

The dashboard follows a **Star Schema**, allowing efficient filtering, simplified DAX calculations, and improved report performance.

```text
                    Products
                       │
                       │
                       ▼
              Line Productivity
                       │
                       ▼
                Line Downtime
                       ▲
                       │
                       │
              Downtime Factors
```

---

# 📐 Key DAX Measures

The dashboard includes several custom DAX measures, including:

- Total Batches
- Total Production Time
- Total Minimum Time
- Total Downtime
- Average Batch Time
- Line Efficiency %
- Operator Efficiency %
- Total Operators
- Operator Rank
- Best Performing Operator
- Average Downtime per Batch
- Downtime Incidents
- Average Downtime per Incident
- Operator Error Downtime
- Operator Error %
- Operator Error Incidents
- Average Error Downtime
- Top Downtime Factor
- Worst Error Type

---

# 📊 Dashboard Pages

## 🏠 Executive Overview

Provides a high-level summary of overall manufacturing performance.

### KPIs

- Total Production Batches
- Total Production Time
- Total Downtime
- Average Batch Time
- Line Efficiency %

### Visuals

- Line Efficiency Trend
- Production Time vs Target
- Product Performance
- Downtime Distribution

📷 **Dashboard Preview**

<img width="1530" height="859" alt="Overview" src="https://github.com/user-attachments/assets/f1ecd17e-0883-4d0f-bef8-f8f1e4c99c05" />

---

## 👷 Operator Performance

Compares production performance across operators to identify top performers and underperformers.

### KPIs

- Total Operators
- Best Performing Operator
- Average Efficiency
- Average Downtime per Batch

### Visuals

- Operator Efficiency
- Downtime by Operator
- Average Batch Time by Operator
- Performance Summary Table
- Efficiency vs Downtime Scatter Plot

📷 **Dashboard Preview**

<img width="1530" height="859" alt="Operator Performance" src="https://github.com/user-attachments/assets/be2a6661-1123-413b-ac70-a8502e0efa0d" />

---

## ⏱️ Downtime Analysis

Analyzes production interruptions to identify the major contributors to downtime.

### KPIs

- Total Downtime
- Average Downtime per Batch
- Top Downtime Factor
- Operator Error %

### Visuals

- Downtime by Factor
- Downtime Trend
- Downtime by Product
- Downtime Details Table

📷 **Dashboard Preview**

<img width="1531" height="857" alt="Downtime Analysis" src="https://github.com/user-attachments/assets/a4ed8b32-af85-41a6-b52f-73ca38b01bc9" />

---

## ⚠️ Operator Error Analysis

Focuses specifically on operator-related production issues to support targeted improvement initiatives.

### KPIs

- Operator Error Downtime
- Operator Error %
- Operator Error Incidents
- Worst Error Type

### Visuals

- Operator Error by Operator
- Error Type Distribution
- Operator × Error Type Matrix
- Error Details Table

📷 **Dashboard Preview**

<img width="1528" height="863" alt="Operator Error Analysis" src="https://github.com/user-attachments/assets/199d418a-8f09-4600-b59c-5ee9c1b42648" />

---

# 📈 Key Findings

After analyzing the manufacturing data, several operational insights were identified:

- 📦 The production line completed **38 production batches** across **6 products**, managed by **4 operators**.
- ⏱ Total production time reached **3,858 minutes**, while **1,388 minutes** were lost due to downtime.
- 📊 Overall **Line Efficiency was 64.0%**, indicating opportunities to improve operational performance.
- ⚠️ Operator-related issues contributed **776 minutes**, accounting for **55.9%** of all downtime.
- 🔧 **Machine Adjustment** emerged as the leading downtime factor, resulting in the highest production loss.
- 📋 A total of **32 operator error incidents** were recorded, highlighting the need for improved operational consistency.
- 🥤 Certain products consistently experienced more downtime than others, indicating potential process or equipment-related challenges.
- 📉 Downtime was concentrated among a small number of recurring factors, suggesting that targeted corrective actions could significantly improve production efficiency.

---

# 💼 Business Recommendations

### 🏭 1. Strengthen Preventive Maintenance

The analysis shows that equipment-related issues such as **Machine Adjustment** contribute heavily to production downtime. Implementing preventive maintenance schedules and routine equipment inspections can reduce unexpected stoppages and improve machine reliability.

---

### 👨‍🏭 2. Enhance Operator Training

With **55.9% of total downtime** linked to operator-related issues, focused training programs should be introduced to improve adherence to production procedures and reduce avoidable production delays.

---

### 📋 3. Standardize Operating Procedures

Recurring production errors indicate inconsistencies in operational practices. Developing and enforcing standardized operating procedures (SOPs) will help reduce process variation and improve production quality.

---

### 📊 4. Monitor Line Efficiency Continuously

The current **64.0% line efficiency** indicates considerable room for improvement. Daily monitoring of production KPIs through Power BI dashboards will enable supervisors to detect performance issues early and take corrective action promptly.

---

### ⚙️ 5. Prioritize High-Impact Downtime Factors

Applying the Pareto Principle, management should prioritize resolving the few downtime factors responsible for the majority of production losses before addressing less significant issues.

---

### 🥤 6. Optimize High-Downtime Products

Products with consistently higher downtime should undergo detailed production reviews to identify bottlenecks, optimize machine settings, and improve production scheduling.

---

### 📈 7. Establish Continuous Performance Reviews

Regularly reviewing operator performance, downtime trends, and production efficiency will support continuous improvement initiatives and help sustain long-term operational excellence.

---

# 🚀 Business Impact

This dashboard enables manufacturing teams to:

- 📈 Monitor production performance in real time.
- 👷 Evaluate operator productivity using objective performance metrics.
- ⛔ Identify the primary causes of production downtime.
- ⚠️ Reduce operator-related production errors through targeted interventions.
- 🥤 Optimize product-specific manufacturing processes.
- 📊 Support faster and more informed operational decision-making.
- 💰 Improve productivity while reducing manufacturing costs and operational losses.

---

# 🛠️ Tools & Technologies

- 📊 Microsoft Power BI
- ⚙️ Power Query
- 📐 DAX (Data Analysis Expressions)
- 🗂️ Data Modeling
- ⭐ Star Schema
- 📈 Interactive Data Visualization

---

# ⭐ If you found this project helpful, consider giving it a star!

It helps others discover the project and supports my work.

---

If you have any feedback, suggestions, or would like to collaborate, feel free to connect with me through LinkedIn or explore my other Power BI projects on GitHub.
