---
title: "PCA y Selección de Features: Reducción de Dimensionalidad y Relevancia de Variables"
date: 2025-11-03
---

# Análisis de componentes principales y selección de variables relevantes

## Contexto

En esta práctica se exploraron técnicas de reducción de dimensionalidad y selección de variables, fundamentales para optimizar modelos y mejorar la interpretabilidad.  
Se trabajó con un dataset numérico multivariable, aplicando Feature Importance, SelectKBest y PCA (Principal Component Analysis) para identificar las variables más influyentes y evaluar cómo se puede conservar la mayor cantidad de información con menos dimensiones.

## Objetivos

- Comprender la importancia de la reducción de dimensionalidad.  
- Calcular la relevancia de variables mediante métricas estadísticas y modelos.  
- Aplicar SelectKBest y RandomForest Feature Importance.  
- Implementar y analizar PCA con distintas cantidades de componentes.  
- Evaluar la pérdida de información y la varianza explicada.  
- Visualizar relaciones entre variables originales y componentes principales.

## Actividades

- Carga y exploración del dataset — 10 min  
- Selección de features mediante importancia y correlaciones — 20 min  
- Aplicación de SelectKBest y Feature Importance — 25 min  
- Reducción de dimensionalidad con PCA — 25 min  
- Visualización de componentes y análisis de varianza — 20 min  

## Desarrollo

### 1. Exploración del dataset

Se cargó el dataset y se realizó una consulta de variables numéricas.  
Se calcularon estadísticas descriptivas y se observaron correlaciones entre columnas para detectar redundancia de información.  
Posteriormente, se estandarizaron las variables para garantizar que PCA no se viera afectado por escalas distintas.

### 2. Selección de variables mediante importancia

Se aplicaron dos enfoques complementarios:

- SelectKBest: se utilizaron pruebas estadísticas para seleccionar las variables con mayor poder explicativo respecto al target.  
- Random Forest Feature Importance: se entrenó un modelo que permitió obtener una medida empírica de importancia de cada feature.  

Ambos métodos coincidieron en destacar las variables de mayor correlación con el objetivo, confirmando la validez del criterio.

### 3. Reducción de dimensionalidad con PCA

Se implementó Análisis de Componentes Principales (PCA) sobre el conjunto de variables estandarizadas.  
Los pasos fueron:

- Cálculo de componentes principales con sklearn.decomposition.PCA.  
- Análisis de la varianza explicada acumulada.  
- Visualización del gráfico de codo para determinar el número óptimo de componentes.

El PCA mostró que con 3 componentes se retenía aproximadamente el 90 % de la varianza total, reduciendo significativamente la dimensionalidad sin pérdida notable de información.

### 4. Visualización y análisis

Se graficaron los dos primeros componentes principales, mostrando agrupaciones en los datos.   También se generó una matriz de carga para interpretar qué variables contribuían más a cada componente.

### 5. Conclusiones intermedias

- PCA es útil para eliminar redundancias y acelerar modelos con muchas variables correlacionadas.  
- SelectKBest permite una selección más directa y estadísticamente fundamentada.  
- Feature Importance aporta una perspectiva basada en desempeño predictivo.  
En conjunto, estas herramientas ayudan a decidir qué variables conservar según el objetivo del análisis.

## Evidencias

- Notebook del trabajo: [entrega_diez.ipynb](../tareas_obligatorias/diezz.ipynb)  
- Visualizaciones:  
  ![Varianza explicada por PCA](../imagenes/UT3/diez/foto1.png)  
  ![Componentes principales](../imagenes/UT3/diez/foto2.png)

## Reflexión

Aprendí a aplicar PCA y comparar distintos métodos de selección de variables.  
Comprendí que reducir dimensiones no solo mejora la eficiencia del modelo, sino que también ayuda a interpretar mejor los patrones subyacentes.  
PCA es especialmente valioso en datasets grandes o con variables correlacionadas.

## Conclusión

El uso de Feature Selection y PCA permite equilibrar simplicidad y rendimiento en los modelos.  
A través de esta práctica, se reforzó la comprensión del valor de la reducción de dimensionalidad como herramienta para mejorar tanto la interpretabilidad como la eficiencia del análisis de datos.

## Referencias

- [Scikit-learn: PCA](https://scikit-learn.org/stable/modules/generated/sklearn.decomposition.PCA.html)  
- [Scikit-learn: Feature Selection](https://scikit-learn.org/stable/modules/feature_selection.html)  