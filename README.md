# 🛡️ AeroGuard

### AI-Powered Predictive Maintenance & Fleet Availability Platform

AeroGuard is an AI-powered predictive maintenance and fleet readiness platform designed to improve aircraft availability by predicting remaining useful life, detecting abnormal sensor behaviour, assessing aircraft health, and supporting maintenance planning.

The system combines **Machine Learning, anomaly detection, FastAPI, and React** into a unified maintenance intelligence platform.

---

## 🚀 Problem Statement

### SIH26249 — Air Power: Predictive Maintenance & Fleet Availability

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

# 🎯 Objectives

AeroGuard aims to:

- Predict **Remaining Useful Life (RUL)** of aircraft engines
- Estimate an overall **aircraft health score**
- Detect abnormal sensor behaviour
- Classify aircraft into different **risk levels**
- Generate maintenance recommendations
- Estimate fleet availability
- Forecast fleet availability over multiple days
- Provide a centralized maintenance dashboard
- Provide an API for integration with other systems

---

# 🧠 Core Features

## 1. Remaining Useful Life Prediction

A machine learning model predicts the estimated number of operational cycles remaining before maintenance may be required.

Example:

```text
Predicted RUL: 116.33 cycles
