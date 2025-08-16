# ALURA-TELECOM-X-2

**Propósito del análisis**

El objetivo principal del proyecto es predecir el abandono (cancelación) de clientes de Telecom X utilizando variables relevantes del historial de clientes. Esto permite identificar clientes en riesgo y tomar medidas preventivas para mejorar la retención.

**Estructura del proyecto**

* Cuaderno principal: Contiene todo el flujo del análisis, desde la carga de datos hasta la evaluación de modelos.

* Datos: Se encuentran en formato CSV o JSON, con información de clientes, facturación, servicios contratados, entre otros.

* Carpeta de visualizaciones: Contiene gráficos generados durante el análisis exploratorio y la evaluación de modelos (por ejemplo, boxplots, heatmaps, curvas Precisión-Recall).

  *Preparación de los datos**

1. Clasificación de variables:

* Categóricas: género, tipo de contrato, método de pago, etc.

* Numéricas: edad, facturación mensual, tiempo de permanencia, consumo de servicios.

2. Procesamiento y transformación:

* Codificación de variables categóricas en formato numérico (one-hot encoding o label encoding).

* Normalización de variables numéricas para asegurar que tengan la misma escala y no sesguen los modelos.

3. Separación de datos:

* Dividido en conjunto de entrenamiento y conjunto de validación/prueba para evaluar la capacidad predictiva de los modelos.

**Modelización y decisiones**

1. Se probaron varios modelos de clasificación:

* Regresión Logística

* Árbol de Decisión

* KNN

* SVC

* Random Forest

2. Justificación de decisiones:

* Se utilizó predict_proba o decision_function para obtener scores continuos, necesarios para evaluar precisión-recall.

* Se eligieron métricas como Average Precision Score para capturar la efectividad de los modelos en detectar clientes que abandonan, especialmente en un problema con clases desbalanceadas.

**Análisis exploratorio de datos (EDA) e insights**

1. Se generaron gráficos de correlación y distribución de variables, permitiendo identificar relaciones importantes, outliers y tendencias.

2. Ejemplos de insights:

* Clientes con facturas mensuales altas tienen mayor riesgo de abandono.

* Los contratos a corto plazo muestran mayor churn que los contratos a largo plazo.

* La combinación de servicios contratados puede influir en la retención.

**Evaluación de modelos**

* Para cada modelo se calculó el Average Precision Score, midiendo la capacidad de identificar correctamente clientes que abandonarán.

* Esto permitió seleccionar el modelo más confiable para implementar estrategias de retención.

**Instrucciones para ejecutar el cuaderno**

1. Instalar bibliotecas necesarias:

pip install pandas numpy scikit-learn matplotlib seaborn


2. Cargar los datos tratados:

import pandas as pd
df = pd.read_csv("ruta_a_datos.csv")


3. Ejecutar las celdas del cuaderno en orden, desde la carga de datos hasta la evaluación de modelos.

4. Revisar la carpeta de visualizaciones para interpretar gráficos e insights.

**Conclusión general:**
El proyecto combina preparación de datos, análisis exploratorio, modelización y evaluación rigurosa para predecir el churn. Esto permite tomar decisiones informadas para retener clientes en riesgo y mejorar la estrategia comercial de Telecom X.
