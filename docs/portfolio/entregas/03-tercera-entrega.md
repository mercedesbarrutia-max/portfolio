---

title: "Análisis Exploratorio — Archivo Tres (NYC Yellow Taxi)"
date: 2025-08-27
----------------

# Análisis Exploratorio — Archivo tres (NYC Yellow Taxi)

## Contexto

Se realizó un análisis sobre el dataset **Yellow Taxi** de NYC, integrándolo con el mapa de zonas de taxis y un calendario de eventos. El foco estuvo en validar la calidad de los datos, preparar datos para joins y obtener vistas descriptivas útiles para luego contestar preguntas.

## Objetivos

* Cargar el dataset principal en formato **Parquet** y auxiliares (zonas, calendario).
* Normalizar nombres/tipos y **verificar datos** para joins.
* Identificar y cuantificar **valores faltantes** en columnas clave.
* Generar métricas descriptivas (horarios, correlaciones, cobertura de zonas).
* Experimentar con **Prefect**
  
## Actividades 

* Carga y exploración inicial — 20 min
* Limpieza, normalización y verificación de joins — 20 min
* Análisis de valores faltantes — 10 min
* Visualizaciones y métricas — 25 min
* Conclusiones — 20 min

## Desarrollo

1. **Carga de datos**

   - `pd.read_parquet(url)` para viajes (`trips`).  
   - `pd.read_csv()` para zonas.  
   - Calendario cargado como DataFrame auxiliar.  
  
   * Yellow Taxi: **3,066,766** filas, **19** columnas.
   * Zonas: **265** filas, **4** columnas.
   * Período observado en trips: **2008‑12‑31 23:01:42** a **2023‑02‑01 00:56:53**.

2. **Normalización y preparación**

   * Estandarización de variables en nombres de columnas (ej.: `PULocationID` → `pulocationid`) usando:
   trips.columns = trips.columns.str.lower()
   zones.columns = zones.columns.str.lower()
   * Creación de `pickup_date` y verificación de tipos para joins.
   * Limpieza básica previa a joins usando:
   trips = trips.dropna()
   zones['borough'] = zones['borough'].fillna('Desconocido')

1. **Integración (JOINS)**
   
   * **trips + zones** por `pulocationid`.  
   * **trips + zones + calendar** por `pickup_date`. 

2. **Análisis descriptivo y correlaciones**
    
   * Agregado por borough (`groupby`).  
   * Comparación de días normales vs días especiales (`is_special_day`).
   * Correlaciones entre variables numéricas clave: `trip_distance`, `total_amount`, `fare_amount`, `tip_amount`.  
   * Visualización con heatmap de seaborn.
  
3. **Se respondieron preguntas adicionales en el notebook.** 
   Para finalizar se respondieron preguntas de análisis más profundo, las cuales fueron anexadas en la entrada del código. Las mismas pueden verse allí mismo.

## Evidencias

* Notebook del análisis: **[03-tercera-entrega.ipynb](tres.ipynb)**

## Reflexión

* **Aprendizajes**:
  - Lectura directa de **Parquet** (mucho más eficiente que CSV).  
  - Normalización previa evita errores en joins.  
  - El **LEFT JOIN** permite conservar todos los viajes, incluso sin zona.  
  - Prefect facilita reintentos y estructuración del pipeline.  
  
* **Siguientes pasos**:
  - Incorporar dropoff zones y análisis origen‑destino.
  - Modelar demanda por franja horaria y borough. 
  - Posible incorporación de **tarifas dinámicas.

## Conclusión

El dataset está **completo** para las variables que analizamos y fue útil para aprender sobre parquet, tema desconocido hasta el momento. Ahora la base queda lista para profundizar en patrones origen‑destino o segmentación por zonas.

## Referencias

* pandas (documentación): [https://pandas.pydata.org/docs/](https://pandas.pydata.org/docs/)  
* pyarrow / fastparquet  
* Prefect: [https://docs.prefect.io](https://docs.prefect.io)  
