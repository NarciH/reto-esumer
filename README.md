# Clasificación de Tweets usando Redes Neuronales Recurrentes (RNN)

Este proyecto aborda el reto de clasificar 20,001 tweets en dos categorías usando arquitecturas basadas en redes neuronales recurrentes (RNN) con capas LSTM. A continuación, se describen los pasos para configurar el entorno, preprocesar los datos y diseñar el modelo.

---

## Requisitos

- **Python**: 3.10
- **Entorno virtual**: Se utilizará `venv` para gestionar las dependencias.

---

## Configuración del Entorno

### 1. Crear el entorno virtual

```bash
python3 -m venv rnn_env
```

### 2. Activar el entorno virtual

- En macOS/Linux:
  ```bash
  source rnn_env/bin/activate
  ```
- En Windows:
  ```bash
  .\rnn_env\Scripts\activate
  ```

### 3. Instalar las dependencias

Con el entorno virtual activado, ejecuta:

```bash
pip install --upgrade pip
pip install -r requirement.txt
```

---

## Dataset

El dataset está compuesto por un conjunto de **20,001 tweets**, cada uno etiquetado en una de dos categorías.
Este Dataset está público en esta url: https://www.kaggle.com/datasets/dataturks/dataset-for-detection-of-cybertrolls?resource=download

---

## Métrica de Evaluación

Se utilizarán redes neuronales recurrentes (RNN) para clasificar cada tweet en su correspondiente categoría.

---

## Estrategia de Resolución

### 1. Preprocesamiento de texto

Se debe realizar un preprocesamiento adecuado, que incluye:

- **Limpieza**: Remover caracteres especiales, emojis, menciones, URLs, etc.
- **Tokenización**: Convertir el texto en secuencias numéricas.
- **Padding**: Asegurar que todas las secuencias tengan la misma longitud mediante `pad_sequences`. Será necesario analizar el dataset para determinar un tamaño óptimo.

### 2. Diseño y Evaluación del Modelo

Se evaluarán diferentes arquitecturas utilizando las siguientes capas:

- **Sequential()**
- **Embedding()**
- **LSTM()**
- **Dropout()**
- **Dense()**

#### Parámetros a Evaluar

1. Dimensión de la capa `Embedding()`:
   - `[32, 64, 128]`

2. Dimensión de la capa `LSTM()`:
   - `[64, 128, 196]`

3. Función de pérdida inicial:
   - **Suma Cuadrática**

El modelo generará un vector de probabilidades, asignando una categoría según la probabilidad más alta.

---

### 3. Evaluación de Variaciones del Modelo (Opcional)

Se explorarán las siguientes configuraciones adicionales con el objetivo de cuestionar dicha decisión y evalaur el cambio que puede tener en el modelo. 

Estas configuraciones son:

1. Cambiar la función de activación de la capa `Dense` a **ReLU**.
2. Configurar la tasa de aprendizaje en **1e-5** y el decaimiento en **1e-5**.
3. Ajustar la capa `Embedding()` a una salida de **128 elementos**.
4. Configurar la capa `LSTM()` con un espacio de salida de **196 elementos**.
5. Cambiar la función de pérdida a **Crosentropía Binaria**.
6. Manejar el desbalanceo en las categorías del dataset.
7. Incrementar el número de épocas a **25**.

---

## Ejecución

1. Asegúrate de tener el entorno virtual activado.
2. Desde Visual Studio Code abre el archivo
   ```bash
   Reto Clasificación Texto - BootCamp IA.ipynb
   ```
3. Inicia con el desarrollo de tu código.
---

## Resultados Esperados

Al final del entrenamiento, se generarán las métricas de evaluación (precisión, recall, F1-score) para determinar el desempeño del modelo en la clasificación de los tweets.
