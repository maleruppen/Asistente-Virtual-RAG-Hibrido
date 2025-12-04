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

Este proyecto está diseñado para ejecutarse en Google Colab.

1. Haz clic en el botón de abajo para abrir el cuaderno:
   [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/maleruppen/Asistente-Virtual-RAG-Hibrido/blob/main/TP_NLP_FINAL.ipynb)
2. Una vez abierto, asegúrate de subir los archivos de datos (`fuentes_de_informacion.zip`, etc.) al entorno de Colab o conectar tu Drive si es necesario.
3. Ejecuta las celdas en orden (Entorno > Ejecutar todas).
