# 🧮 Calculadora Flask

Una aplicación web de calculadora construida con Flask que proporciona una interfaz web moderna para realizar operaciones matemáticas básicas.

## 📁 Estructura del Proyecto

```
├── app.py                 # Aplicación Flask principal
├── calculator.py          # Lógica de la calculadora y servidor HTTP legacy
├── templates/
│   └── index.html        # Interfaz web de la calculadora
├── requirements.txt       # Dependencias de Python
├── test_calculator.py     # Pruebas unitarias
├── Dockerfile            # Configuración de Docker
└── .github/              # Configuraciones de GitHub
```

## 🚀 Instalación y Uso

### Prerrequisitos
- Python 3.7 o superior
- pip (gestor de paquetes de Python)

### Instalación

1. **Instalar dependencias:**
   ```bash
   pip install -r requirements.txt
   ```

### Ejecutar la Aplicación

#### Opción 1: Aplicación Flask (Recomendada)
```bash
python app.py
```
La aplicación estará disponible en: http://localhost:5000

#### Opción 2: Servidor HTTP básico (Legacy)
```bash
python calculator.py
```
El servidor estará disponible en: http://localhost:4000

## 🌟 Características

### Aplicación Flask
- ✅ Interfaz web moderna y responsive
- ✅ Operaciones: suma, resta, multiplicación, división
- ✅ Validación de errores (división por cero, entradas inválidas)
- ✅ API REST JSON
- ✅ Diseño atractivo con CSS

### Operaciones Disponibles
- **Suma** ➕
- **Resta** ➖ 
- **Multiplicación** ✖️
- **División** ➗ (con protección contra división por cero)

## 🔧 API Endpoints

### POST /calculate
Realiza cálculos matemáticos.

**Request Body:**
```json
{
  "a": 10,
  "b": 5,
  "operation": "add"
}
```

**Operaciones disponibles:**
- `add` - Suma
- `subtract` - Resta
- `multiply` - Multiplicación
- `divide` - División

**Response (éxito):**
```json
{
  "result": 15
}
```

**Response (error):**
```json
{
  "error": "No se puede dividir por cero"
}
```

## 🧪 Pruebas

Ejecutar las pruebas unitarias:
```bash
python -m pytest test_calculator.py
```

## 🚀 Despliegue en Railway

### Opción 1: Deploy desde GitHub (Recomendado)
1. Sube tu código a un repositorio de GitHub
2. Ve a [Railway.app](https://railway.app)
3. Conecta tu cuenta de GitHub
4. Selecciona "Deploy from GitHub repo"
5. Elige tu repositorio
6. Railway detectará automáticamente el Dockerfile
7. ¡Tu app estará desplegada en minutos!

### Opción 2: Deploy con Railway CLI
```bash
# Instalar Railway CLI
npm install -g @railway/cli

# Login a Railway
railway login

# Inicializar proyecto
railway init

# Deploy
railway up
```

### Configuración Railway
- **Puerto:** Dinámico (Railway asigna automáticamente)
- **Build:** Dockerfile
- **Start Command:** `python app.py`
- **Health Check:** Configurado en `/`

## 🐳 Docker Local

Para pruebas locales con Docker:
```bash
docker build -t calculadora-flask .
docker run -p 5000:5000 calculadora-flask
```

## 📱 Uso de la Interfaz Web

1. Abre tu navegador en http://localhost:5000
2. Ingresa el primer número
3. Selecciona la operación deseada
4. Ingresa el segundo número
5. Haz clic en "Calcular"
6. Ve el resultado instantáneamente

## 🛠️ Desarrollo

La aplicación está estructurada de manera modular:

- **`Calculator` class**: Contiene la lógica de las operaciones matemáticas
- **Flask app**: Maneja las rutas web y la API REST
- **Templates**: Interfaz HTML con JavaScript para interactividad
- **Tests**: Pruebas unitarias para validar la funcionalidad

## 📄 Licencia

Este proyecto es de código abierto y está disponible bajo la licencia MIT.