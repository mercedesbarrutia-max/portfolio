---
title: "Análisis de Comportamiento de Clientes con Temporal Features y PCA"
date: 2025-11-06
---

# Construcción de variables temporales y clasificación de clientes premium

## Contexto

En práctica se crearon variables temporales, se usó encoding categórico y reducción de dimensionalidad. Se simuló un dataset de transacciones comerciales para analizar el comportamiento de compra de distintos clientes y predecir cuáles pueden considerarse “premium”.

## Objetivos

- Generar variables temporales a partir de fechas de compra.  
- Agregar información a nivel cliente para identificar patrones de gasto.  
- Aplicar codificación categórica mixta (LabelEncoder + TargetEncoder).  
- Reducir dimensionalidad con PCA y clasificar clientes mediante Random Forest.  

## Actividades

- Generación de dataset simulado — 10 min  
- Feature engineering temporal — 15 min  
- Encoding y normalización — 20 min  
- Aplicación de PCA y clasificación — 20 min  

## Desarrollo

Se generaron 2000 órdenes correspondientes a 600 clientes en distintos países.  
Se derivaron variables como hora de compra, día de semana y mes.  
Luego se agregaron las transacciones por cliente, calculando indicadores como gasto total, gasto promedio, cantidad media y días de actividad.

Los países se codificaron mediante LabelEncoder y TargetEncoder, y las variables se estandarizaron antes de aplicar PCA (2 componentes), que explicó un 54.33 % de la varianza total.

Por último, se entrenó un modelo Random Forest para clasificar a los clientes en “premium” y “no premium".

## Evidencias

- Notebook: [tarea_extra_3.ipynb](../tareas_extras/tarea_extra_tres.ipynb)  
- Visualización de proyección PCA:  
  ![Clientes proyectados en PCA](../imagenes/extras/image.png)  

## Reflexión y Conclusión

Esta tarea integró los temas de encoding avanzado, análisis temporal y reducción de dimensionalidad.  
El uso de TargetEncoder y PCA permitió mejorar la representación de los datos y reducir complejidad sin pérdida de información.

El análisis demostró cómo distintas transformaciones contribuyen a mejorar el desempeño de los modelos y la comprensión de los datos.
