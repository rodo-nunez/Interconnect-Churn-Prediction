# Interconnect - Predicción de Tasa de Cancelación de Clientes 🚀📉

Este proyecto desarrolla un modelo de **Machine Learning** para predecir la probabilidad de cancelación de clientes para el operador de telecomunicaciones **Interconnect**. Si el modelo identifica que un cliente podría cancelar el servicio, se le ofrecerán códigos promocionales o planes especiales para mejorar la retención. El objetivo principal es maximizar el puntaje **AUC-ROC**, con la **exactitud** como métrica secundaria.

<p align="center">
  <img src="https://media.giphy.com/media/26tPtg8zGK8sgpmuY/giphy.gif" width="250" alt="Interconnect GIF">
</p>

---

## Tecnologías Utilizadas 🛠️

| Tecnología | Descripción |
| --- | --- |
| ![Python](https://img.shields.io/badge/-Python-3776AB?logo=python&logoColor=white&style=for-the-badge) | Lenguaje principal de desarrollo |
| ![Pandas](https://img.shields.io/badge/-Pandas-150458?logo=pandas&logoColor=white&style=for-the-badge) | Manipulación de datos |
| ![NumPy](https://img.shields.io/badge/-NumPy-013243?logo=numpy&logoColor=white&style=for-the-badge) | Cálculos numéricos |
| ![Scikit-Learn](https://img.shields.io/badge/-Scikit%20Learn-F7931E?logo=scikitlearn&logoColor=white&style=for-the-badge) | Desarrollo de modelos de ML |
| ![TensorFlow](https://img.shields.io/badge/-TensorFlow-FF6F00?logo=tensorflow&logoColor=white&style=for-the-badge) | Redes neuronales profundas |
| ![Matplotlib](https://img.shields.io/badge/-Matplotlib-11557C?logo=plotly&logoColor=white&style=for-the-badge) | Visualización de datos |

---

## 📊 Descripción del Proyecto

El equipo de marketing de Interconnect ha recopilado datos personales de sus clientes, información sobre contratos y servicios utilizados. Nuestro objetivo es construir un modelo que permita anticipar la cancelación de clientes. **Principales servicios ofrecidos**:

1. **Teléfono Fijo** - Conexión simultánea de varias líneas.
2. **Internet** - Red configurable a través de DSL (línea telefónica) o fibra óptica.

Además, los clientes tienen acceso a:

- **Seguridad en Internet**: Antivirus y bloqueador de sitios maliciosos.
- **Soporte Técnico**: Línea de soporte.
- **Backup Online**: Almacenamiento en la nube.
- **Streaming**: TV y películas.

### Estructura de los Datos

Los datos se presentan en cuatro archivos:

- `contract.csv` — Información del contrato.
- `personal.csv` — Datos personales de los clientes.
- `internet.csv` — Servicios de Internet.
- `phone.csv` — Servicios telefónicos.

Cada archivo contiene una columna `customerID` como identificador único para cada cliente.

---

## Objetivo 📌

**Característica objetivo:** Determinar si `EndDate = 'No'` (cliente activo o cancelado).

### Métricas
- **Principal**: AUC-ROC (Area Under the Curve - Receiver Operating Characteristic).
- **Secundaria**: Exactitud.

#### Criterios de Evaluación
| AUC-ROC Range | Puntuación (SP) |
| ------------- | --------------- |
| AUC-ROC < 0.75 | 0 SP |
| 0.75 ≤ AUC-ROC < 0.81 | 4 SP |
| 0.81 ≤ AUC-ROC < 0.85 | 4.5 SP |
| 0.85 ≤ AUC-ROC < 0.87 | 5 SP |
| 0.87 ≤ AUC-ROC < 0.88 | 5.5 SP |
| AUC-ROC ≥ 0.88 | 6 SP |

---

## 🛠️ Etapas del Proyecto

1. **Planificación y Recolección de Datos**  
   Organización de archivos y verificación de valores ausentes, duplicados y tipos de datos.

2. **Análisis Exploratorio de Datos (EDA)**  
   Análisis de la distribución de datos y características de los clientes para identificar patrones.

3. **Preparación de Datos y Selección de Características**  
   Ingeniería de características y balanceo de clases con técnicas como SMOTE para evitar sesgos.

4. **Desarrollo del Modelo y Evaluación**  
   Entrenamiento y evaluación de varios modelos de ML (Random Forest, Gradient Boosting, MLP Classifier) usando validación cruzada y ajuste de hiperparámetros.

5. **Informe de Resultados**  
   Resumen de métricas, comparación de modelos y recomendaciones para la implementación en producción.

---

## 🚀 Requisitos

Para ejecutar el proyecto, instala las siguientes dependencias con el comando:

```bash
pip install -r requirements.txt
