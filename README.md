# ¿Cómo conseguir un mejor descanso? Análisis para la optimización del sueño

Proyecto final del posgrado en Analítica de Datos y Programación aplicada 
a las Ciencias Sociales (2022–2023). Análisis estadístico y visual de 
métricas de sueño extraídas del smartwatch **Garmin Fenix 6X Pro** durante 
**237 días** (2022-06-15 / 2023-03-29).

El objetivo del proyecto no es realizar una investigación clínica, sino 
demostrar un flujo completo de **ETL, análisis estadístico y visualización 
de datos en R**, con el informe generado mediante **R Markdown + Knit**.

## Fuente de datos

Los datos biométricos se exportaron en formato **JSON** desde el portal de 
Garmin. El dataset original estaba dividido en **3 archivos** con hasta 
**20 variables** cada uno, agrupando métricas de fases del sueño 
(deep, light, REM, awake), biométricas (SPO2, frecuencia cardíaca, 
respiración, estrés) y puntuaciones de calidad del sueño (overallScore, 
qualityScore, recoveryScore, entre otras).

## Pipeline ETL

El proceso de unificación y depuración incluyó: merge de los 3 archivos, 
extracción de variables anidadas en listas mediante `cbind()`, creación de 
variables nuevas de tiempo total de sueño en minutos y horas, recodificación 
de tipos (fechas, factores, numéricos) y eliminación de NAs. El resultado 
fue un dataset de **200 observaciones y 30 variables**.

## Análisis exploratorio

Se generaron visualizaciones en distintas escalas temporales para estudiar 
el comportamiento de `overallScore`: un gráfico de dispersión por grupos de 
calidad del sueño (Pobre / Justo / Bueno / Excelente), un dashboard con 
líneas temporales diaria, semanal y mensual, y una serie de **calendarios 
de calor mensuales** con la puntuación escalada de 0 a 1.

## Análisis estadístico

**Regresión lineal simple:** se modeló la relación entre las horas totales 
de sueño (`totalsleepH`) y la puntuación global (`overallScore`), obteniendo 
un R²ajustado = **0.193**. El modelo es significativo (p < 0.05) pero 
explica solo el 19.3% de la variabilidad, lo que motivó un análisis más 
profundo.

**Análisis PCA:** se redujo la dimensionalidad del dataset (19 variables, 
200 observaciones) identificando **6 componentes principales** que acumulan 
el **83.16% de la varianza explicada**. Aplicando regresión lineal múltiple 
sobre estos 6 PC se alcanzó un R²ajustado = **0.891**, explicando el 89.1% 
de la variabilidad en `overallScore`.

---

<br>

# 🇺🇸 How to Get Better Rest? A Sleep Optimization Analysis

Final project for the postgraduate program in Data Analytics and Programming 
applied to Social Sciences (2022–2023). Statistical and visual analysis of 
sleep metrics extracted from a **Garmin Fenix 6X Pro** smartwatch over 
**237 days** (2022-06-15 / 2023-03-29).

The goal is not clinical research, but to demonstrate a complete 
**ETL, statistical analysis, and data visualization workflow in R**, 
with the report generated using **R Markdown + Knit**.

## Data Source

Biometric data was exported in **JSON format** from the Garmin portal. The 
original dataset was split into **3 files** with up to **20 variables** each, 
covering sleep phase metrics (deep, light, REM, awake), biometrics (SPO2, 
heart rate, respiration, stress), and sleep quality scores (overallScore, 
qualityScore, recoveryScore, among others).

## ETL Pipeline

The unification and cleaning process included: merging the 3 files, 
extracting nested list variables using `cbind()`, creating new variables 
for total sleep time in minutes and hours, recoding data types (dates, 
factors, numerics), and removing NAs. The result was a dataset of 
**200 observations and 30 variables**.

## Exploratory Analysis

Visualizations were generated at multiple time scales to study `overallScore` 
behaviour: a scatter plot by sleep quality groups (Poor / Fair / Good / 
Excellent), a dashboard with daily, weekly, and monthly time series, and a 
series of **monthly heat map calendars** with scores scaled from 0 to 1.

## Statistical Analysis

**Simple linear regression:** the relationship between total sleep hours 
(`totalsleepH`) and overall score (`overallScore`) was modelled, yielding 
an adjusted R² = **0.193**. The model is statistically significant (p < 0.05) 
but explains only 19.3% of variability, motivating a deeper analysis.

**PCA analysis:** dimensionality was reduced from a 19-variable, 
200-observation dataset, identifying **6 principal components** that 
account for **83.16% of cumulative explained variance**. Applying multiple 
linear regression on these 6 PCs achieved an adjusted R² = **0.891**, 
explaining 89.1% of the variability in `overallScore`.
