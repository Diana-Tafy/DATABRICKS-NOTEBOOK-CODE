# My Coffee Shop Data Warehouse Architecture

This directory houses the core data assets for the retail coffee shop optimization project. The data model follows a star schema design optimized for fast analytical queries, performance tracking, and customer loyalty segmentation.

**Database Schema:** `my_coffee_shop_v1`

---

## 👥 1. Dimension: Customers (`dim_customers`)

**Description:** Contains master data for all registered coffee shop customers, tracking demographic essentials alongside loyalty program tiers and engagement points.

### Schema Definition
| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| `customer_id` | Integer | Unique primary key for each customer |
| `first_name` | String / Varchar | Customer's first name |
| `last_name` | String / Varchar | Customer's last name |
| `email` | String / Varchar | Primary communication email address |
| `tier` | String / Varchar | Loyalty tier classification (e.g., Bronze, Silver, Gold) |
| `points` | Integer | Accumulated active loyalty reward points |
| `created_at` | Timestamp | Account creation date and time |

### Analytical Use Cases
* **Customer Segmentation:** Grouping purchase behaviors based on loyalty tier classifications.
* **Churn Analysis:** Monitoring point accrual patterns against account age (`created_at`) to identify inactive users.

---

## ☕ 2. Dimension: Products (`dim_products`)

**Description:** Serves as the single source of truth for the retail item catalog, mapping internal inventory codes to consumer-facing menu details, retail pricing, and categories.

### Schema Definition
| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| `product_id` | Integer | Unique primary key for each product catalog item |
| `product_code` | String / Varchar | Internal inventory/SKU code identifier |
| `product_name` | String / Varchar | Consumer-facing item name (e.g., Chinesse Tea, Coffee etc) |
| `price` | Decimal / Double | Standard unit retail price |
| `category` | String / Varchar | Menu classification category (e.g., Coffee,Tea,etc) |

### Analytical Use Cases
* **Menu Optimization:** Aggregating sales metrics by category to identify underperforming vs. high-margin items.
* **Price Sensitivity Analysis:** Cross-referencing order volume fluctuations against product retail pricing points.

---

## 🛠️ Data Lineage & Tech Stack
* **Platform:** Databricks (Free Edition / Community Cloud)
* **Storage Provider:** Delta Lake / Hive Metastore
* **Language:** ANSI SQL

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/b4151865-7fd2-4de2-81a4-5db81e5e856b" />

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/77245a46-d56a-411d-a317-c189f6d65408" />


