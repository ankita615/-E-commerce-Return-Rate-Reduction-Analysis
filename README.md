# 📦 E-commerce Return Rate Reduction Analysis

## 📌 Objective

Identify why customers return products and how return rates vary by category, geography, and marketing channel. Predict return probabilities and visualize insights using an interactive dashboard.

---

## 🛠️ Tools & Technologies

* **Python (Pandas, Scikit-learn)**: Data processing, analysis, prediction model
* **Power BI**: Visualization dashboard with filters and drill-throughs
* **SQL (Optional)**: Data merging and preprocessing

---

## 📁 Project Structure

```
ecommerce-return-analysis/
│
├── data/
│   ├── orders.csv                  # Order details
│   ├── returns.csv                 # Return logs
│   └── high_risk_products.csv      # Output of predictive model
│
├── ecommerce_return_analysis.ipynb # Full Python analysis and modeling
│
├── dashboard/
│   └── return_risk_score.pbix      # Power BI interactive dashboard (user-generated)
│
└── README.md
```

---

## 📊 Dataset Description

### `orders.csv`

| Column             | Description                    |
| ------------------ | ------------------------------ |
| order\_id          | Unique identifier of order     |
| product\_id        | Product code                   |
| customer\_id       | Buyer ID                       |
| order\_date        | Date of order                  |
| category           | Product category               |
| region             | Geographic region              |
| marketing\_channel | Marketing source (Email, etc.) |
| supplier           | Product supplier               |
| quantity           | Units ordered                  |
| sales              | Total sales amount             |

### `returns.csv`

| Column         | Description                    |
| -------------- | ------------------------------ |
| return\_id     | Unique ID for the return event |
| order\_id      | Linked order ID                |
| return\_date   | Date of return                 |
| return\_reason | Reason provided for the return |
| return\_status | 1 = Returned, 0 = Not returned |

---

## 📈 Steps Performed

### 1. **Data Cleaning & Merging**

* Merged order and return datasets on `order_id`
* Created a binary `is_returned` field for modeling

### 2. **Exploratory Data Analysis**

* Analyzed return percentage by `category`, `region`, `marketing_channel`, and `supplier`

### 3. **Predictive Modeling**

* One-hot encoded categorical variables
* Trained a logistic regression model to predict the likelihood of return
* Generated a `return_probability` for each order

### 4. **High-Risk Product Identification**

* Filtered and exported products with return probability > 70% into `high_risk_products.csv`

### 5. **Power BI Dashboard**

* Bar chart: Return % by Category
* Map: Return % by Region
* Line chart: Monthly Return Rate
* Table: High-risk Products with probability
* Slicers for Category, Supplier, Region, Channel
* Drill-through for product-level insights

---

## 📤 Output Files

* 🔢 `high_risk_products.csv`: Products with return probability > 70%
* 📊 `return_risk_score.pbix`: Dashboard for management and product team

---

## 🚀 How to Run

1. Open `ecommerce_return_analysis.ipynb` in Jupyter
2. Run all cells to process data and generate predictions
3. Use `high_risk_products.csv` as input in Power BI for visuals
4. Open `return_risk_score.pbix` and refresh dataset (if needed)
