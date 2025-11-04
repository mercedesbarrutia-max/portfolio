---
title: "Entrega de ejercicio machine learning"
---

# Tarea extra 01 — Regresión y clasificación 

## Contexto
En otra materia de mi carrea llamada machine learning nos proponen desafíos que se relacionan con temáticas enseñadas en el curso de Ingeniería de datos. Por esto, decidí incluir mi trabajo en este portfolio como tarea extra.

## Objetivos

Propósito: Integrar exploración de datos, modelado supervisado y toma de decisiones clínicas con el dataset **Heart Disease (Cleveland)** de UCI.
El objetivo es predecir la presencia de enfermedad cardíaca** y proponer una estrategia de priorización de pacientes.

## Datos y variable objetivo

- Dataset: **Heart Disease (Cleveland)** (clase binaria: `target` = 1 presencia de enfermedad; 0 ausencia).
  
- **Preprocesamiento mínimo esperado**:
  * Revisión de valores faltantes y outliers.
  * Correlación de variables.
  * Codificación de variables categóricas (one-hot o tratamiento ordinal justificado).
  * Estandarización para modelos lineales/regularizados.
  * Partición train/test (p. ej., 70/30) 

---

## Modelo lineal (Regresión Logística)

**Tareas**

1. Entrenar un modelo lineal para clasificación (Regresión Logística).
2. Significancia estadística:
   - Reportar coeficientes, errores estándar y p-values.
   - Interpretar el signo y magnitud .
3. Regularización:
   - Investigue cómo es la regularización en modelos lineales. Explique con sus palabras.
   - Comparar L2 (Ridge), L1 (Lasso) y Elastic Net con validación cruzada.
   - Discutir cuáles variables parecen relevantes.

**Salidas**

- Métricas en test: accuracy, precision, recall, F1, AUC-ROC, AUC-PR.
- Tabla de coeficientes (modelo sin regularizar vs. mejor regularizado).

---

## Árbol de decisión

**Tareas**

1. Entrenar un **Decision Tree Classifier** optimizando hiperparámetros clave mediante **GridSearchCV** o **RandomizedSearchCV**:
   - `max_depth`, `min_samples_split`, `min_samples_leaf`, `max_features`, `ccp_alpha`.
  
2. Reportar importancias de variables y reglas del árbol final:
   - Extraer rutas de decisión.
  
3. Analizar complejidad vs. generalización: mostrar el efecto de `max_depth` (o `ccp_alpha`) en desempeño de validación.

**Salidas**

- Métricas en test.
- Gráfico: desempeño vs. `max_depth`

---

## Random Forest

**Tareas**

1. Entrenar un Random Forest Classifier optimizando hiperparámetros con GridSearchCV o RandomizedSearchCV:
   - `n_estimators`, `max_features`, `max_depth`, `min_samples_leaf`, `min_samples_split`, `bootstrap`.
  
2. Importancias de variables:
   - Investigar sobre importancia de variables en RF.
   - Reportar Gini importance y, si es posible, Permutation Importance (sobre test o CV) para contrastar sesgos.
  
3. Efecto de la cantidad de árboles:
   - Graficar una métrica (p. ej., AUC-ROC) en validación/test vs. `n_estimators`.
   - Si usa `bootstrap=True`, incluir OOB score (`oob_score=True`) para evidenciar que no sobreajusta al incrementar árboles.

**Salidas**

- Métricas en test.
- Top-k variables más informativas.
- Gráfico desempeño vs. `n_estimators`.

---

## Comparativa de modelos

**Tareas**

1. Comparar Regresión Logística (mejor variante) vs. Árbol vs. Random Forest.

2. Incluyendo:
   - Tabla con métricas en test (**accuracy, precision, recall, F1).
   - Curvas ROC y Precision-Recall superpuestas.
  
3. Analizar:
   - Interpretabilidad vs. desempeño.
   - Riesgo de overfitting y cómo mitigar.

---


## Evidencias

* Notebook del análisis: **[Tarea_extra_01.ipynb](../tareas_extras/tarea_extra_uno.ipynb)**




