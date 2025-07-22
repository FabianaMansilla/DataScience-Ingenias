# Proyecto DataScience - Ingenias: Producción de Gas Natural en Argentina
# **Introducción al Proyecto**
Este proyecto tiene como objetivo realizar un análisis exploratorio y desarrollar un modelo predictivo de la producción de gas natural en Argentina, aprovechando dos fuentes de datos complementarias:

*  Dataset1: Serie histórica agregada de producción de gas natural por cuenca geológica y subtipo de recurso (convencional vs no convencional), con mediciones mensuales a nivel nacional.
*   Dataset2: Detalle de producción mensual a nivel de pozo no convencional, con información de empresa operadora, ubicación geográfica y volumen extraído de gas y petróleo.

Al combinar la visión macro (Dataset1) con el detalle micro (Dataset2), se podrá identificar patrones globales y específicos que expliquen el crecimiento de los recursos no convencionales y permitan proyectar tendencias futuras.

---

**Objetivo general**

Realizar un análisis exploratorio y desarrollar un modelo predictivo de la producción de gas natural en Argentina, utilizando datos históricos agregados y datos de pozos no convencionales, para identificar patrones temporales y proyectar la evolución futura de la producción a nivel nacional y por cuenca.

**Objetivos específicos**


1.   Análisis histórico: Describir la evolución anual de la producción total de gas natural y su desglose por cuenca (Neuquina, Austral, Golfo San Jorge, Noroeste, Cuyana) y tipo de recurso (convencional vs no convencional) utilizando el Dataset1.
2.   Exploración de pozos: Analizar la producción de gas a nivel de pozo no convencional según tipo de recurso (shale, tight),  cuenca y coordenadas geográficas con el Dataset2.
3. Evolución de recursos no convencionales: Investigar el peso relativo y la tasa de crecimiento del gas shale y tight sobre la producción nacional total (Dataset1).
4. Modelo predictivo: Desarrollar modelos que estimen la producción futura de gas natural, tanto agregada como por cuencas, a partir de las variables temporales, geográficas y técnicas disponibles en ambos datasets.

---
**Integrantes: Equipo 5**

Mansilla, Fabiana Yamila

Perea, Daniela

---
**Hipótesis de trabajo**

La producción de gas natural en Argentina puede modelarse y predecirse con precisión a partir de patrones temporales y geográficos presentes en los datos. En particular, se espera que el desarrollo de los recursos no convencionales (shale y tight), concentrado principalmente en la cuenca Neuquina, sea el principal motor del aumento sostenido de la producción nacional.

---

**Descripción de los datasets**

**Dataset1: Serie histórica de producción de Gas Natural (CapítuloIV)**

*   Fecha: Año, Mes, (índice de tiempo mensual).
*   Producción de gas: Por cuenca y tipo de recurso (convencional vs no convencional).
*   Totales: Volumen mensual nacional y promedio diario.

Útil para analizar evolución histórica, comparar convencional vs no convencional y proyectar tendencias.

**Dataset2: Producción de Pozos de Gas y Petróleo No Convencional**

*  Identificadores: idempresa, idpozo.

*  Producción: Petróleo (m³), gas (Miles de m³), agua (m³).

*  Volúmenes inyectados: iny_agua, iny_gas, iny_co2 (todos ceros en este caso).

*  Geografía: Cuenca, provincia, latitud, longitud, proyecto, tipo_recurso, clasificación y subclasificación.

Permite análisis detallado por pozo, comparación entre empresas y estudio de factores operativos.

---

**Fuente de datos**

*  Dataset1: Serie histórica de producción de Gas Natural por cuenca y subtipo de recurso (CapítuloIV). Disponible en la sección “Serie histórica de producción de Gas Natural por cuenca y subtipo de recurso (CapítuloIV)” del portal de datos energía de Argentina.

  Enlace: http://datos.energia.gob.ar/dataset/serie-historica-de-produccion-de-gas-natural-por-cuenca-y-sub-tipo-de-recurso-captulo-iv

*  Dataset2: Producción de Pozos de Gas y Petróleo No Convencional. Disponible en la sección “Producción de petróleo y gas por pozo” (no convencional) del portal de datos energía de Argentina.

  Enlace: http://datos.energia.gob.ar/dataset/produccion-de-petroleo-y-gas-por-pozo
  
---

**Estructura del Repositorio**

El repositorio está organizado en carpetas, cada una correspondiente a una etapa del proyecto:

📁 Pre-Entrega 1: Contiene las notebooks individuales 5 y 7, realizadas por cada integrante como entregas previas al trabajo grupal.

📁 Pre-Entrega 2: En esta carpeta comienza el desarrollo del proyecto grupal. Se incluye la notebook con el proceso de limpieza de datos y el análisis exploratorio, que ya toma como base el problema específico de la producción de gas natural en Argentina. 

📁 Pre-Entrega 3: En esta carpeta podran encontrar la notebook con el desarrollo y evaluación de distintos modelos de aprendizaje supervisado para estimar la producción futura de gas natural en Argentina, haciendo foco en el crecimiento de los recursos no convencionales (shale y tight). 

📁 Pre-Entrega 4: En esta fase se aplicaron técnicas de aprendizaje no supervisado con el objetivo de identificar patrones ocultos y segmentar la producción de gas natural en Argentina. El desarrollo toma como base los análisis realizados en las etapas previas, enfocándose en la caracterización de regiones productoras y comportamientos diferenciados entre recursos convencionales y no convencionales (shale y tight). La notebook incluye la implementación de algoritmos como clustering y reducción de dimensionalidad, junto con su interpretación y visualización de resultados.

📄 Presentación: Este archivo pdf ofrece una visión global del proyecto, destacando los objetivos, la metodología, las principales conclusiones y predicciones sobre el futuro del gas natural en Argentina, incluyendo los insights y conclusiones de los modelos supervisados y no supervisados.

📄 README.md: Este archivo contiene la documentación general del proyecto.

---

**Metodología**

1. Limpieza de datos: Se llevó a cabo el tratamiento de valores nulos, la normalización de formatos de fecha, la estandarización de variables categóricas y la unificación de criterios entre ambos conjuntos de datos para permitir su análisis conjunto.
2. Análisis exploratorio: Se trabajó con ambos datasets desde dos perspectivas temporales: la serie histórica completa y un recorte de los últimos 10 años, para captar tanto la evolución general como las tendencias más recientes.
Los análisis se realizaron con agregación anual, lo que permitió visualizar mejor los patrones y reducir la variabilidad propia de los datos mensuales.
   * En el Dataset 1, se examinó la evolución anual de la producción total de gas natural, desagregando por cuenca y tipo de recurso (convencional vs no convencional).
   *  En el Dataset 2, se analizaron las producciones de pozos no convencionales según sub tipo de recurso (shale, tight), tipo de pozo (Gasífero), tipo de estado y por cuenca.
   *  Se investigó especialmente el crecimiento de los recursos no convencionales dentro del total nacional.
3. Modelado predictivo (aprendizaje supervisado): Con el objetivo de estimar la producción futura de gas natural, se desarrollaron y evaluaron distintos modelos de aprendizaje supervisado, utilizando variables temporales y técnicas.
   *   Se implementaron modelos como Random Forest Regressor, Support Vector Regressor (SVR), XGBoost y Prophet.
   *   Se aplicó validación cruzada y ajuste de hiperparámetros (GridSearchCV) para optimizar el rendimiento.
   *   La evaluación se basó en métricas como RMSE, MAE y R², comparando predicciones a nivel agregado y por cuenca.
4. Aprendizaje no supervisado: Para complementar el enfoque supervisado y descubrir patrones ocultos en los datos, se aplicaron técnicas de clustering y reducción de dimensionalidad.
   *   Se utilizaron algoritmos como K-means y DBSCAN para segmentar los datos según comportamientos similares de producción.
   *   Se aplicó PCA (Análisis de Componentes Principales) para visualizar relaciones multidimensionales de forma más interpretable.
   *   Se analizaron los grupos identificados en función de variables como cuenca, tipo de recurso (convencional, shale, tight) y región geográfica.

Este enfoque metodológico integral permitió abordar el problema desde múltiples dimensiones, integrando análisis descriptivo, modelado predictivo y segmentación exploratoria.

---

**Herramientas utilizadas**

* Lenguaje: Python 3.10
* Análisis y visualización: pandas, numpy, matplotlib, seaborn, plotly, scipy
* Modelado predictivo: sklearn (train_test_split, RandomForestRegressor, SVR), XGBoost, Prophet, GridSearchCV
* Modelo No Supervisado:  scikit-learn (KMeans, DBSCAN, PCA), yellowbrick (para visualización de clusters y elbow method)
* Entorno: Google Colab, Jupyter Notebook, GitHub
