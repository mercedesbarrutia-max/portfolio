---
title: "Entrega de ejercicio machine learning"
---

# Tarea extra 01 — Regresión y clasificación 

## Contexto
En otra materia de mi carrea llamada machine learning nos proponen desafíos que se relacionan con temáticas enseñadas en el curso de Ingeniería de datos. Por esto, decidí incluir mi trabajo en este portfolio como tarea extra.

## Objetivos

Propósito: Integrar exploración de datos, modelado supervisado y toma de decisiones clínicas con el dataset **Heart Disease (Cleveland)** de UCI.
El objetivo es predecir la presencia de enfermedad cardíaca** y proponer una estrategia de priorización de pacientes.

## 0) Datos y variable objetivo

- Dataset: **Heart Disease (Cleveland)** (clase binaria: `target` = 1 presencia de enfermedad; 0 ausencia).
- **Preprocesamiento mínimo esperado**:
  - Revisión de valores faltantes y outliers.
  - Correlación de variables.
  - Codificación de variables categóricas (one-hot o tratamiento ordinal **justificado**).
  - Estandarización para modelos lineales/regularizados.
  - Partición **train/test** (p. ej., 70/30) 

---

## 1) Modelo lineal (Regresión Logística)

**Tareas**
1. Entrenar un modelo lineal para clasificación (**Regresión Logística**).
2. **Significancia estadística**:
   - Reportar coeficientes, errores estándar y p-values.
   - Interpretar el **signo** y **magnitud** .
3. **Regularización**:
   - Investigue cómo es la regularización en modelos lineales. Explique con sus palabras.
   - Comparar **L2 (Ridge)**, **L1 (Lasso)** y **Elastic Net** con validación cruzada.
   - Discutir cuáles variables parecen relevantes.

**Salidas**
- Métricas en test: **accuracy, precision, recall, F1, AUC-ROC, AUC-PR**.
- Tabla de coeficientes (modelo sin regularizar vs. mejor regularizado).

---

## 2) Árbol de decisión

**Tareas**
1. Entrenar un **Decision Tree Classifier** optimizando hiperparámetros clave mediante **GridSearchCV** o **RandomizedSearchCV**:
   - `max_depth`, `min_samples_split`, `min_samples_leaf`, `max_features`, `ccp_alpha`.
2. Reportar **importancias de variables** y **reglas** del árbol final:
   - Extraer **rutas de decisión**.
3. Analizar **complejidad vs. generalización**: mostrar el efecto de `max_depth` (o `ccp_alpha`) en desempeño de validación.

**Salidas**
- Métricas en test.
- Gráfico: **desempeño vs. `max_depth`**

---

## 3) Random Forest

**Tareas**
1. Entrenar un **Random Forest Classifier** optimizando hiperparámetros con **GridSearchCV** o **RandomizedSearchCV**:
   - `n_estimators`, `max_features`, `max_depth`, `min_samples_leaf`, `min_samples_split`, `bootstrap`.
2. **Importancias de variables**:
   - Investigar sobre importancia de variables en RF.
   - Reportar **Gini importance** y, si es posible, **Permutation Importance** (sobre test o CV) para contrastar sesgos.
3. **Efecto de la cantidad de árboles**:
   - Graficar una **métrica** (p. ej., AUC-ROC) en validación/test **vs. `n_estimators`**.
   - Si usa `bootstrap=True`, incluir **OOB score** (`oob_score=True`) para evidenciar que **no sobreajusta** al incrementar árboles.

**Salidas**
- Métricas en test.
- **Top-k** variables más informativas.
- Gráfico **desempeño vs. `n_estimators`**.

---

## 4) Comparativa de modelos

**Tareas**
1. Comparar **Regresión Logística (mejor variante)** vs. **Árbol** vs. **Random Forest**.
2. Incluyendo:
   - Tabla con métricas en test (**accuracy, precision, recall, F1).
   - Curvas **ROC** y **Precision-Recall** superpuestas.
3. Analizar:
   - **Interpretabilidad** vs. **desempeño**.
   - Riesgo de **overfitting** y cómo mitigar.

---

## 5) Priorización de pacientes (toma de decisiones)

Imagine que debe **priorizar la atención** de pacientes con mayor probabilidad de enfermedad (recursos limitados).

**Tareas**
1. Definir una **estrategia de umbral** sobre probabilidades (p. ej., “priorizar si *p* ≥ τ”).
2. Elegir **τ** con un **criterio operativo**:
   - Maximizar **recall** sujeto a **precision ≥ P₀**.
   - Selección **top-k** pacientes (p. ej., los 20 con mayor *p*).
   - **Análisis de costos**: asignar costos a FN/FP y maximizar utilidad esperada.
3. **Ejemplificar**:
   - Tabla con los **k** pacientes con mayor *p*, variables clave y clasificación.
   - **Confusion matrix** y métricas resultantes con ese umbral/estrategia.
   - Implicancias clínicas: riesgo de **FN** (no priorizar a quien sí padece) vs. **FP** (priorizar a quien no padece).
4. **Extra**
   - Breve **discusión ética** y de **equidad** (posibles sesgos por `sex`, edad u otras variables).

---

## Evidencias

* Notebook del análisis: **[Tarea_extra_01.ipynb](tarea_extra_uno.ipynb)**




