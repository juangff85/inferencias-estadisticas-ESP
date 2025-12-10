---
title: 8. Justificación del Tamaño de la Muestra
---


# 8. Justificación del Tamaño de la Muestra

## 8.1. ¿Por qué justificar el tamaño de la muestra?

La justificación del tamaño de la muestra es el paso en el que un investigador explica por qué decidió utilizar un número particular de observaciones ($N$). No se trata simplemente de un requisito ético o de publicación, sino de una parte crucial para lograr la **informatividad** del estudio.

Un estudio es informativo solo si tiene la capacidad de distinguir resultados de interés de resultados que no lo son. Un tamaño de muestra debe garantizar que:

1.  Se minimiza el riesgo de errores Tipo II (Potencia adecuada) para detectar un efecto de interés.
2.  El intervalo de estimación del parámetro (IC o ICred) es lo suficientemente estrecho para ser útil (Precisión adecuada).

## 8.2. Enfoques para la Justificación del Tamaño de la Muestra

Existen seis enfoques principales para justificar el tamaño de la muestra:

### 8.2.1. Planificación basada en el Control de Errores (Análisis de Potencia)

Este es el enfoque más común y se alinea con el marco de Neyman-Pearson (Capítulo 1). Se planifica el tamaño de la muestra para lograr una potencia estadística específica (típicamente $1 - \beta = 0.80$ o $0.90$) para detectar un **Tamaño del Efecto de Interés (ESOI)** previamente especificado.

* **Requisitos:**
    1.  Nivel de significancia ($\alpha$, generalmente $0.05$).
    2.  Potencia deseada ($1 - \beta$, generalmente $0.80$).
    3.  El **ESOI** (el tamaño del efecto más pequeño que se considera importante y que se desea detectar).

Si el estudio tiene la potencia adecuada para detectar el ESOI, entonces un resultado no significativo es más informativo que si el estudio tuviera baja potencia. 

### 8.2.2. Planificación basada en la Precisión (AIPE)

El enfoque **Accuracy in Parameter Estimation (AIPE)** planifica el tamaño de la muestra para que el **Intervalo de Confianza (IC)** resultante sea de una anchura preespecificada.

* **Requisitos:**
    1.  Nivel de confianza ($1 - \alpha$, generalmente $0.95$).
    2.  Anchura deseada del IC.

AIPE es ideal cuando el objetivo principal del estudio es la **estimación precisa** del tamaño del efecto, en lugar de la simple prueba de hipótesis nula.

### 8.2.3. Uso de Recursos o Restricciones

A veces, el tamaño de la muestra está limitado por recursos prácticos (tiempo, dinero, disponibilidad de población). En este caso, la justificación consiste en mostrar el **ESOI más pequeño que el estudio tiene potencia para detectar** con el $N$ disponible, o la **precisión** que se puede lograr.

* **Conclusión:** Si el ESOI que se puede detectar es demasiado grande para ser práctico, el estudio es inherentemente poco informativo.

### 8.2.4. Justificación Basada en la Adición de un Participante

Este enfoque es común en los estudios que añaden datos a colecciones existentes (por ejemplo, grandes bases de datos). La justificación es que el muestreo se detiene una vez que se han recogido todos los datos disponibles.

### 8.2.5. Análisis Secuencial

El muestreo se detiene cuando la evidencia es lo suficientemente fuerte para tomar una decisión (ya sea rechazar $H_0$ o aceptar $H_0$). Este enfoque es eficiente porque el muestreo no continúa más allá de lo necesario. (Ver Capítulo 10).

### 8.2.6. No hay justificación explícita

En algunos casos, el investigador puede no tener una justificación formal. Es crucial ser transparente sobre esto y discutir las implicaciones de la falta de potencia o precisión del estudio.

## 8.3. Especificación del Tamaño del Efecto de Interés (ESOI)

El paso más crítico en la justificación del tamaño de la muestra es la elección del ESOI para el análisis de potencia. Las opciones para seleccionar el ESOI incluyen:

1.  **El efecto más pequeño de interés práctico (MPE):** Basado en el costo, beneficio o importancia clínica.
2.  **El efecto esperado (o meta-analítico):** Basado en la literatura existente, preferiblemente de un meta-análisis (Capítulo 11).
3.  **El efecto de Convención (Ejemplo: $d = 0.50$ de Cohen):** Este es el método menos deseable, ya que las convenciones de Cohen suelen ignorar el contexto y el campo de estudio.

Una justificación sólida debe demostrar que el tamaño de la muestra es adecuado para el ESOI más pequeño que el investigador considera importante.

## 8.4. Realizar la Justificación y Reportarla

La justificación de la muestra debe ser un informe detallado que explique:

* El enfoque utilizado (Potencia, AIPE, o Recursos).
* La razón para el nivel $\alpha$ y la potencia ($1 - \beta$) elegida.
* La base empírica y teórica para el **ESOI** elegido.
* El cálculo exacto que llevó al $N$ final.

Una justificación de la muestra que se basa en recursos limitados solo es informativa si el investigador también realiza un **análisis de sensibilidad** para mostrar qué ES puede detectar el estudio con esa limitación de recursos.
