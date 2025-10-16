# Introducción a la Ciencia de Datos y Machine Learning — Demo

Este repositorio acompaña una clase de prueba (15–20 minutos) para el curso **“Introducción a la Ciencia de Datos y Machine Learning”**.  
Incluye un cuaderno base con un flujo mínimo reproducible: carga de datos, exploración rápida, división train/test, entrenamiento de un modelo simple y evaluación.

## Objetivos del repositorio

- Mostrar el **flujo de trabajo** básico en ciencia de datos con Python.
- Proveer una **configuración reproducible** del entorno (venv) y dependencias.
- Ejecutar un **notebook demostrativo** listo para presentar en clase.
- Servir como plantilla mínima para extender a módulos del curso.

## Estructura del proyecto

```
.
├─ notebooks/
│  └─ 01_demo_intro_dsml.ipynb        # Cuaderno de 15–20 min
├─ data/
│  ├─ raw/                            # Datos crudos (si aplica)
│  └─ processed/                      # Datos procesados (si aplica)
├─ src/                               # Funciones auxiliares opcionales
├─ requirements.txt                   # Dependencias del demo
├─ .env.example                       # Variables de entorno (opcional)
└─ README.md
```

> **Nota:** El cuaderno está listo para correrse sin credenciales. Si luego se agregan fuentes externas, copia `.env.example` a `.env` y completa las variables necesarias.

## Requisitos previos

- **Python 3.10+**
- **Git**
- **Visual Studio Code** con extensiones:
  - *Python* (Microsoft)
  - *Jupyter* (Microsoft)

> Alternativa: puedes usar **Conda** si lo prefieres (instrucciones abajo).

## Configuración rápida (venv + pip)

### 1) Clonar el repositorio

```bash
git clone <URL_DE_TU_REPO>
cd <NOMBRE_DEL_REPO>
```

### 2) Crear y activar entorno virtual

**macOS / Linux:**
```bash
python3 -m venv .venv
source .venv/bin/activate
```

**Windows (PowerShell):**
```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
```

### 3) Actualizar pip e instalar dependencias

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

> Si tu red usa proxy/certificados, agrega `--trusted-host` o configura `PIP_INDEX_URL` según tu entorno.

## Uso en Visual Studio Code

1. Abre el proyecto:
   ```bash
   code .
   ```
2. VS Code detectará el entorno virtual. Si pregunta por el intérprete, elige:
   - **macOS/Linux:** `.venv/bin/python`
   - **Windows:** `.venv\Scripts\python.exe`
3. Abre `notebooks/01_demo_intro_dsml.ipynb`.
4. Selecciona el **Kernel** del cuaderno → elige el Python de `.venv`.
5. Ejecuta las celdas (Run All) o navega paso a paso.
6. (Opcional) Si aparece el aviso de “Trust”, marca el repo como confiable.

## Alternativa con Conda (opcional)

```bash
conda create -n dsml-demo python=3.10 -y
conda activate dsml-demo
pip install --upgrade pip
pip install -r requirements.txt
code .
```

En el notebook, selecciona el kernel de `dsml-demo`.

## Variables de entorno (opcional)

Si necesitas credenciales/flags:

1. Copia el ejemplo:
   ```bash
   cp .env.example .env
   ```
2. Edita `.env` con tus valores.
3. Desde Python, puedes leerlas con `os.getenv` (si usas `python-dotenv`, se cargan automáticamente en el notebook).

## Datos de ejemplo

El notebook puede:
- Usar un dataset sintético generado con `scikit-learn`, **o**
- Leer un CSV simple dentro de `data/raw/`.

Para repetir la demo sin depender de archivos externos, el cuaderno por defecto genera datos sintéticos.

## Plan de la demo (15–20 min)

1. **Contexto** (1–2 min): objetivo del flujo (de datos a modelo).
2. **EDA mínima** (5–7 min): carga/generación de datos, `pandas.head()`, gráfica rápida.
3. **Split + Modelo** (5–7 min): `train_test_split`, modelo sencillo (p. ej., `LogisticRegression` o `DecisionTreeClassifier`).
4. **Evaluación** (3–4 min): métricas básicas y breve interpretación.
5. **Cierre** (1 min): siguientes pasos (pipelines, validación, deployment).

> El cuaderno `01_demo_intro_dsml.ipynb` ya contiene celdas ordenadas para este guion.

## Comandos útiles

```bash
# Activar entorno
source .venv/bin/activate              # macOS/Linux
.\.venv\Scripts\Activate.ps1           # Windows

# Instalar/actualizar dependencias
pip install -r requirements.txt
pip install -U <paquete>

# Abrir VS Code
code .

# Salir del entorno
deactivate
```

## Solución de problemas

- **VS Code no encuentra el kernel:**
  Asegúrate de que el venv esté activo y vuelve a seleccionar el intérprete (Cmd/Ctrl + Shift + P → “Python: Select Interpreter”).
- **Error al instalar librerías (Windows):**
  Abre VS Code en **PowerShell** o **CMD** con permisos estándar; si falla por compilación, instala *Microsoft C++ Build Tools* o usa ruedas precompiladas.
- **Conflictos de versión:**
  Ejecuta `pip list` y valida versiones; si es necesario, borra `.venv/` y repite la instalación.

## Licencia

Uso educativo para la clase de demostración. Puedes reutilizar esta plantilla en tus propios cursos.
