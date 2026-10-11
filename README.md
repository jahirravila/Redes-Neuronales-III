# 🧠 Redes Neuronales III: Optimización y Evaluación de Modelos (MNIST)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1LKQMvso1kJTglo2uXEtc0SZQ7hNAL5fI?usp=sharing)


Este repositorio contiene la práctica de la asignatura **Redes Neuronales III**, enfocada en la implementación, optimización y evaluación de un Perceptrón Multicapa (MLP) utilizando **TensorFlow y Keras**. El objetivo principal es clasificar dígitos manuscritos del famoso conjunto de datos **MNIST**, aplicando técnicas avanzadas de Deep Learning para gestionar el *Tradeoff Bias-Variance*.

## 📋 Tabla de Contenidos
- [Descripción del Proyecto](#-descripción-del-proyecto)
- [Arquitectura y Técnicas Aplicadas](#-arquitectura-y-técnicas-aplicadas)
- [Resultados y Métricas](#-resultados-y-métricas)
- [Ejecución en Google Colab](#-ejecución-en-google-colab)
- [Autor](#-autor)

---

## 🚀 Descripción del Proyecto

El proyecto demuestra el ciclo de vida completo del entrenamiento de una red neuronal profunda, abarcando desde la preparación de los datos hasta la evaluación exhaustiva del modelo. Se hace especial énfasis en:
*   La correcta partición de los datos en conjuntos de **Entrenamiento (Train), Validación (Dev) y Prueba (Test)**.
*   El control del sobreajuste (*overfitting*) mediante técnicas de **regularización**.
*   El uso de algoritmos de **optimización** modernos para una convergencia eficiente.

## ⚙️ Arquitectura y Técnicas Aplicadas

### 1. Preprocesamiento de Datos
*   **Aplanamiento:** Conversión de imágenes 2D (28x28) a vectores 1D (784 características).
*   **Normalización:** Escalamiento de píxeles al rango `[0, 1]` para acelerar el cálculo del gradiente.

### 2. Arquitectura de la Red (MLP)
*   **Entrada:** 784 neuronas.
*   **Capas Ocultas:** Dos capas densas de 256 y 128 neuronas.
*   **Activación Oculta:** `ReLU` (Rectified Linear Unit) con inicialización `he_normal` para evitar el desvanecimiento del gradiente.
*   **Salida:** 10 neuronas con activación `Softmax` (distribución de probabilidad).

### 3. Optimización y Regularización
*   **Optimizador:** Algoritmo **Adam** con tasa de aprendizaje adaptativa (`learning_rate=1e-3`).
*   **Dropout:** Tasa de `0.2` en las capas ocultas para evitar la co-adaptación de neuronas.
*   **Early Stopping:** Monitoreo de `val_loss` con una paciencia de 3 épocas para restaurar los mejores pesos y evitar el overfitting.

---

## 📊 Resultados y Métricas

El modelo fue evaluado en el conjunto de prueba (10,000 imágenes nunca antes vistas), logrando resultados altamente robustos gracias a la regularización implementada:

*   **Exactitud (Accuracy):** ~98.22%
*   **Pérdida (Loss):** ~0.0626
*   **Precision, Recall y F1-Score:** > 98% en promedio.

Se generó además una **Matriz de Confusión** que permite identificar las equivocaciones morfológicas más frecuentes del modelo (ej. confundir un 7 con un 2 o un 9 con un 4).

---

## 💻 Ejecución en Google Colab

El código fuente está diseñado para ser ejecutado de forma interactiva en Google Colab. No se requiere configuración local ni instalación de dependencias, ya que el entorno en la nube de Google provee todo lo necesario.

👉 **[Ejecutar el Notebook Interactivo Aquí](https://colab.research.google.com/drive/1LKQMvso1kJTglo2uXEtc0SZQ7hNAL5fI?usp=sharing)**

---

## ✍️ Autor
* **Jahir Avila** - *Estudiante Universitario*

*Proyecto académico desarrollado para evidenciar la aplicación de buenas prácticas en Deep Learning, en cumplimiento con las normas institucionales.*
