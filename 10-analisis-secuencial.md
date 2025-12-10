---
title: 10. Análisis Secuencial
---


# 10. Análisis Secuencial

## 10.1. El Problema del Muestreo Opcional

En la estadística frecuentista tradicional (Neyman-Pearson), la tasa de error Tipo I ($\alpha$) se garantiza solo si el tamaño de la muestra ($N$) se fija *antes* de observar cualquier dato.

El **muestreo opcional** (o detenerse cuando el valor $p$ es significativo) ocurre cuando el investigador monitorea los datos y detiene la recolección tan pronto como se alcanza la significación. Este procedimiento **infla artificialmente la tasa de error Tipo I ($\alpha$)**, lo que lleva a un mayor riesgo de falsos positivos.

El análisis secuencial es una familia de métodos que permiten al investigador monitorear los datos y detener la recolección de manera **planificada** sin inflar el $\alpha$.

## 10.2. Análisis Secuencial Frecuentista (Sequential Analysis, SA)

El análisis secuencial frecuentista divide la recolección de datos en etapas planificadas, con reglas de parada predefinidas para cada etapa.

### 10.2.1. El Procedimiento de Pocock

El procedimiento de Pocock utiliza un umbral de significancia más estricto ($\alpha_{ajustado}$) que es el mismo en cada etapa de análisis. Esto asegura que la tasa de error Tipo I general (FWER) se mantenga en el nivel deseado (ej., $\alpha = 0.05$).

### 10.2.2. El Procedimiento de O'Brien-Fleming

El procedimiento de O'Brien-Fleming es más conservador en las etapas iniciales y se vuelve menos estricto en las etapas posteriores. Esto es útil porque la mayoría de los estudios grandes tienen un buen conocimiento de la potencia en las etapas posteriores.

La esencia de los enfoques SA es establecer los **límites de parada** (stopping boundaries) en un gráfico de diseño secuencial , que definen cuándo la evidencia es suficientemente fuerte para detenerse (ya sea para rechazar $H_0$ o, en diseños más complejos, para mantener $H_0$).

**Ventaja del SA Frecuentista:** Es muy eficiente, ya que el tamaño esperado de la muestra es a menudo mucho menor que el de un estudio de tamaño fijo con la misma potencia.

## 10.3. Análisis Secuencial Bayesiano

El enfoque Bayesiano ofrece la solución más elegante y flexible al problema del muestreo opcional. Como se mencionó en el Capítulo 4, el Factor de Bayes ($BF$) y la distribución a posteriori **no se ven afectados por la regla de parada o la intención de muestreo**.

Esto significa que un investigador puede monitorear el $BF$ o el Intervalo de Credibilidad continuamente y detenerse en cualquier momento, una vez que la evidencia alcance un umbral preespecificado (por ejemplo, $BF_{10} \geq 10$ o $BF_{01} \geq 10$).

### 10.3.1. Reglas de Parada Bayesianas

Los investigadores pueden establecer reglas de parada claras, como:

* **Evidencia a favor de $H_1$:** Detenerse si $BF_{10}$ es mayor que un umbral alto (ej., 10).
* **Evidencia a favor de $H_0$:** Detenerse si $BF_{01}$ es mayor que un umbral alto (ej., 10), lo que permite concluir la evidencia a favor de la ausencia de efecto, de forma similar a TOST.

El monitoreo Bayesiano permite al investigador detener la recolección tan pronto como se resuelve la pregunta, lo que es eficiente y ético.

## 10.4. Análisis Secuencial para Pruebas de Equivalencia (TOST)

El análisis secuencial también se puede aplicar a las Pruebas de Equivalencia (Capítulo 9). El investigador puede monitorear los datos y detenerse cuando el Intervalo de Confianza (generalmente el IC del $90\%$) cae completamente dentro del margen de equivalencia preespecificado ($\Delta$).

## 10.5. Importancia de la Planificación

Tanto el SA frecuentista como el bayesiano son poderosos, pero **ambos requieren un plan de análisis preespecificado**.

Para el SA frecuentista, se deben preespecificar las etapas y los límites de $\alpha$. Para el enfoque Bayesiano, se deben preespecificar los umbrales de $BF$ (o precisión) para la parada. 

La belleza del análisis secuencial es que permite tomar una decisión informada lo antes posible, maximizando la eficiencia de la investigación y el uso ético de los recursos, siempre que la regla de parada sea parte del plan de registro (Capítulo 13).
