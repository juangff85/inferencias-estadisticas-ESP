---
layout: default
title: Verosimilitudes
nav_order: 4
---
# 3. Verosimilitudes

## 3.1. Introducción a la verosimilitud

El enfoque del valor $p$ y el de Neyman-Pearson se centran en la probabilidad de los datos *dada* la hipótesis nula ($P(\text{Datos} | H_0)$). Un enfoque alternativo que se centra en cuán probables son los datos *bajo diferentes hipótesis* es el enfoque de la **verosimilitud**.

La **función de verosimilitud** ($\mathcal{L}$) mide la plausibilidad de un valor de parámetro dado, una vez que se han observado los datos.

Una idea clave de la verosimilitud es el **Principio de Verosimilitud**: Todos los resultados de la inferencia estadística sobre un parámetro deben basarse únicamente en la función de verosimilitud.

La verosimilitud de una hipótesis o parámetro ($\theta$), dados los datos observados ($D$), se define como la probabilidad de observar esos datos, dada la hipótesis:

$$\mathcal{L}(\theta | D) = P(D | \theta)$$

**Importante:** La verosimilitud ($\mathcal{L}$) no es una probabilidad de la hipótesis. Las probabilidades suman 1; la verosimilitud solo es una medida relativa de cuán bien un parámetro predice los datos observados.

## 3.2. Razón de Verosimilitud (Likelihood Ratio)

Dado que la verosimilitud absoluta es difícil de interpretar, a menudo utilizamos la **Razón de Verosimilitud (Likelihood Ratio, $LR$)** para comparar dos hipótesis (o parámetros) diferentes:

$$LR = \frac{\mathcal{L}(\theta_1 | D)}{\mathcal{L}(\theta_2 | D)} = \frac{P(D | \theta_1)}{P(D | \theta_2)}$$

* Si $LR = 5$, los datos observados son 5 veces más probables si $\theta_1$ es verdadera que si $\theta_2$ es verdadera.
* Si $LR = 0.2$, los datos observados son 5 veces más probables si $\theta_2$ es verdadera que si $\theta_1$ es verdadera ($1/0.2 = 5$).

La razón de verosimilitud proporciona una medida de la **fuerza relativa de la evidencia** que los datos aportan en favor de una hipótesis sobre otra.

## 3.3. Estimación de Máxima Verosimilitud (Maximum Likelihood Estimation, MLE)

Una aplicación fundamental de la verosimilitud es la **Estimación de Máxima Verosimilitud (MLE)**.

El estimador de máxima verosimilitud ($\hat{\theta}_{MLE}$) es el valor del parámetro ($\theta$) que hace que los datos observados sean **más probables** (es decir, el que maximiza la función de verosimilitud).

$$\hat{\theta}_{MLE} = \text{arg} \max_{\theta} \mathcal{L}(\theta | D)$$

Los estimadores de MLE son deseables porque tienen varias propiedades asintóticas (cuando el tamaño de la muestra es grande): son consistentes, eficientes y están distribuidos normalmente. Muchos métodos estadísticos (incluyendo la regresión lineal y logística) utilizan MLE para encontrar los mejores ajustes para sus modelos.

## 3.4. El Teorema de la Razón de Verosimilitud (Likelihood Ratio Test)

La razón de verosimilitud también se utiliza para realizar pruebas de hipótesis, conocidas como **Pruebas de Razón de Verosimilitud (LRT)**.

La LRT compara la verosimilitud de un modelo restringido (generalmente correspondiente a $H_0$) con la verosimilitud de un modelo menos restringido o más complejo (generalmente correspondiente a $H_1$).

El estadístico de prueba (a menudo denotado como $G^2$ o $\Lambda$) a menudo se calcula como:

$$\Lambda = -2 \ln \left( \frac{\mathcal{L}(\text{Modelo restringido} | D)}{\mathcal{L}(\text{Modelo no restringido} | D)} \right)$$

Bajo $H_0$, este estadístico de prueba se distribuye aproximadamente como una distribución **chi-cuadrado ($\chi^2$)**, con grados de libertad iguales a la diferencia en el número de parámetros entre los dos modelos. Esto permite calcular un valor $p$ y tomar una decisión en el marco de Neyman-Pearson.

## 3.5. Comparación de Verosimilitud y el valor $p$

| Característica | Enfoque del valor $p$ (NP) | Enfoque de la Razón de Verosimilitud (LR) |
| :--- | :--- | :--- |
| **Pregunta principal** | ¿Son los datos compatibles con $H_0$? | ¿Qué hipótesis predice mejor los datos? |
| **Medida** | Probabilidad de los datos bajo $H_0$ ($P(\text{Datos} | H_0)$) | Razón de la probabilidad de los datos bajo $H_1$ y $H_0$ ($\frac{P(D | H_1)}{P(D | H_0)}$) |
| **Conclusión** | Decisión binaria (Rechazar/Mantener $H_0$) | Evidencia relativa continua a favor de una hipótesis sobre otra |
| **Control de errores** | Control de $\alpha$ y $\beta$ a largo plazo | No controla directamente las tasas de error Tipo I o Tipo II |

La verosimilitud ofrece una forma intuitiva de cuantificar la evidencia sin necesidad de un umbral fijo como $\alpha$. Proporciona una medida de evidencia **relativa** que, a diferencia del valor $p$, se interpreta de la misma manera independientemente de la intención de muestreo o la regla de parada.
