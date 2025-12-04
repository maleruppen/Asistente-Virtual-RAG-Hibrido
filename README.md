# Asistente-Virtual-RAG-Hibrido

Este proyecto implementa un **Asistente Virtual Inteligente** diseñado para el dominio de electrodomésticos, utilizando una arquitectura avanzada de **RAG Híbrido (Retrieval-Augmented Generation)** evolucionada hacia un **Agente Autónomo (ReAct)**.

El sistema es capaz de razonar, planificar y ejecutar búsquedas sobre múltiples fuentes de datos heterogéneas para responder consultas complejas de usuarios, desde soporte técnico hasta análisis de ventas.

## Características Principales

* **Arquitectura RAG Híbrida:** Combina recuperación de información desde tres fuentes distintas:
    * **Vectorial (Semántica):** Manuales de usuario y reseñas en ChromaDB usando embeddings multilingües (`intfloat/multilingual-e5-small`).
    * **Tabular (Estructurada):** Consultas SQL dinámicas sobre bases de datos de productos, ventas, inventario y devoluciones (SQLite).
    * **Grafos (Relacional):** Exploración de relaciones entre productos, marcas y categorías mediante consultas Cypher en KūzuDB.
* **Agente ReAct con Memoria:** Implementado con LangChain, el agente decide autónomamente qué herramienta utilizar (o combinarlas) basándose en la intención del usuario.
* **Router Inteligente:** Clasificador de intención basado en LLM (Few-Shot Prompting) con una precisión del 100% en pruebas, superando a clasificadores tradicionales.
* **Analytics Tool:** Capacidad para generar gráficos de análisis de datos (ej. distribución de pagos) en tiempo real usando Python y Matplotlib.

## Tech Stack

* **Orquestación:** LangChain
* **LLM:** Google Gemini 2.0 Flash (Temperature=0 para determinismo)
* **Bases de Datos:** ChromaDB (Vectores), KūzuDB (Grafos), SQLite (Tabular)
* **Embeddings:** HuggingFace (`intfloat/multilingual-e5-small`)
* **Entorno:** Google Colab

## Ejecución del Proyecto

Este proyecto está diseñado para ejecutarse en Google Colab y descarga los datos automáticamente.

1. **Abrir el cuaderno:** Haz clic en el botón de abajo:
   [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](AQUÍ_VA_TU_ENLACE)

2. **Configurar API Keys:** Antes de ejecutar, ve al ícono de la "Llave" 🔑 en la barra izquierda de Colab ("Secretos") y agrega tus claves con los nombres:
   * `GOOGLE_KEY` (Para Gemini)
   * `HF_TOKEN` (Para Hugging Face)
   * *Recuerda habilitar el interruptor "Permiso de acceso al cuaderno" para cada una.*

3. **Instalación y Descarga:** Ejecuta la **primera celda** de código. Esto instalará las librerías y descargará automáticamente los datasets necesarios.

4. **⚠️ PASO CRÍTICO: REINICIAR ENTORNO**
   Al finalizar la instalación de la celda 1, reinicia la sesión para actualizar las dependencias:
   * Ve al menú superior: **Entorno de ejecución > Reiniciar sesión**.

5. **Ejecución final:** Una vez reiniciado, ejecuta el resto de las celdas (**Entorno de ejecución > Ejecutar todas** o Ctrl+F9).
