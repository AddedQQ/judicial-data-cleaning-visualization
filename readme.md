# Análisis y Visualización Interactiva de Registros Judiciales de Violencia de Género y Familiar (2022 - 2024)

[![Python Version](https://img.shields.io/badge/Python-3.10%2B-blue.svg)](https://www.python.org/)
[![Power BI](https://img.shields.io/badge/Power_BI-Interactive_Dashboard-yellow.svg)](https://powerbi.microsoft.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)

Este repositorio contiene el código fuente, notebooks de procesamiento y la arquitectura de datos del trabajo de integración final para la **Licenciatura en Ciencia de Datos**.

El proyecto realiza el procesamiento integral de registros judiciales semiestructurados sobre violencia de género y familiar, aplicando técnicas de limpieza de texto, detección de anomalías, binarización de variables categóricas y modelado multidimensional para tableros interactivos.

---

## Objetivos del Proyecto

* **Normalización y Limpieza:** Resolver problemas de codificación (*mojibake* / UTF-8), caracteres especiales e inconsistencias tipográficas en registros judiciales.
* **Tratamiento de Datos Nulos y Atípicos:** Auditar el nivel de incompletitud por columna y filtrar inconsistencias en las edades registradas de denunciantes y denunciados.
* **Binarización y Categorización:** Transformar entradas multietiqueta (tipos de violencia constatada y medidas cautelares) en variables indicadoras ($0$ y $1$) para análisis cuantitativo.
* **Exportación y Visualización:** Generar reportes gráficos estáticos a alta resolución ($300\text{ DPI}$) e integrar la base procesada a **Power BI** mediante un modelo en estrella.

---

## Estructura del Repositorio

```text
.
├── 01_datos_originales/       # Datasets originales sin procesar (Excel/CSV)
├── 02_datos_limpios/          # Datasets procesados, normalizados y tabulados
├── 03_notebooks/              # Secuencia de Jupyter Notebooks explicativos
│   ├── 01_diagnostico_inicial.ipynb                   # Diagnóstico inicial: estructura, calidad, detección de nulos y duplicados
│   ├── 02_analisis_exploratorio.ipynb                 # EDA: distribuciones temporales, tipologías de violencia y mapa territorial
│   ├── 03_cruces_e_indicadores.ipynb                  # Construcción de variables derivadas (gravedad máxima, cantidad de medidas)
│   ├── 04_pruebas_estadisticas_y_tasas.ipynb          # Prueba Chi-cuadrado, V de Cramér y tasa de incidencia por 10k hab. (Censo 2022)
│   └── 05_preparacion_dashboard.ipynb                 # Exportación de consolidados finales estructurados para Power BI / Streamlit
├── 04_graficos_resultados/    # Gráficos exportados automáticamente en formato PNG (300 DPI)
├── 05_dashboard_powerbi/      # Archivo (.pbix) del tablero interactivo
├── .gitignore                 # Exclusión de archivos temporales y locales
├── README.md                  # Documentación principal del proyecto
└── requirements.txt           # Dependencias y librerías necesarias de Python
```

---

## Tecnologías y Librerías

* **Lenguaje de Programación:** Python 3.10+
* **Manipulación y Análisis de Datos:** `pandas`, `numpy`
* **Visualización de Datos:** `matplotlib`, `seaborn`
* **Business Intelligence:** Microsoft Power BI (Lenguaje DAX, Modelado Dimensional)
* **Entorno de Trabajo:** Jupyter Notebook / Visual Studio Code

---

## Pipeline de Procesamiento de Datos

```text
[Datos Originales (.xlsx)]
          │
          ▼
┌──────────────────────────────────────────────────────────┐
│ Notebook 01: Auditoría y Diagnóstico Inicial             │
│  - Revisión de estructura, tipos de datos y columnas     │
│  - Detección de valores nulos y control de duplicados    │
│  - Corrección de Mojibake y normalización de texto       │
└──────────────────────────────────────────────────────────┘
          │
          ▼
┌──────────────────────────────────────────────────────────┐
│ Notebook 02: Análisis Exploratorio & Visualización       │
│  - Análisis de frecuencias temporales(anuales/mensuales) │
│  - Prevalencia por tipos de violencia constatada         │
│  - Generación de mapa de distribución territorial        │
└──────────────────────────────────────────────────────────┘
          │
          ▼
┌──────────────────────────────────────────────────────────┐
│ Notebook 03: Cruces Estadísticos e Indicadores           │
│  - Construcción de variable derivada "Gravedad Máxima"   │
│  - Agregación y conteo de medidas judiciales dictadas    │
│  - Matrices de contingencia entre violencia y medidas    │
└──────────────────────────────────────────────────────────┘
          │
          ▼
┌──────────────────────────────────────────────────────────┐
│ Notebook 04: Pruebas Estadísticas y Tasa Territorial     │
│  - Evaluación de asociación: Chi-cuadrado y V de Cramér  │
│  - Cálculo de Tasa de Incidencia cada 10.000 hab. (Censo)│
│  - Generación de gráficos comparativos en alta resolución│
└──────────────────────────────────────────────────────────┘
          │
          ▼
┌──────────────────────────────────────────────────────────┐
│ Notebook 05: Preparación de Salidas para Dashboard       │
│  - Formateo y consolidación del dataset depurado         │
│  - Exportación de tablas estructuradas (.xlsx / .csv)    │
└──────────────────────────────────────────────────────────┘
          │
          ├──────────────────────────────────┐
          ▼                                  ▼
[Gráficos PNG a 300 DPI]        [Dashboard Power BI / Streamlit]
```

---

## Guía de Instalación y Ejecución

Sigue estos pasos para replicar el entorno de desarrollo en tu equipo:

1. **Clonar el repositorio:**
   ```bash
   git clone https://github.com/AddedQQ/judicial-data-cleaning-visualization.git
   cd judicial-data-cleaning-visualization
   ```

2. **Crear y activar un entorno virtual:**
   * En Windows:
     ```bash
     python -m venv venv
     venv\Scripts\activate
     ```
   * En macOS/Linux:
     ```bash
     python3 -m venv venv
     source venv/bin/activate
     ```

3. **Instalar dependencias:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Iniciar Jupyter Notebook:**
   ```bash
   jupyter notebook
   ```
   Abre la carpeta `03_notebooks/` y ejecuta los archivos en orden numérico.

---

## Protección de Datos y Privacidad

Los datasets procesados en este trabajo respetan la normativa vigente sobre protección de datos personales. Todos los registros han sido previa y estrictamente **anonimizados**, eliminando nombres, números de documento, domicilios concretos e identificadores directos de las partes involucradas.

---
*Trabajo de Integración Final — Licenciatura en Ciencia de Datos.*
