## **Stage 1: Problem Definition and Requirements Gathering**

*(Role: Business Analyst)*

We will load both datasets into Python, explore them, and analyze the columns along with their data types.

### **Business Questions**

From the provided datasets, we aim to answer:

* Which products generate the highest total revenue, and how do their sales volumes compare?
* How do monthly sales trends differ across the top 5 best-selling products?
* Which products have the highest and lowest average customer sentiment scores?
* How does customer sentiment for each product change month over month?
* Do products with higher sentiment scores generate higher revenue?
* Which high-revenue products have relatively low sentiment scores, indicating potential quality or service issues?

---

### **Data Points**

| Data Point        | Source File                                     | Purpose                                                       |
| ----------------- | ----------------------------------------------- | ------------------------------------------------------------- |
| `product_id`      | `sales_data_raw.csv` & `customer_feedback.json` | Links sales data with customer feedback for analysis          |
| `sale_price`      | `sales_data_raw.csv`                            | Calculates revenue per sale                                   |
| `quantity`        | `sales_data_raw.csv`                            | Determines total units sold and total revenue                 |
| `sale_date`       | `sales_data_raw.csv`                            | Tracks sales trends over time                                 |
| `customer_id`     | `sales_data_raw.csv` & `customer_feedback.json` | Connects purchases with feedback; identifies repeat customers |
| `sentiment_score` | `customer_feedback.json`                        | Measures customer satisfaction (1–5 scale)                    |
| `review_date`     | `customer_feedback.json`                        | Tracks changes in customer sentiment over time                |

---

### **Problem Statement**

The business wants to identify top-performing products by revenue and understand how customer sentiment varies for these products over time.
By linking sales data with customer feedback, we aim to uncover opportunities to improve product performance, customer satisfaction, and overall revenue growth.

---

### **Key Metrics**

**From Sales Data:**

* **Total Revenue** = `sum(sale_price × quantity)` per product
* **Total Units Sold** per product
* **Monthly Sales Trend** = total revenue by month

**From Feedback Data:**

* **Average Sentiment Score** per product (1–5 scale)
* **Monthly Sentiment Trend** per product

**Combined Metrics:**

* Correlation between revenue and sentiment per product
* Identification of High Revenue / Low Sentiment products

---

### **Desired Insights**

* Top 5 products by total revenue and their sales volumes.
* Average customer sentiment for each top product.
* Trends in sales and sentiment over time for top products.
* Products with high sales but low sentiment (potential quality issues).
* Products with improving sentiment that may indicate positive changes in quality or service.

---

## **Stage 2: Role-Based Collaboration Simulation**

### **1. Data Engineer – Data Ingestion and Cleaning**

**Tasks:**

* Ingest `sales_data_raw.csv` and `customer_feedback.json` from respective sources.
* Store raw files in a staging area for preprocessing.
* Standardize data formats:

  * Remove currency symbols and convert `sale_price` to numeric.
  * Fill missing `quantity` values with zeros or appropriate estimates.
  * Standardize date formats (`sale_date` and `review_date`) to `YYYY-MM-DD`.
* Ensure data integrity by removing duplicates and correcting invalid entries.
* Join datasets using `product_id` (and optionally `customer_id`) to prepare a consolidated dataset for analysis.

---

### **2. Data Scientist – Analysis and Modeling**

**Tasks:**

* Aggregate sales data to compute total revenue, units sold, and monthly sales trends.
* Analyze customer sentiment by calculating average sentiment scores and sentiment trends.
* Conduct correlation analysis between revenue and sentiment.
* Develop predictive models to forecast sales based on sentiment and historical data.
* Apply clustering to segment products by sales and sentiment characteristics.

---

### **3. Business Analyst – Interpretation and Reporting**

**Tasks:**

* Translate analytical findings into actionable recommendations for business strategy.
* Identify high-revenue products with low sentiment for quality improvement initiatives.
* Highlight products with increasing sentiment for targeted promotional campaigns.
* Create dashboards and reports (Power BI, Tableau) to visualize:

  * Top revenue products
  * Sentiment trends
  * Revenue vs. sentiment relationships
* Communicate insights clearly to stakeholders in both technical and non-technical terms.

---

### **4. Stakeholder Contributions**

* **Data Engineer:** Ensures high-quality, consistent, and integrated data.
* **Data Scientist:** Derives patterns, predictions, and advanced analytics.
* **Business Analyst:** Contextualizes results, aligns insights with business goals, and facilitates decision-making.

---

### **5. Flow of Responsibilities and Dependencies**

```
Raw Data 
  ↓ (Data Engineer) Cleaning & Integration 
  ↓ (Data Scientist) Analysis & Modeling 
  ↓ (Business Analyst) Reporting & Recommendations 
  ↓ (Management) Decision Making
```


