# dynamic-pricing
# 🚗 Dynamic Parking Pricing – Summer Analytics 2025

An intelligent real-time parking pricing system built using Pathway, Bokeh, and Python. This project was developed as part of the Summer Analytics 2025 Hackathon to dynamically update parking prices based on occupancy data and demand.

---

## 👤 Team Member
- Syed Shahabaz A.

---

## 📌 Problem Statement

To design a real-time pricing algorithm for urban parking spaces that dynamically adjusts the parking cost based on various parameters such as occupancy and demand. The goal is to improve traffic flow, parking efficiency, and optimize revenue.

---

## 🧰 Tech Stack

| Tool        | Purpose                        |
|-------------|---------------------------------|
| Python      | Core programming language       |
| Pathway     | Real-time stream processing     |
| Bokeh       | Interactive data visualization  |
| Google Colab| Development environment         |
| GitHub      | Version control and submission  |

---

Files in This Repository

| File                                     | Description                          |
|------------------------------------------|--------------------------------------|
| Dynamic_Pricing_Shahabaz_Final.ipynb   | Main notebook with both models       |
| README.md                              | Project overview and explanation     |

---


arc of model 1Features & Logic:
            +------------------+
            | Occupancy        |
            | Capacity         |
            +--------+---------+
                     |
                     v
        +--------------------------+
        | price = 10 + 0.5 × (O/C) |
        +--------------------------+
                     |
                     v
        +--------------------------+
        | Clip: min=5, max=20      |
        +--------------------------+
                     |
                     v
           Final Daily Price


Model 1: Baseline Linear Pricing
- Formula:  
  price = 10 + 0.5 × (Occupancy / Capacity)
- Price is bounded between $5 and $20
- Simple rule-based pricing tied to usage

---
arc of model 2 feature and logic:
         +-------------------------+
         | Occupancy / Capacity    |
         | λ (lambda = 0.5)        |
         +-----------+-------------+
                     |
                     v
     +------------------------------------+
     | demand = occupancy / capacity      |
     | price = 10 × (1 + λ × demand)      |
     +----------------+-------------------+
                      |
                      v
           +-------------------------+
           | Clip price (5 to 20 $)  |
           +-------------------------+
                      |
                      v
             Final Dynamic Price
             
Model 2: Demand-Based Dynamic Pricing
- Demand is defined as:  
  demand = Occupancy / Capacity
- Pricing formula:  
  price = 10 × (1 + λ × demand)
- λ (lambda) = 0.5
- Price is still clipped between $5 and $20

---

Visualization with Bokeh

- Real-time line chart showing price updates per day
- Interactive dashboard generated using Panel + Bokeh
- Sorting by timestamp to see daily pricing trend

---

Architecture Flow

1. Load occupancy data via Pathway
2. Stream processed data in tumbling daily windows
3. Apply pricing formula (Model 1 or 2)
4. Clamp the price to be within allowed bounds
5. Plot price output over time

---

How to Run

1. Open the notebook in Google Colab
2. Run all cells in order
3. Final cells will display the Bokeh price dashboard

---

Notes

- Currently, only occupancy and capacity are used.
- Queue length, traffic level, or special days can be added later for Model 3.
- All code and logic comply with Pathway’s real-time stream model.


Contact

For any questions or clarifications:
- 📧 Email: syedshahabaza@gmail.com
- 📱 LinkedIn: [Your LinkedIn](https://www.linkedin.com/in/syed-shahabaz-a-81663a270) 
-  mobile number: 9620054215
- woring google collab link: https://colab.research.google.com/drive/1fBwKBl6EWDqpnSSU8pjZXXRXqzYHM4Oe?usp=sharing

    > This project was developed as part of the Summer Analytics 2025 Hackathon. Powered by Pathway.
