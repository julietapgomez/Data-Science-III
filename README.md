# Clasificación Automática de Sentimiento en Reseñas de Amazon mediante NLP y Deep Learning

## Descripción del proyecto

El presente proyecto aplica técnicas de **Procesamiento de Lenguaje Natural (NLP)** y **Deep Learning** para clasificar automáticamente reseñas de productos de Amazon según su sentimiento.

Las categorías de clasificación utilizadas son:

- Positivo
- Neutral
- Negativo

El objetivo principal consiste en comparar el desempeño de un modelo clásico de Machine Learning (**Regresión Logística**) frente a modelos basados en **Redes Neuronales Artificiales**, evaluando ventajas, limitaciones y capacidad predictiva.

---

## Dataset

Se trabajó con un conjunto de reseñas de productos de Amazon compuesto por aproximadamente **17.000 registros**, incluyendo texto procesado y etiqueta de sentimiento.

### Distribución de clases

El dataset presenta un **desbalance de clases**, característica frecuente en problemas reales de clasificación:

- Positivas: ~54,8%
- Neutrales: ~36,3%
- Negativas: ~8,8%

Este desbalance representa un desafío especialmente relevante para la detección de reseñas negativas, al tratarse de una clase minoritaria.

---

## Metodología aplicada

### 1. Análisis exploratorio de datos (EDA)

Se realizó una exploración inicial del dataset incluyendo:

- Distribución de sentimientos
- Identificación de valores nulos
- Distribución de longitud de reseñas
- Comparación de longitud textual según sentimiento

Entre los hallazgos preliminares se observó que las **reseñas negativas tienden a ser más extensas**, lo que podría sugerir que los usuarios insatisfechos suelen describir sus experiencias con mayor nivel de detalle.

---

### 2. Procesamiento de Lenguaje Natural (NLP)

Se implementó un pipeline de preprocesamiento textual compuesto por:

- Conversión a minúsculas
- Tokenización
- Eliminación de stopwords
- Filtrado de palabras no alfabéticas
- Lematización

Estas transformaciones permitieron reducir ruido textual y conservar información lingüística relevante para el modelado.

---

### 3. Vectorización del texto

Para convertir texto en variables numéricas se utilizó **TF-IDF (Term Frequency – Inverse Document Frequency)**.

Configuración utilizada:

- `max_features = 5000`
- `ngram_range = (1,2)`

Esto permitió representar las reseñas en formato numérico considerando tanto palabras individuales como combinaciones frecuentes de términos.

---

## Modelos implementados

### Modelo baseline — Regresión Logística

Se implementó un modelo baseline basado en **Regresión Logística**, ampliamente utilizado en tareas de clasificación textual por su interpretabilidad y buen desempeño sobre representaciones TF-IDF.

**Resultado obtenido:**

- Accuracy aproximada: **83,5%**

Fortalezas:

- Buen desempeño general
- Entrenamiento rápido
- Alta interpretabilidad

Limitaciones:

- Baja capacidad para detectar reseñas negativas (clase minoritaria)

---

### Modelo de Deep Learning 1

Arquitectura:

- Dense(64)
- Activación ReLU
- Capa de salida Softmax

Resultado:

- Accuracy aproximada: **83%**

El modelo mostró un desempeño similar al baseline, aunque con indicios de overfitting moderado.

---

### Modelo de Deep Learning 2

Arquitectura:

- Dense(64)
- Dropout(0.3)
- Dense(32)
- Capa de salida Softmax

Resultado:

- Accuracy aproximada: **84,8%**

Este modelo logró una mejora moderada respecto del baseline y mostró mejor capacidad para identificar reseñas negativas.

---

## Comparación de resultados

| Modelo | Accuracy aproximada |
|---------|---------------------|
| Regresión Logística | ~83,5% |
| Red neuronal simple | ~83% |
| Red neuronal con Dropout | ~84,8% |

### Hallazgos principales

Si bien el modelo de Deep Learning no produjo mejoras drásticas en accuracy global, sí logró una **mejor detección de la clase negativa**, especialmente en términos de **recall**, aspecto particularmente relevante dada la presencia de desbalance en el dataset.

Esto sugiere que, para problemas de clasificación textual utilizando representaciones TF-IDF, los modelos clásicos continúan siendo altamente competitivos, aunque las redes neuronales pueden aportar mejoras sobre clases minoritarias.

---

## Tecnologías utilizadas

- Python
- Pandas
- NumPy
- Scikit-learn
- TensorFlow / Keras
- NLTK
- Matplotlib
- Seaborn

---

## Posibles mejoras futuras

Como líneas de trabajo futuras podrían explorarse:

- Word embeddings (Word2Vec, GloVe, FastText)
- Técnicas de balanceo de clases
- Arquitecturas más avanzadas de Deep Learning
- Modelos basados en Transformers

---

## Estructura del repositorio

```text
.
├── notebook/
│   └── NLP_Amazon_Reviews.ipynb
├── data/
│   └── amazon_reviews.csv
└── README.md
```
