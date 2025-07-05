# Summer-Analytics-2025
Dynamic Pricing for Urban Parking Lots


🚗 Project Overview

This project implements a dynamic pricing system for 14 urban parking lots using historical and simulated real-time data. Developed as part of the Summer Analytics 2025 Capstone Project, it uses data science and economic principles to optimize parking prices based on demand, congestion, queue length, and competitor pricing.

🧠 Objective

To build a data-driven, explainable, and smooth dynamic pricing engine that:

Updates prices based on occupancy, traffic, vehicle type, queue length, and special days

Incorporates competitor pricing based on location

Simulates real-time decision-making

📦 Dataset

The dataset includes:

18,368 records

73 days of data from 14 parking lots

Features:

Occupancy, Capacity

QueueLength, TrafficConditionNearby

VehicleType, IsSpecialDay

Latitude, Longitude

Timestamp

🧩 Models Implemented

🔹 Model 1: Baseline Linear Model

Simple pricing based on current occupancy:

Price_t+1 = Price_t + α × (Occupancy / Capacity)

🔹 Model 2: Demand-Based Model

Multivariate demand function incorporating real-world features:

Demand = α·(Occupancy/Capacity) + β·QueueLength − γ·Traffic + δ·IsSpecialDay + ε·VehicleTypeWeight
Price = BasePrice × (1 + λ × NormalizedDemand)

Price clipped to range [$5, $20] for stability

🔹 Model 3: Competitive Model

Adds geo-intelligence by checking distance and pricing of nearby lots:

Reduces price if lot is full and cheaper lots are nearby

Increases price if competitors are more expensive

🔍 Assumptions

Base price = $10

Vehicle type weights: Car=1.0, Bike=0.5, Truck=1.5

Traffic mapping: Low=1, Medium=2, High=3

Distance threshold = 500 meters for competitor proximity

All models implemented using only pandas, numpy, geopy, and bokeh

📊 Visualizations

Real-time pricing line plots for each parking lot using Bokeh

Compare pricing patterns across Model 1, Model 2, and Model 3

🛠 Tools Used

Python (NumPy, Pandas)

Bokeh for real-time plots

Geopy for distance computation

Google Colab

🚀 How to Run

Upload dataset.csv in Google Colab

Run each model cell block (Model 1 → Model 2 → Model 3)

Call the plot_price_evolution() function for a desired parking lot

Final results are exported as final_dynamic_prices.csv

📈 Sample Visualization Code

plot_price_evolution(df_model3, "Model 3 - Competitive", "BHMBCCMKT01")

📂 Output

final_dynamic_prices.csv with final prices from Model 3

Interactive plots inline in notebook

📌 Future Scope

Real-time integration using Pathway

Suggest rerouting users to cheaper nearby lots automatically

Incorporate weather and event APIs for smarter adjustments
