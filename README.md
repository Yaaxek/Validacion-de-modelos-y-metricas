# 🚀 Validación Robusta y Datos Desbalanceados

Este repositorio contiene una suite de proyectos de **Machine Learning** enfocados en resolver problemas de clasificación binaria complejos. Se implementan técnicas avanzadas de validación, métricas de evaluación profunda y estrategias de balanceo de datos para modelos aplicados a finanzas (Morosidad) y salud (Diabetes).

---

## 📋 Proyectos Incluidos

### 1. 🏦 Análisis de Riesgo Financiero (Prestacar)
**Objetivo:** Automatizar la identificación de clientes morosos para una empresa de financiamiento de automóviles.
* **Dataset:** `prestacar.csv`
* **Desafío:** Superar el proceso manual ineficiente mediante un modelo que maximice la detección de impagos sin afectar a los buenos clientes.

### 2. 🏥 Diagnóstico Predictivo de Diabetes
**Objetivo:** Clasificar si un paciente tiene diabetes basándose en indicadores clínicos.
* **Desafío:** Trabajar con datasets donde la clase positiva suele ser minoritaria, requiriendo validación estratificada y balanceo sintético.

---

## 🛠️ Stack Tecnológico

* **Lenguaje:** Python 3.x
* **Análisis de Datos:** `Pandas`, `NumPy`
* **Machine Learning:** `Scikit-Learn` (Trees, Ensembles, Pipelines)
* **Balanceo de Datos:** `Imbalanced-Learn` (SMOTE, NearMiss)
* **Visualización:** `Matplotlib`, `Seaborn`

---

## 🧬 Metodología de Validación y Modelado

El repositorio sigue un flujo de trabajo riguroso diseñado para garantizar la **generalización** de los modelos:

1.  **Partición de Datos:** División en Entrenamiento, Validación y Prueba (Hold-out set del 5%) utilizando `stratify` para preservar la proporción de las clases.
2.  **Modelado Base:** Comparativa entre `DecisionTreeClassifier` y `RandomForestClassifier` con control de profundidad (`max_depth`) para evitar el sobreajuste (overfitting).
3.  **Validación Cruzada Avanzada:**
    * **KFold & StratifiedKFold:** Validación en 10 partes para estabilidad estadística.
    * **LeaveOneOut:** Para conjuntos de datos pequeños.
    * **Intervalos de Confianza:** Cálculo de $\mu \pm 2\sigma$ para reportar el rendimiento esperado de forma científica.

---

## 📊 Métricas de Evaluación Progresiva

No nos basamos solo en la exactitud (Accuracy). Evaluamos el éxito mediante:
* **Matriz de Confusión:** Para entender los tipos de error (Falsos Positivos vs. Falsos Negativos).
* **Curvas ROC & AUC:** Capacidad de discriminación del modelo.
* **Precision-Recall & AP:** Crucial para evaluar el rendimiento en la clase minoritaria (ej. detectar morosos).
* **Classification Report:** F1-Score, Recall y Precision detallados por clase.

---

## ⚖️ Estrategias para Datos Desbalanceados

Para combatir el sesgo hacia la clase mayoritaria, implementamos **Pipelines** que integran:
* **Oversampling (SMOTE):** Generación de muestras sintéticas.
* **Undersampling (NearMiss):** Reducción de la clase dominante.
* **Validación Integrada:** El balanceo se realiza exclusivamente dentro de los folds de entrenamiento para evitar el *Data Leakage*.
