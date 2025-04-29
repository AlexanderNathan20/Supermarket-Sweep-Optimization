# 🛒 Supermarket Sweep Optimization

This project was developed as part of **ISyE 4133: Advanced Optimization (Spring 2024)** at Georgia Tech. The objective was to formulate and solve an optimization problem inspired by the game show *Supermarket Sweep*, in which two shoppers aim to collect the most valuable items in the shortest time possible.

---

## 📌 Problem Overview

Given:
- 56 distinct supermarket items
- A single start/end location
- A 60-second time constraint for each shopper
- A 10-item pickup limit per shopper

The goal is to determine optimal paths for two shoppers to collect the most valuable items without overlap, subject to time and item count constraints.

---

## 🔧 Methods

### Part A: Shortest Path Calculations
- Calculated travel time between all item locations using grid-based movement and Euclidean/Manhattan approximations.

### Part B: MIP Formulation (Simultaneous Model)
- Mixed Integer Programming model implemented in Gurobi.
- Objective: Maximize total item value across both shoppers.
- Constraints include:
  - Time limit (60 seconds)
  - Max 10 items per shopper
  - No item duplication
  - Must return to start

### Part C: Optimization Results
- **Shopper 1**: $81.19 collected  
- **Shopper 2**: $83.39 collected  
- **Total Value**: **$164.60**

### Part D: Visualization
- Explored value collected vs. time available.
- Logarithmic relationship observed beyond 170 seconds.

### Part E: Sequential Model
- Shopper 1's path optimized first.
- Shopper 2 optimizes with restricted item set.
- **Total Value**: **$155.81**

---

## 📈 Key Insights

- The **simultaneous model** outperforms the **sequential model** by $8.79.
- Value collection increases with time, but with diminishing returns beyond ~180 seconds.
- Optimization under constraints mirrors real-world logistics and queuing systems.

---

## 💻 Technologies Used

- **Python**
- **Gurobi Optimizer**
- **Pandas / NumPy**
- **Matplotlib** (for visualizations)

---

## 📁 File Structure

📂 supermarket-sweep/ ├── shortest_paths.py # Part A: Distance calculations ├── mip_model.py # Part B: MIP model (simultaneous) ├── sequential_model.py # Part E: MIP model (sequential) ├── visualization.py # Part D: Value vs. Time plots ├── data/ │ └── items.csv # Item location and value data ├── report/ │ └── Supermarket_Sweep_Report.pdf # Full project write-up └── README.md #
