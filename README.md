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

### 👗 Fashion Retail - Business Context  

The company operates in the **fashion retail and e-commerce industry**, offering seasonal apparel collections and lifestyle products through both online and offline channels.  

Growth is heavily driven by **multi-channel marketing campaigns**, including paid digital advertising, performance media, and promotional activations. Revenue performance is closely tied to marketing execution efficiency and SKU-level campaign effectiveness.

As competition intensifies and customer acquisition costs increase, leadership requires deeper visibility into how marketing investments translate into sales outcomes and overall profitability.

---

### 🎯 Business Objective  

Executive leadership needs a connected view of:

- Marketing spend allocation across campaigns and SKUs  
- Revenue performance influenced by advertising activities  
- ROI and efficiency metrics at campaign and product level  

The objective is to optimize marketing budget utilization by linking **Spend → Traffic → Conversion → Revenue Impact**, ensuring sustainable and performance-driven growth.

---

### ❗ Why This Analysis Matters  

In fashion retail, aggressive marketing without performance control can quickly erode margins.

Without structured analysis:

- Budget allocation may favor high-spend but low-ROI campaigns  
- Revenue growth may not translate into profitability  
- High-performing SKUs may be underfunded  
- Marketing cost inflation may outpace revenue contribution  

This analysis provides a consolidated view of **marketing efficiency, sales contribution, and SKU-level profitability**, enabling data-driven budget optimization and tactical campaign adjustments.

---

### 👤 Target Users  

- Senior Management  
- Marketing Directors  
- Performance Marketing Teams  
- E-commerce Managers  
- Finance & Strategy Teams  
- Business Intelligence Analysts  

---

### ❓ Key Business Questions  

- How effectively does marketing spend convert into revenue?  
- Which campaigns and SKUs deliver the highest ROI?  
- Is budget allocation aligned with revenue contribution?  
- Where are inefficiencies impacting marketing profitability?  

---

### 📊 Project Outcome  

- Identified high-spend campaigns with declining marginal ROI → budget reallocation opportunities  
- Revealed SKU-level performance gaps between revenue contribution and advertising cost  
- Highlighted campaigns with strong CTR but weak revenue conversion → funnel optimization required  
- Established clear performance tiers to guide future budget prioritization  

This project enables alignment between **marketing investment strategy, product performance management, and revenue quality improvement**, supporting scalable and data-driven growth.

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

<img width="1300" alt="image" src="https://github.com/user-attachments/assets/cb14f377-54c4-4533-a8e2-00e225f0e512" />


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

<img width="1400" alt="image" src="https://github.com/user-attachments/assets/ca4cd75c-ab79-4983-9206-cc15bc6cecab" />
<img width="1400" alt="image" src="https://github.com/user-attachments/assets/496567e6-e546-451d-a846-ac7733bec1bc" />

### 2️⃣ Define Point of View  

<img width="1400" alt="image" src="https://github.com/user-attachments/assets/6b9f0a17-3ea3-4ec4-8953-533701592e0f" />
<img width="1400" alt="image" src="https://github.com/user-attachments/assets/65691566-6200-4b48-8575-92e96e14e9d9" />
<img width="1400" alt="image" src="https://github.com/user-attachments/assets/ab37f472-0372-4e1c-88b1-9371ee250f57" />


### 3️⃣ Ideate
<img width="1400" alt="image" src="https://github.com/user-attachments/assets/3b4bec41-f112-4c54-aaf0-2858545486f7" />
<img width="1400" alt="image" src="https://github.com/user-attachments/assets/af6f6cf9-44f2-4418-b481-43aaafe1c982" />


### 4️⃣ Prototype and Review
This phase is implemented and validated directly within the interactive dashboard.

---

## 📊 Key Insights & Visualizations

### 🔍 Dashboard Preview

### I. Business Overview

<img width="1300" alt="image" src="https://github.com/user-attachments/assets/3bc2785b-173f-4e3e-ae5b-70026f2d09c0" />

### 📌 Key Findings:

#### 1. Overall Marketing Performance  

**ROAS reached 7.67**, generating **3.02bn Ad Sales** from **394.13M Ad Spend**.  
Marketing contributed **63.34% of Total Revenue**, while Direct Sales accounted for **1.75bn**.  
→ Growth is **strongly marketing-driven with high return efficiency**.

#### 2. Weekly ROAS & Spend Trend  

ROAS remained stable (~7.6–7.7) before peaking at **~9.0 (Week 5)**.  
Ad Spend peaked around **Week 3–4**, with Ad Sales following the same trend.  
→ Indicates **performance optimization improved toward later weeks**.

#### 3. Top Campaign Performance  

Top campaign achieved **ROAS > 100**, significantly outperforming others.  
Clear performance gap between **Top 3 vs Bottom campaigns**.  
→ Budget should be **reallocated to high-ROAS campaigns**.

#### 4. Product Type Performance by ROAS  

**“Váy Chiết Eo Ôm” led with ROAS 22.09**, far above portfolio average.  
Most product types clustered between **ROAS 4–10**.  
→ A few SKUs act as **core efficiency drivers**.

#### 5. Revenue Structure: Ad vs Direct  

**Ad Sales = 63% of total revenue**.  
→ Business is **highly dependent on paid marketing performance**.

#### 6. Budget Utilization  

Ad Spend reached **82.75% of allocated budget**.  
→ Controlled spending with **room to scale high-performing segments**.

#### 7. Geographic Performance  

ROAS & Spend concentrated in **major urban cities in Vietnam**.  
→ Urban markets remain **primary conversion & revenue hubs**.


### II. Marketing Analysis

<img width="1300" alt="image" src="https://github.com/user-attachments/assets/13cefbbb-fe61-4b07-925e-67bd50ef8c11" />

### 📌 Key Findings:

#### 1. Overall Marketing Performance  

**ROAS reached 7.67** across 175 campaigns, generating **3.02bn Ad Sales** from **394.13M Spend**.  
Cost efficiency remained stable with **CPC = 9.46K**, **CPM = 77.14K**, **CTR = 0.01**.  
→ Performance is **efficient and cost-controlled at scale**.

#### 2. Campaign Revenue Concentration  

Top campaign delivered **0.26bn Ad Sales**, followed by **0.16bn** and **0.11bn**.  
Clear performance gap between top-tier and lower campaigns.  
→ Revenue is **highly concentrated**, scaling top performers will maximize returns.

#### 3. Marketing Funnel Efficiency  

From **5,108.97K impressions → 41.65K clicks → 2.27K orders**.  
Strong top-of-funnel reach, but noticeable drop from **Click → Order**.  
→ Optimization opportunity lies in **mid-to-bottom funnel conversion**.

#### 4. Cost & Engagement Trend (CTR / CPC / CPM)  

**CTR peaked in Week 4**, indicating strongest engagement.  
**CPC highest in Week 2**, then improved in later weeks.  
**CPM increased after Week 1** but efficiency still improved.  
→ Cost structure stabilized while **conversion efficiency improved toward Week 5**.

#### 5. High Spend – Low Return Campaigns  

Several campaigns show **high spend but weak ROAS**.  
Investment is not evenly efficient across portfolio.  
→ Budget reallocation is required to **improve capital productivity**.


### III. Product Analysis

<img width="1300" alt="image" src="https://github.com/user-attachments/assets/68fae7f9-dcca-4732-819e-b5b3a8c2724a" />

### 📌 Key Findings:

#### 1. Overall Product Performance  

Ad Sales reached **3.02bn** from **394.13M Ad Spend**, delivering **ROAS = 7.67**.  
Total Ad Orders recorded **2,267**, with **CPA = 173.85K** and **AOV = 1.33M**.  
→ Product portfolio is **profitable with strong return efficiency**.

#### 2. ROAS Distribution by Product  

Majority of products cluster at **ROAS < 20**,  
while a few outliers reach **ROAS ~59 and 86**.  
→ Performance is **highly skewed**, with a small group driving exceptional returns.

#### 3. Product Category Performance  

**Váy Chiết Eo Ôm** & **Váy Suông Xòe** generate high Ad Sales with solid ROAS.  
**Áo Tách Set** shows higher spend relative to return.  
→ Dresses are the **core revenue driver**, while some categories require optimization.

#### 4. Sales Structure by Product Type  

Several product types rely heavily on **Ad Sales contribution (>50%)**.  
A few categories show stronger Direct Sales proportion.  
→ Business remains **paid-traffic dependent**, but diversification exists.

#### 5. Campaign & Product Efficiency Summary  

Top-performing SKUs (e.g., Gavin Trouser – ROAS 6.21) outperform portfolio average.  
Overall **Ad Spend/Budget = 82.75%**, indicating controlled scaling.  
→ Budget allocation is relatively efficient but can be optimized toward high-ROAS SKUs.

#### 6. Cost per Acquisition (CPA) Variation  

CPA ranges widely from **~476K to ~923K** across products.  
Higher CPA products do not always generate proportional sales.  
→ Significant opportunity to **rebalance spend toward lower-CPA, higher-ROAS items**.


# 🔎 Final Conclusion & Recommendation

| Strategy | Insight | Recommendation |
|-----------|----------|----------------|
| 🚀 **1. Marketing Efficiency & Growth Scaling** | - **ROAS = 7.67**, generating **3.02bn Ad Sales** from **394.13M Spend**. <br>- Marketing contributes **63% of total revenue** (high paid-media dependence). <br>- ROAS peaked at ~9.0 in Week 5, showing optimization impact. | - Maintain ROAS ≥ 7.5 while scaling. <br>- Increase budget during high-efficiency weeks. <br>- Strengthen Direct Sales to reduce long-term paid dependency. |
| 🎯 **2. Campaign Portfolio Optimization** | - Revenue highly concentrated (Top campaign ~0.26bn). <br>- Clear performance gap between Top vs Bottom campaigns. <br>- Several high-spend campaigns deliver weak ROAS. | - Reallocate budget to Top 10–20% campaigns. <br>- Pause or restructure low-ROAS campaigns. <br>- Apply structured A/B testing to replicate winning models. |
| 🛍 **3. Product & SKU Optimization** | - “Váy Chiết Eo Ôm” achieved **ROAS 22.09** (well above average). <br>- Majority of SKUs cluster ROAS 4–10. <br>- Dresses act as core revenue driver. | - Prioritize scaling high-ROAS SKUs. <br>- Bundle/upsell to increase AOV (1.33M). <br>- Reduce spend on high-CPA, low-return SKUs. |
| 🔁 **4. Funnel & Conversion Optimization** | - 5.1M impressions → 41.6K clicks → 2.27K orders. <br>- Significant drop from Click → Order stage. <br>- CTR peaked Week 4; CPC improved after Week 2. | - Optimize product pages & checkout UX. <br>- Strengthen retargeting for high-intent users. <br>- Improve offer structure (bundle, urgency, promo). |
| 💰 **5. Cost Control & Capital Productivity** | - Budget utilization at **82.75%** (room to scale). <br>- CPA varies widely (~476K–923K). <br>- Higher CPA ≠ higher revenue. | - Shift budget toward lower-CPA, higher-ROAS items. <br>- Set CPA ceiling per category. <br>- Monitor marginal ROAS before scaling. |
| 🌏 **6. Geographic Focus Strategy** | - ROAS & Spend concentrated in major urban cities. <br>- Urban markets are primary revenue hubs. | - Maintain Tier-1 city focus. <br>- Test expansion in Tier-2 with pilot budgets. <br>- Localize creatives & offers by region. |
