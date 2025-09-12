---
title: "Entrada 01 — Mi primera experiencia"
date: 2025-08-13
---

# Entrada 01 — Mi primera experiencia

## Contexto
Actividad inicial del curso en la cual trabajé con el dataset **Iris**.  
El objetivo fue practicar la carga de datos desde diferentes fuentes (GitHub, seaborn, sklearn, archivo local) y verificar la consistencia entre datasets y comenzar a responder preguntas simples con las especies de flores.  

Finalmente se trabajó con el dataset cargado desde CSV. Esto permitió ejercitar la carga, limpieza, exploración y visualización de un dataset real.

## Objetivos
- Familiarizarme con el trabajo del portafolio.
- Practicar carga y exploración de datos en Python.
- Plantear y responder preguntas básicas a partir de un dataset.

## Actividades (con tiempos estimados)
- Configurar entorno y repositorio — 30 min  
- Cargar dataset Iris desde distintas fuentes — 15 min  
- Formular y responder preguntas de negocio iniciales — 30 min  
- Documentar la experiencia en el portafolio — 30 min  


## Desarrollo

1. **Entorno:**  
   Se instalaron librerías y se configuró la estructura para guardar resultados.  Se importaron `pandas`, `numpy`, `matplotlib`, `seaborn` y `kagglehub`.

2. **Carga de datos:**  
   Se importó el dataset desde diferentes fuentes.  
   - `pd.read_csv(url)` cargó los datos de Netflix desde GitHub.  
   - Se verificó el número de filas y columnas con `df.shape`.  

3. **Detección de valores faltantes y outliers**  
   - Se hicieron algunos ajustes cuando se descubrieron valores anormales.
   - Valores faltantes → `df.isnull().sum()` y porcentaje sobre el total.  
   - Outliers → conversión de `release_year` a numérico con `pd.to_numeric` y revisión con `describe()`.  
  
   - Visualización con boxplots:
   - `results/entrega1/valores.png`   
   - `results/entrega1/outliers.png`  

4. **ANÁLISIS DE INFORMACIÓN POR CATEGORÍA**  
   * Se contaron las frecuencias de cada categoría  (`df['type'].value_counts()`).
   * Se visualizó lo mencionado y distribuciones por categoría:  
   - `results/entrega1/g.png`   
   * Se visualizaron tendencias temporales, conteo de estrenos por año (`value_counts().sort_index()`).
   - `results/entrega1/tem.png`  

5. **ANÁLISIS DE PAÍSES CON VISUALIZACIONES**  
   * Los 5 países con mayor contenido son:  
     United States 2609, India 838, United Kingdom 601, Canada 318, France 271  
   - `results/entrega1/gg.png`  
   * Los 5 ratings más comunes son:  
     TV-MA 2027, TV-14 1698, TV-PG 701, R 508, PG-13 286  
   - `results/entrega1/rat.png`  

   - Los resultados se graficaron con `matplotlib` y `seaborn`.

6. **Dashboard interactivo**  
    - Se calcularon totales (`len(df)`), cantidad de películas y series (`df[df['type']=='Movie']`).  
   - Se integraron en un tablero con `plt.subplots` para mostrar varias métricas juntas.
  
   - `results/entrega1/dash.png`
  
7. **Preguntas iniciales:**
   * ¿Cuál es la especie con pétalo más largo?  
   * ¿Existe relación entre el largo del sépalo y del pétalo?  
   * ¿Cuál es la especie con promedio de sépalo más ancho?  

8. **Se respondieron preguntas adicionales de negocio en el notebook.** 
   Para finalizar se respondieron preguntas de análisis más profundo, las cuales fueron anexadas en la entrada del código. Las mismas pueden verse allí mismo.

## Evidencias
- Notebook del análisis: [entrega_uno.ipynb](uno.ipynb)

## Reflexión
Lo más desafiante: cargar los datos desde distintas fuentes y formas que no conocía.  
Próximos pasos: avanzar hacia análisis más profundo (estadísticas comparativas por especie) y visualizaciones más avanzadas.  

## Conclusión
Esta primera práctica permitió reforzar conceptos básicos de manejo de datos en Python. El dataset Iris fue ideal para practicar carga, exploración y validación de datos.  

---------------------

