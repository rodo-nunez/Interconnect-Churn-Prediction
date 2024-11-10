# Interconnect - Predicción de Tasa de Cancelación de Clientes
Proyecto de pronóstico de tasa de cancelación de clientes para el operador de telecomunicaciones Interconnect

Este proyecto desarrolla un modelo de machine learning para predecir la probabilidad de cancelación de clientes para el operador de telecomunicaciones **Interconnect**. Si el modelo identifica que un cliente podría cancelar el servicio, se le ofrecerán códigos promocionales o planes especiales para mejorar la retención. Este proyecto se enfoca en maximizar el puntaje AUC-ROC, siendo esta la métrica principal, y la exactitud como métrica secundaria.

## Servicios de Interconnect

Interconnect ofrece servicios principales de telefonía e Internet con varias opciones de personalización:
1. **Comunicación por teléfono fijo**: Ofrece conexión simultánea de varias líneas.
2. **Internet**: Configurable a través de DSL (línea telefónica) o fibra óptica.

Además, los clientes pueden elegir entre múltiples métodos de pago y recibir facturación electrónica. Otros servicios incluyen:
- **Seguridad en Internet**: Antivirus y bloqueador de sitios maliciosos.
- **Soporte Técnico**: Línea de soporte para problemas técnicos.
- **Backup Online**: Almacenamiento de datos en la nube.
- **Streaming**: Opciones de TV y películas.

## Estructura de Datos

Los datos de clientes y servicios se dividen en cuatro archivos CSV:
- `contract.csv` - Información del contrato de cada cliente.
- `personal.csv` - Datos personales de los clientes.
- `internet.csv` - Servicios de Internet contratados.
- `phone.csv` - Servicios telefónicos contratados.

Cada archivo contiene una columna `customerID` como identificador único de cada cliente.

## Objetivo del Proyecto

**Característica objetivo:** Determinar si `EndDate = 'No'` (cliente activo o cancelado).

**Métricas**:
- **Principal**: AUC-ROC (Area Under the Curve - Receiver Operating Characteristic).
- **Secundaria**: Exactitud.

### Criterios de Evaluación:
- AUC-ROC < 0.75 — 0 SP
- 0.75 ≤ AUC-ROC < 0.81 — 4 SP
- 0.81 ≤ AUC-ROC < 0.85 — 4.5 SP
- 0.85 ≤ AUC-ROC < 0.87 — 5 SP
- 0.87 ≤ AUC-ROC < 0.88 — 5.5 SP
- AUC-ROC ≥ 0.88 — 6 SP

## Etapas del Proyecto

1. **Planificación y Recolección de Datos**  
   Organización de los archivos proporcionados y verificación de valores ausentes, duplicados, y tipos de datos.

2. **Análisis Exploratorio de Datos (EDA)**  
   Análisis de la distribución de datos, características de clientes y servicios, además de la identificación de patrones relevantes.

3. **Preparación de Datos y Selección de Características**  
   Ingeniería de características para mejorar el rendimiento del modelo y balanceo de clases con técnicas como SMOTE para evitar sesgos en la clase minoritaria.

4. **Desarrollo del Modelo y Evaluación**  
   Entrenamiento y evaluación de varios modelos de machine learning (Random Forest, Gradient Boosting, MLP Classifier) utilizando validación cruzada y ajuste de hiperparámetros. 

5. **Informe de Resultados**  
   Resumen de métricas, comparación de modelos y recomendaciones para la implementación en producción.

## Requisitos

Para ejecutar el proyecto, necesitas instalar las siguientes dependencias. Puedes instalarlas con el siguiente comando:

```bash
pip install -r requirements.txt
