# 📊 Urban Experience Dashboard – Customer Experience (CX)

This project presents a strategic analysis of customer experience across urban zones, using simulated operational data. The solution combines modeling in Databricks and visualizations in Power BI to identify friction points, critical areas, and opportunities for improvement.

---

## 📦 Dataset Used

The analysis is based on the public dataset `samples.nyctaxi.trips`, available on Databricks Community Edition. This dataset contains real taxi trip records from New York City, including:

- Pickup and drop-off timestamps  
- Trip distance  
- Fare amount  
- Origin and destination ZIP codes  

Although the context is urban and simulated, the data was used as an analogy to map patterns of friction and improvement opportunities in the customer journey — with a focus on **Customer Experience (CX)**.

---

## 🎯 Objective

To evaluate the customer journey across different urban regions using real-world data, going beyond traditional NPS metrics. The goal is to identify systemic failures, anticipate dissatisfaction, and support operational decisions with an experience-driven approach.

---

## 💡 Why Power BI?

While technical teams already use Databricks dashboards for daily operational analysis, this project introduces an additional visualization layer tailored for **business leaders and decision-makers**, with a focus on **Customer Experience (CX)**.

The Power BI dashboard aims to make key indicators that impact **NPS** and **customer relationships** more accessible, intuitive, and actionable for strategic decision-making.

---

## 🧭 Integration with Daily Performance Dashboard

We recommend embedding the **NPS gauge** into the daily performance and goals dashboard, with an option to open the full CX report when deeper analysis is needed.

This approach allows:

- ✅ Avoiding information overload in daily reports  
- ✅ Keeping NPS visible as a strategic alert  
- ✅ Enabling quick action in case of significant score changes

---

## 🤝 CX Engagement and Culture

To encourage company-wide commitment to customer experience, we suggest assigning **weight to the NPS score** in the overall performance rating of each branch (or equivalent unit). This reinforces the importance of CX and promotes a customer-centric culture across all operational levels.

---

## 🧩 Key Metrics

### 🟢 Final Score  
A composite indicator summarizing overall customer experience per zone. Calculated from four operational factors:
- Average trip time  
- Average fare  
- Frustration index  
- Proportion of expensive rides  
Scale: 0 to 10, with 10 being the best possible experience.

---

### 🕒 Average Wait Time  
Average time a customer waits before the ride starts. Lower values indicate better agility perception.

---

### 💰 Fare per Minute  
Average amount paid per minute of ride. Helps assess perceived fairness of pricing.

---

### 😠 Frustration Index  
A derived metric simulating the “not worth it” feeling. Combines time, fare, and distance to measure friction.

---

### 📈 Proportion of Expensive Rides  
Percentage of rides priced above average. High recurrence may cause dissatisfaction even on short trips.

---

### 🧮 Average Friction Score  
Aggregated metric summarizing key friction factors. Higher values indicate greater negative impact on experience.  
**Use cases:** operational thermometer, zone comparison, prioritization.

---

### 🔴 Critical Zones  
Total number of zones with final score below 6. These areas pose high dissatisfaction risk and should be monitored closely.

---

### 📍 Highlighted Critical Area  
Identifies the ZIP code with the highest friction score. Represents the most compromised region in terms of operations and customer perception.

---

### ⚪ Experience Gap  
Difference between the maximum score (10) and the average final score. Indicates how far the experience is from excellence.  
**Formula:** `Gap = 10 - FinalScore`

---

## 📈 Power BI Visuals

The dashboard is divided into two pages:

### Page 1 – Overview  
- Experience Gauge  
- Donut Chart showing Experience Gap  
- ZIP Code Map  
- KPI Cards  
- Tooltips explaining each metric

### Page 2 – Critical Zones  
- Average Friction Score  
- Number of Critical Zones  
- Highlighted Critical Area  
- Scatter Plot (Friction vs Frustration)  
- Full zone map

---

## 🔗 Power BI Dashboard Access

The full dashboard is available [here](https://app.powerbi.com/view?r=eyJrIjoiZDFjZDVmZmMtYmZkZS00MGZlLTg2Y2ItZjFlYzBkOTYxNjBkIiwidCI6IjY1OWNlMmI4LTA3MTQtNDE5OC04YzM4LWRjOWI2MGFhYmI1NyJ9)  
*A corporate login or permission may be required to view.*

---

## 🔗 Databricks Dashboard Access

The original dashboard was built in Databricks using the notebook `cx_insights_demo`.  
It is available [here](https://dbc-2f7c928f-6564.cloud.databricks.com/editor/notebooks/2346340275943328/dashboards/340c5e1e-afc5-4f87-9ba0-52e1fb0ea9d9?o=1637696810741543) for users with access to the same workspace.

> ⚠️ Access is granted to all internal workspace users. External users will not be able to view the content directly. For public review, please refer to the exported notebook (`.ipynb`) and the snapshots included in this repository.

---

## 🖼️ Sample Visuals

### 1. Cover Page  
![Cover](https://github.com/user-attachments/assets/d8f5b5a9-e516-4bdb-a59b-7cb8163f0586)

### 2. Urban Experience Radar  
![Radar](https://github.com/user-attachments/assets/19b549ba-0ead-414d-b515-24facb8bd065)

### 3. Experience Analysis  
![Analysis](https://github.com/user-attachments/assets/e7634ec7-250d-416d-b263-07927000302e)

---

## 🧠 Recommendations

- Prioritize zones with score < 6 and high friction  
- Investigate systemic causes such as inefficient routes, aggressive pricing, or long wait times  
- Use the scatter plot to identify outlier zones  
- Monitor the experience gap as a continuous improvement target

> These recommendations aim to turn operational data into actionable insights, strengthening CX culture and data-driven decision-making.

---

## 🗂️ Repository Files

- `notebooks/cx_insights_demo.ipynb` → Databricks notebook with modeling and analysis  
- `dashboards/cx_insights` → snapshots of Databricks dashboards (.png)  
- `docs/resumo_executivo.md` → metric explanations and strategic insights  
- `powerBI/CX_TaxisNYC.pbix` → Power BI dashboard file

---


