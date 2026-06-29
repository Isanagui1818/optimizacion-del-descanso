**🌐 Idioma:** [English](README_en.md) · Español

# ¿Cómo descansar mejor? Un análisis de optimización del sueño

Proyecto final del posgrado en Análisis y Programación de Datos aplicado a las
Ciencias Sociales (2022–2023). Análisis de las métricas de sueño extraídas de
un reloj inteligente **Garmin Fenix 6X Pro** durante 237 días, con el informe
generado en **R Markdown**.

## Pipeline ETL

Los datos se exportaron del portal de Garmin en formato JSON repartidos en tres
ficheros con estructuras diferentes. El proceso de unificación incluyó la
extracción de variables anidadas, la creación de nuevas variables de tiempo de
sueño, la recodificación de tipos de datos y la eliminación de valores nulos
para obtener un dataset limpio y listo para el análisis.

## Análisis exploratorio

La calidad del sueño se visualizó en tres escalas temporales — diaria, semanal
y mensual —, complementadas con calendarios de mapa de calor mes a mes para
identificar patrones y anomalías a lo largo del periodo de estudio.

## Análisis estadístico

Se aplicaron dos modelos de regresión lineal. El primero, usando solo las horas
de sueño como predictor, explicaba apenas el **19,3 %** de la variabilidad de la
calidad del sueño. Para mejorarlo, se realizó un **análisis PCA** para reducir la
dimensionalidad y, aplicando una regresión lineal múltiple sobre las componentes
seleccionadas, se alcanzó una capacidad explicativa del **89,1 %**.

## Contenido del repositorio

| Fichero | Descripción |
|---|---|
| [`Proyecto final Garmin metricas sueño.R`](Proyecto%20final%20Garmin%20metricas%20sueño.R) | Script de R con el ETL completo, el EDA y el modelado estadístico |
| [`Informe final.Rmd`](Informe%20final.Rmd) | Código fuente en R Markdown del informe final |
| [`Proyecto final Rmarkdown.pdf`](Proyecto%20final%20Rmarkdown.pdf) | Informe final renderizado (PDF) |

## Stack

R · R Markdown · Regresión lineal · PCA · Limpieza de datos · Análisis exploratorio de datos · Garmin

## Aviso legal

Proyecto de portfolio personal basado en mis propios datos de sueño
autorregistrados. Compartido con fines educativos y de demostración.
