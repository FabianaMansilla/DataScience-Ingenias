# 📊 **Pre-Entrega 3 - Modelado Predictivo de Producción de Gas Natural en Argentina**

Este documento forma parte del proyecto grupal de Data Science del programa Ingenias+, y corresponde a la tercera etapa de entrega. En esta fase se trabajó con técnicas de aprendizaje supervisado para generar modelos predictivos de la producción de gas natural en Argentina, con base en los análisis realizados en las etapas anteriores.

---

🎯 **Objetivo de esta etapa**

Desarrollar y evaluar distintos modelos de aprendizaje supervisado para estimar la producción futura de gas natural en Argentina, haciendo foco en el crecimiento de los recursos no convencionales (shale y tight). Esta etapa incluye:

* Implementación de modelos de regresión
* Evaluación de desempeño mediante métricas específicas
* Ajuste y optimización de hiperparámetros
* Comparación de resultados
* Predicción futura de la producción de gas

---

👩‍💻 **Integrantes - Equipo 5**

Fabiana Yamila Mansilla

Daniela Perea

---

🧠 **Modelos Supervisados Utilizados**

Durante esta entrega se aplicaron distintos algoritmos de aprendizaje supervisado con el objetivo de predecir el volumen de producción mensual de gas natural (tanto a nivel nacional como por pozo). Se trabajó principalmente con el Dataset1 (serie histórica) y el Dataset2 (pozos no convencionales).

**Modelos de regresión:**
* Regresión Lineal
* Random Forest Regressor
* Support Vector Regressor (SVR)
* XGBoost Regressor
* Prophet (para series temporales)
* Arima (para series temporales)
* Sarima (para series temporales)

---

⚙️ **Proceso de trabajo**

**0. Carga e inspección del *Dataset1***

* Cargar los dataset
* Visualización del Dataset.
* Analisis del Dataset.
  
**1. Desarrollo y Evaluación de Modelos Predictivos de Producción (Regresión) (Dataset 1)** 

* Generar series temporales agregadas (mensuales o anuales) de la producción total a nivel nacional.
* Crear variables temporales predictoras relevantes: tendencia, estacionalidad, rezagos, entre otras.
* Entrenar y testear modelos clásicos de regresión como Regresión lineal, Árboles de decisión, Random Forest y SVR (Support Vector Regressor).
* Realizar validación temporal: entrenar los modelos con un conjunto de datos históricos y evaluar su rendimiento con los datos más recientes disponibles.
* Comparar visualmente las predicciones del modelo con los datos de producción reales para evaluar su precisión.
* Cálculo de métricas:
    * MAE (Error Absoluto Medio)
    * MSE (Error Cuadrático Medio)
    * R² (Coeficiente de determinación)
    * MAPE (Error Porcentual Absoluto Medio, en Prophet)
      
**2. Prediccion de la Producción Futura *(Dataset 1)***

* Utilizar el modelo seleccionado para realizar proyecciones de la producción futura de gas a nivel nacional para los próximos 5 años.
* Visualizar la predicción futura, incluyendo intervalos de confianza para estimar el rango de incertidumbre.
* Comparar los primeros 4 meses de 2025 predichos con los datos históricos del año en curso.

**3. Prediccion por Cuenca (Dataset 2)**

* Filtrar el Dataset por Cuenca y análisis exploratorio
* Selección de cuencas con mayor producción
* Entrenar y evaluar modelos de regresión por cuenca
* Visualizar las predicciones por cuenca

---

🗂️ **Estructura de la carpeta**

📁 Pre-entrega3/

├── 📄 README.md ← Este archivo

├── 📓 Pre-Entrega3_Equipo5.ipynb

├── 📁 Dataset/ ← Subcarpeta con datasets procesados

│ ├── Dataset1_editado.csv

│ └── Dataset2_editado.csv

---

📚 **Fuentes de datos**
* Dataset1: Serie histórica por cuenca y subtipo
* Dataset2: Producción de pozos no convencionales

---

🛠️ **Herramientas utilizadas**

* Lenguaje: Python 3.10
* Análisis y visualización: pandas, numpy, matplotlib, seaborn, plotly, scipy
* Modelado predictivo: sklearn (train_test_split, RandomForestRegressor, SVR), XGBoost, Prophet, GridSearchCV
* Entorno: Google Colab, Jupyter Notebook, GitHub

---

🔍 **Conclusiones preliminares**

Los modelos de regresión muestran buen potencial para estimar tendencias futuras en la producción de gas natural.
El modelo Prophet es especialmente útil para capturar tendencias estacionales y de largo plazo en la serie histórica nacional.
La predicción de la producción futura sigue una tendencia creciente pero más progresiva. Esta predicción se mantiene dentro de un rango relativamente estable, lo cual sugiere una fase de consolidación y crecimiento moderado, aunque dependerá de condiciones externas y políticas energéticas futuras.

---

Fecha de Entrega: 18/06/2025
