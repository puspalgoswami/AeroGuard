# 🛡️ AeroGuard

## AI-Powered Predictive Maintenance & Fleet Availability Platform

AeroGuard is an AI-powered predictive maintenance and fleet readiness platform designed to improve aircraft availability by predicting Remaining Useful Life (RUL), detecting abnormal sensor behaviour, assessing aircraft health, and supporting maintenance planning.

The system combines Machine Learning, anomaly detection, FastAPI, and React into a unified predictive maintenance platform.

---

## 🚀 Smart India Hackathon

### Problem Statement: SIH26249

**Title:** Air Power - Predictive Maintenance & Fleet Availability

### Problem

Aircraft maintenance is often fragmented across health-monitoring systems, technical records, spare-parts information, and maintenance agencies.

This can result in:

- Reactive rather than predictive maintenance
- Unexpected aircraft downtime
- Delayed fault detection
- Inefficient maintenance scheduling
- Poor utilisation of available aircraft
- Reduced fleet availability

AeroGuard addresses this problem by using aircraft sensor data and machine learning to provide early health and maintenance insights.

---

## 🎯 Objectives

AeroGuard aims to:

- Predict Remaining Useful Life (RUL) of aircraft engines
- Estimate aircraft health
- Detect abnormal sensor behaviour
- Classify aircraft into different risk levels
- Generate maintenance recommendations
- Monitor fleet availability
- Forecast fleet availability
- Provide a centralized maintenance dashboard
- Provide an API for integration with other systems

---

# 🧠 Core Features

### 1. Remaining Useful Life Prediction

A machine learning model predicts the estimated number of operational cycles remaining before maintenance may be required.

Example:

```text
Predicted RUL: 116.33 cycles

2. Aircraft Health Score
AeroGuard converts model predictions into an easy-to-understand aircraft health score.
Example:
Health Score: 93.07%

3. Predictive Risk Classification
Aircraft are classified into four risk categories:
LOW
MODERATE
HIGH
CRITICAL

This allows maintenance teams to prioritize aircraft requiring attention.
4. Anomaly Detection
AeroGuard uses an anomaly detection model to identify unusual sensor behaviour.
Possible states:
NORMAL
ANOMALY

5. Maintenance Recommendation
The system combines RUL, health score, risk level, and anomaly status to generate a maintenance recommendation.
Example:
Risk Level: LOW
Anomaly Status: NORMAL
Recommendation: Normal operation

6. Fleet Availability Monitoring
AeroGuard provides a fleet-level overview.
Example:
Total Aircraft       : 100
Available Aircraft   : 93
Under Maintenance    : 7
Fleet Availability   : 93%

7. Fleet Availability Forecast
AeroGuard generates a 7-day fleet availability forecast.
Example:
Day 1 : 58 available | 42 maintenance | 58.0%
Day 2 : 65 available | 35 maintenance | 65.0%
Day 3 : 71 available | 29 maintenance | 71.0%
Day 4 : 80 available | 20 maintenance | 80.0%
Day 5 : 84 available | 16 maintenance | 84.0%
Day 6 : 88 available | 12 maintenance | 88.0%
Day 7 : 95 available |  5 maintenance | 95.0%

🤖 Machine Learning
AeroGuard currently uses the NASA C-MAPSS FD001 turbofan engine dataset for development and experimentation.
Dataset
Training Engines : 100
Test Engines     : 100

The dataset contains multiple operational and sensor measurements recorded across engine cycles.
📊 Model Performance
RUL Prediction Model
A Random Forest Regression model is used for Remaining Useful Life prediction.
Test performance:
MAE  : 12.60 cycles
RMSE : 17.39 cycles
R²   : 0.8248

The model achieved an R² score of approximately 82.48% on the test data.
Anomaly Detection
AeroGuard uses an Isolation Forest model for anomaly detection.
The model analyses selected sensor measurements and identifies unusual operating patterns.
🏗️ System Architecture
                 Aircraft Sensor Data
                         │
                         ▼
              ┌─────────────────────┐
              │ Sensor Processing    │
              │ & Feature Selection  │
              └──────────┬──────────┘
                         │
                ┌────────┴────────┐
                │                 │
                ▼                 ▼
       ┌────────────────┐  ┌─────────────────┐
       │ RUL Prediction │  │ Anomaly Detection│
       │ Random Forest  │  │ Isolation Forest │
       └───────┬────────┘  └────────┬────────┘
               │                    │
               └─────────┬──────────┘
                         ▼
              ┌─────────────────────┐
              │ Health & Risk Engine │
              └──────────┬──────────┘
                         │
                         ▼
                ┌─────────────────┐
                │    FastAPI      │
                │    /predict     │
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │ React Dashboard │
                │    AeroGuard    │
                └─────────────────┘

💻 Technology Stack
Machine Learning
- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Joblib
Backend
- Python
- FastAPI
- Uvicorn
- Pydantic
Frontend
- React
- Vite
- JavaScript
- CSS
- Lucide React
Dataset
- NASA C-MAPSS FD001
📁 Project Structure
AeroGuard/
│
├── backend/
│   ├── main.py
│   └── requirements.txt
│
├── data/
│   ├── train_FD001.txt
│   ├── test_FD001.txt
│   └── RUL_FD001.txt
│
├── models/
│   ├── rul_model.pkl
│   ├── anomaly_model.pkl
│   └── model_config.pkl
│
├── frontend/
│   ├── src/
│   │   ├── App.jsx
│   │   ├── App.css
│   │   └── ...
│   ├── package.json
│   └── vite.config.js
│
├── model.ipynb
│
└── README.md

⚙️ Installation & Setup
1. Clone the Repository
git clone https://github.com/your-username/AeroGuard.git
cd AeroGuard

🐍 Backend Setup
Navigate to the backend:
cd backend

Install the required Python packages:
pip install -r requirements.txt

Start the FastAPI server:
uvicorn main:app --reload

The backend will run at:
http://127.0.0.1:8000

📖 API Documentation
FastAPI automatically provides interactive Swagger documentation.
Open:
http://127.0.0.1:8000/docs

Available endpoints:
GET  /
GET  /health
POST /predict

⚛️ Frontend Setup
Open a new terminal.
Navigate to the frontend:
cd frontend

Install dependencies:
npm install

Start the development server:
npm run dev

The dashboard will be available at:
http://localhost:5173

🔌 API Usage
Endpoint
POST /predict

Request
{
  "sensor_2": 642.58,
  "sensor_3": 1581.22,
  "sensor_4": 1398.91,
  "sensor_7": 554.42,
  "sensor_8": 2388.08,
  "sensor_9": 9056.4,
  "sensor_11": 47.23,
  "sensor_12": 521.79,
  "sensor_13": 2388.06,
  "sensor_14": 8130.11,
  "sensor_15": 8.4024,
  "sensor_17": 393,
  "sensor_20": 38.81,
  "sensor_21": 23.3552
}

Response
{
  "predicted_rul": 116.33,
  "health_score": 93.07,
  "risk_level": "LOW",
  "anomaly_status": "NORMAL",
  "alert": "NORMAL",
  "maintenance_action": "Normal operation"
}

🖥️ AeroGuard Dashboard
The React dashboard provides a centralized view of aircraft and fleet health.
Dashboard capabilities
- Fleet availability
- Critical aircraft count
- Maintenance workload
- Aircraft health score
- Remaining Useful Life
- Risk classification
- Anomaly detection
- Maintenance recommendation
- 7-day fleet availability forecast
- ML model performance
- API connectivity status
📈 Example Prediction
For one test aircraft, AeroGuard generated:
Predicted RUL       : 116.33 cycles
Health Score        : 93.07%
Risk Level          : LOW
Anomaly Status      : NORMAL
Alert               : NORMAL
Recommendation      : Normal operation

🔐 Deployment Considerations
The current implementation is a research and prototype system using the NASA C-MAPSS dataset.
For real-world deployment, AeroGuard could integrate:
- Secure aircraft health-monitoring data
- Real-time sensor feeds
- Authentication and authorization
- Role-based access control
- Encrypted communication
- Database systems
- Model monitoring
- Audit logging
- Maintenance management systems
- Spare-parts management systems
🔮 Future Scope
Digital Twin Integration
Develop digital twins of aircraft engines to simulate equipment health and degradation.
Real-Time Sensor Streaming
Integrate real-time aircraft health-monitoring systems.
Intelligent Maintenance Scheduling
Automatically prioritize maintenance based on:
- Remaining Useful Life
- Aircraft priority
- Spare availability
- Maintenance capacity
- Fleet requirements
Spare Parts Optimization
Predict required spare parts before an aircraft enters maintenance.
Fleet-Level Optimization
Extend AeroGuard from individual aircraft prediction to complete fleet-level maintenance planning.
Explainable AI
Provide explanations for why an aircraft has been classified as high or critical risk.
Advanced Time-Series Models
Future versions could experiment with:
- LSTM
- GRU
- XGBoost
- Temporal Fusion Transformer
- Other time-series forecasting approaches
🛡️ Security & Safety
AeroGuard is a prototype developed for academic and hackathon purposes.
The current implementation uses the publicly available NASA C-MAPSS dataset and does not use classified, restricted, or operational military aircraft data.
Predictions are intended for research and demonstration purposes and should not replace certified aircraft maintenance procedures or engineering judgment.
🏆 Smart India Hackathon 2026
Problem Statement: SIH26249
Title: Air Power - Predictive Maintenance & Fleet Availability
Organization: Ministry of Defence
Team Project: AeroGuard
👨‍💻 Project Team
Developed as part of Smart India Hackathon 2026.
⭐ Key Result
AeroGuard demonstrates a complete end-to-end predictive maintenance pipeline:
Aircraft Sensor Data
        ↓
Machine Learning
        ↓
RUL Prediction
        ↓
Anomaly Detection
        ↓
Health & Risk Assessment
        ↓
Maintenance Recommendation
        ↓
FastAPI Backend
        ↓
React Dashboard

AeroGuard
From Reactive Maintenance to Predictive Fleet Readiness.
