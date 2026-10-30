Análisis y Visualización Interactiva de Registros Judiciales de Violencia de Género y Familiar (2022 - 2024)Este repositorio contiene los scripts de procesamiento, limpieza de datos, análisis estadístico descriptivo y el flujo de trabajo completo desarrollado para la tesis de grado de la Licenciatura en Ciencias de Datos.El proyecto abarca la ingesta, estructuración y normalización de los registros de denuncias del Poder Judicial, transformando información semiestructurada sobre violencia de género y familiar en tableros interactivos y gráficos analíticos para la toma de decisiones e investigación pública.
Objetivos del ProyectoEstructurar y Normalizar: Limpiar y unificar la base de datos original de registros judiciales (2022–2024), resolviendo inconsistencias de formato, caracteres con errores de codificación (mojibake) e imprecisiones tipográficas.Tratamiento de Datos Nulos y Atípicos: Auditar y documentar el impacto de las variables incompletas (demográficas, sociales e institucionales) y filtrar anomalías en edades de denunciantes y denunciados.Análisis Categoricial y Binarización: Categorizar y binarizar los tipos de violencia constatada (Psicológica, Física, Económica/Patrimonial, Ambiental, Sexual, Digital, etc.) y las medidas cautelares dictadas por los juzgados.Visualización e Integración: Exportar gráficos estáticos de alta resolución para la redacción académica e integrar la base procesada a un modelo multidimensional en Power BI.
Estructura del Repositorio.
├── 01_datos_originales/       # Archivos de origen (Excel/CSV) - Datos sin procesar
├── 02_datos_limpios/          # Dataset final limpio y tablas de resumen procesadas
├── 03_notebooks/              # Notebooks de Jupyter con la secuencia analítica
│   ├── 01_auditoria_y_limpieza.ipynb      # Carga, codificación UTF-8, tratamiento de nulos y atípicos
│   ├── 02_binarizacion_y_categorizacion.ipynb # Binarización de tipos de violencia y medidas
│   └── 03_analisis_exploratorio_y_graficos.ipynb # Visualización de datos y exportaciones
├── 04_graficos_resultados/    # Visualizaciones exportadas automáticamente (PNG a 300 DPI)
├── 05_dashboard_powerbi/      # Archivo (.pbix) del tablero interactivo
├── .gitignore                 # Archivos e historiales excluidos de Git
├── README.md                  # Documentación principal del repositorio
└── requirements.txt           # Dependencias de Python necesarias
Tecnologías y Librerías UtilizadasLenguaje Principal: Python 3.13+Procesamiento de Datos: pandas, numpyVisualización de Datos: matplotlib, seabornBusiness Intelligence / BI: Microsoft Power BI (Modelado de datos en estrella, lenguaje DAX)Control de Versiones: Git y GitHub
Flujo de Trabajo (Pipeline de Datos)flowchart LR
    A[Datos Originales Excel] --> B[Notebook 01: Limpieza y Normalización]
    B --> C[Notebook 02: Binarización de Violencias]
    C --> D[Notebook 03: EDA y Gráficos]
    D --> E[(Dataset Limpio .CSV / .XLSX)]
    D --> F[Gráficos PNG 300 DPI]
    E --> G[Dashboard Power BI]
Detalle de las Etapas:Limpieza y Estandarización de Texto:Corrección de errores de decodificación de texto (mojibake / Latin1 a UTF-8).Estandarización de nombres de columnas y eliminación de caracteres especiales.Auditoría de Incompletitud y Outliers:Mapeo sistemático de valores faltantes (NaN) en variables demográficas y procesales.Depuración de rangos etarios inválidos en denunciantes y denunciados.Transformación y Binarización:Creación de variables dicotómicas ($0$ y $1$) para múltiples tipos de violencia constatada en un mismo registro.Agregación y conteo de medidas cautelares dictadas por las autoridades judiciales.Visualización Interactiva:Conexión del dataset depurado a Power BI para el análisis interactivo mediante filtros cruzados por rango etario, tipo de violencia, período temporal y juzgado interviente.
Instalación y Uso LocalSi deseas replicar el análisis o ejecutar los notebooks en tu entorno local:Clonar este repositorio:git clone https://github.com/tu-usuario/tesis-analisis-registros-judiciales-violencia.git
cd tesis-analisis-registros-judiciales-violencia
Crear y activar un entorno virtual (opcional pero recomendado):python -m venv venv
# En Windows:
venv\Scripts\activate
# En macOS/Linux:
source venv/bin/activate
Instalar las dependencias:pip install -r requirements.txt
Ejecutar los Notebooks:jupyter notebook
Abre la carpeta 03_notebooks/ y sigue el orden numérico de los archivos.📄 Licencia y Uso de DatosLos datos utilizados en este trabajo provienen de registros públicos del Poder Judicial. Con el fin de resguardar la privacidad y confidencialidad de las partes involucradas, todos los datos han sido anonimizados previamente a su procesamiento, eliminando nombres, documentos de identidad y direcciones específicas conforme a las normativas vigentes de protección de datos personales.Trabajo de integración final para la Licenciatura en Ciencias de Datos.
