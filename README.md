# How to Get Better Rest? A Sleep Optimization Analysis

Final project for the postgraduate program in Data Analytics and Programming 
applied to Social Sciences (2022–2023). Analysis of sleep metrics extracted 
from a **Garmin Fenix 6X Pro** smartwatch over 237 days, with the report 
generated in **R Markdown**.

## ETL Pipeline

Data was exported from the Garmin portal in JSON format across three files 
with different structures. The unification process involved extracting nested 
variables, creating new sleep time variables, recoding data types, and 
removing null values to produce a clean, analysis-ready dataset.

## Exploratory Analysis

Sleep quality was visualised across three time scales — daily, weekly, and 
monthly — complemented by month-by-month heat map calendars to identify 
patterns and anomalies throughout the study period.

## Statistical Analysis

Two linear regression models were applied. The first, using only sleep hours 
as a predictor, explained just **19.3%** of the variability in sleep quality. 
To improve this, a **PCA analysis** was performed to reduce dimensionality, 
and applying multiple linear regression on the selected components achieved 
an explanatory capacity of **89.1%**.
