---
title: "Análisis Exploratorio de Netflix"
date: 2025-08-21
---

# Análisis Exploratorio de Netflix

## Contexto
Se realizó un análisis exploratorio del dataset público de Netflix, que contiene información sobre películas y series.  
El objetivo fue conocer la estructura de los datos, identificar valores faltantes y obtener visualizaciones descriptivas.

## Objetivos
- Cargar y explorar el dataset de Netflix desde una fuente online.
- Identificar y cuantificar datos faltantes.
- Generar visualizaciones para entender la distribución de variables.

## Actividades (con tiempos estimados)
- Carga y exploración inicial del dataset — 15 min  
- Análisis de valores faltantes — 15 min  
- Visualizaciones exploratorias — 30 min  
- Síntesis de hallazgos — 30 min  

## Desarrollo
1. **Carga de datos**: se utilizó `pandas` para leer el CSV.  
2. **Exploración inicial**: con `shape`, `head`, `info` y `describe` se obtuvo un panorama general de las variables.  
3. **Detección de valores faltantes**: se consulto si hbaía datos faltantes por columna.  
4. **Visualizaciones**: con `matplotlib` y `seaborn` se graficó y se exploraron distribuciones de variables.  
5. **Hallazgos preliminares**: se detectaron columnas con muchos nulos y se confirmó que el dataset tiene más películas que series y que la mayor parte del contenido se concentra en los últimos 20 años.

## Evidencias
- Notebook del análisis: [analysis.ipynb](analysis.ipynb)  

##Reflexión
Aprendizaje: recordé funciones de pandas, matplotlib y seaborn y aprendí caracteristicas de EDA.
Próximos pasos: análisis con mayor profundidad, con datos actualizados y mayor cantidad de variables. 

##Conclusión
El análisis exploratorio me permitió validar el dataset de Netflix, con datos que nos permitieron trabajr y practicar (valores faltantes y variables confusas). Aun con esto, se 
identificaron tendencias como el crecimiento sostenido de producciones en las últimas dos décadas y el predominio de películas sobre series. Esta base abre la posibilidad a análisis más avanzados de contenido y estrategias de producción.

#Referencias 
Dataset: https://www.kaggle.com/shivamb/netflix-shows
https://pandas.pydata.org/docs/
https://seaborn.pydata.org/
