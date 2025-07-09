
# 📊 Capstone Report: Dynamic Pricing for Urban Parking Lots

## 🧠 Project Overview

This project aims to develop a dynamic pricing engine for urban parking lots using real-time data and intelligent pricing models. It is structured into three progressive models.

---

## 📍 Dataset Summary

- **Total Lots:** 14
- **Days Covered:** 3 (Simulated)
- **Time Interval:** Every 30 minutes (8 AM to 4:30 PM)
- **Features Used:**
  - Occupancy, Capacity, Queue Length
  - Traffic Congestion Level
  - Special Day Indicator
  - Vehicle Type
  - Latitude & Longitude

---

## 🧩 Model 1: Baseline Linear Model

**Formula:**  
\[
\text{Price}_{t+1} = \text{Price}_t + \alpha \cdot \left(\frac{\text{Occupancy}}{\text{Capacity}}\right)
\]

**Key Characteristics:**
- Linear response to occupancy.
- Simple and interpretable.
- Serves as a control model.

---

## 📈 Model 2: Demand-Based Price Function

**Demand Function:**
\[
\text{Demand} = \alpha \cdot \left(\frac{\text{Occupancy}}{\text{Capacity}}\right) + \beta \cdot \text{Queue} - \gamma \cdot \text{Traffic} + \delta \cdot \text{Special Day} + \epsilon \cdot \text{Vehicle Type Weight}
\]

**Pricing Logic:**
\[
\text{Price}_t = \text{Base} \cdot \left(1 + \lambda \cdot \text{Normalized Demand}\right)
\]

**Notes:**
- Price bounded between 0.5x and 2x base.
- Smooth transitions ensured via clipping.

---

## 🧭 Model 3: Competitive Pricing (Optional)

**Features Used:**
- Geographic proximity (haversine distance)
- Nearby competitor prices

**Logic:**
- Increase price if nearby lots are costlier.
- Suggest rerouting or decrease price if our lot is full and cheaper lots are nearby.

---

## 📊 Visualizations

- Real-time pricing trends using Bokeh
- Lot-wise price comparison
- Optional: heatmap of pricing across locations

---

## 📝 Assumptions

- Vehicle types have assigned static weights.
- Traffic values are normalized between 0 and 1.
- Demand is capped for stability.
- Competitor pricing assumed as 10 ± small margin.

---

## ✅ Conclusion

This simulation demonstrates how data-driven, real-time pricing models can enhance the efficiency of urban parking systems. Future work can include:
- Pathway-based live deployment
- Integration with routing algorithms
- Deeper RL-based or probabilistic pricing

---

© Summer Analytics 2025 | Consulting & Analytics Club × Pathway
