---
title: "Análisis Exploratorio de Netflix"
date: 2025-08-21
---

# Análisis Exploratorio de Netflix

## Contexto
Se realizó un análisis exploratorio del dataset público de Netflix, que contiene información sobre películas y series.  
El objetivo fue conocer la estructura de los datos, identificar valores faltantes y obtener visualizaciones descriptivas.

En el notebook de esta entrega se trabajó con el dataset **Iris**, cargado desde múltiples fuentes (CSV online, seaborn, sklearn y archivo subido). Esto sirvió para ejercitar la validación y consistencia de datasets, además del análisis principal de Netflix.

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
   > 🔧 **En código**:  
   - `pd.read_csv(url)` para Netflix.  
   - Para Iris se usaron:  
     - CSV desde GitHub (`iris.csv`).  
     - `sns.load_dataset("iris")`.  
     - `sklearn.datasets.load_iris(as_frame=True)`.  
     - `files.upload()` en Colab para archivo local.  

2. **Exploración inicial**: con `shape`, `head`, `info` y `describe` se obtuvo un panorama general de las variables.  
   > 🔧 **En código**:  
   - `df.shape` para dimensiones.  
   - `df.dtypes` y `df.isna().sum()` para tipos y valores faltantes.  
   - `df.describe(include="all").T` para estadísticos descriptivos.  

3. **Detección de valores faltantes**: se consultó si había datos faltantes por columna.  
   > 🔧 **En código**:  
   - `df.isnull().sum().sort_values(ascending=False)` para ranking de nulos.  

4. **Visualizaciones**: con `matplotlib` y `seaborn` se graficó y se exploraron distribuciones de variables.  
   > 🔧 **En código**:  
   - `sns.histplot`, `sns.countplot` y `sns.boxplot` para distribuciones.  
   - `df['species'].value_counts().plot(kind="bar")` para frecuencias de Iris.  

5. **Hallazgos preliminares**: se detectaron columnas con muchos nulos y se confirmó que el dataset tiene más películas que series y que la mayor parte del contenido se concentra en los últimos 20 años.  
   > 🔧 **En código**:  
   - Se verificó comparando `df['type'].value_counts()` en Netflix.  
   - Para Iris, se hicieron correlaciones numéricas con `df.corr()` y conversiones de tipo categórico (`astype('category')`).  

## Evidencias
- Notebook del análisis: [entrega_dos.ipynb](dos.ipynb)  

## Reflexión
Aprendizaje: recordé funciones de pandas, matplotlib y seaborn y aprendí características de EDPA.  
Próximos pasos: análisis con mayor profundidad, con datos actualizados y mayor cantidad de variables.  

## Conclusión
El análisis exploratorio me permitió validar el dataset de Netflix, con datos que nos permitieron trabajar y practicar (valores faltantes y variables confusas). Aun con esto, se identificaron tendencias como el crecimiento sostenido de producciones en las últimas dos décadas y el predominio de películas sobre series.  

> 🔧 **Nota técnica**: la práctica con Iris permitió comprobar la **equivalencia de datasets de distintas fuentes** (`df1.equals(df2)`, etc.) y reforzar el manejo de tipos de datos y correlaciones, algo que será útil en análisis más avanzados.

# Referencias 
Dataset: https://www.kaggle.com/shivamb/netflix-shows  
https://pandas.pydata.org/docs/  
https://seaborn.pydata.org/  
