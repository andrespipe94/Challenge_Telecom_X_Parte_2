# 📊 Predicción de Abandono de Clientes (Churn) - Telecom X

Este proyecto aplica técnicas de **Machine Learning** para identificar patrones de abandono y predecir qué clientes tienen mayor probabilidad de cancelar su servicio en la empresa **Telecom X**.

---

## 📋 Tabla de contenidos

1. [📖 Descripción](#-descripción)
2. [🎯 Objetivo del proyecto](#-objetivo-del-proyecto)
3. [🏁 Estado del proyecto](#-estado-del-proyecto)
4. [⚙️ Desarrollo del proyecto](#-desarrollo-del-proyecto)
5. [📌 Resultados destacados](#-resultados-destacados)
6. [✅ Tecnologías utilizadas](#-tecnologías-utilizadas)
7. [🚀 Instrucciones para ejecutar el cuaderno](#-instrucciones-para-ejecutar-el-cuaderno)
---

## 📖 Descripción

El proyecto desarrolla un modelo predictivo a partir de un dataset de telecomunicaciones previamente tratado. El flujo de trabajo incluyó:
* **Análisis exploratorio de datos (EDA)** para entender el comportamiento del cliente.
* **Transformación y codificación** de variables categóricas.
* **Balanceo de clases** mediante la técnica **SMOTE** para corregir el sesgo hacia clientes que no cancelan.
* **Entrenamiento y comparación** de modelos supervisados.
* **Análisis de importancia de variables** para entender los "porqués" del abandono.
* **Propuesta de estrategias** de negocio basadas en datos.

---

## 🎯 Objetivo del proyecto

* **Identificación temprana:** Construir modelos capaces de detectar clientes en riesgo de fuga.
* **Benchmarking:** Comparar el rendimiento de distintos algoritmos (Árboles, KNN, etc.).
* **Interpretabilidad:** Detectar las variables críticas que influyen en la decisión del cliente.
* **Accionabilidad:** Traducir métricas técnicas en estrategias de retención.

> [!IMPORTANT]
> Se priorizó la métrica **Recall**. En este contexto, un "Falso Negativo" (un cliente que se va sin ser detectado) es mucho más costoso que un "Falso Positivo" (un cliente leal que recibe una oferta de retención).

---

## 🏁 Estado del proyecto

![Finalizado](https://img.shields.io/badge/ESTADO-FINALIZADO-brightgreen?style=for-the-badge)

---

## ⚙️ Desarrollo del proyecto

### 1️⃣ Análisis Exploratorio (EDA)
Se utilizaron herramientas visuales para identificar correlaciones:
* **Matriz de correlación:** Para evaluar la relación entre variables numéricas.
* **Countplots:** Segmentación por la variable objetivo (*Abandono*).
* **Boxplots:** Análisis de dispersión en variables clave como meses de permanencia y cargos mensuales.



### 2️⃣ Preprocesamiento
* Limpieza de columnas no informativas.
* División de datos en conjuntos de *Train* y *Test*.
* **Codificación:** Uso de `OneHotEncoder` para datos categóricos.
* **Balanceo:** Aplicación de `SMOTE` en el set de entrenamiento.
* **Normalización:** Uso de `MinMaxScaler` para optimizar algoritmos basados en distancia (KNN).

### 3️⃣ Modelos Implementados
* **DummyClassifier:** Utilizado como línea base (*Baseline*).
* **Decision Tree Classifier:** Configurado con `max_depth=4` para evitar el sobreajuste.
* **K-Nearest Neighbors (KNN):** Configurado con `n_neighbors=15` y pesos por distancia.

### 4️⃣ Métricas Evaluadas
Se realizó un análisis exhaustivo mediante:
* Accuracy, Recall, Precision y F1-score.
* **Matrices de Confusión.**
* **Permutation Importance** para validar la relevancia de las variables.

---

## 📌 Resultados destacados

### 📊 Comparación de modelos

| Modelo | Accuracy | Recall |
| :--- | :---: | :---: |
| Dummy Classifier | 0.50 | 0.50 |
| K-Nearest Neighbors | **0.84** | 0.65 |
| **Árbol de Decisión** | 0.78 | **0.80** |

**Interpretación:** Aunque el KNN es más preciso globalmente, el **Árbol de Decisión** es el ganador para el negocio al capturar el **80% de los casos de abandono reales (Recall)**.

### 🔎 Factores más influyentes
1. **Contratos mes a mes:** Representan la mayor fuente de inestabilidad.
2. **Método de pago:** El cheque electrónico está altamente correlacionado con el churn.
3. **Servicio de Fibra Óptica:** Presenta una tasa de abandono inusualmente alta frente al DSL.

---

## 🚀 Estrategias propuestas

1. **Migración de Contratos:** Incentivar el paso de "mes a mes" a contratos anuales.
2. **Fidelización Temprana:** Monitoreo intensivo en los primeros 6 meses de vida del cliente.
3. **Optimización de Fibra Óptica:** Investigar fallas técnicas o de precio en este segmento específico.
4. **Automatización de Pagos:** Fomentar el uso de tarjetas de crédito o transferencias automáticas.

---

## ✅ Tecnologías utilizadas

* **Lenguaje:** Python 🐍
* **Librerías:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `imbalanced-learn`.
* **Entorno:** Google Colab.

---

## 🚀 Instrucciones para ejecutar el cuaderno

1. **Clonar el repositorio:**
   ```bash
   git clone [https://github.com/JonathanMarino/Challenge-Telecom-X-parte-2.git](https://github.com/JonathanMarino/Challenge-Telecom-X-parte-2.git)
   cd Challenge-Telecom-X-parte-2
