---
layout: default
title: Usando valores p para probar una hipótesis # Título en la barra lateral
nav_order: 2  # ¡Importante! Debe ser un número único y secuencial.
              # "index.md" es el 1, este es el 2, el siguiente será el 3, etc.
---
# 1. Usando valores p para probar una hipótesis

## 1.1. Introducción al enfoque de prueba de hipótesis de Neyman-Pearson

Cuando se utiliza el valor $p$ para tomar decisiones sobre las hipótesis, a menudo se hace referencia al enfoque de la **prueba de hipótesis de Neyman-Pearson (NP)**. En el enfoque NP, la meta principal es controlar la probabilidad de diferentes tipos de errores. Este enfoque requiere que el investigador especifique dos hipótesis mutuamente excluyentes:

1.  La **hipótesis nula ($H_0$)**: Representa el *statu quo* o la ausencia de un efecto. Se asume que es verdadera a menos que la evidencia empírica la contradiga fuertemente.
2.  La **hipótesis alternativa ($H_1$)**: Representa el efecto o la diferencia que el investigador espera o desea demostrar.

El enfoque NP te obliga a especificar un umbral, **alfa ($\alpha$)**, *antes* de la recopilación de datos. Alfa es la tasa de error Tipo I a largo plazo que el investigador está dispuesto a aceptar. El error Tipo I ocurre cuando el investigador **rechaza una $H_0$ verdadera**.

En el contexto de las pruebas $t$, la $H_0$ es usualmente un valor específico (por ejemplo, una diferencia de medias de cero, $\mu_1 - \mu_2 = 0$). La $H_1$ puede ser direccional (por ejemplo, $\mu_1 > \mu_2$) o no direccional (por ejemplo, $\mu_1 \neq \mu_2$).

## 1.2. El valor $p$ y su distribución bajo $H_0$

El valor $p$ es la probabilidad de observar un resultado tan extremo o más extremo que el que se ha observado, **asumiendo que la hipótesis nula ($H_0$) es verdadera**.

Si $H_0$ es verdadera, el valor $p$ está **uniformemente distribuido** entre 0 y 1. Esto significa que es igualmente probable que se obtenga cualquier valor $p$ entre 0 y 1 si no hay un efecto real. 

$$P(p \leq x | H_0) = x$$

donde $x$ es cualquier número entre 0 y 1. Si realizas un gran número de experimentos en los que $H_0$ es verdadera, rechazarás $H_0$ el $5\%$ de las veces si estableces $\alpha = 0.05$.

## 1.3. La regla de decisión de Neyman-Pearson

En el enfoque NP, la decisión se basa en comparar el valor $p$ con $\alpha$:

* Si $p < \alpha$, el resultado se considera **estadísticamente significativo** y se **rechaza $H_0$**.
* Si $p \geq \alpha$, el resultado se considera **no significativo** y se **mantiene $H_0$** (o se "no se rechaza").

Si rechazas $H_0$ cuando $p < \alpha$, tienes una tasa de error Tipo I a largo plazo controlada en $\alpha$.

## 1.4. Errores Tipo II y Potencia (Power)

El error Tipo I ($\alpha$) es rechazar una $H_0$ que es verdadera.

El **error Tipo II ($\beta$)** es **mantener una $H_0$ que es falsa** (es decir, no detectar un efecto que realmente existe). 

La **potencia estadística** o **poder** de una prueba (denotada como $1 - \beta$) es la probabilidad de rechazar correctamente una $H_0$ cuando $H_1$ es verdadera. La potencia depende de tres factores:

1.  **El nivel $\alpha$**: Una $\alpha$ más grande aumenta la potencia.
2.  **El tamaño del efecto (Effect Size, $ES$)**: Un efecto mayor es más fácil de detectar, por lo que aumenta la potencia.
3.  **El tamaño de la muestra ($N$)**: Una muestra más grande aumenta la potencia.

El enfoque NP enfatiza el control de ambos tipos de errores. Sin una justificación del tamaño de la muestra basada en un control de errores adecuado (es decir, alta potencia), el proceso de toma de decisiones está incompleto. Esto se abordará en el Capítulo 8: Justificación del Tamaño de la Muestra.

## 1.5. Malentendidos comunes del valor $p$

Es fundamental entender **lo que el valor $p$ no es**:

1.  **El valor $p$ no es la probabilidad de que $H_0$ sea verdadera.** Es una probabilidad *bajo* la asunción de que $H_0$ es verdadera.
2.  **$1 - p$ no es la probabilidad de que $H_1$ sea verdadera.**
3.  **El valor $p$ no es la probabilidad de que el resultado sea un hallazgo por azar.**

Estos malentendidos son comunes, pero incorrectos. El valor $p$ es una declaración sobre la compatibilidad de los datos con el modelo nulo; **no es una declaración sobre la probabilidad de las hipótesis**. Para obtener la probabilidad de una hipótesis, se requiere un enfoque Bayesiano (Capítulo 4).

## 1.6. ¿Valor $p$ o enfoque de Neyman-Pearson?

Existe debate sobre si los investigadores deben usar el enfoque del **valor $p$** (propuesto por Fisher), que informa la evidencia contra $H_0$, o el enfoque de **Neyman-Pearson** (NP), que se centra en el control de errores a largo plazo.

En la práctica, la comunidad científica suele mezclar ambos:

* Se utiliza el umbral de NP ($\alpha = 0.05$) para tomar una decisión binaria (significativo/no significativo).
* Se informa el valor $p$ exacto (el enfoque de Fisher).

Para mejorar las inferencias, es más útil centrarse en el **control de errores de Neyman-Pearson**, ya que esto obliga a los investigadores a considerar la **potencia** y el **tamaño del efecto de interés** antes de recopilar los datos.
