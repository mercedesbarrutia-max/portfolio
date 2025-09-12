---
title: "Entrada 01 — Mi primera experiencia"
date: 2025-08-13
---

# Entrada 01 — Mi primera experiencia

## Contexto
Actividad inicial del curso en la cual trabajé con el dataset **Iris**.  
El objetivo fue practicar la carga de datos desde diferentes fuentes (GitHub, seaborn, sklearn, archivo local) y verificar la consistencia entre datasets, además de responder preguntas simples sobre especies de flores.

Finalmente se trabajó con el dataset cargado desde CSV. Esto permitió ejercitar la carga, limpieza, exploración y visualización de un dataset real.

## Objetivos
- Familiarizarme con el trabajo del portafolio.
- Practicar carga y exploración de datos en Python.
- Plantear y responder preguntas básicas a partir de un dataset.

## Actividades (con tiempos estimados)
- Configurar entorno y repositorio — 30 min  
- Cargar dataset Iris desde distintas fuentes — 15 min  
- Formular y responder preguntas de negocio iniciales — 20 min  
- Documentar la experiencia en el portafolio — 20 min  


## Desarrollo

1. **Entorno**  
   Se instalaron librerías y se configuró la estructura para guardar resultados. Se importaron `pandas`, `numpy`, `seaborn`, `matplotlib`.  

2. **Carga de datos**  
   Se importó el dataset Iris desde cuatro fuentes distintas.   
   - CSV en GitHub → `pd.read_csv(url)`.  
   - Dataset de seaborn → `sns.load_dataset("iris")`.  
   - Dataset de sklearn → `load_iris(as_frame=True)`.  
   - Archivo local → `files.upload()` en Colab.  
   - Se compararon los dataframes con `df1.equals(df2)` para comprobar consistencia.  

2. **Detección de valores faltantes y outliers**  
   - Valores faltantes: `df.isna().sum()`.  
   - Exploración con `describe()`, histogramas y boxplots.  
   - Frecuencias → `df["species"].value_counts()`.  
 
3. **Se buscaron las correlaciones numéricas**
   Con `df.corr()` y conversiones categóricas (`astype('category')`). 

4. **Preguntas iniciales:**
   * ¿Cuál es la especie con pétalo más largo?  
   * ¿Existe relación entre el largo del sépalo y del pétalo?  
   * ¿Cuál es la especie con promedio de sépalo más ancho?  

5.  **Se respondieron preguntas adicionales de negocio en el notebook.** 
   Para finalizar se respondieron preguntas de análisis más profundo, las cuales fueron anexadas en la entrada del código. Las mismas pueden verse allí mismo.

## Evidencias
- Notebook del análisis: [entrega_uno.ipynb](uno.ipynb)

## Reflexión
Lo más desafiante: cargar los datos desde distintas fuentes y formas que no conocía.  
Próximos pasos: avanzar hacia análisis más profundo (estadísticas comparativas por especie) y visualizaciones más avanzadas.  

## Conclusión
Esta primera práctica permitió reforzar conceptos básicos de manejo de datos en Python. El dataset Iris fue ideal para practicar carga, exploración y validación de datos.  

---------------------

