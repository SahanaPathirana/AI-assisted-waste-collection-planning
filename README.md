AI-Assisted Waste Collection & Resource Planning System

A portfolio project combining Business Analysis, Business Intelligence, ERP design, and Machine Learning - applied to municipal waste management.
Built across two degrees in Information Systems Engineering and Environmental Conservation and Management, this project addresses a real-world operational problem: municipal councils that follow fixed collection routes waste fuel, miss overflowing bins, and make decisions based on habit rather than data. This system replaces that with a data-driven, predictive planning approach.
The fictional council used throughout is Riverside Municipal Council, operating across five zones with distinct waste profiles over a 6-month period (January – June 2026).

What This Project Covers
Layer	What Was Built
Business Analysis	Stakeholder analysis, MoSCoW requirements, AS-IS and TO-BE BPMN swimlane diagrams, gap analysis
Business Intelligence	3-page Power BI dashboard - Executive Summary, Operational Insights, AI Predictions
ERP Design	5-module system design covering Vehicle, Employee, Route, Collection, and Reporting functions
AI / Machine Learning	Linear Regression waste forecasting + Random Forest overflow risk classifier + rule-based resource recommendations

Project Files
File	Description
waste_collection_data.csv	Synthetic dataset - 379 collection records across 5 areas, 6 months, 11 columns
waste_collection_dataset.xlsx	Same dataset with Data Dictionary and Scenario Notes sheets
Riverside_AI_Forecasting_Model.ipynb	Google Colab notebook - EDA, feature engineering, forecasting model, overflow classifier, predictions export
waste_predictions.csv	2 - week forward forecast output (June 16 –29, 2026) feeding the Power BI Page 3
BA_Deliverables_Riverside_Council.docx	Full BA document - stakeholders, requirements, BPMN diagrams, gap analysis
ERP_Module_Design_Riverside_Council.docx	ERP module design - 5 modules, integration map, end-to-end data flow

The Problem This Solves
Municipal waste councils typically operate like this:
Residents generate waste
        ↓
Council follows a fixed weekly route - same every week
        ↓
Truck visits every area on schedule regardless of fill level
        ↓
Some bins overflow. Some trucks visit half - empty areas.
No data is recorded. Cycle repeats.
The environmental cost: unnecessary truck trips burn fuel and produce emissions. Overflowing bins create public health and environmental hazards - both directly relevant to Environmental Conservation principles around waste minimization and resource efficiency.
The TO-BE system:
Historical collection data
        ↓
AI model forecasts waste volume + overflow risk per area
        ↓
System recommends optimized routes and resource allocation
        ↓
Supervisor reviews and approves
        ↓
Truck follows dynamic, risk - prioritized route
        ↓
Results logged automatically → feeds next prediction cycle

Dataset Design
The synthetic dataset was built with realistic patterns rather than random noise - so the AI model has genuine signals to learn from:
•	Market Square (Commercial) - highest waste generator, ~1,015 kg average per collection
•	Lakeview Residences (Residential, growing) - waste rises ~24% from January to June, simulating a developing neighbourhood
•	Riverside Heights (Residential, stable) - consistent baseline
•	Hillside Gardens (Suburban) - lowest waste generator
•	Greenfield Industrial Park (Industrial) - second highest overflow risk despite not being the highest waste generator
Built-in patterns the model learns:
•	Sinhala & Tamil New Year spike (Apr 10 – 17): ~50% waste increase, overflow rate jumps from 8% to 43%
•	Vesak period (May 1 - 3): ~20% increase
•	Saturday collections run ~18% heavier than weekday collections
•	Overflow risk is driven by waste load relative to workers assigned - not random
AI Model Results
Waste Forecasting - Linear Regression
Metric	Result
Mean Absolute Error	95.9 kg per collection run
R² Score	0.717
Top predictor	Festival period (+332 kg average)
Second predictor	Area type
Third predictor	Weekend (+134 kg average)
The model explains 71.7% of waste variation using only calendar features and area type - no sensors or IoT required.
Overflow Risk - Random Forest Classifier
Setting	Value
Algorithm	Random Forest (100 estimators)
Class weighting	Balanced - handles 10% minority overflow class
Top predictor	Waste collected (kg)
Second predictor	Days elapsed (growth trend)
Third predictor	Workers assigned
Note on model performance: With 379 rows and ~10% overflow rate, the test set contains only 8 overflow cases - too few for high recall on the minority class. The model's overflow probability scores (continuous, 0 – 1) are meaningful and used for the High/Medium/Low risk classification in the predictions output. This is a known and documented limitation; a larger real-world dataset would improve recall significantly.

How to Run the Notebook
1.	Open Google Colab
2.	File → Upload notebook → select Riverside_AI_Forecasting_Model.ipynb
3.	Upload waste_collection_data.csv using the folder icon in the left sidebar
4.	Run cells top to bottom using Shift+Enter
5.	After Step 9, download waste_predictions.csv from the Colab files panel
All libraries used (pandas, numpy, scikit-learn, matplotlib) are pre-installed in Google Colab - no pip install required.

Power BI Dashboard
The dashboard was built in Power BI Desktop (free) using waste_collection_data.csv as the primary source and waste_predictions.csv for the AI Predictions page.
Page 1 - Executive Summary
•	4 KPI cards: Total Waste Collected, Total Collection Runs, Total Fuel Used, Overflow Rate %
•	Donut chart: waste mix by area type (Commercial / Residential / Industrial / Suburban)
•	Line chart: monthly waste trend (Jan–Jun 2026) showing the April festival spike
•	Slicer: filter by area type
Page 2 - Operational Insights
•	Bar chart: total waste by area (Market Square leads at ~96K kg)
•	Bar chart: overflow rate by area (Greenfield Industrial Park leads at ~17%)
•	Table: truck performance - fuel per trip, collection time, total distance
•	Slicer: filter by area
Page 3 - AI Predictions (June 16–29, 2026)
•	Bar chart: predicted waste volume per area
•	Bar chart: predicted overflow probability per area
•	Table: recommended workers and trucks per area with risk level
•	KPI cards: total predicted waste and total workers recommended
Environmental Conservation Context
Waste management is one of the most direct intersections between urban operations and environmental impact. Fixed, inefficient collection routes contribute to:
•	Unnecessary fuel consumption and vehicle emissions from trucks visiting low-waste areas on schedule
•	Overflow incidents that create ground contamination and public health risks
•	Poor resource planning that prevents councils from scaling up during high-generation periods (festivals, seasonal events)
This project applies data-driven thinking to those problems - predicting where waste will accumulate before it overflows, and recommending the minimum resources needed to handle it. Fewer unnecessary trips means lower emissions. Better overflow prediction means fewer environmental incidents. These are measurable outcomes, not just operational efficiencies.

Skills Demonstrated
Business Analysis Requirements Engineering BPMN Process Mapping Gap Analysis Power BI DAX Data Modelling Python pandas scikit-learn Linear Regression Random Forest Feature Engineering ERP Design Data Visualization Synthetic Data Generation

Author
Sahana Pathirana BSc (Hons) in Information Technology, Specialized in Information Systems Engineering | BSc Environmental Conservation and Management
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue)](https://linkedin.com/in/sahana-pathirana-2036453a7)
[![Email](https://img.shields.io/badge/Email-Contact-green)](mailto:sana2003s0619@gmail.com)
