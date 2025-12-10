---
layout: default
title: Meta-análisis
nav_order: 12
---
# 11. Meta-análisis

## 11.1. Definición y Propósito

El **Meta-análisis** es el análisis estadístico de una colección de resultados de múltiples estudios individuales, con el propósito de integrar los hallazgos. Es una herramienta esencial para la inferencia estadística, ya que permite obtener una estimación del tamaño del efecto que es más precisa y potente que la estimación de cualquier estudio individual.

### 11.1.1. Ventajas del Meta-análisis

* **Mayor Precisión:** Un estudio combinado con una muestra efectiva mucho mayor reduce el error estándar y produce un Intervalo de Confianza más estrecho (Capítulo 7).
* **Mayor Potencia:** La mayor precisión aumenta la capacidad de detectar efectos reales (reduce el error Tipo II, Capítulo 8).
* **Resolución de Controversias:** Puede ayudar a resolver resultados contradictorios entre estudios.
* **Estimación del ESOI:** Proporciona la mejor estimación del Tamaño del Efecto de Interés (ESOI), crucial para la justificación del tamaño de la muestra de futuros estudios (Capítulo 8).

## 11.2. Pasos en un Meta-análisis

Un meta-análisis bien ejecutado implica varios pasos clave:

1.  **Formulación de la Pregunta:** Definir claramente el efecto de interés, la población y los diseños de estudio que se incluirán.
2.  **Búsqueda Sistemática de Literatura:** Identificar todos los estudios relevantes (publicados y no publicados) para minimizar el sesgo.
3.  **Extracción de Datos:** Recopilar el tamaño del efecto ($ES$) y el error estándar de cada estudio.
4.  **Selección del Modelo:** Elegir entre un modelo de efectos fijos o un modelo de efectos aleatorios.
5.  **Cálculo del ES Promedio:** Estimar el tamaño del efecto combinado.
6.  **Análisis de Heterogeneidad y Sesgo:** Evaluar la variabilidad entre estudios y el posible sesgo de publicación (Capítulo 12).

## 11.3. Modelos de Meta-análisis

Los dos modelos principales para combinar tamaños del efecto son:

### 11.3.1. Modelo de Efectos Fijos (Fixed-Effect Model)

Este modelo asume que todos los estudios incluidos están midiendo el **mismo verdadero tamaño del efecto** en la población. Las diferencias observadas entre los resultados de los estudios se deben únicamente al error de muestreo.

### 11.3.2. Modelo de Efectos Aleatorios (Random-Effects Model)

Este modelo es más conservador y realista. Asume que el verdadero tamaño del efecto **varía** entre los estudios (heterogeneidad). Las diferencias observadas se deben tanto al error de muestreo como a la variación real en los tamaños del efecto (por ejemplo, debido a diferencias en poblaciones, métodos o contextos).

## 11.4. Heterogeneidad

La **Heterogeneidad** se refiere a la variación real en los tamaños del efecto entre los estudios. Si la heterogeneidad es alta, un modelo de efectos aleatorios es más apropiado.

La heterogeneidad se evalúa a menudo utilizando el estadístico $I^2$:

* **$I^2$:** Mide la proporción de la varianza total observada en los tamaños del efecto que es atribuible a la heterogeneidad real, en lugar del error de muestreo. 
* Valores altos de $I^2$ (ej., > 50%) sugieren que la variación no se explica solo por el azar, lo que indica la necesidad de explorar moderadores (variables que explican las diferencias).

## 11.5. Visualización: El Diagrama de Bosque (Forest Plot)

Un Diagrama de Bosque es la forma estándar de visualizar los resultados de un meta-análisis. Muestra:

* El tamaño del efecto y el Intervalo de Confianza para cada estudio individual (representado por una caja y una línea horizontal).
* El tamaño del efecto combinado (la estimación agrupada), típicamente representado por un diamante en la parte inferior.

## 11.6. Meta-análisis Acumulativo

En un **meta-análisis acumulativo**, los estudios se combinan secuencialmente en orden cronológico o por tamaño de muestra. Esto muestra cómo la estimación combinada y su precisión evolucionan a medida que se agregan más datos. Este enfoque puede ser útil para determinar cuándo la evidencia se ha vuelto suficientemente concluyente (similar a los objetivos del análisis secuencial, Capítulo 10).

## 11.7. Uso del Meta-análisis para la Planificación

El meta-análisis no es solo una herramienta de revisión; es una herramienta de planificación:

* La estimación del tamaño del efecto combinado (el punto central del diamante) debe utilizarse como el mejor **ESOI** para calcular la potencia de los futuros estudios primarios.
* La varianza observada en los tamaños del efecto (la heterogeneidad) puede informar la selección de variables moderadoras para futuras investigaciones.
