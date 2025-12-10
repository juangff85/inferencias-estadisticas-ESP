# 5. Formulando Preguntas Estadísticas

## 5.1. Tres tipos de preguntas estadísticas

Una investigación sólida comienza con la formulación clara de la pregunta. En estadística, las preguntas de investigación suelen caer en una de estas tres categorías:

1.  **¿Existe un efecto?** (Énfasis en la significancia)
2.  **¿Cuál es el tamaño del efecto?** (Énfasis en la estimación)
3.  **¿Qué hipótesis es más probable a la luz de los datos?** (Énfasis en la comparación de modelos o evidencia)

### 5.1.1. Pregunta 1: ¿Existe un efecto? (Prueba de Significación)

Este es el enfoque tradicional de la **Prueba de Hipótesis de Significación Nula (NHST)**, que se centra en rechazar la hipótesis nula ($H_0$).

* **Ejemplo:** ¿La nueva droga mejora el tiempo de reacción?
* **Hipótesis:** $H_0: \mu_1 = \mu_2$ (No hay diferencia) vs. $H_1: \mu_1 \neq \mu_2$ (Hay diferencia).
* **Herramienta:** El valor $p$ y el control del error Tipo I ($\alpha$).

Este enfoque tiene una limitación clave: la hipótesis nula de cero es casi siempre falsa en el mundo real, lo que hace que la pregunta de si *existe* un efecto sea trivialmente respondida con una muestra lo suficientemente grande. Sin embargo, sigue siendo útil para tomar decisiones binarias (sí/no) con errores controlados.

### 5.1.2. Pregunta 2: ¿Cuál es el tamaño del efecto? (Estimación)

Este enfoque se centra en la precisión de la medición y en estimar el valor del parámetro (por ejemplo, la media, la diferencia de medias, la correlación).

* **Ejemplo:** ¿Cuál es el rango de beneficios que podemos esperar de la nueva droga con un 95% de confianza?
* **Herramienta:** Intervalos de Confianza (Capítulo 7) o Intervalos de Credibilidad (Capítulo 4).
* **Objetivo:** Proporcionar el mejor estimado puntual (por ejemplo, $d = 0.50$) junto con un intervalo que refleje la incertidumbre (por ejemplo, $[0.20, 0.80]$).

### 5.1.3. Pregunta 3: ¿Qué hipótesis es más probable? (Evidencia)

Este enfoque se centra en la fuerza de la evidencia que los datos proporcionan para dos modelos alternativos, no solo en un solo modelo nulo.

* **Ejemplo:** ¿Los datos proporcionan más apoyo para la hipótesis de un efecto moderado ($H_1$) o para la hipótesis nula de ningún efecto ($H_0$)?
* **Herramienta:** El Factor de Bayes ($BF$) (Capítulo 4) o la Razón de Verosimilitud (Capítulo 3).
* **Objetivo:** Cuantificar la evidencia relativa para un modelo sobre otro, sin forzar una decisión binaria.

## 5.2. El problema de la "Dicotomía de la Significación"

Uno de los principales problemas al formular preguntas estadísticas es caer en la **Dicotomía de la Significación**, donde se trata la significación estadística ($p < \alpha$) como la única medida de interés. Esto lleva a:

* **Interpretar erróneamente un resultado no significativo ($p \geq \alpha$)** como evidencia de la ausencia de efecto, ignorando la posibilidad de error Tipo II (falta de potencia).
* **Interpretar erróneamente un resultado significativo ($p < \alpha$)** como un efecto grande o importante, ignorando la importancia práctica (tamaño del efecto).

## 5.3. Preguntas de intervalo e hipótesis de equivalencia

Para ir más allá de la pregunta simple "¿Existe un efecto?", los investigadores pueden formular preguntas sobre un rango o intervalo de valores.

### 5.3.1. Pruebas de Equivalencia (Equivalence Testing)

Las pruebas de equivalencia invierten la $H_0$. En lugar de asumir que no hay efecto ($H_0: \delta = 0$), asumen que hay un efecto que es *demasiado grande* para considerarse equivalente al cero.

* **Hipótesis:** $H_0: |\delta| \geq \Delta$ (El efecto es mayor o igual a $\Delta$, es decir, *no* es equivalente a cero) vs. $H_1: |\delta| < \Delta$ (El efecto está dentro del margen $\pm\Delta$, es decir, es equivalente a cero).
* **Propósito:** Demostrar que un efecto, si existe, es tan pequeño que no tiene importancia práctica (o es equivalente a un control o estándar). 

Las pruebas de equivalencia permiten responder a la pregunta: **"¿El efecto es suficientemente pequeño para ser ignorado?"** o **"¿Mi nuevo tratamiento es equivalente al tratamiento estándar?"** (Esto se discute en profundidad en el Capítulo 9).

### 5.3.2. Hipótesis de Intervalo

Las hipótesis de intervalo se utilizan para probar si el verdadero valor del parámetro se encuentra dentro de un rango específico de interés. Permiten al investigador probar su hipótesis de que el tamaño del efecto no es exactamente cero, sino que se encuentra dentro de un rango significativo específico (por ejemplo, $\delta \in [0.20, 0.50]$).

## 5.4. Conclusión

Para mejorar la inferencia, es crucial que los investigadores formulen preguntas más allá de la dicotomía de la significación:

* En lugar de solo "¿El $p$ es menor que $0.05$?", pregunte: **"¿Qué tan grande es el efecto?"** (Estimación).
* En lugar de solo rechazar $H_0$, pregunte: **"¿Los datos apoyan más la hipótesis nula o la alternativa?"** (Evidencia Bayesiana).
* Para demostrar la ausencia de un efecto importante, pregunte: **"¿El efecto es menor que el umbral de importancia práctica?"** (Prueba de Equivalencia).

Estas preguntas requieren herramientas más avanzadas (Capítulos 6, 7 y 9), pero conducen a conclusiones científicas más robustas.
