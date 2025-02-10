# Entrenamiento de CNN con Transfer Learning utilizando MobileNetV2

Este proyecto implementa una **Red Neuronal Convolucional (CNN)** para la clasificación de imágenes utilizando **Transfer Learning** con MobileNetV2 como modelo base. Se utiliza un conjunto de datos de imágenes de Pokémon para entrenar y evaluar el modelo. El objetivo principal es aprovechar la arquitectura preentrenada de MobileNetV2 y agregar capas personalizadas para lograr una clasificación precisa.

---

## Descripción del Proyecto

El programa incluye las siguientes características principales:

- **Preprocesamiento del Dataset**:
  - Se carga un archivo ZIP que contiene el conjunto de datos de imágenes, se descomprime y organiza.
  - Las imágenes se procesan a un tamaño estándar de 224x224 píxeles y se normalizan para valores entre 0 y 1.
  - Las etiquetas de las imágenes se codifican numéricamente utilizando `LabelEncoder`.

- **División del Dataset**:
  - Se divide el conjunto de datos en tres subconjuntos: entrenamiento (70%), validación (20%) y prueba (10%).

- **Arquitectura del Modelo**:
  - Se utiliza **MobileNetV2**, un modelo preentrenado en ImageNet, como base congelada.
  - Se añaden capas densas personalizadas para adaptar el modelo al conjunto de datos.
  - Se utiliza una capa `GlobalAveragePooling2D` seguida de capas `Dense` con activaciones `ReLU` y `softmax`.

- **Entrenamiento y Evaluación**:
  - Se entrena el modelo durante 40 épocas con `EarlyStopping` para prevenir el sobreajuste.
  - El modelo alcanza una precisión del **85% en el conjunto de prueba**.
  - Se evalúa el desempeño con imágenes externas y se genera una matriz de confusión normalizada para visualizar las predicciones.

- **Pruebas con Imágenes Externas**:
  - Se prueban imágenes no vistas previamente para medir la capacidad de generalización del modelo.

---

## Requisitos del Proyecto

Para ejecutar este proyecto, necesitarás instalar las siguientes bibliotecas de Python:

- `tensorflow`
- `tensorflow_model_optimization`
- `numpy`
- `matplotlib`
- `seaborn`
- `scikit-learn`
- `Pillow`

Puedes instalarlas con:
```bash
pip install tensorflow tensorflow-model-optimization numpy matplotlib seaborn scikit-learn Pillow
