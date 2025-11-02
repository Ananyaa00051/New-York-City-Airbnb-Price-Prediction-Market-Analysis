

#  New York City Airbnb Price Prediction & Market Analysis

###  A Data-Driven Exploration of Airbnb Pricing, Host Behavior & Location Dynamics in NYC

---

## 🧠 Overview

This project performs an **end-to-end Exploratory Data Analysis (EDA)** and builds a **CatBoost-based regression model** to predict Airbnb listing prices across **New York City**.
The goal is to uncover **what drives pricing variations** — exploring host factors, property attributes, and geographic location — while building a **high-performing, interpretable model** to estimate Airbnb prices.

---

## 🚀 Objectives

1. **Exploratory Analysis**

   * Understand how prices vary across NYC neighborhoods and property types.
   * Visualize key host and listing patterns (availability, reviews, amenities).

2. **Feature Engineering**

   * Create new, business-relevant features such as `price_per_person`, `amenity_count`, and `host_tenure_days`.
   * Clean and preprocess data with robust imputation and transformation steps.

3. **Predictive Modeling**

   * Train a **CatBoostRegressor** to predict Airbnb prices with strong generalization.
   * Evaluate model performance using **MAE**, **RMSE**, and **R²** metrics.

4. **Interpretability & Insights**

   * Use feature importance and explainability tools (SHAP) to understand model behavior.
   * Derive actionable insights for hosts and market analysts.

---

## 🧩 Dataset

* **Source:** [Inside Airbnb: New York City Dataset](http://insideairbnb.com/get-the-data/)
* **Scope:** Airbnb listings within the **five boroughs of NYC** — Manhattan, Brooklyn, Queens, Bronx, and Staten Island.
* **Key Variables:**

  * `price`, `room_type`, `accommodates`, `amenities`, `latitude`, `longitude`,
  * `host_since`, `availability_365`, `reviews_per_month`, and others.

---

## 🧮 Feature Engineering

| Feature                      | Description                                    |
| ---------------------------- | ---------------------------------------------- |
| `host_tenure_days`           | Days since the host joined Airbnb              |
| `price_per_person`           | Price divided by number of guests accommodated |
| `amenity_count`              | Count of amenities listed in the description   |
| `log_price`                  | Log-transformed price for normalization        |
| `property_type`, `room_type` | Encoded categorical features                   |
| `latitude`, `longitude`      | Used for NYC-level geospatial visualization    |

---

## 🌇 Geospatial Analysis

* Created **price heatmaps** using `folium` to visualize Airbnb pricing across NYC neighborhoods.
* **Findings:**

  * **Manhattan** and **Brooklyn waterfront areas** show consistently higher average prices.
  * Outer boroughs (Bronx, Queens, Staten Island) tend to have more affordable stays.
  * Proximity to major tourist zones (Times Square, Central Park) significantly impacts price.

🗺️ *The heatmap clearly demonstrates the location premium effect inherent to NYC listings.*

---

## ⚙️ Model Architecture

* **Algorithm:** CatBoostRegressor
* **Why CatBoost?**

  * Handles categorical and numerical data efficiently
  * Robust to missing values and outliers
  * Excellent generalization with minimal tuning
  * Built-in interpretability and feature importance tracking

### 🧾 Model Performance

| Metric       | Score   |
| ------------ | ------- |
| **Train R²** | 0.974   |
| **Test R²**  | 0.933   |
| **MAE**      | 188.44  |
| **RMSE**     | 1216.58 |

✅ Indicates **strong predictive accuracy** and **no significant overfitting**.

---

## 📈 Model Explainability

* **Feature Importance Findings:**

  * `price_per_person` dominated as a key feature, reflecting cost scaling with accommodation size.
  * `amenity_count` and `accommodates` were next, showing how property quality and size influence pricing.
  * Host-related features like `host_tenure_days` and `host_total_listings_count` also added significant predictive value.

* **SHAP & Interpretability:**

  * Visualized local and global feature contributions to predicted prices.
  * Helped confirm that **location, property size, and host experience** are the strongest drivers.

---

## 💡 Key Insights

* 💰 **Manhattan listings** are the most premium, followed by **Brooklyn**.
* 🛏️ **Larger accommodations and more amenities** strongly increase price.
* 👩‍💼 **Hosts with longer tenure and more listings** tend to command higher prices.
* 🗺️ **Geospatial pricing gradients** clearly reflect NYC’s tourism and business zones.

---

## 🧭 Tech Stack

| Category         | Tools & Libraries                   |
| ---------------- | ----------------------------------- |
| Data Processing  | Python, Pandas, NumPy               |
| Visualization    | Matplotlib, Seaborn, Plotly, Folium |
| Machine Learning | CatBoost, Scikit-Learn              |
| Explainability   | SHAP                                |
| Environment      | Jupyter Notebook / Google Colab     |

---


## 🧠 Future Enhancements

* Add **sentiment analysis** on textual reviews (to capture guest satisfaction).
* Deploy an **interactive Streamlit dashboard** for visualization.
* Include **temporal price trends** for dynamic pricing insights.
* Combine with **neighborhood crime/safety scores** for deeper socio-economic analysis.

---

## 🤝 Acknowledgements

* Data: **Inside Airbnb – NYC Dataset**
* Libraries: **CatBoost**, **SHAP**, **Folium**, and **Plotly**

---

