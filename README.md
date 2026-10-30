# Análisis de Registros Judiciales de Violencia de Género y Familiar (2022 - 2024)

Este repositorio contiene los scripts de procesamiento, limpieza de datos, análisis exploratorio y generación de visualizaciones correspondientes al trabajo de tesis para la **Licenciatura en Ciencias de Datos**.

## Descripción del Proyecto
El objetivo principal de este trabajo es realizar un flujo completo de Ciencia de Datos aplicado a registros judiciales no estructurados/semiestructurados del Poder Judicial, abarcando desde la preparación y normalización de la base original hasta el análisis de variables demográficas, tipos de violencia constatada y medidas cautelares u oficios dictados.

## Estructura del Proyecto
```text
├── 01_datos_originales/       # Base original sin procesar (Excel)
├── 02_datos_limpios/          # Datos procesados, limpios y resúmenes tabulares
├── 03_notebooks/              # Notebooks de Jupyter con los análisis paso a paso
│   ├── 01_limpieza_y_normalizacion.ipynb
│   └── 02_analisis_y_graficos.ipynb
├── 04_graficos_resultados/    # Exportación automática de gráficos (PNG a 300 DPI)
├── README.md                  # Descripción del repositorio
└── requirements.txt           # Librerías de Python requeridas
