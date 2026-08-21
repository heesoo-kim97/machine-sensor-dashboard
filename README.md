# Machine Sensor Dashboard

**Real-Time Manufacturing Monitoring Dashboard | BIX5, JavaScript, CSS**

## About This Project

### Business Case

While working at **Sinzinet in South Korea**, I developed this project using the company's proprietary **BIX5 Business Intelligence platform** as part of a client-facing dashboard demonstration environment.

Manufacturing environments rely heavily on equipment monitoring to identify abnormal operating conditions and reduce the risk of production downtime. The objective of this project was to simulate a **smart factory monitoring system** that allows managers to continuously track machine performance and quickly identify potential issues through real-time dashboard alerts.

Permission was granted by Sinzinet to publicly showcase this work.

> **Note:** The complete dashboard and production code are hosted within the BIX5 environment. This repository contains a partial code implementation demonstrating the underlying dashboard logic.

## How It Works

The dashboard monitors **six independent machines** using four simulated sensor inputs:

* Operation Rate
* Production Rate
* Machine Temperature
* Internal Pressure

Sensor values are dynamically generated using JavaScript and stored in a centralized `factoryData` object that updates every five seconds.

Each dashboard widget listens for a `factoryDataReady` event and updates its displayed values when new sensor data becomes available.

### Machine Health Classification

Condition-based logic evaluates each sensor against defined operational thresholds and classifies machine health into three states:

* 🟢 **Normal**
* 🟡 **Caution**
* 🔴 **Critical**

This allows operators to quickly identify machines that require attention without manually reviewing every individual sensor reading.

## Technical Implementation

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

JavaScript is responsible for:

* Generating dynamic sensor values
* Updating the centralized `factoryData` object
* Triggering dashboard updates
* Evaluating sensor thresholds
* Classifying machine health
* Updating visual status indicators

CSS customization is applied at the widget level to control dashboard styling and visually communicate machine conditions.

## Dashboard Visualizations

Each machine is monitored through:

* **Table views** for detailed sensor values
* **Circular gauges** for visual performance monitoring
* **Color-coded alerts** for machine health status

The visual components update dynamically as new sensor values are generated, allowing users to view both individual sensor performance and overall machine health at a glance.

## Key Insights

The dashboard demonstrates how multiple independent sensor readings can be aggregated into a single **machine-level health classification**.

Instead of requiring operators to manually review temperature, pressure, production, and operation metrics separately, the dashboard provides an immediate visual indication of which machines may require attention.

Condition-based monitoring can support:

* Faster identification of abnormal equipment conditions
* Proactive maintenance planning
* Improved operational visibility
* Reduced risk of unplanned downtime

## Technologies

* **BIX5** — Business Intelligence & Dashboard Platform
* **JavaScript** — Data generation, event handling, and monitoring logic
* **CSS** — Dashboard styling and visual customization
* **HTML** — Dashboard structure

