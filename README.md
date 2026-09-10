# Minería de Datos: Predicción de riesgo cardiovascular (Heart Disease UCI)

Proyecto de minería de datos en **R** sobre el dataset [Heart Failure Prediction](https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction/) (Heart Disease UCI), que combina análisis exploratorio, técnicas no supervisadas y modelos supervisados para predecir el riesgo de enfermedad cardiovascular en pacientes.

## Contenido

| Archivo | Descripción |
|---|---|
| `01_seleccion_preparacion_dataset.Rmd` / `.html` | Selección del dataset, limpieza de datos (valores faltantes/imposibles), análisis univariante y bivariante, normalización, discretización y Análisis de Componentes Principales (PCA). |
| `02_clustering_modelos_supervisados.Rmd` / `.html` | Clustering no supervisado (K-Means, K-Medians, comparación de métricas de distancia, DBSCAN/OPTICS) con validación por Silhouette Score, y modelos supervisados (árbol de decisión C5.0, Random Forest) con evaluación mediante matriz de confusión, sensibilidad y especificidad. |
| `heart.csv` | Dataset original (918 pacientes, 11 variables clínicas + variable objetivo `HeartDisease`). Distribuido bajo licencia **CC0 - Dominio Público**. |

Los archivos `.html` contienen el análisis ya ejecutado, con todos los gráficos y resultados — se pueden abrir directamente en cualquier navegador sin necesidad de instalar R.

## Técnicas y librerías utilizadas

- **Lenguaje**: R (R Markdown)
- **Manipulación de datos**: `dplyr`, `readr`
- **Visualización**: `ggplot2`, `factoextra`
- **Clustering**: K-Means, K-Medians (`flexclust`), DBSCAN, OPTICS (`dbscan`)
- **Reducción de dimensionalidad**: PCA
- **Modelos supervisados**: Árboles de decisión (`C50`), Random Forest (`randomForest`)
- **Validación**: Silhouette Score, matriz de confusión, sensibilidad/especificidad (`caret`)

## Resultados destacados

- Comparación de varios algoritmos de clustering (K-Means, K-Medians, DBSCAN, OPTICS) con distintas métricas de distancia, validados mediante Silhouette Score y visualización por PCA.
- Comparación de dos modelos supervisados para la predicción de enfermedad cardíaca:
  - **Árbol de decisión (C5.0)**: ~78% accuracy / ~89% sensibilidad
  - **Random Forest**: ~86% accuracy / ~93% sensibilidad
- Discusión sobre por qué, en un contexto clínico, priorizar la **sensibilidad** (minimizar falsos negativos) es más relevante que la accuracy global.
- Identificación de limitaciones del dataset (desequilibrio por sexo, tamaño muestral) y de los riesgos de aplicar el modelo en producción sin supervisión médica.

## Cómo reproducirlo

1. Clona el repositorio (el dataset `heart.csv` ya está incluido).
2. Abre `01_seleccion_preparacion_dataset.Rmd` en RStudio y ejecútalo primero (genera la preparación de datos usada en el segundo archivo).
3. Ejecuta `02_clustering_modelos_supervisados.Rmd` para el modelado y la evaluación.

## Contexto

Proyecto realizado como parte de la asignatura *Minería de Datos* del Grado en Ingeniería Informática (UOC). El enunciado original de la práctica se ha omitido por respeto a la propiedad intelectual de la universidad; este repositorio contiene únicamente el análisis, el código y las conclusiones propias.

---
**Autor**: Manuel Membrilla Martinez — [LinkedIn](https://www.linkedin.com/in/mmembrillam)
