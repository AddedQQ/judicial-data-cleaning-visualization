# Análisis y Visualización Interactiva de Registros Judiciales de Violencia de Género y Familiar (2022 - 2024)

[![Python Version](https://img.shields.io/badge/Python-3.10%2B-blue.svg)](https://www.python.org/)
[![Power BI](https://img.shields.io/badge/Power_BI-Interactive_Dashboard-yellow.svg)](https://powerbi.microsoft.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)

Este repositorio contiene el código fuente, notebooks de procesamiento y la arquitectura de datos del trabajo de integración final para la **Licenciatura en Ciencias de Datos**.

El proyecto realiza el procesamiento integral de registros judiciales semiestructurados sobre violencia de género y familiar, aplicando técnicas de limpieza de texto, detección de anomalías, binarización de variables categóricas y modelado multidimensional para tableros interactivos.

---

## 📌 Objetivos del Proyecto

* **Normalización y Limpieza:** Resolver problemas de codificación (*mojibake* / UTF-8), caracteres especiales e inconsistencias tipográficas en registros judiciales.
* **Tratamiento de Datos Nulos y Atípicos:** Auditar el nivel de incompletitud por columna y filtrar inconsistencias en las edades registradas de denunciantes y denunciados.
* **Binarización y Categorización:** Transformar entradas multietiqueta (tipos de violencia constatada y medidas cautelares) en variables indicadoras ($0$ y $1$) para análisis cuantitativo.
* **Exportación y Visualización:** Generar reportes gráficos estáticos a alta resolución ($300\text{ DPI}$) e integrar la base procesada a **Power BI** mediante un modelo en estrella.

---

## 📁 Estructura del Repositorio

```text
.
├── 01_datos_originales/       # Datasets originales sin procesar (Excel/CSV)
├── 02_datos_limpios/          # Datasets procesados, normalizados y tabulados
├── 03_notebooks/              # Secuencia de Jupyter Notebooks explicativos
│   ├── 01_auditoria_y_limpieza.ipynb      # Carga, codificación UTF-8, tratamiento de nulos y atípicos
│   ├── 02_binarizacion_y_categorizacion.ipynb # Binarización de violencias y medidas dictadas
│   └── 03_analisis_exploratorio_y_graficos.ipynb # Visualización de datos y exportaciones
├── 04_graficos_resultados/    # Gráficos exportados automáticamente en formato PNG (300 DPI)
├── 05_dashboard_powerbi/      # Archivo (.pbix) del tablero interactivo
├── .gitignore                 # Exclusión de archivos temporales y locales
├── README.md                  # Documentación principal del proyecto
└── requirements.txt           # Dependencias y librerías necesarias de Python
```

---

## 🛠️ Tecnologías y Librerías

* **Lenguaje de Programación:** Python 3.10+
* **Manipulación y Análisis de Datos:** `pandas`, `numpy`
* **Visualización de Datos:** `matplotlib`, `seaborn`
* **Business Intelligence:** Microsoft Power BI (Lenguaje DAX, Modelado Dimensional)
* **Entorno de Trabajo:** Jupyter Notebook / Visual Studio Code

---

## 🔄 Pipeline de Procesamiento de Datos

```text
[Datos Originales (.xlsx)]
          │
          ▼
┌────────────────────────────────────────┐
│ Notebook 01: Auditoría y Limpieza       │
│  - Corrección de Mojibake (UTF-8)      │
│  - Filtrado de outliers en edades      │
│  - Estandarización de columnas          │
└────────────────────────────────────────┘
          │
          ▼
┌────────────────────────────────────────┐
│ Notebook 02: Transformación           │
│  - Binarización de tipos de violencia  │
│  - Agregación de medidas cautelares    │
└────────────────────────────────────────┘
          │
          ▼
┌────────────────────────────────────────┐
│ Notebook 03: EDA & Exportación          │
│  - Generación de gráficos (300 DPI)    │
│  - Exportación de dataset limpio (.csv)│
└────────────────────────────────────────┘
          │
          ├──────────────────────────┐
          ▼                          ▼
[Gráficos PNG para Tesis]   [Dashboard Power BI (.pbix)]
```

---

## 🚀 Guía de Instalación y Ejecución

Sigue estos pasos para replicar el entorno de desarrollo en tu equipo:

1. **Clonar el repositorio:**
   ```bash
   git clone https://github.com/tu-usuario/tesis-registros-judiciales-violencia.git
   cd tesis-registros-judiciales-violencia
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

## 📄 Protección de Datos y Privacidad

Los datasets procesados en este trabajo respetan la normativa vigente sobre protección de datos personales. Todos los registros han sido previa y estrictamente **anonimizados**, eliminando nombres, números de documento, domicilios concretos e identificadores directos de las partes involucradas.

---
*Trabajo de Integración Final — Licenciatura en Ciencias de Datos.*