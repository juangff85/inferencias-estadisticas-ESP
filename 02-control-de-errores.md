---
layout: default
title: Verosimilitudes
nav_order: 4 # (Después del 2 y el 3)
---
# 2. Control de errores

## 2.1. Tasas de error de la prueba

Cuando utilizamos el enfoque de Neyman-Pearson, nuestro objetivo es controlar las tasas de error a largo plazo.

El **error Tipo I ($\alpha$)** es la probabilidad de rechazar la hipótesis nula ($H_0$) cuando $H_0$ es verdadera. La tasa de error Tipo I se controla al establecer el nivel $\alpha$ para nuestra prueba (típicamente $\alpha = 0.05$).

El **error Tipo II ($\beta$)** es la probabilidad de no rechazar la hipótesis nula ($H_0$) cuando la hipótesis alternativa ($H_1$) es verdadera. La probabilidad de evitar un error Tipo II se llama **potencia estadística** ($1 - \beta$).

En los diseños de investigación, buscamos un equilibrio entre controlar el error Tipo I y maximizar la potencia (es decir, minimizar el error Tipo II).

| Decisión | $H_0$ es Verdadera | $H_0$ es Falsa ($H_1$ es Verdadera) |
| :--- | :--- | :--- |
| **Rechazar $H_0$** | **Error Tipo I ($\alpha$)** (Falso Positivo) | **Decisión Correcta** (Potencia $1-\beta$) |
| **Mantener $H_0$** | **Decisión Correcta** | **Error Tipo II ($\beta$)** (Falso Negativo) |



## 2.2. Error por experimento (Error-per-experiment)

En la mayoría de los estudios, realizamos solo una prueba de hipótesis estadística para tomar una decisión clave (por ejemplo, comparar dos grupos de tratamiento). Si establecemos $\alpha = 0.05$, controlamos la tasa de error Tipo I en el $5\%$ para ese experimento o prueba individual. Esto se denomina **tasa de error por experimento**.

Si el investigador realiza múltiples pruebas en un solo estudio, el control de errores se vuelve más complicado.

## 2.3. Error familiar (Family-wise error)

El **error familiar (Family-wise Error Rate, FWER)** es la probabilidad de cometer al menos un error Tipo I en una **familia** (o conjunto) de pruebas de hipótesis relacionadas.

Si realizas $k$ pruebas independientes, cada una con un $\alpha = 0.05$, la probabilidad de no cometer un error Tipo I en ninguna de ellas es $(1 - \alpha)^k$.

Por lo tanto, la FWER es:

$$FWER = 1 - (1 - \alpha)^k$$

Si se realizan 5 pruebas independientes (donde $k=5$), la probabilidad de cometer al menos un error Tipo I es:
$1 - (1 - 0.05)^5 \approx 0.226$
Esto significa que la probabilidad de un falso positivo se dispara al $22.6\%$, que es mucho más alta que el $\alpha = 0.05$ deseado.

Para controlar la FWER en $\alpha$ (típicamente $0.05$), se deben aplicar correcciones al nivel $\alpha$ para cada prueba individual.

### 2.3.1. Corrección de Bonferroni

El método más común para controlar la FWER es la **Corrección de Bonferroni**.

La corrección ajusta el $\alpha$ por prueba ($\alpha_{ajustado}$) dividiendo el nivel de significancia deseado ($\alpha_{FWER}$) por el número de pruebas ($k$):

$$\alpha_{ajustado} = \frac{\alpha_{FWER}}{k}$$

Si realizamos 5 pruebas y queremos una FWER de $0.05$:

$$\alpha_{ajustado} = \frac{0.05}{5} = 0.01$$

Ahora, solo rechazaríamos $H_0$ para cualquier prueba individual si $p < 0.01$.

* **Ventajas:** Es simple y muy conservador.
* **Desventajas:** Puede ser demasiado conservador, reduciendo la potencia para detectar efectos reales.

### 2.3.2. Otros métodos de control de FWER

Existen otros métodos más sofisticados que pueden ofrecer un mejor equilibrio entre el control del Tipo I y la potencia, especialmente cuando las pruebas son dependientes o están correlacionadas:

* **Procedimiento de Holm:** Un procedimiento secuencial paso a paso que mantiene la FWER y es uniformemente más potente que Bonferroni.
* **Corrección de Tukey's HSD:** Comúnmente utilizado para comparaciones por pares *post hoc* después de un ANOVA.
* **Corrección de Scheffé:** Útil para controlar todas las comparaciones posibles, pero muy conservador.

## 2.4. Tasa de Falso Descubrimiento (False Discovery Rate, FDR)

Controlar la FWER es crucial cuando no se toleran errores Tipo I, por ejemplo, en ensayos clínicos donde un falso positivo podría llevar a tratamientos ineficaces o dañinos.

Sin embargo, en la investigación exploratoria o en campos con muchas pruebas (como la Genética), los investigadores a menudo controlan la **Tasa de Falso Descubrimiento (FDR)**.

La FDR es la proporción esperada de **falsos positivos** (descubrimientos incorrectos) entre el total de descubrimientos (pruebas significativas).

$$FDR = E \left[ \frac{V}{R} \right]$$

Donde:
* $V$ es el número de falsos positivos (pruebas significativas donde $H_0$ es verdadera).
* $R$ es el número total de resultados rechazados (pruebas significativas).

Controlar la FDR es un enfoque más permisivo que controlar la FWER, ya que permite más errores Tipo I a cambio de una mayor potencia. El procedimiento más popular para controlar la FDR es el de **Benjamini-Hochberg (BH)**.

## 2.5. Recomendaciones para el control de errores

La elección de la tasa de error a controlar depende de los objetivos de la investigación:

* **Para estudios confirmatorios** con un número limitado de hipótesis primarias: Se recomienda el **control FWER** (usando Holm o Bonferroni) para asegurar un alto nivel de confianza en cada conclusión individual.
* **Para estudios exploratorios** donde el objetivo es generar nuevas hipótesis o identificar un gran número de posibles efectos: El **control FDR** (usando BH) es a menudo más apropiado para maximizar el descubrimiento sin abrumarse por falsos positivos.
