# ¿Cómo conseguir un mejor descanso? Análisis para la optimización del sueño

Proyecto final del posgrado en Analítica de Datos y Programación aplicada 
a las Ciencias Sociales (2022–2023). Análisis de métricas de sueño extraídas 
del smartwatch **Garmin Fenix 6X Pro** durante 237 días, con el informe 
generado en **R Markdown**.

## Pipeline ETL

Los datos se exportaron desde el portal de Garmin en formato JSON, 
distribuidos en tres archivos con variables de distinta estructura. 
El proceso de unificación implicó extraer variables anidadas, crear 
nuevas variables de tiempo de sueño, recodificar tipos de datos y 
eliminar valores nulos hasta obtener un dataset limpio y analizable.

## Análisis exploratorio

Se visualizó la evolución de la calidad del sueño en tres escalas 
temporales: diaria, semanal y mensual, complementado con calendarios 
de calor mes a mes que permiten identificar patrones y anomalías 
a lo largo del período de estudio.

## Análisis estadístico

Se aplicaron dos modelos de regresión lineal. El primero, usando únicamente 
las horas de sueño como predictor, explicaba solo el **19.3%** de la 
variabilidad en la calidad del sueño. Para mejorar este resultado se realizó 
un **análisis PCA** que redujo la dimensionalidad del dataset, y aplicando 
regresión lineal múltiple sobre los componentes seleccionados se alcanzó 
una capacidad explicativa del **89.1%**.

---

<br>

# 🇺🇸 English version

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
