# Customer Segmentation Using RFM Analysis & K-Means Clustering

## 📌 Project Overview

This project performs customer segmentation using transactional retail data by applying **RFM (Recency, Frequency, Monetary) analysis** and **K-Means clustering**. The goal is to identify meaningful customer segments that can be used to support targeted marketing strategies, customer retention, and revenue optimization.

The project follows a full data science workflow including:
- Data cleaning
- Feature engineering
- Clustering evaluation
- Model selection
- Business interpretation

---

## 📊 Dataset

The dataset contains transactional records from an online retail store and includes the following fields:

- `InvoiceNo`
- `InvoiceDate`
- `CustomerID`
- `Quantity`
- `UnitPrice`
- `Country`

Each transaction represents a product purchase made by a customer.

---

## ⚙️ Methodology

### 1. Data Cleaning & Preparation

- Removed duplicate records  
- Handled encoding artifacts in column headers  
- Filtered invalid transactions (negative quantity or price)  
- Converted date and numeric columns to appropriate formats  
- Created transaction-level revenue feature (`TotalPrice`)  

---

### 2. Feature Engineering (RFM Metrics)

Customer-level features were created using RFM methodology:

- **Recency** — Days since last purchase  
- **Frequency** — Number of unique invoices  
- **Monetary** — Total customer spending  

These metrics capture customer engagement and value.

---

### 3. Feature Scaling

- RFM features were standardized using `StandardScaler` to ensure equal contribution to clustering.

---

### 4. Cluster Selection

The optimal number of clusters was selected using:

- Elbow Method (Inertia / SSE)  
- Silhouette Score  
- Minimum cluster size constraints (business usability)  

Evaluation results showed that **k = 4** provided the best tradeoff between clustering quality and segment interpretability.

---

### 5. K-Means Clustering

- Customers were segmented into **four behavioral clusters** using K-Means clustering.

---

### 6. Segment Profiling

- Clusters were analyzed using average RFM values and revenue contribution to generate actionable business insights.

---

## 📈 Key Results

### Revenue Contribution by Segment

| Segment             | Revenue Share |
|---------------------|---------------|
| Regular Customers   | 46.5%         |
| Loyal High Value    | 29.1%         |
| VIP Champions       | 18.6%         |
| At Risk Customers   | 5.7%          |

> Despite representing only **0.3% of customers**, **VIP Champions** generated nearly **19% of total revenue**.

---

### Segment Definitions

#### 🏆 VIP Champions
- High-frequency, high-spend, recently active customers  
- Primary focus for retention and loyalty programs  

#### 💎 Loyal High Value
- Strong repeat buyers with high upsell potential  

#### 👥 Regular Customers
- Large-volume segment with moderate engagement and revenue contribution  

#### ⚠️ At Risk Customers
- Inactive or low-engagement customers suitable for reactivation campaigns  

---

## 💡 Business Impact

This segmentation enables:

- Personalized marketing campaigns  
- Improved customer retention strategies  
- Revenue optimization through targeted offers  
- Better allocation of marketing budgets  
- Reduced churn risk  

---

## 🛠 Technologies Used

- Python  
- Pandas, NumPy  
- Scikit-Learn  
- Matplotlib, Seaborn  
- Jupyter Notebook  

---

## 📌 Future Improvements

- Integrate customer demographics and product categories  
- Apply alternative clustering algorithms (DBSCAN, Hierarchical)  
- Implement automated segment refresh pipelines  
- Deploy segmentation as part of a CRM workflow  
- Build dashboard visualizations for real-time monitoring  