# 🐾 Miausistente — ChatBot Multilingüe e Inteligente de Consultas Académicas

Asistente conversacional interactivo desarrollado en **Python** para resolver consultas institucionales, programas académicos e información del campus de la **UADE**. Proyecto premiado con el **4° Puesto en Competencia Universitaria** y **adoptado oficialmente** para su uso en la universidad.

## 🌟 Características Principales

* **Soporte Multilingüe:** Interfaz y procesamiento en **Español**, **Inglés** y **Portugués**, adaptando modismos y frases de los gatos de UADE (Nala, Luigi, Otto).
* **Procesamiento de Lenguaje Natural (NLP):**
  * Limpieza avanzada de texto: remoción de diacríticos, contracciones, caracteres invisibles, signos de puntuación y *stopwords* por idioma.
  * Algoritmo de Stemming usando `SnowballStemmer de nltk`.
* **Motor de Búsqueda Híbrido:**
  * Coincidencia exacta estandarizada.
  * Score de similitud combinado usando `difflib.SequenceMatcher` (70%) e intersección de tokens/raíces de palabras (30%).
* **Autoaprendizaje Dinámico (Fallback Loop):** Si no detecta una respuesta con confianza suficiente (score ≥ 0.55), sugiere alternativas o permite al usuario enseñar la respuesta correcta en tiempo real, actualizando la base de datos JSON.
* **Herramientas Integradas:** Módulo interactivo para el cálculo y validación de promedios de notas parciales.
* **Sistema de Telemetría/Logs:** Registro en tiempo real de consultas, respuestas, personajes e idiomas en `logs/registro.txt`.

## 🛠️ Tecnologías y Librerías

* **Lenguaje:** Python 3.x
* **Librerías:** `nltk` (SnowballStemmer), `difflib`, `unicodedata`, `json`, `datetime`, `re`.

## 📂 Estructura del Proyecto

```text
.
├── main.py                  # Punto de entrada principal
├── core/
│   ├── asistente.py         # Flujo interactivo y control de conversación
│   ├── procesamiento.py     # Lógica de NLP, limpieza, stemming y similitud
│   ├── idiomas.py           # Diccionarios de internacionalización y stemmers
│   ├── respuestas.py        # Lectura/escritura de archivos JSON
│   ├── promedios.py         # Calculadora de promedios académicos
│   └── log.py               # Módulo de auditoría y registros
└── datos/                   # Bases de preguntas/respuestas por idioma y personaje
```
