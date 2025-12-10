# 4. Estadística Bayesiana

La estadística Bayesiana ofrece un marco alternativo a los enfoques de Neyman-Pearson y del valor $p$. La inferencia Bayesiana se centra en la **probabilidad de las hipótesis** o de los parámetros, en lugar de la probabilidad de los datos.

## 4.1. El Teorema de Bayes

El corazón de la estadística Bayesiana es el **Teorema de Bayes**. Este teorema proporciona una manera de actualizar nuestras creencias sobre una hipótesis (o un parámetro) a la luz de los nuevos datos.

La probabilidad de una hipótesis ($H$) dados los datos ($D$), la **probabilidad a posteriori**, es proporcional a la probabilidad de los datos dada la hipótesis, multiplicada por la probabilidad de la hipótesis antes de ver los datos:

$$P(H | D) = \frac{P(D | H) P(H)}{P(D)}$$

Donde:

* $P(H | D)$ es la **Probabilidad a Posteriori** (la probabilidad de la hipótesis después de ver los datos).
* $P(D | H)$ es la **Verosimilitud** (la probabilidad de observar los datos dada la hipótesis $H$).
* $P(H)$ es la **Probabilidad a Priori** (nuestra creencia inicial en la hipótesis antes de ver los datos).
* $P(D)$ es la probabilidad marginal de los datos (una constante de normalización).

## 4.2. Pasos en la Inferencia Bayesiana

La inferencia Bayesiana se puede resumir en un proceso de tres pasos:

1.  **Establecer la Priori ($P(H)$)**: El investigador debe especificar una distribución de probabilidad que represente sus creencias sobre la hipótesis o el parámetro antes de que se recojan los datos. Esta *priori* puede ser informativa (basada en conocimientos previos) o no informativa (que expresa incertidumbre).
2.  **Calcular la Verosimilitud ($P(D | H)$)**: Esto es idéntico a la función de verosimilitud utilizada en el Capítulo 3. Mide qué tan bien la hipótesis predice los datos observados.
3.  **Calcular la Posteriori ($P(H | D)$)**: Se combina la *priori* y la verosimilitud usando el Teorema de Bayes para producir la distribución de probabilidad a *posteriori*, la cual representa las creencias actualizadas después de ver los datos. 

## 4.3. El Factor de Bayes (Bayes Factor, $BF$)

En el enfoque Bayesiano, para comparar dos hipótesis, a menudo se utiliza el **Factor de Bayes ($BF$)**.

El $BF$ es la razón de la verosimilitud marginal de la hipótesis alternativa ($H_1$) frente a la hipótesis nula ($H_0$):

$$BF_{10} = \frac{P(D | H_1)}{P(D | H_0)}$$

El Factor de Bayes representa la medida en que los datos cambian la razón de probabilidades *a priori* de $H_1$ frente a $H_0$ a la razón de probabilidades *a posteriori*.

$$\frac{P(H_1 | D)}{P(H_0 | D)} = \frac{P(D | H_1)}{P(D | H_0)} \times \frac{P(H_1)}{P(H_0)}$$

$$(\text{Razón a Posteriori}) = (\text{Factor de Bayes}) \times (\text{Razón a Priori})$$

**Interpretación del $BF_{10}$:**

* $BF_{10} = 1$: Los datos son igualmente probables bajo ambas hipótesis.
* $BF_{10} = 10$: Los datos son 10 veces más probables bajo $H_1$ que bajo $H_0$. Esto proporciona evidencia fuerte a favor de $H_1$.
* $BF_{10} = 0.10$: Los datos son 10 veces más probables bajo $H_0$ que bajo $H_1$. Esto proporciona evidencia fuerte a favor de $H_0$.

El Factor de Bayes puede cuantificar la evidencia a favor de la $H_0$, algo que el enfoque del valor $p$ no puede hacer directamente.

## 4.4. Ventajas de la Estadística Bayesiana

1.  **Evidencia a favor de $H_0$:** Permite cuantificar la evidencia a favor de la hipótesis nula ($H_0$), no solo evidencia *contra* ella.
2.  **Inclusión de Conocimiento Previo:** Incorpora explícitamente el conocimiento previo a través de la distribución *a priori*.
3.  **Inferencia directa:** Proporciona inferencias directas sobre la probabilidad de los parámetros o hipótesis. Por ejemplo, se puede afirmar: "Existe una probabilidad del 95% de que el tamaño del efecto se encuentre entre X e Y" (Intervalo de Credibilidad).
4.  **Monitoreo de datos flexible:** Los análisis pueden monitorearse continuamente (análisis secuencial) sin que esto infle la tasa de error Tipo I, ya que el Teorema de Bayes no se ve afectado por la intención de parada o el plan de muestreo. (Esto se aborda en el Capítulo 10).

## 4.5. Intervalos de Credibilidad (Credible Intervals)

En el enfoque Bayesiano, el equivalente al Intervalo de Confianza (Capítulo 7) es el **Intervalo de Credibilidad (Credible Interval, CI)**.

Mientras que un Intervalo de Confianza del 95% establece que, si repitiéramos el experimento muchas veces, el $95\%$ de los intervalos resultantes contendrían el verdadero valor del parámetro, un Intervalo de Credibilidad del 95% es una afirmación directa: **existe una probabilidad del 95% de que el valor real del parámetro se encuentre dentro de este intervalo**.

El Intervalo de Credibilidad se deriva directamente de la distribución *a posteriori* y tiene una interpretación mucho más intuitiva.
