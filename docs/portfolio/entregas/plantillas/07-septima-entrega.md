---
title: "Entrega siete: Detectar y Corregir Sesgo con Fairlearn"
date: 2025-10-01
---

# Detección y corrección de sesgo algorítmico con Fairlearn

## Contexto

El avance del aprendizaje automático trae el desafío de garantizar la equidad en los modelos predictivos. En esta práctica se aplicó la librería Fairlearn para detectar y corregir sesgos en tres datasets:  
1. **Boston Housing** (regresión)  
2. **Titanic** (clasificación)  
3. **Ames Housing** (extensión final)

---

## Objetivos

* DETECTAR sesgo histórico en datasets reales (Boston Housing + Titanic)
* ANALIZAR impacto del sesgo en predicciones de modelos
* COMPARAR estrategias: detección (regresión) vs corrección (clasificación)
* EVALUAR cuándo detectar vs cuándo intentar corregir automáticamente
* DESARROLLAR criterios éticos para deployment responsable


## Actividades

- Parte 1 - Boston Housing: DETECTAR Sesgo Histórico — 30 min  
     * Analizar sesgo oculto en variable 'B' (proporción afroamericana)
     * Cuantificar impacto del sesgo en predicciones (regresión)
     * Analizar correlaciones y distribuciones por grupos raciales
  
- Parte 2 - Titanic: DETECTAR + CORREGIR Sesgo Sistemático — 30 min  
     * Detectar sesgo género/clase en protocolo "Women and Children First"
     * Analizar interseccionalidad (género × clase social)
     * Aplicar Fairlearn para corrección (clasificación natural)
  
- Parte 3 - Aplicar en Ames Housing — 30 min  
  
- Conclusiones finales — 20 min  


## Desarrollo

### Parte 1 — Boston Housing
- Se analizó la variable B (proporción de población afroamericana).  
- Se cuantificó el impacto del sesgo en las predicciones de regresión.

### Parte 2 — Titanic
- Se estudió el sesgo de género y clase social.  
- Se aplicó Fairlearn para ajustar la paridad demográfica sin sacrificar demasiada precisión.

### Parte 3 — Ames Housing
- Se exploraron sesgos de ubicación y tipo de vivienda.  
- Los modelos tendían a subestimar zonas de menor valor, reflejando sesgo socioeconómico.  

---

## Evidencias
* Notebook: **[07 - Sesgo con Fairlearn.ipynb](../tareas_obligatorias/siete.ipynb)**  
* Gráficos:  
![distribución](../imagenes/UT2/siete/foto1.png) 

---

## Reflexión
La práctica introdujo la responsabilidad que hay que tener a la hora de trabajar con el modelado. Es decir, aprender a detectar y corregir sesgos no solo mejora los modelos, sino que también garantiza decisiones más justas y transparentes.  
El equilibrio entre rendimiento y equidad es clave para la ciencia de datos.

---

## Conclusión
El uso de Fairlearn permitió analizar, visualizar y reducir sesgos en distintos contextos.  
Más allá de lo técnico, la experiencia me demostró que la ingeniería de datos debe incluir un enfoque ético en cada etapa del proceso analítico.
