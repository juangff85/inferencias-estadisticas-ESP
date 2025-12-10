---
layout: default
title: Reproducibilidad Computacional
nav_order: 15
---
# 14. Reproducibilidad como elemento fundamental de la ciencia

## 14.1. Definiciones de Reproducibilidad

La reproducibilidad es un paso esencial para lograr la **verdad** y la **confianza** en los hallazgos científicos. El término se utiliza de diferentes maneras:

1.  **Replicación (Replication):** Un estudio independiente utiliza un nuevo conjunto de datos para intentar confirmar el hallazgo original (Capítulo 17).
2.  **Reproducibilidad Computacional (Computational Reproducibility):** También conocida como **Reproducibilidad del Análisis** o **Re-análisis**. Ocurre cuando un investigador utiliza los mismos datos, código y procedimientos del estudio original y llega al mismo resultado numérico.
3.  **Reproducibilidad Metodológica (Metodological Reproducibility):** La capacidad de un investigador para seguir los métodos descritos en la publicación y recopilar datos en un nuevo estudio.

La reproducibilidad computacional es la base de la transparencia. Si no se puede recrear el análisis, no podemos verificar la exactitud de los resultados reportados.

## 14.2. ¿Por qué es baja la Reproducibilidad Computacional?

La incapacidad de replicar un análisis se debe a menudo a la falta de tres componentes clave:

1.  **Falta de Datos Abiertos:** El conjunto de datos original no se comparte o es inaccesible.
2.  **Falta de Código Abierto:** El código utilizado para limpiar, procesar y analizar los datos no se comparte.
3.  **Falta de Entorno de Computación Documentado:** El software, la versión de los paquetes y el sistema operativo no se especifican, lo que dificulta la ejecución del código.

## 14.3. Herramientas para la Reproducibilidad Computacional

Para lograr la reproducibilidad, los investigadores deben proporcionar tanto el código como los datos, y utilizar herramientas que vinculen explícitamente el texto del informe con el código que lo generó.

### 14.3.1. Literate Programming (Programación Literaria)

Este enfoque, ejemplificado por herramientas como **R Markdown** o **Jupyter Notebooks**, combina prosa (el informe o el manuscrito) con bloques de código ejecutable. Esto garantiza que cualquier número, gráfico o tabla en el informe se derive directamente del código proporcionado.

* **Ventaja:** Permite que los revisores o lectores ejecuten el código línea por línea y verifiquen que el código genera el resultado reportado.

### 14.3.2. Contenedores y Entornos Virtuales

Para abordar el problema del entorno de computación (es decir, las diferencias en las versiones de software entre ordenadores), los investigadores pueden utilizar herramientas de contenedorización como **Docker** o **virtualización**.

* Estas herramientas empaquetan la versión exacta del sistema operativo, el software estadístico y todas las bibliotecas dependientes. Esto permite que cualquiera ejecute el código exactamente en el mismo entorno utilizado por el autor original.

### 14.3.3. Repositorios de Código y Datos

* **Datos Abiertos:** Los datos deben alojarse en un repositorio persistente con un Identificador de Objeto Digital (DOI), como el **Open Science Framework (OSF)**, **Zenodo** o **Dryad**.
* **Código Abierto:** El código del análisis debe alojarse en repositorios con control de versiones, como **GitHub** o **GitLab**.

## 14.4. Buenas Prácticas de Codificación

Incluso con código y datos abiertos, el análisis solo es reproducible si el código es comprensible. Las buenas prácticas de codificación incluyen:

* **Comentarios:** Usar comentarios extensos para explicar los pasos del análisis.
* **Convenciones de Nomenclatura:** Usar nombres de variables y archivos que sean claros y consistentes.
* **No Codificación Manual (Manual Coding):** Minimizar los pasos manuales (como copiar y pegar de una hoja de cálculo a un documento) y, en su lugar, automatizar todo el proceso.

## 14.5. La Reproducibilidad como Mínimo

La reproducibilidad computacional debe considerarse el **estándar mínimo** de la investigación. Un análisis no reproducible es equivalente a un análisis que no ha sido verificado.

La reproducibilidad reduce los errores inocentes, previene el sesgo de *p-hacking* al exponer la flexibilidad en el análisis, y acelera la ciencia al permitir que otros investigadores utilicen el código para extender o verificar los hallazgos.
