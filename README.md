# 📊 Marketing Performance & Budget Optimization For A Fashion Retail Company | Power BI

**Author:** Van Bat Phuc Tai  
**Tools Used:** Power BI  

---

## 📑 Table of Contents
- [📌 Background & Overview](#-background--overview)
- [📂 Dataset Description & Data Structure](#-dataset-description--data--structure)
- [🧠 Design Thinking Process](#-design-thinking-process)
- [📊 Key Insights & Visualizations](#-key-insights--visualizations)
- [🔎 Final Conclusion & Recommendation](#-final-conclusion--recommendation)

---

## 📌 Background & Overview

### 🎯 Objective
Developed a Power BI dashboard to analyze marketing spending efficiency and its impact on sales performance for a fashion retail & e-commerce company.  

The project transforms raw marketing and sales data into actionable insights, supporting leadership in optimizing marketing budget allocation and improving ROI.  

### The analysis focuses on:
- Evaluating overall marketing spend vs. revenue performance  
- Measuring campaign effectiveness across channels and SKUs  
- Identifying high-ROI campaigns and underperforming investments  
- Supporting data-driven budget optimization strategies  

---

### 👤 Target Users
- C-Level Executives (CEO, CMO)  
- Marketing Managers  
- Sales & E-commerce teams  
- Business/Data Analysts  

---

### ❓ Key Business Questions
- How effectively is marketing budget being utilized?  
- Which campaigns, channels, and SKUs generate the highest ROI?  
- Are we overspending on low-performing campaigns?  
- How can budget allocation be optimized to maximize revenue and profitability?  

---

### 🎯 Project Outcome
Marketing activities significantly contributed to revenue generation; however, performance varied widely across campaigns and SKUs.  

Some campaigns delivered strong ROI and high conversion efficiency, while others consumed large budgets with limited incremental revenue impact.  

SKU-level analysis revealed that certain product categories responded strongly to paid marketing, while others showed low return despite high ad spend.  

The dashboard enables leadership to align budget allocation, campaign performance, and revenue growth strategy, ensuring more efficient marketing investments.  

---

## 📂 Dataset Description & Data Structure

### 📌 Company Overview
The company operates in the fashion retail and e-commerce industry, executing multi-channel marketing campaigns (both online and offline) to drive sales and brand awareness.  

---

### 📌 Data Source
- **Source:** Internal Marketing & Sales Data  
- **Format:** Excel (.xlsx)  
- **Scope:** Multi-channel marketing & retail sales performance  

### Data Volume Overview:
- ~3,500 order records  
- 855 marketing campaigns  
- 3,875 SKU-level campaign cost records  
- 200 distinct products  

The dataset integrates sales transactions, campaign-level spending, SKU-level allocation, and product master data, enabling end-to-end marketing ROI analysis.  

---

### 📊 Data Structure

### 1️⃣ Tables Used
The dataset consists of four relational tables, connecting marketing investment with sales outcomes at both campaign and product levels.  

📢 mkt_camp_by_sku_cost - Contains SKU-level marketing spending and performance data (3,875 records), enabling granular ROAS, ROI, and product-level efficiency analysis across 855 campaigns.

<details>
<summary><strong>Table 1: mkt_camp_by_sku_cost</strong></summary>

| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| Tên chiến dịch | VARCHAR | Name of the marketing campaign. |
| Ngày | DATE | Date when campaign performance was recorded. |
| Đơn vị tiền tệ | VARCHAR | Currency used for campaign spending (e.g., VND). |
| Số tiền đã chi tiêu (VND) | DECIMAL | Total amount spent on the campaign for the given date. |
| Phân phối chiến dịch | VARCHAR | Campaign delivery status or distribution type. |
| Ngân sách chiến dịch | DECIMAL | Total budget allocated to the campaign. |
| Loại ngân sách chiến dịch | VARCHAR | Budget type (daily, lifetime, etc.). |
| Lần bắt đầu cuộc trò chuyện qua tin nhắn | INT | Number of initiated conversations via messaging. |
| Bình luận về bài viết | INT | Number of comments generated on the advertisement. |
| CPM | DECIMAL | Cost per 1,000 impressions. |
| CPC | DECIMAL | Cost per click. |
| CTR | DECIMAL | Click-through rate (clicks divided by impressions). |
| Tin nhắn mới | INT | Number of new incoming messages generated. |
| Lượt hiển thị | INT | Total number of ad impressions. |
| Mã Sản phẩm | VARCHAR | Unique product identifier (SKU). |
| Tên Sản Phẩm | VARCHAR | Product name. |
| Giá bán | DECIMAL | Selling price of the product. |
| Tên Bài Chạy | VARCHAR | Name of the running advertisement. |
| Bài chạy theo ngày | VARCHAR | Daily ad execution details. |
| Tiền đã chạy Theo Sản phẩm | DECIMAL | Marketing cost allocated to each specific product. |
| Ngân sách | DECIMAL | Budget allocated corresponding to the product or campaign. |

</details>

📊 mkt_camp_cost - Stores campaign-level budget and advertising efficiency metrics, supporting overall budget monitoring and performance evaluation across 855 campaigns.

<details>
<summary><strong>Table 2: mkt_camp_cost</strong></summary>

| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| Tên chiến dịch | VARCHAR | Name of the marketing campaign. |
| Ngày | DATE | Date when campaign cost data was recorded. |
| Số tiền đã chi tiêu | DECIMAL | Total marketing expenditure for the campaign. |
| Phân phối chiến dịch | VARCHAR | Campaign delivery status or distribution type. |
| Ngân sách chiến dịch | DECIMAL | Total allocated campaign budget. |
| Loại ngân sách chiến dịch | VARCHAR | Type of campaign budget (daily, lifetime, etc.). |
| CPM (Chi phí trên mỗi 1.000 lần hiển thị) | DECIMAL | Average cost per 1,000 impressions. |
| CPC (Chi phí trên mỗi lượt click vào liên kết) | DECIMAL | Average cost per click on the advertisement link. |
| Lượt hiển thị | INT | Total number of impressions generated. |
| Click | INT | Total number of clicks generated. |

</details>

🛒 order - Contains nearly 3,500 transaction records and serves as the primary sales fact table for revenue, margin, and customer analysis.

<details>
<summary><strong>Table 3: order</strong></summary>

| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| ID | VARCHAR | Unique order identifier. |
| Thời gian | DATETIME | Timestamp when the order was created. |
| Nguồn | VARCHAR | Sales channel or order source. |
| Tên khách hàng | VARCHAR | Customer full name. |
| Mã khách hàng | VARCHAR | Unique customer identifier. |
| Cấp độ khách hàng | VARCHAR | Customer tier or segmentation level. |
| Sinh nhật | DATE | Customer date of birth. |
| Thành phố | VARCHAR | Customer city. |
| Quận huyện | VARCHAR | Customer district. |
| Phường xã | VARCHAR | Customer ward. |
| Sản phẩm | VARCHAR | Name of the product sold. |
| Mã sản phẩm cha | VARCHAR | Parent product identifier. |
| Tên sản phẩm cha | VARCHAR | Parent product name. |
| Mã sản phẩm | VARCHAR | Product SKU code. |
| Mã vạch | VARCHAR | Product barcode. |
| Danh mục sản phẩm | VARCHAR | Product category. |
| Chiết khấu | DECIMAL | Discount applied to the product. |
| Giá | DECIMAL | Selling price per unit. |
| Số lượng | INT | Quantity sold. |
| Giá vốn | DECIMAL | Cost of goods sold per unit. |
| Trạng thái | VARCHAR | Order status (completed, canceled, etc.). |
| Lý do hủy | VARCHAR | Reason for cancellation (if applicable). |

</details>

👗 danh sach san pham - Contains master data for 200 distinct products, supporting pricing, margin, inventory, and performance allocation analysis.

<details>
<summary><strong>Table 4: danh sach san pham</strong></summary>

| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| ID | VARCHAR | Unique product identifier. |
| Mã vạch | VARCHAR | Product barcode. |
| Loại sản phẩm | VARCHAR | Product type classification. |
| Mã sản phẩm | VARCHAR | Product SKU code. |
| Tên sản phẩm | VARCHAR | Product name. |
| Giá nhập | DECIMAL | Purchase/import price of the product. |
| Giá bán | DECIMAL | Standard selling price. |
| Giá bán + VAT | DECIMAL | Selling price including VAT. |
| Giá vốn | DECIMAL | Cost of goods sold. |
| Trạng thái | VARCHAR | Product status (active, inactive, etc.). |
| Mã danh mục | VARCHAR | Product category code. |
| Danh mục | VARCHAR | Product category name. |
| Mã danh mục nội bộ | VARCHAR | Internal category identifier. |
| Thương hiệu | VARCHAR | Product brand. |
| Màu sắc | VARCHAR | Product color. |
| Chất liệu | VARCHAR | Product material. |
| Theo sản phẩm | VARCHAR | Allocation or performance indicator by product. |
| Inbox Theo AM | INT | Number of inbox messages recorded by AM. |
| Comments Theo AM | INT | Number of comments recorded by AM. |
| Inbox + Comments Theo AM | INT | Total engagement (inbox + comments) recorded by AM. |
| CP/KQ Theo AM | DECIMAL | Cost per result recorded by AM. |
| CPM Theo AM | DECIMAL | Cost per 1,000 impressions recorded by AM. |
| CPC Theo AM | DECIMAL | Cost per click recorded by AM. |
| CTR Theo AM | DECIMAL | Click-through rate recorded by AM. |
| Khách mới Theo AM | INT | Number of new customers acquired by AM. |
| Khách cũ Theo AM | INT | Number of returning customers by AM. |
| Lượt hiển thị Theo AM | INT | Total impressions recorded by AM. |
| SL bán tổng | INT | Total quantity sold. |
| Tổng CMT trên SP | INT | Total comments on the product. |
| SL bán được phân bổ theo tỉ lệ | INT | Quantity sold allocated proportionally. |
| SL tồn | INT | Remaining inventory quantity. |
| Tổng SL bán theo Campaign | INT | Total quantity sold attributed to campaign. |

</details>

### 2️⃣ Data Relationships:

### 📐 Data Model Relationships

| From Table | To Table | Join Key | Relationship Type |
|------------|----------|----------|-------------------|
| fact_mkt_camp_by_sku_cost | dim_danh sach san pham | Mã sản phẩm | Many-to-One (*:1) |
| fact_mkt_camp_by_sku_cost | dim_mkt_camp_cost | Campaign ID | Many-to-One (*:1) |
| fact_mkt_camp_by_sku_cost | dim_date | Ngày | Many-to-One (*:1) |
| fact_order | dim_danh sach san pham | Mã sản phẩm | Many-to-One (*:1) |
| fact_order | dim_date | Thời gian (Date) | Many-to-One (*:1) |
| fact_order | dim_city | Location ID | Many-to-One (*:1) |

---

### 🧠 Model Structure Explanation (Accurate to Diagram)

#### 🔹 Fact Tables
- fact_order → Sales transactions (~3,500 records)  
- fact_mkt_camp_by_sku_cost → SKU-level marketing performance (3,875 records)  

#### 🔹 Dimension Tables
- dim_danh sach san pham → Product dimension  
- dim_mkt_camp_cost → Campaign dimension  
- dim_date → Time dimension  
- dim_city → Location dimension  


## 🧠 Design Thinking Process  

### 1️⃣ Empathize  

### 🧠 STAGE 1: EMPATHIZE – 5W1H  

| Who will view this Dashboard? | What problem does this dashboard solve? | When and where will stakeholders view this dashboard? | Why is this analysis needed? | How do stakeholders make decisions? |
|--------------------------------|------------------------------------------|--------------------------------------------------------|------------------------------|--------------------------------------|
| - Head of Marketing <br> - Marketing Manager <br> - Marketing Team Members <br> - Sales Department | - Strategic dashboard. <br> - Provides a comprehensive overview of marketing budget spending and performance across marketing campaigns. <br> - Connects marketing activities to revenue and overall sales performance. <br> - Tracks marketing budget efficiency based on KPIs. <br> - Supports recommendations for performance improvement. | **When:** <br> - During strategic meetings and weekly/monthly/quarterly performance reviews. <br><br> **Where:** <br> - On mobile devices or laptops. <br> - During presentations (drill-through, drill-down, tooltip). <br> - Used in meeting rooms or shared internally. | - To adjust strategy promptly when market conditions change. <br> - To present performance results to the Board of Directors or related departments. <br> - To allocate budget effectively across channels and campaigns. <br> - To define marketing direction aligned with customer behavior and trends. | - Through intuitive dashboards: charts, KPIs, heatmaps, trendlines. <br> - Flexible filters (campaign, time, product, revenue). <br> - Integrated alerts (e.g., high CPM, declining ROI). <br> - Easy interaction via drill-down and hover to view details. |
| **If only one key stakeholder is chosen, who would it be?** | **Summarize the problem in one sentence:** |  |  |  |
| (Senior) Marketing Manager | Help the Marketing Manager clearly understand campaign effectiveness to make faster decisions. |  |  |  |


### 🧠 STAGE 1: EMPATHY MAP  

| Thinking & Feeling <br><sub>What does the stakeholder think and feel?</sub> | Seeing <br><sub>What does the stakeholder see?</sub> | Saying & Doing <br><sub>What does the stakeholder say and do?</sub> |
|--------------------------------|--------------------------------|--------------------------------|
| **Thinking** <br> - Is the budget being overspent or wasted? <br> - Which campaign is performing well? <br> - How can I gain an overall view without checking too many reports? <br><br> **Feeling** <br> - Overwhelmed by information, difficult to control. <br> - Worried about not fully understanding each campaign. <br> - Under pressure to make quick decisions but lacking consolidated data. | - Multiple campaigns running simultaneously from agencies and internal teams. <br> - Reports from different sources that are inconsistent and disconnected. <br> - No single dashboard to track budget and performance by campaign. <br> - Struggles to comprehensively monitor and evaluate campaign performance. | **Saying** <br> - "I need to understand the overall effectiveness, not just individual campaigns." <br> - "I want to know which campaign is consuming the most budget and generating the best results." <br><br> **Doing** <br> - Makes strategic decisions based on consolidated data. <br> - Allocates budget across campaigns. <br> - Evaluates performance and reports to higher management. <br> - Adjusts campaigns when performance does not meet expectations. |
| **Pains** <br><sub>What are the biggest problems and challenges?</sub> |  | **Gains** <br><sub>What are the opportunities and benefits?</sub> |
| - Data is fragmented and not standardized. <br> - Lack of effective campaign performance consolidation tools. <br> - Difficult to compare campaigns to optimize budget allocation. <br> - Time-consuming manual data aggregation with high risk of errors. |  | - Centralized data from multiple sources into one unified system, saving time and effort. <br> - Faster and more accurate decision-making through clear data visualization. <br> - More effective marketing budget optimization by comparing campaign performance. <br> - Early detection of risks or opportunities for timely campaign adjustments. |


### 2️⃣ Define Point of View  

### 🚀 STAGE 2: MARKETING STAKEHOLDER JOURNEY  

| Step | Description |
|------|------------|
| 🟢 **Step 1 – Marketing Performance Assessment** | Based on the current marketing performance, the Head of Marketing and Marketing Manager need to understand overall campaign effectiveness, budget utilization, ROI trends, and channel performance. If performance is strong, they may scale high-performing campaigns or increase budget allocation. |
| 🔵 **Step 2 – Data Insights & Dashboard** | To gain clear visibility, stakeholders collaborate with Data Analysts to build dashboards that consolidate campaign data (budget, CPC, ROI, conversions, revenue impact). The dashboard helps identify which campaigns, channels, or products are driving the best results. |
| 🟣 **Step 3 – Strategy & Budget Optimization** | Based on dashboard insights, stakeholders conduct meetings to adjust marketing strategy, reallocate budgets across campaigns, optimize channel mix, and refine targeting to improve overall performance. |
| 🟠 **Step 4 – Execution & Performance Monitoring** | Optimized campaigns are executed, and performance metrics are continuously monitored. Budget adjustments, campaign scaling, or performance corrections are made based on updated data and KPI tracking. |


### 🚀 STAGE 2: NORTHSTAR METRICS & DEFINE POV  

### NORTHSTAR METRICS  

|                          | **NORTH STAR 1** | **NORTH STAR 2 (Optional)** |
|--------------------------|------------------|-----------------------------|
| **What VALUE do you want to measure?** | Measure whether marketing activities are effective and generate value from the allocated budget. |  |
| **WHEN does the value indicate DELIVERY SUCCESS?** | When ROAS reaches or exceeds the company’s expected profitability threshold. <br><br> Example: If ROAS ≥ 3.0, it means every $1 spent on advertising generates at least $3 in revenue. |  |
| **Northstar Metric Name** | ROAS (Return on Ad Spend) |  |
| **WHY do you choose this metric?** | - ROAS reflects actual return on marketing investment. <br> - Helps identify which campaigns are creating real value and which are wasting budget. <br> - Supports budget optimization and data-driven decision-making. <br> - Enables real-time performance tracking and timely adjustments. |  |


### DEFINE POINT OF VIEW  

| Dimension | View 1 | View 2 | View 3 | View 4 | View 5 | View 6 | View 7 |
|------------|----------|----------|----------|----------|----------|----------|----------|
| Brainstorming Point of View | Overall Business | Marketing Campaign | Product (SKU) | Time | Customer | Geography / Region | Budget & Cost |


### DEFINE KEY BUSINESS VIEWS  

| View | Description | Why do stakeholders need this view? |
|------|------------|--------------------------------------|
| View 1 – Overview | Overall business overview. | - Total revenue, profit, marketing cost, growth rate. <br> - Compare direct sales vs marketing-driven sales. |
| View 2 – Marketing Analysis | Marketing campaign performance. | - Campaign effectiveness (ROAS, CTR, CPC, revenue by campaign). |
| View 3 – Product Analysis | Performance by product or product group. | - Revenue, cost, and ROI by product/SKU. |
| View 4 – Time | - Daily, weekly, monthly, quarterly trend analysis to identify patterns and seasonality. |


### NORTHSTAR FORMULA: GROWTH FORMULA – ROAS  

| Breakdown | Formula |
|------------|----------|
| **NORTHSTAR Formula** | **ROAS = Advertising Revenue / Advertising Cost** |
| Growth formula breakdown by View 1 (Overall Marketing) | **Overall ROAS** = Total Marketing Revenue / Total Advertising Cost |
| Growth formula breakdown by View 2 (Campaign) | **Campaign ROAS** = Campaign Revenue / Campaign Cost |
| Growth formula breakdown by View 3 (Product / SKU) | **Product ROAS** = SKU Revenue / SKU Marketing Cost |
| Growth formula breakdown by View 4 (Time) | **Time-based ROAS** = Revenue by Time Period / Advertising Cost by Time Period |

### 3️⃣ Ideate

### STAGE 3: IDEATE – BRAINSTORMING

**Start with:**  
Based on the Growth Formula breakdown of each view, brainstorm related dimensions and insights aligned with the NorthStar Metric.

---

#### Overview Layer (Core Metrics)

| Metric 1 | Metric 2 | Metric 3 | Metric 4 | Metric 5 | Metric 6 |
|----------|----------|----------|----------|----------|----------|
| Return on Ad Spend (ROAS) | Ad Spend | Ad Sales | Total Clicks | Marketing Share | Direct Sales |

| Metric 7 | Metric 8 | Metric 9 | Metric 10 | Metric 11 | Metric 12 |
|----------|----------|----------|-----------|-----------|-----------|
| CPC | CPM | CTR | Total Campaigns | AOV | Cost per Acquisition (CPA) |

---

#### Brainstorming Breakdown

| Idea Name | Layer 0 Dimension (Overall) | Layer 1 Dimension (1D Breakdown) | Layer 2 Dimension (2D Breakdown) | Anything Important Missed? |
|------------|----------------------------------|-----------------------------------|-----------------------------------|----------------------------|
| **View 1: Marketing Overview** | - Total ROAS <br> - Ad Spend <br> - Ad Sales <br> - Direct Sales <br> - Total Clicks <br> - Marketing Share (Sales on Marketing / Total Revenue) | - Track ROAS performance over time (Day/Week/Month) <br> - Compare campaign effectiveness <br> - Identify highest-performing product categories | - Compare revenue mix: Ad Sales vs Direct Sales by Product Type <br> - Manage Ad Spend vs Budget <br> - Map ROAS & Ad Sales by region (Vietnam) | |
| **View 2: Marketing Analysis** | - ROAS (Primary KPI) <br> - Total Active Campaigns <br> - Total Spend <br> - CPC (Cost per Click) <br> - CPM (Cost per 1,000 Impressions) <br> - CTR (Click-Through Rate) | - Top 10 campaigns by ROAS & Ad Sales <br> - Funnel tracking: Impressions → Clicks → Ad Orders <br> - Detect high-spend but low-return campaigns | - Weekly campaign summary (ROAS, Spend, Clicks, Orders) <br> - Trend analysis of CPC / CPM / CTR over time <br> | |
| **View 3: Product Analysis** | - ROAS <br> - Ad Sales <br> - Ad Spend <br> - Total Ad Orders <br> - CPA (Cost per Ad Order) <br> - AOV (Average Order Value) | - Evaluate advertising effectiveness for each product (SKU) <br> - Top 10 advertising campaigns by product sales performance <br> - Revenue structure (Ad Sales / Total Sales) contributed by each Product Type | - Summarize marketing performance by product → clearly show the relationship between spend – revenue – efficiency – budget  <br> - Measure advertising spending efficiency by product → determine how much advertising cost is required to generate one order | |

### STAGE 3: IDEATE – STRUCTURE IDEA

#### Scorecard Metrics

| Metric 1 | Metric 2 | Metric 3 | Metric 4 | Metric 5 | Metric 6 |
|----------|----------|----------|----------|----------|----------|
| Return on Ad Spend (ROAS) | Ad Spend | Ad Sales | Total Clicks | Marketing Share | Direct Sales |

---
#### Structured Idea Breakdown

| Idea Name | Very Important Information | Important Information | Detailed Information | Anything Important Missed? |
|------------|----------------------------|------------------------|----------------------|----------------------------|
| **View 1 – Marketing Overview (Page 1)** | **KPI Cards:** <br> - Total ROAS <br> - Ad Sales <br> - Direct Sales <br> - Total Orders <br> - Total Ad Spend <br> - Marketing Contribution Ratio (Ad Sales / Total Sales) <br><br> **Slicers:** Date (Day/Week/Month), Product Category, Campaign Name | - Line Chart: ROAS Trend over Time (vs Ad Sales & Ad Spend) <br> - Bar Chart: Top 5 Campaigns by ROAS <br> - Bar Chart: ROAS by Product Type | - Pie Chart: Ad Sales vs Direct Sales <br> - Gauge: Ad Spend vs Budget (Target) <br> - Map: ROAS vs Total Spend vs Ad Sales by Region (Vietnam) |  |
| **View 2 – Marketing Analysis (Page 2)** | - ROAS (primary KPI) <br> - Total Ad Spend <br> - Total Campaigns <br> - CPC (Cost per Click) <br> - CPM (Cost per Mille) <br> - CTR (Click Through Rate) <br> - Total Spend <br><br> **Slicers:** Date (Day/Week/Month), Campaign Name | - Bar Chart: Top 10 Campaigns by ROAS / Ad Sales <br> - Marketing Funnel: Impression → Click → CMT+IB → Ad Orders <br> - Clustered Bar Chart: Bottom 10 Campaigns by ROAS / Ad Spend / Ad Sales | - Matrix Table: Week (Hierarchy: Week, Day, Campaign, Product) <br> - Metrics: ROAS, Ad Sales, Ad Spend, Total Budget, Total Impressions, Total Clicks, Cost per CMT+IB, Total CMT+IB <br> - Parameter: CPC / CPM / CTR by Week |  |
| **View 3 – Product Analysis (Page 3)** | - ROAS <br> - Ad Sales <br> - Ad Spend <br> - Total Orders <br> - CPA (Cost per Order) <br> - AVO <br><br> **Slicer:** Date (Day/Week/Month), Product Category | - Scatter Plot: ROAS vs Ad Sales vs Ad Spend by Product Name <br> - Horizontal Bar Chart: Campaign Name, Product Sold, ROAS <br> - Stacked Column Chart: Direct Sales vs Ad Sales by Product Type | - Table Matrix: Product ROAS & Campaign Performance Summary <br>   Columns: Product Name, Number of Products Sold, ROAS, Ad Sales, Ad Spend, Sales by Week (Mini Chart), Budget, Ad Spend/Budget (%) <br> - Stacked Bar Chart: CPA by Product (Cost per Order comparison) | - Drill-through: Detailed Marketing Campaign view by Product & Total Orders (Scorecard) |

### 4️⃣ Prototype and Review
This phase is implemented and validated directly within the interactive dashboard.

---

## 📊 Key Insights & Visualizations

### 🔍 Dashboard Preview

### I. Business Overview

