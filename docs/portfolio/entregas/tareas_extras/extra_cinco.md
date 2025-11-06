---
title: "Encoding y Feature Engineering con el Dataset Titanic"
date: 2025-11-03
---

# Aplicación de codificación de variables y creación de features derivadas

## Contexto

En esta tarea se aplicaron técnicas de codificación categórica y creación de variables usando el clásico dataset **Titanic**.  
El objetivo fue preparar los datos para un modelo predictivo de supervivencia, explorando el uso de variables mixtas, transformaciones numéricas y estrategias de encoding combinadas.

## Objetivos

- Practicar la aplicación de LabelEncoder y OneHotEncoder.  
- Crear nuevas features basadas en variables originales.  
- Integrar transformación logarítmica y agrupación de edades.  
- Evaluar el rendimiento del modelo con las variables transformadas.  

## Actividades

- Carga y limpieza de datos — 5 min  
- Feature engineering — 15 min  
- Codificación categórica — 15 min  
- Entrenamiento y evaluación del modelo — 10 min  

## Desarrollo

Se utilizó el dataset `sns.load_dataset("titanic")` de Seaborn.  
Tras eliminar filas con valores faltantes relevantes, se seleccionaron las columnas: `sex`, `age`, `fare`, `embarked`, `class`, `alone`, `survived`.

Se realizaron las siguientes transformaciones:

- Creación de la variable `age_group` (niño, adolescente, adulto, maduro, mayor).  
- Transformación logarítmica de `fare`  a `fare_log`.  
- Aplicación de OneHotEncoder a variables categóricas y estandarización de las numéricas.

El modelo de clasificación **Random Forest** alcanzó un accuracy de **0.784**, utilizando 12 variables después del encoding.

## Evidencias

- Notebook: [tarea_extra_1.ipynb](../tareas_extras/extra_cinco.ipynb)  

## Reflexión

La práctica me permitió reforzar el proceso de preparación de datos mixtos para clasificación. Además, de comprobar la utilidad de transformar distribuciones sesgadas.  

## Conclusión

Combinar feature engineering con encoding mejora la interpretabilidad y el rendimiento de los modelos de clasificación. El uso de esta técnica permite obtener resultados sólidos en problemas de predicción binaria.
