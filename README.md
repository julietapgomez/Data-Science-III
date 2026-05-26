# Clasificación automática de sentimientos en reseñas de Amazon mediante NLP y Deep Learning

## Descripción del proyecto

Este proyecto tiene como objetivo clasificar automáticamente el sentimiento de reseñas de productos de Amazon utilizando técnicas de Procesamiento de Lenguaje Natural (NLP), Machine Learning y Deep Learning.

Se desarrolló un pipeline completo de análisis de texto, incluyendo exploración de datos, preprocesamiento lingüístico, representación numérica mediante TF-IDF y entrenamiento de modelos predictivos.

El objetivo principal fue identificar si una reseña expresa un sentimiento:

- Positivo
- Neutral
- Negativo

---

## Objetivos

- Aplicar técnicas de NLP sobre un dataset real de reseñas.
- Analizar la distribución de clases y características textuales.
- Implementar un pipeline de limpieza y normalización del lenguaje.
- Comparar estrategias de lematización utilizando **NLTK** y **spaCy**.
- Representar texto mediante **TF-IDF**.
- Construir un modelo baseline con **Regresión Logística**.
- Implementar modelos de **Deep Learning** utilizando redes neuronales densas.
- Evaluar el rendimiento mediante métricas de clasificación.

---

## Dataset utilizado

Se utilizó un dataset de reseñas de Amazon con más de **17.000 registros**, incluyendo:

- Texto de la reseña
- Clasificación del sentimiento
- Puntaje de review

El dataset cumple con los requisitos mínimos de volumen de datos establecidos para el proyecto final.

---

## Tecnologías y librerías utilizadas

### Lenguaje
- Python

### Librerías principales

#### Análisis y manipulación de datos
- Pandas
- NumPy

#### Visualización
- Matplotlib
- Seaborn

#### Procesamiento de Lenguaje Natural (NLP)
- NLTK
- spaCy
- Regex (re)

#### Machine Learning
- Scikit-Learn

#### Deep Learning
- TensorFlow / Keras

---

## Proceso realizado

### 1. Exploración del dataset (EDA)
Se realizó un análisis exploratorio del conjunto de datos para comprender:

- Distribución de sentimientos
- Longitud textual de reseñas
- Palabras más frecuentes
- Posible desbalance de clases

### 2. Preprocesamiento del texto
Se implementó un pipeline NLP compuesto por:

- Limpieza mediante Regex
- Conversión a minúsculas
- Tokenización
- Eliminación de stopwords
- Filtrado de caracteres no alfabéticos
- Lematización con NLTK
- Comparación con spaCy

### 3. Representación numérica
Se utilizó **TF-IDF (Term Frequency - Inverse Document Frequency)** para transformar el texto en representaciones numéricas aptas para modelos predictivos.

### 4. Modelado
Se entrenaron distintos modelos:

#### Modelo baseline
- Regresión Logística

#### Modelos Deep Learning
- Red neuronal densa simple
- Red neuronal con BatchNormalization y Dropout

### 5. Evaluación
Los modelos fueron evaluados utilizando:

- Accuracy
- Precision
- Recall
- F1-score
- Classification Report
- Matriz de confusión
- Validación cruzada (Cross Validation)

---

## Resultados

El modelo baseline de **Regresión Logística** alcanzó un accuracy cercano al **83,5%**, mostrando un desempeño competitivo para clasificación textual mediante TF-IDF.

Posteriormente, se implementaron modelos de **Deep Learning**, alcanzando un accuracy aproximado de **84,8%**, con mejoras moderadas respecto al baseline y mejor comportamiento sobre clases minoritarias.

---

## Limitaciones

El proyecto utiliza representaciones **TF-IDF**, por lo que los modelos no capturan completamente el contexto semántico profundo del lenguaje.

Como trabajo futuro podrían explorarse:

- Word2Vec
- GloVe
- FastText
- LSTM
- GRU
- Transformers

---

## Estructura del repositorio

```text
📁 dataset/
📄 amazon_reviews.csv

📁 notebook/
📄 proyecto_final_nlp_amazon.ipynb

📄 README.md
```

---

## Autor

**Julieta Gómez**  
Proyecto final – Data Science III  
CODERHOUSE
