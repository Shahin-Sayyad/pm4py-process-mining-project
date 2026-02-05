# pm4py-process-mining-project
Process Mining project using PM4Py to discover, analyze, and optimize business processes from event logs. Includes process discovery, performance analysis, bottleneck detection, and visualization using Petri Nets and DFG.

📊 Process Mining using PM4Py
🚀 Order Management Process Analysis & Optimization
✅ Project Overview

This project demonstrates Process Mining using the PM4Py (Process Mining for Python) library to analyze business process event logs and discover the real execution flow of processes.

The project focuses on:

✅ Discovering actual process flow from system logs
✅ Visualizing process behavior using Petri Nets and DFG
✅ Identifying bottlenecks and delays
✅ Performing performance analysis
✅ Exporting process models for further analysis

📌 Main Idea

Process Mining helps organizations understand how processes actually run in reality instead of how they are assumed to run.

🎯 Project Objectives

Understand event log structure

Convert raw data into PM4Py event log format

Discover process models automatically

Analyze performance and delays

Detect bottlenecks

Provide process improvement insights

🏢 Real-World Use Case

In real business environments such as e-commerce or banking:

Expected Process:

Order Received → Payment Done → Order Shipped


Actual Process (from logs):

Order Received → Payment Done → Payment Recheck → Order Shipped


Process Mining helps detect these hidden steps and inefficiencies automatically.

📁 Dataset Description

The dataset is an event log containing process execution history.

Each record includes:

Column	Description
case_id	Unique process instance (Order ID)
activity	Activity performed
timestamp	Time of activity execution
Example
case_id	activity	timestamp
1	Order Received	2024-01-01 10:00
1	Payment Done	2024-01-01 10:05
1	Order Shipped	2024-01-01 12:00
🛠 Technologies Used

Python

PM4Py

Pandas

Graphviz

Jupyter Notebook

⚙ Project Architecture
Event Log (CSV)
        ↓
Data Preprocessing
        ↓
PM4Py Event Log Conversion
        ↓
Process Discovery (Inductive Miner)
        ↓
Petri Net Visualization
        ↓
Performance Analysis
        ↓
Bottleneck Detection

🔍 Methodology
1️⃣ Data Loading

Event log data is loaded using Pandas for preprocessing.

2️⃣ Event Log Formatting

Data is converted into PM4Py compatible format using:

case_id

activity

timestamp

3️⃣ Process Discovery

The Inductive Miner algorithm automatically discovers the process model.

4️⃣ Process Visualization

Two main visualizations are generated:

✅ Petri Net – shows process logic and flow
✅ Directly-Follows Graph (DFG) – shows activity sequence

5️⃣ Performance Analysis

Performance DFG is used to measure:

Time between activities

Waiting time

Process delays

🚧 Bottleneck Detection

A bottleneck is a step where process execution slows down.

Example:

Payment Done → (2 hours delay) → Shipping


This indicates inefficiency in the shipping preparation step.

📈 Results & Insights

Process flow discovered automatically

Activity sequence identified

Delays between activities detected

Inefficient steps highlighted

Process model exported as PNML

🧠 Key Concepts
Process Mining

Analyzing event logs to discover and improve processes.

Event Log

A record of activities executed in a process.

Process Discovery

Automatic creation of process model from logs.

Petri Net

Graphical representation of process flow.

DFG (Directly-Follows Graph)

Shows activity transitions and frequency.

Bottleneck

A step causing maximum delay in the process.

🏭 Industry Applications

Process Mining is used in:

Banking (Loan approval processes)

Healthcare (Patient flow analysis)

E-commerce (Order lifecycle analysis)

Manufacturing (Production monitoring)

Customer Support (Ticket analysis)

Industry tools include:

Celonis

SAP Signavio

UiPath Process Mining

PM4Py

▶️ Installation
pip install pm4py pandas graphviz


Install Graphviz separately:

https://graphviz.org/download/

▶️ Project Execution
import pandas as pd
import pm4py

df = pd.read_csv("order_event_log.csv")

log = pm4py.format_dataframe(
    df,
    case_id="case_id",
    activity_key="activity",
    timestamp_key="timestamp"
)

net, im, fm = pm4py.discover_petri_net_inductive(log)
pm4py.view_petri_net(net, im, fm)

📦 Output

Petri Net visualization

Directly-Follows Graph

Performance analysis graph

PNML process model file

🏁 Conclusion

This project demonstrates how process mining converts raw system logs into actionable business insights. It helps organizations improve efficiency, reduce delays, and make data-driven decisions.

👨‍💻 Author

Shahin Sayyad
Python Developer | Data Science Enthusiast
GitHub: https://github.com/Shahin-Sayyad
