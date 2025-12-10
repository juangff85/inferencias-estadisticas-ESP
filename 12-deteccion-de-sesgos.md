---
layout: default
title: Detección de Sesgos
nav_order: 13
---
# 12. Detección de Sesgos

La validez de la inferencia estadística depende de la calidad de los datos y de los procedimientos utilizados para obtenerlos. El **sesgo** en la investigación se refiere a cualquier desviación sistemática de la verdad en la recopilación, análisis, interpretación o publicación de los resultados.

## 12.1. Sesgo de Publicación (Publication Bias)

El sesgo de publicación es quizás el sesgo más conocido y sistemático que afecta a la literatura científica, especialmente en campos que dependen en gran medida del valor $p$.

* **Definición:** Ocurre cuando la probabilidad de que un estudio sea publicado depende de la naturaleza y la dirección de sus hallazgos (por ejemplo, los estudios con resultados estadísticamente significativos ($p < 0.05$) y en la dirección esperada tienen más probabilidades de ser publicados que los estudios con resultados no significativos).
* **Efecto:** El sesgo de publicación hace que las estimaciones publicadas del tamaño del efecto sean sistemáticamente **sobreestimadas** y sesgadas positivamente.

### 12.1.1. Herramientas para la Detección del Sesgo de Publicación

1.  **Diagrama de Embudo (Funnel Plot):** Es la herramienta gráfica más utilizada en el meta-análisis (Capítulo 11) para evaluar el sesgo. Un diagrama de embudo traza el tamaño del efecto (eje X) frente a la precisión o el error estándar (eje Y) de los estudios.
    * **Ausencia de Sesgo:** Los estudios se distribuyen simétricamente alrededor del tamaño del efecto combinado, formando un embudo invertido. 
    * **Presencia de Sesgo:** Si faltan estudios no significativos de baja potencia (los que estarían en la parte inferior izquierda o derecha del embudo), el gráfico parece asimétrico, sugiriendo sesgo de publicación.
2.  **Pruebas de Egger y Begg:** Pruebas estadísticas formales que evalúan la asimetría del diagrama de embudo.

## 12.2. $p$-Hacking (Data-dependent analysis)

El **$p$-hacking** es una forma de sesgo que ocurre cuando los investigadores ajustan de manera flexible los procedimientos de recolección o análisis de datos hasta que se alcanza el umbral de significación estadística ($p < 0.05$).

Ejemplos de $p$-hacking incluyen:
* Excluir puntos de datos después de mirar los resultados.
* Recolectar más datos después de un análisis inicial no significativo (muestreo opcional no planificado).
* Probar múltiples variables dependientes y reportar solo las significativas.
* Usar diferentes análisis estadísticos hasta que uno sea significativo.

El $p$-hacking infla la tasa de error Tipo I ($\alpha$) del estudio.

### 12.2.1. Herramientas para la Detección de $p$-Hacking

1.  **Distribución de $p$-valores (p-curve):** Bajo la hipótesis nula, los valores $p$ están distribuidos uniformemente (Capítulo 1). Si hay un efecto real, la distribución de los $p$-valores debe estar sesgada hacia valores pequeños. El *p-curve* analiza la forma de la distribución de los $p$-valores en un conjunto de estudios. 
    * Una acumulación inusual de $p$-valores justo por debajo de $0.05$ (ej., entre $0.04$ y $0.05$) es una señal de advertencia de posible $p$-hacking.
2.  **Análisis de Sensibilidad de Muestreo Opcional:** Evaluar si la significación depende de la regla de parada o si el efecto se mantiene estable a medida que se añaden más datos.

## 12.3. HARKing (Hypothesizing After the Results are Known)

**HARKing** (Formular Hipótesis Después de Conocer los Resultados) es el sesgo de presentar una hipótesis *exploratoria* (descubierta después del análisis de datos) como si fuera una hipótesis *confirmatoria* (establecida antes del análisis de datos).

* **Efecto:** Distorsiona el proceso científico y la confianza que se le debe dar al hallazgo, ya que infla la probabilidad de que los resultados significativos sean simplemente coincidencias.

## 12.4. Estrategias de Mitigación

La mejor defensa contra la mayoría de las formas de sesgo (especialmente el $p$-hacking y el HARKing) es la **Transparencia** y el **Prerregistro** del estudio (Capítulo 13).

* **Prerregistro:** Al preespecificar el plan de análisis, el $N$ de la muestra y las hipótesis antes de la recolección de datos, se convierte en imposible el $p$-hacking.
* **Informar Todos los Resultados:** Publicar estudios nulos (que a menudo se logran al hacer la investigación con alta potencia, como se discute en el Capítulo 8) mitiga el sesgo de publicación.
* **Datos Abiertos:** Compartir el conjunto de datos y el código (Capítulo 14) permite que otros investigadores evalúen la flexibilidad en los análisis y confirmen la validez de los procedimientos.
