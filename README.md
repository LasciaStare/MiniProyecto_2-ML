# Predicción de Precios y Clasificación de Autos Usados

Este proyecto utiliza un conjunto de datos de Craigslist [Used Cars Dataset](https://www.kaggle.com/datasets/austinreese/craigslist-carstrucks-data) sobre ventas de autos para desarrollar modelos de aprendizaje supervisado. Los objetivos principales son:

1.  **Estimar el precio** de un vehículo usado basándose en sus características (tarea de regresión).
2.  **Clasificar si un vehículo** tiene una alta o baja demanda en el mercado (tarea de clasificación binaria).

## 📝 Descripción del Proyecto

El proyecto abarca un flujo de trabajo completo de ciencia de datos, desde la limpieza y el análisis exploratorio de datos (EDA) hasta la implementación y evaluación de modelos de regresión y clasificación. Se utilizan técnicas de regularización como Ridge (L2) y Lasso (L1) para la predicción de precios, y Regresión Logística para la clasificación de la demanda.

El análisis completo y los resultados se pueden encontrar en la página del proyecto: [Análisis y Modelado de Autos Usados](https://lasciastare.github.io/MiniProyecto_2-ML/ridge.html).

## ✨ Características Principales

*   **Análisis Exploratorio de Datos (EDA):** Se realiza un análisis detallado para comprender la distribución de las variables y sus relaciones.
*   **Limpieza de Datos:** Se manejan valores faltantes a través de diversas estrategias de imputación y se eliminan datos irrelevantes.
*   **Manejo de Outliers:** Se identifican y filtran valores atípicos en variables clave como `price` y `odometer` para mejorar la robustez del modelo.
*   **Ingeniería de Características:** Se crea una nueva variable objetivo binaria, `HighDemand`, basada en la mediana del precio para la tarea de clasificación.
*   **Modelado y Evaluación:**
    *   **Regresión:** Se implementan y comparan modelos Ridge y Lasso para predecir el precio de los vehículos.
    *   **Clasificación:** Se utiliza un modelo de Regresión Logística para clasificar los autos en "Alta Demanda" o "Baja Demanda".

## 🤖 Modelos Implementados

### 1. Modelos de Regresión (Predicción de Precios)

Se utilizaron pipelines de `scikit-learn` que incluyen preprocesamiento (escalado para variables numéricas y One-Hot Encoding para categóricas) y el modelo. La búsqueda de hiperparámetros se realizó con `GridSearchCV`.

*   **Ridge Regression:**
    *   **Resultado:** Obtuvo un R² de **0.7588** en el conjunto de prueba.
    *   **MAE:** 3788.85
    *   **RMSE:** 6379.60
*   **Lasso Regression:**
    *   **Resultado:** Alcanzó un R² de **0.7580** en el conjunto de prueba.
    *   **MAE:** 3896.72
    *   **RMSE:** 6390.29

Ambos modelos lineales ofrecieron un rendimiento similar, explicando aproximadamente el 76% de la varianza en el precio.

### 2. Modelo de Clasificación (Clasificación de Demanda)

*   **Regresión Logística:**
    *   **Resultado:** Logró una precisión (accuracy) del **91%**.
    *   **ROC AUC:** Alcanzó una puntuación de **0.9683**, lo que indica una excelente capacidad para distinguir entre las clases de alta y baja demanda.

##  Conclusiones

*   Para la **predicción de precios**, los modelos Ridge y Lasso proporcionan una base sólida. Sin embargo, los análisis de residuos mostraron signos de heterocedasticidad, sugiriendo que modelos no lineales podrían capturar mejor la complejidad del mercado automotriz.
*   Para la **clasificación de la demanda**, el modelo de Regresión Logística demostró un rendimiento sobresaliente, clasificando correctamente los vehículos con alta precisión y un excelente poder de discriminación (AUC).

## 🛠️ Librerías

Para ejecutar un análisis similar, necesitarás un entorno de Python con las siguientes bibliotecas principales:

*   `numpy`
*   `pandas`
*   `scikit-learn`
*   `matplotlib`
*   `seaborn`
*   `missingno`

El flujo de trabajo general a seguir es:
1.  Cargar el conjunto de datos.
2.  Aplicar las técnicas de limpieza y preprocesamiento descritas.
3.  Realizar el análisis exploratorio de datos.
4.  Crear la característica `HighDemand`.
5.  Definir y entrenar los pipelines de regresión (Ridge, Lasso) y clasificación (Regresión Logística).
6.  Evaluar los modelos utilizando las métricas apropiadas.

## 🧑‍💻 Autores

Este proyecto fue desarrollado por:
*   José Menco
*   Camilo Vargas
*   Iván Ramirez
