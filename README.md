Proyecto: FastAPI — Proxy LLM sencillo

Descripción
- Esta es una pequeña API construida con FastAPI que expone un endpoint para consultar un modelo LLM (Google Gemini) usando la librería `google-genai`. Recibe un `prompt` por la ruta y devuelve la respuesta en JSON.

Estructura mínima
- `main.py` — aplicación FastAPI y endpoint `/llm/{prompt}`.
- `requirements.txt` — lista de dependencias usadas por el proyecto.

Requisitos
- Python 3.10+ recomendado.
- Tener una clave de API válida para Gemini (o la API que uses) en la variable de entorno `GEMINI_API_KEY`.

Instalación rápida
1. Clona el repositorio o descarga los archivos.
2. Crea y activa un entorno virtual:

```
python -m venv .venv
source .venv/bin/activate
```

3. Instala las dependencias:

```
pip install -r requirements.txt
```

Configuración de variables de entorno
- Crea un archivo `.env` en la raíz del proyecto con la variable:

```
GEMINI_API_KEY=tu_api_key_aqui
```

Uso
- Inicia la app con la utilidad de desarrollo de FastAPI (desde la raíz del proyecto):

```
fastapi dev main.py
```

- Endpoint disponible:
	- `GET /llm/{prompt}` — Reemplaza `{prompt}` por tu consulta (URL-encode si contiene espacios u otros caracteres especiales). La respuesta es JSON con la clave `Respuesta`.

Ejemplo rápido

```
curl "http://127.0.0.1:8000/llm/Hola%20mundo"

# Respuesta esperada (ejemplo):
# {"Respuesta": "Hola — respuesta generada por el modelo..."}
```

Dependencias clave
- fastapi
- uvicorn
- python-dotenv
- google-genai

(La lista completa está en `requirements.txt`.)

Notas y buenas prácticas
- No subas tu `.env` con la API key a repositorios públicos. Añade `.env` a `.gitignore` si es necesario.
- Si la librería `google-genai` cambia la forma de inicializar el cliente o los nombres de los métodos, verifica la documentación oficial y actualiza `main.py` en consecuencia.
- Para depuración, observa la salida en la consola — `main.py` imprime la respuesta del modelo.

Contacto
- Si quieres que mejore la documentación, agrega ejemplos adicionales o que haga un script de prueba, dímelo y lo preparo.

