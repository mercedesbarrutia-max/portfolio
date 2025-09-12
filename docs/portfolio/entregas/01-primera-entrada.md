---
title: "Entrada 01 — Mi primera experiencia"
date: 2025-08-13
---

# Entrada 01 — Mi primera experiencia

## Contexto
Actividad inicial del curso en la cual trabajé con el dataset **Iris**.
El objetivo fue practicar la carga de datos desde diferentes fuentes (GitHub, seaborn, sklearn, archivo local) y verificar la consistencia entre datasets y comenzar a responder preguntas simples con las especies de flores. 

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

1. **Entorno:** se instalaron librerías y se configuró la estructura para guardar resultados.  

2. **Carga de datos:** se importó el dataset Iris desde cuatro fuentes distintas:

   * CSV en GitHub.
   * Dataset de seaborn.
   * Dataset de sklearn (`load_iris`).
   * Archivo subido manualmente.  

   Se verificó que las distintas fuentes entregan la misma información.  
  
3. **Deteccion de valores faltantes y outliers**

   - `results/entrega1/valores.png`   
   - `results/entrega1/outliers.png` 
  

4. **ANÁLISIS DE INFORMACIÓN POR CATEGORÍA** 
   * Se contaron las frecuencias de cada categoría
   * Se visualizó lo mencionado y distribuciones por categoría:
   - `results/entrega1/g.png` 
   * Se visualizaron tendencias temporales:
   - `results/entrega1/tem.png` 
 
5. **ANÁLISIS DE PAÍSES CON VISUALIZACIONES**
   * Los 5 países con mayor contenido son:
   United States     2609
   India              838
   United Kingdom     601
   Canada             318
   France             271
   - `results/entrega1/gg.png`
   * Los 5 ratings más comunes son:
   TV-MA    2027
   TV-14    1698
   TV-PG     701
   R         508
   PG-13     286
   - `results/entrega1/rat.png`
    
6. **Dashboard interactivo**
   - `results/entrega1/dash.png`

7. **Preguntas iniciales:**

   * ¿Cuál es la especie con pétalo más largo?
   * ¿Existe relación entre el largo del sépalo y del pétalo?
   * ¿Cuál es la especie con promedio de sépalo más ancho?  

8. **Para finalizar se respondieron preguntas de análisis más profundo, las cuales fueron anexadas en la entrada del código. Las mismas pueden verse allí mismo.**

## Evidencias
   - Notebook del análisis: [entrega_uno.ipynb](uno.ipynb)


## Reflexión
Lo más desafiante: cargar los datos desde distintas fuentes y formas que no conocía.
Próximos pasos: avanzar hacia análisis más profundo (estadísticas comparativas por especie) y visualizaciones más avanzadas.

## Conclusión
Esta primera práctica permitió reforzar conceptos básicos de manejo de datos en Python. El dataset Iris fue ideal para practicar carga, exploración y validación de datos.

