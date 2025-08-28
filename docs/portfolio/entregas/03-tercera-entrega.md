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

## Actividades 

* Carga y exploración inicial — 20 min
* Limpieza, normalización y verificación de joins — 20 min
* Análisis de valores faltantes — 10 min
* Visualizaciones y métricas — 25 min
* Conclusiones — 20 min

## Desarrollo

1. **Carga de datos**

   * Yellow Taxi: **3,066,766** filas, **19** columnas.
   * Zonas: **265** filas, **4** columnas.
   * Período observado en trips: **2008‑12‑31 23:01:42** a **2023‑02‑01 00:56:53**.

2. **Normalización y preparación**

   * Estandarización de variables en nombres de columnas (ej.: `PULocationID` → `pulocationid`).
   * Creación de `pickup_date` y verificación de tipos para joins.
   * Limpieza básica previa a joins.

3. **Integración (JOINS)**

   * **trips + zones**
   * **trips + zones + calendar**

4. **Verificamos los valores faltantes**

## Evidencias

* Notebook del análisis: **[03-tercera-entrega.ipynb](tres.ipynb)**

## Reflexión

* **Aprendizajes técnicos**: lectura directa de **Parquet** (mejor que CSV en tiempos y memoria), verificación de datos para evitar errores al hacer join y la utilidad del **LEFT JOIN** para conservar todos los viajes aunque falte la zona. 

* **Siguientes pasos**:

  * Incorporar dropoff zones y análisis origen‑destino.
  * Modelar demanda por franja horaria y borough. 
  * Posible incorporación de **tarifas dinámicas.

## Conclusión

El dataset está **completo** para las variables que analizamos y fue útil para aprender sobre parquet, tema desconocido hasta el momento. Ahora la base queda lista para profundizar en patrones origen‑destino o segmentación por zonas.

## Referencias

* pandas (documentación): [https://pandas.pydata.org/docs/](https://pandas.pydata.org/docs/)
* pyarrow / fastparquet 
