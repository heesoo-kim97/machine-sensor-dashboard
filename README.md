# Machine Sensor Dashboard

**Real-Time Manufacturing Monitoring Dashboard | BIX5, JavaScript, CSS**

---

## 📋 Table of Contents

* [Demo](#-demo)
* [About This Project](#about-this-project)
* [Business Case](#business-case)
* [How It Works](#how-it-works)
* [Technical Implementation](#technical-implementation)
* [Code Highlights](#code-highlights)
* [Key Insights](#key-insights)
* [Technologies](#technologies)
* [Repository](#repository)

---

## 🎥 Demo

### Video Demo

[![Watch the Machine Sensor Dashboard Demo](photo/cover_machine_sensor.png)](https://www.youtube.com/watch?v=EAPOjczOX-U)

**▶️ Click the image above to watch the interactive dashboard demo**

The demo showcases the dashboard's real-time machine monitoring capabilities, including dynamic sensor values, circular gauges, machine health classification, and color-coded status alerts.

---

## About This Project

This project was developed while working at **Sinzinet in South Korea** using the company's proprietary **BIX5 Business Intelligence platform**.

The dashboard was created as a **client-facing demonstration environment** to showcase BIX5's ability to support customized, real-time manufacturing dashboards using JavaScript and CSS.

Permission was granted by Sinzinet to publicly showcase this work.

> **Note:** The complete dashboard and production code are hosted within the BIX5 environment. This repository contains a partial implementation demonstrating the underlying dashboard logic and customization.

---

## Business Case

Manufacturing environments rely heavily on equipment monitoring to identify abnormal operating conditions and reduce the risk of production downtime.

The objective of this project was to simulate a **smart factory monitoring system** that allows managers to continuously monitor machine performance and quickly identify potential issues through real-time dashboard alerts.

The dashboard monitors **six independent machines** using four simulated sensor inputs:

* Operation Rate
* Production Rate
* Machine Temperature
* Internal Pressure

By combining these sensor readings into a machine-level health status, operators can quickly identify machines that may require attention without manually reviewing each individual metric.

---

## How It Works

Sensor values are dynamically generated using JavaScript and stored in a centralized `factoryData` object.

The data is refreshed every **five seconds**, allowing the dashboard to simulate a continuous stream of machine sensor data.

```text
Simulated Sensor Data
        ↓
   factoryData Object
        ↓
 factoryDataReady Event
        ↓
   Dashboard Widgets
        ↓
 Threshold-Based Logic
        ↓
Normal / Caution / Critical
```

### Machine Health Classification

Each machine is evaluated against defined operational thresholds.

Depending on the sensor conditions, the machine is classified as:

* 🟢 **Normal** — Operating within expected conditions
* 🟡 **Caution** — Sensor readings approaching defined limits
* 🔴 **Critical** — Sensor readings exceeding defined limits

The resulting status is communicated visually through color-coded dashboard indicators.

---

## Technical Implementation

The dashboard combines **JavaScript event-driven logic** with BIX5's widget framework.

Each visual component is connected to the centralized `factoryData` object. When new data becomes available, the `factoryDataReady` event triggers the widgets to refresh their displayed values.

### 1. Centralized Sensor Data

Sensor values for each machine are stored in a centralized data structure.

```javascript
const factoryData = {
    machine1: {
        sensor1: operationRate,
        sensor2: productionRate,
        sensor3: temperature,
        sensor4: pressure
    }
};
```

This structure allows multiple dashboard components to reference the same underlying sensor data.

### 2. Real-Time Data Updates

The dashboard periodically generates new sensor values to simulate real-time equipment monitoring.

```javascript
setInterval(() => {
    updateSensorData();
    dispatchFactoryDataReady();
}, 5000);
```

This allows the dashboard widgets to continuously refresh without requiring manual interaction.

### 3. Condition-Based Classification

Sensor values are evaluated against predefined thresholds to determine the machine's health state.

```javascript
if (sensorValue >= criticalThreshold) {
    status = "Critical";
} else if (sensorValue >= cautionThreshold) {
    status = "Caution";
} else {
    status = "Normal";
}
```

This logic transforms individual sensor measurements into an easily interpretable operational status.

### 4. Dynamic Dashboard Updates

Each widget listens for the `factoryDataReady` event and updates its visualization when new sensor data is available.

```javascript
document.addEventListener("factoryDataReady", () => {
    updateGauge();
    updateTable();
    updateMachineStatus();
});
```

This event-driven approach keeps the dashboard components synchronized with the latest sensor values.

---

## Dashboard Visualizations

Each machine is monitored through multiple visual components:

* **Table Views** — Display individual sensor values
* **Circular Gauges** — Provide quick visual assessment of sensor performance
* **Status Indicators** — Communicate overall machine health
* **Color-Coded Alerts** — Highlight abnormal operating conditions

Together, these components allow users to evaluate both **individual sensor performance** and **overall machine health** at a glance.

---

## Key Insights

The dashboard demonstrates how multiple independent sensor readings can be transformed into a single **machine-level health classification**.

Instead of manually reviewing temperature, pressure, production, and operation metrics separately, operators can use the dashboard's visual indicators to quickly identify machines that may require intervention.

Condition-based monitoring can support:

* Faster identification of abnormal equipment conditions
* Proactive maintenance planning
* Improved operational visibility
* Prioritization of equipment requiring intervention
* Reduced risk of unplanned downtime

---

## Technologies

![BIX5](https://img.shields.io/badge/BIX5-Business%20Intelligence-2F5597?style=for-the-badge)
![JavaScript](https://img.shields.io/badge/JavaScript-Data%20Logic-F7DF1E?style=for-the-badge\&logo=javascript\&logoColor=black)
![HTML](https://img.shields.io/badge/HTML-Dashboard%20Structure-E34F26?style=for-the-badge\&logo=html5\&logoColor=white)
![CSS](https://img.shields.io/badge/CSS-Dashboard%20Styling-1572B6?style=for-the-badge\&logo=css3\&logoColor=white)

<br>

![Git](https://img.shields.io/badge/Git-Version%20Control-F05032?style=for-the-badge\&logo=git\&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-Repository-181717?style=for-the-badge\&logo=github\&logoColor=white)

---

## Repository

The complete dashboard was developed and hosted within Sinzinet's **BIX5 environment**.

This repository contains a **partial code implementation** demonstrating the JavaScript logic used to generate sensor data, classify machine conditions, and update dashboard components.

---

## Project Context

This project demonstrates experience with:

* Business Intelligence dashboard development
* Real-time data visualization
* JavaScript-based event handling
* Condition-based monitoring logic
* Dashboard customization using CSS
* Translating raw sensor data into actionable visual indicators



