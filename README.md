# Dynamic Energy Pricing Optimization for Smart Meters

**Goal**: Optimize energy prices dynamically using machine learning to reduce peak demand, maximize grid efficiency, and minimize user cost—tailored for smart meter deployments in smart grids.

---

## Project Overview

Dynamic pricing models can help utilities incentivize off-peak usage, prevent blackouts, and align consumption with supply. This project uses real-time energy usage data from smart meters, combined with external factors (e.g., temperature, time of day), to optimize hourly energy prices using predictive ML and optimization techniques.

---

## Features

- Forecast short-term electricity demand using ML  
- Predict consumer response to price changes (price elasticity modeling)  
- Optimize hourly dynamic prices using reinforcement learning or convex optimization  
- Simulate smart meter behavior and user adaptation  
- Visualize grid load vs. pricing strategies

---

## Tech Stack

- **Languages**: Python 3.10+  
- **ML Libraries**: Scikit-learn, XGBoost, LightGBM, TensorFlow (optional)  
- **Optimization**: PuLP / SciPy / OR-Tools / RLlib (for RL-based pricing)  
- **Visualization**: Plotly, Seaborn, Dash / Streamlit  
- **Data Handling**: Pandas, NumPy  
- **Optional**: Docker, Flask for API

---

## Project Structure

```
dynamic-energy-pricing/
│
├── data/                    # Sample smart meter & weather datasets
├── notebooks/               # EDA & development notebooks
├── src/                     # Core modules
│   ├── preprocessing.py
│   ├── demand_forecasting.py
│   ├── pricing_model.py
│   ├── optimization_engine.py
│   └── simulator.py
├── app/                     # Streamlit dashboard (optional)
├── tests/                   # Unit tests
├── requirements.txt
└── README.md
```

---

## ML Workflow

1. **Data Collection**  
   - Hourly smart meter data (consumption per household)  
   - Weather data (temperature, humidity)  
   - Time features (hour, weekday, holidays)

2. **Forecasting Demand**  
   - Train a supervised model to predict hourly electricity demand

3. **Price Elasticity Modeling**  
   - Learn how demand changes with different pricing

4. **Optimization**  
   - Solve for the optimal hourly prices to flatten peak demand while maintaining revenue  
   - Approaches:
     - **Linear/Convex Optimization**
     - **Reinforcement Learning (DQN or PPO)**

5. **Simulation**  
   - Simulate user response to pricing  
   - Visualize impact on peak load and cost

---

## Sample Results

- Demand forecast MAE: `0.32 kWh`  
- Peak load reduction: `~17%`  
- Average user cost drop: `8%`  
- Revenue retention: `~96%` of flat-rate model

*(all values from synthetic test data)*

---

## Setup & Run

```bash
# 1. Clone repo
git clone https://github.com/Zyiar/Dynamic-Energy-Pricing-for-Smart-Meters.git
cd dynamic-energy-pricing

# 2. Install dependencies
pip install -r requirements.txt

# 3. Run the pipeline
python src/main.py

# 4. Launch dashboard (optional)
streamlit run app/dashboard.py
```

---

## Example Use Case

> Given predicted high demand on a hot weekday afternoon, the system increases prices from 2–6 PM to discourage consumption, while lowering prices at night to encourage off-peak usage (e.g., EV charging at 1 AM).

---

## Datasets Used

- [UK Domestic Smart Meter Data](https://data.london.gov.uk/dataset/smartmeter-energy-use-data-in-london-households)  
- [Open Power System Data (OPSD)](https://data.open-power-system-data.org/time_series/)  
- NOAA Weather Data via [NOAA API](https://www.ncei.noaa.gov/support/access-data-service-api-user-documentation)

---

## License

MIT License. See `LICENSE` for details.

---

## Contributing

Pull requests are welcome! For major changes, open an issue first to discuss what you'd like to change.
