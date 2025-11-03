# Clasificación de dígitos manuscritos con Redes Neuronales Artificiales (MNIST)

## Descripción general
Este proyecto implementa un modelo de red neuronal multicapa (MLP) para el reconocimiento de dígitos manuscritos utilizando el conjunto de datos **MNIST**.  
El objetivo es comprender el funcionamiento de las redes neuronales profundas, su proceso de entrenamiento, y evaluar su desempeño con datos de prueba y con imágenes personalizadas diseñadas por el estudiante.

---

## Objetivos del proyecto
1. Implementar una red neuronal multicapa utilizando **TensorFlow/Keras**.  
2. Entrenar y validar el modelo con el dataset **MNIST**.  
3. Evaluar su rendimiento con un conjunto de prueba y con **50 imágenes personalizadas**.  
4. Aplicar tres técnicas de mejora del modelo base.  
5. Implementar un sistema de **predicción en tiempo real** mediante cámara.  
6. Documentar el proceso completo de entrenamiento, evaluación y resultados.

---

## Estructura del proyecto
| Bloque | Descripción |
|---------|--------------|
| **Bloque 1** | Importación de librerías necesarias para el entrenamiento, visualización y evaluación. |
| **Bloque 2** | Carga y normalización del dataset MNIST (0–9). |
| **Bloque 3** | Construcción del modelo MLP con tres capas densas y una capa de salida softmax. |
| **Bloque 4** | Entrenamiento del modelo y visualización de las gráficas de pérdida y exactitud. |
| **Bloque 5** | Evaluación del modelo con datos de prueba no vistos. |
| **Bloque 6** | Carga de 50 imágenes personalizadas desde Google Drive y preprocesamiento. |
| **Bloque 7** | Evaluación del modelo con las imágenes personalizadas y generación de reportes. |
| **Bloque 8** | Implementación de tres mejoras: Dropout, Regularización L2 y Estandarización Z-score. |
| **Bloque 9** | Predicción en tiempo real con cámara y visualización de resultados. |

---

## Arquitectura del modelo
El modelo base está compuesto por:
- **Entrada:** 28x28 píxeles (convertidos a vector de 784 valores).  
- **Capas ocultas:**  
  - Dense(128, activation='relu')  
  - Dense(64, activation='relu')  
  - Dense(32, activation='relu')  
- **Capa de salida:** Dense(10, activation='softmax')  
- **Optimización:** Adam  
- **Función de pérdida:** Sparse Categorical Crossentropy  

---

## Resultados principales
- Exactitud de entrenamiento: ~98%  
- Exactitud de validación: ~97%  
- Exactitud en prueba (MNIST): ~97%  
- Exactitud en imágenes personalizadas: ~94%  
- Se observaron mejoras con Dropout y Regularización L2 en la estabilidad del modelo.

---

## Mejoras implementadas
1. **Dropout:** reduce el sobreajuste desactivando aleatoriamente neuronas durante el entrenamiento.  
2. **Regularización L2:** penaliza los pesos grandes para mejorar la generalización.  
3. **Estandarización Z-score:** normaliza los datos considerando su media y desviación estándar.

---

## Predicción en tiempo real
El modelo se puede ejecutar con una cámara para realizar predicciones en tiempo real.  
Durante la ejecución:
- Presionar **q** para salir.  
- Presionar **i** para invertir colores.  
- Presionar **o** para activar umbral Otsu.  
- Presionar **n** para volver al modo normal.  

Ejemplo de ejecución en terminal (Anaconda):
```bash
python mnist_cam.py --model mnist_model.keras
