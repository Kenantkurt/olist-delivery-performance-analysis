#  Olist Delivery Performance Analysis

A data-driven analysis of delivery performance using the Brazilian Olist e-commerce dataset.  
This project evaluates estimated vs. actual delivery times and analyzes delay patterns to assess the reliability of the delivery estimation system.

---

##  Objective

This analysis aims to:

- Compare estimated delivery dates with actual delivery dates  
- Measure delivery delays and early deliveries  
- Quantify prediction error using Mean Absolute Error (MAE)  
- Determine whether the estimation system is conservative or optimistic  
- Explore the potential impact of late deliveries on customer satisfaction  

---

## 📊 Dataset

**Dataset Used:**  
`olist_orders_dataset.csv`

The dataset includes order-level information such as:

- `order_purchase_timestamp`  
- `order_delivered_customer_date`  
- `order_estimated_delivery_date`  
- `order_status`  
- Customer identifiers  

Source: Olist Brazilian E-Commerce Public Dataset

---

##  Methodology

### 1️⃣ Data Preparation

- Filtered only delivered orders  
- Converted relevant columns to datetime format  
- Computed delivery duration  
- Calculated delivery delay:

```python
delivery_delay = actual_delivery_date - estimated_delivery_date
```

- Created categorical delivery status:
  - Early  
  - On-time  
  - Late  

---

### 2️⃣ Key Metrics Computed

- Percentage of early vs. late deliveries  
- Mean Absolute Error (MAE)  
- Average late delay  
- Average early arrival  
- Distribution of delays (0–30 days)  

---

##  Results

### Delivery Behavior

- **91.9%** of deliveries arrived earlier than estimated  
- **6.8%** of deliveries were late  

###  Prediction Accuracy

- **Average Absolute Error (MAE): ~13.3 days**  
- Late deliveries are delayed by **~10.6 days** on average  
- Early deliveries arrive **~13.7 days earlier** than estimated  

### 🔎 Insight

The delivery estimation system appears **highly conservative** and systematically overestimates delivery times.

While this reduces SLA risk and late delivery complaints, it may negatively affect customer expectations by inflating perceived waiting time.

---

##  Visualization

A histogram of delivery delays (0–30 days) was generated using Plotly and exported as a static PNG for GitHub compatibility.

The distribution reveals:

- A strong concentration of 1–7 day early deliveries  
- A long-tail pattern for late deliveries  
- Rare but extreme delay outliers  

---

##  Hypothesis

- **H0:** Late delivery has no impact on review score  
- **H1:** Late delivery decreases review score  

(Prepared for future statistical testing.)

---

##  Technologies Used

- Python 3.x  
- Pandas  
- NumPy  
- Plotly  
- Kaleido (static rendering for GitHub compatibility)  
- Jupyter Notebook  

---

## 📂 Project Structure

```
olist-delivery-performance-analysis/
│
├── olist_delivery_performance_analysis.ipynb
├── olist_orders_dataset.csv
└── README.md
```

---

##  How to Run

### 1️⃣ Clone the repository

```bash
git clone https://github.com/your-username/olist-delivery-performance-analysis.git
```

### 2️⃣ Install dependencies

```bash
pip install pandas numpy plotly kaleido
```

### 3️⃣ Open the notebook

```bash
jupyter notebook
```

### 4️⃣ Run all cells

---

##  Key Takeaways

- The estimation model significantly overestimates delivery times.  
- Most customers receive their orders earlier than promised.  
- Conservative estimation reduces operational risk but increases perceived waiting time.  
- Extreme delays exist but are statistically rare.  

---

##  Future Improvements

- Merge with review dataset to test the hypothesis statistically  
- Perform regression analysis on delivery delay vs. review score  
- Build a predictive model for delivery delay  
- Analyze geographic impact on delivery performance  
- Detect outlier sellers or regions  

---

## 👤 Author

**Kenan Kurt**  
Data Analyst | Python | SQL | Data Engineering Enthusiast  

---

##  If you found this project useful

Consider giving it a star ⭐

