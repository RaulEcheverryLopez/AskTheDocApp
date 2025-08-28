# LLMapp - Aplicación Streamlit con LangChain

Esta es una aplicación web desarrollada con Streamlit que utiliza un modelo de lenguaje (LLM) a través de la biblioteca LangChain para procesar y analizar un documento de texto.

## Descripción del Proyecto

El objetivo de esta aplicación es demostrar cómo se puede construir una interfaz de usuario simple con Streamlit para interactuar con un LLM. La aplicación carga un documento de texto local (`Documento Prueba.txt`), lo procesa y permite al usuario hacer preguntas o realizar análisis sobre su contenido.

## Correcciones para Despliegue Online

El proyecto fue modificado para asegurar su correcto funcionamiento tanto en un entorno local como en plataformas de despliegue en la nube (por ejemplo, Streamlit Cloud).

**Problema Original:**
La aplicación funcionaba localmente pero fallaba al ser desplegada. Esto se debía a dos razones principales:
1.  Las dependencias del proyecto no estaban correctamente especificadas.
2.  La ruta al archivo de datos (`Documento Prueba.txt`) estaba codificada de una manera que solo funcionaba en el entorno local.

### Modificaciones Realizadas

1.  **`streamlit_app.py`**:
    *   Se ajustó el código para construir la ruta al archivo `Documento Prueba.txt` de forma dinámica y relativa a la ubicación del script. Esto garantiza que la aplicación pueda encontrar el archivo sin importar el sistema de archivos del servidor donde se despliegue.

2.  **`requirements.txt`**:
    *   Se agregaron todas las bibliotecas necesarias para la ejecución del proyecto, incluyendo `streamlit`, `langchain`, y `langchain-community`. Esto permite que el entorno de despliegue instale automáticamente todas las dependencias requeridas.

3.  **`.gitignore`**:
    *   Se añadió la carpeta del entorno virtual (`LLMapp/`) al archivo. Esta es una buena práctica para evitar que archivos innecesarios y específicos del entorno de desarrollo local se suban al repositorio de código.

## Cómo Ejecutar la Aplicación

1.  **Clonar el repositorio:**
    ```bash
    git clone <URL_DEL_REPOSITORIO>
    cd LLMapp
    ```

2.  **Instalar las dependencias:**
    ```bash
    pip install -r requirements.txt
    ```

3.  **Ejecutar la aplicación Streamlit:**
    ```bash
    streamlit run streamlit_app.py
    ```