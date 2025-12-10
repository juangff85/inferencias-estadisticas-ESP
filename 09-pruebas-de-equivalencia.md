---
title: 9. Pruebas de Equivalencia e Hipótesis de Intervalo
---


# 9. Pruebas de Equivalencia e Hipótesis de Intervalo

## 9.1. El problema de la ausencia de efecto

Cuando un valor $p$ es no significativo ($p \geq 0.05$), la conclusión formal en el marco de Neyman-Pearson es "no rechazar $H_0$". Esto **no** es evidencia de la ausencia de efecto. Un resultado no significativo puede deberse a:

1.  El efecto es verdaderamente cero (o muy pequeño).
2.  El estudio tuvo baja potencia (error Tipo II) y no pudo detectar un efecto existente.

Para demostrar que un efecto es *lo suficientemente pequeño como para ser irrelevante*, necesitamos un enfoque estadístico que invierta el papel de las hipótesis nula y alternativa: la **Prueba de Equivalencia**.

## 9.2. El principio de la Prueba de Equivalencia (TOST)

La Prueba de Equivalencia más común es la prueba de **Two One-Sided Tests (TOST)** (Pruebas de Dos Unilaterales).

En la prueba TOST, el investigador define un **margen de equivalencia** ($\Delta$), que representa el **Tamaño del Efecto más Pequeño de Interés Práctico (MPE)**. El $\Delta$ puede ser positivo ($\Delta_U$) o negativo ($\Delta_L$).

El principio TOST invierte la hipótesis nula tradicional:

* **Hipótesis Nula de Equivalencia ($H_{0E}$):** El verdadero efecto está **fuera** del margen de equivalencia (es decir, el efecto es tan grande que no es equivalente al cero). $H_{0E}: \delta \leq \Delta_L \text{ o } \delta \geq \Delta_U$.
* **Hipótesis Alternativa de Equivalencia ($H_{1E}$):** El verdadero efecto está **dentro** del margen de equivalencia (es decir, el efecto es equivalente al cero). $H_{1E}: \Delta_L < \delta < \Delta_U$.



## 9.3. La Regla de Decisión TOST

Para concluir la equivalencia, el investigador debe **rechazar ambas** las hipótesis unilaterales nulas. Esto se logra realizando dos pruebas de hipótesis $t$ separadas, cada una con un nivel $\alpha$ de significancia (típicamente $\alpha = 0.05$):

1.  **Prueba 1:** Prueba si el efecto es significativamente **mayor** que el límite superior ($\Delta_U$). Rechazamos si $p < \alpha$.
2.  **Prueba 2:** Prueba si el efecto es significativamente **menor** que el límite inferior ($\Delta_L$). Rechazamos si $p < \alpha$.

Si **ambas** pruebas son rechazadas, se puede concluir que el efecto observado es estadísticamente equivalente a cero (o el valor de referencia), dentro del margen $\Delta$.

## 9.4. IC y Equivalencia

La prueba TOST es conceptualmente equivalente a verificar si el **Intervalo de Confianza (IC)** del $100(1-2\alpha)\%$ (es decir, un IC del 90% para $\alpha=0.05$) cae completamente **dentro** del margen de equivalencia ($\Delta_L$ a $\Delta_U$).

* **Si el IC del 90% está completamente dentro del margen de equivalencia:** Se concluye la equivalencia.
* **Si el IC toca o se extiende más allá de cualquiera de los límites:** No se puede concluir la equivalencia.

## 9.5. La Justificación del Margen de Equivalencia ($\Delta$)

El paso más crítico de una prueba TOST es la justificación del margen $\Delta$. Este margen debe basarse en un argumento sustantivo, no estadístico. Las justificaciones comunes incluyen:

1.  **Mínima Importancia Práctica (MPE):** El efecto más grande que aún se consideraría clínicamente o prácticamente trivial.
2.  **Basado en Costos/Beneficios:** El punto en el que el costo del tratamiento supera el beneficio marginal.
3.  **Basado en la Literatura/Estimación:** Basado en la variabilidad o el error de medición del resultado (el "ruido").

## 9.6. Hipótesis de Intervalo

Las pruebas TOST son un tipo de **Hipótesis de Intervalo**, que es cualquier prueba de hipótesis donde la $H_0$ o la $H_1$ definen un rango de valores en lugar de un único valor puntual (como $\delta=0$).

Otro tipo de prueba de intervalo es la prueba de **Superioridad con Margen** (Superiority by a Margin). Aquí, el investigador prueba que un efecto es no solo diferente de cero, sino que es **mejor** que un margen específico ($H_0: \delta \leq \Delta$).

## 9.7. Resumen de Pruebas de Decisión

| Objetivo | Hipótesis Nula ($H_0$) | Conclusión de Interés | Herramienta |
| :--- | :--- | :--- | :--- |
| **Detección** | $\delta = 0$ (No hay efecto) | Rechazar $H_0$ ($p < \alpha$) | NHST (Valor $p$) |
| **Equivalencia** | $|\delta| \geq \Delta$ (Efecto no trivial) | Rechazar $H_0$ (Ambas pruebas TOST son significativas) | TOST (Prueba de Equivalencia) |
| **Superioridad con Margen** | $\delta \leq \Delta$ (No es mejor que $\Delta$) | Rechazar $H_0$ (El efecto es > $\Delta$) | Prueba de una cola ajustada |
