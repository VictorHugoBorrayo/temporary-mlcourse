# Introducción a la Ciencia de Datos y Machine Learning — Demo

Este repositorio acompaña una clase de prueba (15–20 minutos) para el curso **“Introducción a la Ciencia de Datos y Machine Learning”**.  
Incluye dos cuadernos demostrativos que ilustran la evolución desde el **Perceptrón** hasta las **Redes Neuronales Artificiales (ANN)**, mostrando la relación entre sus fundamentos matemáticos y su implementación práctica.

## Objetivos del repositorio

- Demostrar el flujo de trabajo básico de un modelo de aprendizaje supervisado en Python.  
- Presentar la relación entre el perceptrón clásico y la neurona artificial moderna.  
- Ejecutar y visualizar el entrenamiento de una red neuronal simple sobre el conjunto MNIST.  
- Proveer una configuración reproducible del entorno de trabajo para futuras extensiones del curso.

## Estructura del proyecto

```
.
├─ notebooks/
│  ├─ perceptron.ipynb                # Cuaderno del perceptrón y casos lineales
│  └─ ann.ipynb                       # Cuaderno de red neuronal (ANN)
├─ src/                               # Funciones auxiliares opcionales
├─ requirements.txt                   # Dependencias del proyecto
├─ .env.example                       # Variables de entorno (opcional)
└─ README.md
```

> **Nota:** Los cuadernos generan sus propios datos de manera sintética, por lo que no requieren archivos externos ni credenciales.

## Requisitos previos

- **Python 3.10+**
- **Git**
- **Visual Studio Code** con extensiones:
  - *Python* (Microsoft)
  - *Jupyter* (Microsoft)

## Configuración rápida (venv + pip)

### 1) Clonar el repositorio

```bash
git clone <URL_DEL_REPOSITORIO>
cd <NOMBRE_DEL_REPOSITORIO>
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

## Uso en Visual Studio Code

1. Abrir el proyecto:  
   ```bash
   code .
   ```
2. Seleccionar el intérprete correspondiente:  
   - **macOS/Linux:** `.venv/bin/python`  
   - **Windows:** `.venv\Scripts\python.exe`
3. Abrir el cuaderno deseado en `notebooks/`:
   - `perceptron.ipynb` → demostración del perceptrón.  
   - `ann.ipynb` → demostración de la red neuronal con Keras/TensorFlow.
4. Ejecutar las celdas en orden o utilizar la opción *Run All*.  
5. En caso de aparecer el aviso “Trust”, marcar el repositorio como confiable.

## Variables de entorno (opcional)

Cuando se requiera agregar configuraciones personalizadas:

```bash
cp .env.example .env
```

Editar los valores necesarios y cargarlos desde Python con `os.getenv` o la librería `python-dotenv`.

## Descripción de los notebooks

### `perceptron.ipynb`
- Genera un conjunto de datos linealmente separable.  
- Implementa el perceptrón clásico con Numpy.  
- Muestra el proceso de entrenamiento y la frontera de decisión aprendida.  
- Incluye un caso no linealmente separable (círculos concéntricos) para mostrar la limitación del modelo.

### `ann.ipynb`
- Presenta la transición del perceptrón a una red neuronal multicapa.  
- Explica el *forward* y *backpropagation* mediante código y visualizaciones.  
- Entrena una red neuronal en el conjunto MNIST y muestra las predicciones gráficas.  

## Plan de la demostración (15–20 minutos)

1. **Perceptrón** (5–7 min):  
   - Motivación, definición y entrenamiento sobre un conjunto linealmente separable.  
2. **Caso no linealmente separable** (3–4 min):  
   - Demostración de las limitaciones del modelo.  
3. **Red neuronal (ANN)** (7–8 min):  
   - Explicación de la estructura, entrenamiento con TensorFlow y resultados sobre MNIST.  
4. **Cierre** (1–2 min):  
   - Interpretación de resultados y vinculación con los temas avanzados del curso.

## Comandos útiles

```bash
# Activar entorno
source .venv/bin/activate              # macOS/Linux
.\.venv\Scripts\Activate.ps1           # Windows

# Instalar dependencias
pip install -r requirements.txt

# Abrir Visual Studio Code
code .

# Desactivar entorno
deactivate
```

## Solución de problemas

- **El kernel no aparece en VS Code:** verificar que el entorno esté activo y volver a seleccionar el intérprete (Cmd/Ctrl + Shift + P → “Python: Select Interpreter”).  
- **Error al instalar dependencias:** ejecutar `python -m pip install --upgrade pip` antes de reinstalar.  
- **Conflictos de versión:** eliminar `.venv/` y repetir el proceso de instalación.

## Licencia

Uso educativo para la clase de demostración del curso *Introducción a la Ciencia de Datos y Machine Learning*.  
Este material puede reutilizarse con fines docentes o de divulgación.
