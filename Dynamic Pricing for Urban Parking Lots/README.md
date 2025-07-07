

# 🚗 Dynamic Urban Parking Pricing System

A real-time, intelligent pricing engine for managing urban parking spaces using demand-driven logic, real-time data streams, and machine learning principles — all built **from scratch** using only Python, NumPy, Pandas, and [Pathway](https://pathway.com).

> 📅 Capstone Project — July 2025  

---

## 🧠 Overview

In cities, static parking rates lead to overcrowding and underutilization of valuable spaces. This project simulates a **smart pricing system** that dynamically adjusts parking prices based on:

- Occupancy rate
- Queue length
- Nearby traffic congestion
- Special event indicators
- Vehicle type
- Competitor lot pricing (optional)

The system ingests streaming data, applies economic principles + ML logic, and outputs pricing decisions in real-time.

---

## 🛠️ Tech Stack

| Tool        | Purpose                         |
|-------------|---------------------------------|
| **Python**  | Core logic and data handling    |
| **NumPy**   | Numerical computation           |
| **Pandas**  | Data analysis + preprocessing   |
| **Pathway** | Real-time data streaming & ETL  |
| **Matplotlib** / Bokeh | Visualization        |
| **Google Colab** | Development environment    |

---

## 🧱 System Architecture

```mermaid
flowchart TD
    A[parking_stream.csv] --> B[Pathway Data Pipeline]
    B --> C[Model 1: Linear Pricing]
    B --> D[Model 2: Demand-Based Pricing]
    C --> E[Price Output]
    D --> E
    E --> F[final_prices.csv]
    F --> G[Visualization Engine]
````

---

## ⚙️ Project Architecture & Workflow

1. **Data Streaming**
   Pathway is used to simulate real-time data ingestion from a historical CSV file containing 73 days of parking data.

2. **Model 1: Baseline Pricing**
   Prices increase linearly with occupancy levels.

   $$
   Price_{t+1} = Price_t + \alpha \cdot \frac{Occupancy}{Capacity}
   $$

3. **Model 2: Demand-Based Dynamic Pricing**
   Price is influenced by:

   * Occupancy percentage
   * Queue length at the lot
   * Traffic congestion level
   * Whether it's a special day
   * Vehicle type weight (car, bike, truck)

   The demand score is computed, normalized, and used to scale the base price:

   $$
   Price = Base \cdot (1 + \lambda \cdot Demand)
   $$

4. **Real-Time Prediction Output**
   All predictions are streamed and written to `final_prices.csv`.

5. **Visualization**
   Dynamic price over time is visualized using Matplotlib/Bokeh for analysis and insights.

---

## 📁 Folder Structure

```
📦parking-pricing-system/
 ┣ 📄 README.md
 ┣ 📄 parking_stream.csv
 ┣ 📄 final_prices.csv
 ┣ 📄 model1_model2_notebook.ipynb
 ┗ 📄 requirements.txt
```

---

## 📊 Example Output (Model 2)

| Timestamp           | Occupancy | Capacity | QueueLength | Traffic | IsSpecialDay | VehicleType | Price |
| ------------------- | --------- | -------- | ----------- | ------- | ------------ | ----------- | ----- |
| 2025-07-01 08:00:00 | 20        | 40       | 3           | 0.4     | 0            | car         | 11.80 |
| 2025-07-01 08:30:00 | 25        | 40       | 4           | 0.7     | 0            | bike        | 12.10 |

---

## 🚀 Future Scope

* Add **Model 3** with location-based competitive pricing
* Integrate Google Maps API for routing logic
* Deploy as a web app with user-facing dashboard

---

## 📌 How to Run

1. Clone the repo:

   ```bash
   git clone https://github.com/your-username/parking-pricing-system.git
   ```

2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Run the notebook:

   ```bash
   Open model1_model2_notebook.ipynb in Google Colab or Jupyter
   ```

4. Upload your CSV (or use the sample) and execute.

---

## 🏁 Conclusion

This project showcases how real-world ML techniques and economic logic can be applied in a practical system using pure Python.
It's lightweight, interpretable, and open for further development 🚀


