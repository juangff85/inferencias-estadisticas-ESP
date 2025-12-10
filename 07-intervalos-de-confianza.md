---
layout: default
title: Intervalos de Confianza
nav_order: 8
---
# 7. Intervalos de Confianza

## 7.1. La naturaleza de la estimación por intervalo

Mientras que la prueba de hipótesis se centra en una decisión binaria (rechazar/mantener $H_0$), la estimación se centra en cuantificar el parámetro de interés (por ejemplo, la media, la diferencia o el tamaño del efecto). La estimación por intervalo, a través de los **Intervalos de Confianza (IC)**, nos proporciona una medida de la **precisión** de nuestra estimación.

Un **Intervalo de Confianza (IC)** es un rango de valores plausibles para el verdadero parámetro poblacional, basado en los datos de la muestra.

## 7.2. Interpretación de los Intervalos de Confianza

La interpretación de un IC es a menudo malentendida. Para un IC del 95%:

> Si repitiéramos el muestreo y el análisis de datos un número infinito de veces, el 95% de los intervalos construidos de esta manera contendrían el verdadero valor del parámetro poblacional.

**Lo que el IC NO es:** Un IC del 95% **no** significa que hay un 95% de probabilidad de que el verdadero parámetro se encuentre dentro del intervalo calculado a partir de una única muestra. (Esa es la interpretación del Intervalo de Credibilidad Bayesiano, como se vio en el Capítulo 4).

## 7.3. La relación entre IC y el valor $p$

Existe una relación directa entre los Intervalos de Confianza y los valores $p$ dentro del marco de la Prueba de Hipótesis de Significación Nula (NHST):

1.  **Si un IC del $100(1-\alpha)\%$ (por ejemplo, 95%) para un parámetro (como la diferencia de medias $\mu_1 - \mu_2$) no contiene el valor nulo (por ejemplo, 0),** entonces la prueba de hipótesis correspondiente con un nivel de significancia $\alpha$ será **estadísticamente significativa** ($p < \alpha$).
2.  **Si el IC sí contiene el valor nulo,** entonces la prueba no será estadísticamente significativa ($p \geq \alpha$).

Por lo tanto, los IC proporcionan la misma información de decisión que el valor $p$, pero con la ventaja añadida de la estimación de la magnitud y la precisión.

## 7.4. Factores que afectan la anchura del IC

La anchura del IC (es decir, la precisión de la estimación) se ve influenciada por dos factores principales:

1.  **Tamaño de la muestra ($N$):** A medida que el tamaño de la muestra aumenta, el error estándar disminuye y el IC se vuelve **más estrecho** (más preciso).
2.  **Nivel de Confianza (por ejemplo, 90%, 95%, 99%):** Un nivel de confianza más alto (por ejemplo, 99% en lugar de 95%) requiere capturar una mayor proporción del muestreo hipotético, lo que da lugar a un IC **más ancho** (más incierto).

## 7.5. ICs Informativos y el Valor de la Precisión

Reportar un IC es a menudo más informativo que reportar solo el valor $p$. Un IC nos ayuda a distinguir entre:

* **Un resultado significativo y preciso:** IC estrecho que excluye el cero.
* **Un resultado significativo pero impreciso:** IC ancho que excluye el cero.
* **Un resultado no significativo y preciso:** IC estrecho que incluye el cero, lo que proporciona evidencia sólida de que el efecto es pequeño (similar a una prueba de equivalencia).
* **Un resultado no significativo e impreciso:** IC ancho que incluye el cero, lo que significa que el verdadero efecto podría ser pequeño, moderado o incluso grande, pero los datos no son lo suficientemente informativos para distinguirlo.



## 7.6. ICs y Planificación del Estudio

La planificación de la precisión (Accuracy in Parameter Estimation, AIPE) es un enfoque para la justificación del tamaño de la muestra (Capítulo 8) que se centra en lograr una anchura de IC deseada.

En lugar de planificar para la potencia (la capacidad de rechazar $H_0$), AIPE planifica para la **precisión** (la capacidad de tener un IC que no sea más ancho que un valor específico). Esto cambia el enfoque del estudio, de la simple detección a la estimación precisa.

## 7.7. Intervalos de Confianza para Tamaños del Efecto

Como se mencionó en el Capítulo 6, es una buena práctica informar el IC no solo para las medias sin procesar, sino también para los tamaños del efecto estandarizados (como el $d$ de Cohen o $r$). Un IC sobre un $ES$ estandarizado facilita la comparación de la precisión de los hallazgos entre diferentes estudios.
