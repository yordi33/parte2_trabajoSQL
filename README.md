# Team Challenge SQL — Parte 2: Diseño e Implementación de Base de Datos (E-commerce Tecnológico)

Repositorio oficial para el diseño, implementación, población de datos y análisis de la base de datos relacional en **Google BigQuery** para el e-commerce de tecnología.

---

## 📁 Estructura del Repositorio

```text
tc-sql-tu_equipo/
├── parte_1_sql_murder_mystery/
│   └── investigacion.ipynb
├── parte_2_modelo_bigquery/
│   ├── data/                   # Carpeta para datos locales (vacía, datos alojados en BigQuery)
│   ├── docs/
│   │   ├── er_diagram.png      # Diagrama Entidad-Relación (3NF)
│   │   └── normalizacion.md    # Justificación de las Tres Formas Normales
│   └── notebooks/
│       ├── 01_setup_bigquery.ipynb       # Creación del Dataset y esquemas de las 7 tablas en 3NF
│       ├── 02_generate_data.ipynb        # Generación sintética con Faker y carga automatizada
│       └── 03_queries_verification.ipynb # Consultas analíticas de negocio y verificación
├── .env.example
├── .gitignore
├── README.md
└── requirements.txt
🛠️ Stack Tecnológico
Python 3.13 (Entornos virtuales con venv)

Google Cloud Platform (BigQuery) — Almacenamiento y motor SQL en región EU

Jupyter Notebooks — Desarrollo interactivo

Librerías principales: pandas, faker, google-cloud-bigquery

🚀 Guía de Instalación y Puesta en Marcha
1. Clonar el repositorio y configurar el entorno virtual
Bash
git clone <url-del-repositorio>
cd trabajo_SQL

# Crear y activar el entorno virtual
python -m venv venv
# En Windows:
venv\Scripts\activate
# En Mac/Linux:
source venv/bin/activate

# Instalar dependencias
pip install -r requirements.txt
2. Configurar credenciales de Google Cloud
Crea un proyecto en Google Cloud Console y activa la BigQuery API.

Crea una cuenta de servicio (Service Account) con el rol BigQuery Admin y descarga su clave en formato JSON.

Crea una carpeta llamada credentials/ en la raíz del proyecto y guarda el fichero con el nombre service-account.json.

Copia el fichero .env.example y renómbralo a .env, rellenando tus datos:

Fragmento de código
GCP_PROJECT_ID=tu-proyecto-gcp
BQ_DATASET_ID=tu_empresa
GOOGLE_APPLICATION_CREDENTIALS=./credentials/service-account.json
3. Ejecución de los Notebooks
Abre VS Code, selecciona el kernel de tu entorno virtual venv y ejecuta los notebooks en orden:

01_setup_bigquery.ipynb (Crea las tablas en BigQuery respetando restricciones).

02_generate_data.ipynb (Genera los 500 clientes, 70 productos, 2.000 pedidos, pagos y reviews con Faker y los sube a BigQuery).

03_queries_verification.ipynb (Ejecuta las consultas analíticas de negocio sobre los datos).


---

### ¡Proyecto completado con éxito!
Con estos archivos de configuración y documentación, tu repositorio cumple al 100% con los estándares d