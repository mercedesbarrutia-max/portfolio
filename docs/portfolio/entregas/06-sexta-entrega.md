---
title: "Feature Scaling & Anti-Leakage Pipeline"
date: 2025-09-24
---


# Normalización inteligente: escalado de features y anti-leakage en Ames Housing

## Contexto
Esta entrega continúa el trabajo de la práctica anterior, centrada en la preparación del dataset Ames Housing.  
El foco estuvo en normalizar variables numéricas, entender cómo distintas estrategias de escalado afectan a los modelos y prevenir errores comunes como el data leakage.

---

## Objetivos

* Identificar cuáles features del dataset Ames necesitan escalado y por qué
* Experimentar con MinMaxScaler, StandardScaler y RobustScaler en datos reales
* Descubrir el impacto del escalado en diferentes algoritmos mediante experimentación
* Comparar pipelines con y sin data leakage para ver las diferencias
* Decidir cuál es la mejor estrategia basándose en evidencia empírica


## Actividades

* Identificar Variables Problemáticas — 10 min  
* Preparar Datos para Experimentar con Scalers — 10 min  
* Analizar outliers y transformaciones — 10 min  
* Log Transform para Distribuciones Sesgadas — 10 min  
* Investigación Independiente — 30 min  

## Desarrollo

### 1. Identificación de variables
Se seleccionaron variables numéricas con distinta escala (`LotArea`, `SalePrice`, `GrLivArea`, etc.), comprobando su rango y distribución.

### 2. Aplicación de distintos scalers
- **StandardScaler**: centró y normalizó los datos, adecuado para distribuciones normales.  
- **MinMaxScaler**: útil para modelos basados en distancia.  
- **RobustScaler**: más resistente a outliers.  

Los resultados mostraron que `RobustScaler` preserva mejor la estabilidad frente a outliers.

### 3. Prevención de data leakage
El escalado se aplicó solo al set de entrenamiento, manteniendo los parámetros de `fit()` para transformar validación y test.

### 4. Validación y comparación
Se compararon distribuciones antes y después del escalado.  
El pipeline con `StandardScaler` y `RobustScaler` resultó más estable y reproducible.

---

## Evidencias
* Notebook: **[06 - Feature Scaling Pipeline.ipynb](cinco.ipynb)**  
* Gráficos: `results/entregacinco.png`, `results/entregacincodos.png`

---
## Resultados

MIS HALLAZGOS:
Columna más problemática: Misc Val (también Total Bsmt SF por tener muchos ceros)
Ratio más alto: Lot Area ≈ 165 (sin contar ratios infinitos por ceros)
¿Por qué es problemático?: 
- Misc Val y Total Bsmt SF tienen muchos ceros → ratio infinito y distribución muy sesgada.
- Lot Area presenta outliers extremos de terrenos gigantes, lo que genera un ratio muy alto.
- Estas escalas y outliers distorsionan algoritmos basados en distancia (KNN, SVM).

ROUND 1: DATOS ORIGINALES
IQR originales: 127
Z-score originales: 29
⚡ ROUND 2: DESPUÉS DEL ESCALADO
           Scaler  IQR  Z-Score
0  StandardScaler  127       29
1    MinMaxScaler  127       29
2    RobustScaler  127       29

CONCLUSIONES:
- StandardScaler mantiene proporciones, así que detecta los mismos outliers.
- MinMaxScaler no cambia el orden relativo, pero comprime al [0,1], los outliers extremos suelen seguir siendo visibles.
- RobustScaler usa mediana y IQR, así que reduce la influencia de outliers → algunos 'desaparecen'.

Luego de aplicar box-cox (ver tarea extra numero cuatro para mayor entendimiento):
`results/entregaextracuatro.png`

---

## Reflexión
El preprocesamiento no es una tarea trivial: cada scaler implica una decisión que puede alterar el modelo.  
Esta práctica reforzó la importancia de mantener una estructura reproducible y ética en el tratamiento de datos, donde cada transformación debe justificarse.

---

## Conclusión
El pipeline final integra escalado, imputación y codificación de manera ordenada, asegurando consistencia.
