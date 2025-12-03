# Project_4
El presente repositorio contiene el notebook de Google Colab en el que se realizó el proyecto 4 de computación numérica. Este trabajo fue realizado junto con Marlon Alexander Gonzalez y Laura Sofia Alarcón

# Objetivo
Este proyecto implementa un sistema de clasificación automática de imágenes para determinar si un soporte de pararrayos se encuentra en buen estado o presenta corrosión.
El enfoque combina técnicas tradicionales de Computer Vision con un modelo clásico de Machine Learning, logrando un pipeline reproducible y fácil de interpretar.

# Características evaluadas en las imágenes
Se emplea una combinación de:
HOG (Histogram of Oriented Gradients)
Captura estructura, bordes y gradientes relevantes para describir textura y contornos.
LBP (Local Binary Pattern)
Extrae patrones locales de textura y produce un histograma robusto a cambios de iluminación.

Ambos descriptores se concatenan para formar el vector final de rasgos de cada imagen.

# Modelo implementado
El modelo utilizado es un SVM con kernel lineal, ensamblado mediante un pipeline:
StandardScaler()
Normaliza los rasgos (fundamental para SVM).
SVC(kernel="linear")
Clasifica entre good (0) y rust (1).

El pipeline facilita la reproducibilidad y evita fugas de datos (data leakage).

# Validación
El proyecto soporta validación robusta mediante Stratified K-Fold, lo cual:
- Mantiene el balance de clases en cada fold.
- Permite usar todo el dataset para entrenamiento + validación.
Da métricas más confiables en datasets relativamente pequeños.

Las métricas recomendadas:
- Accuracy
- Precision
- Recall
- F1-Score

# Clasificación individual
El códgio también cuenta con una función que:
- Recibe el índice de una image
- Extrae rasgos (HOG+LBP)
- Predice si está oxidada o no
- Muestra la imagen y la etiqueta predicha

# Tecnologías utilizadas
- Python 3.x
- OpenCV
- Scikit-Learn
- Scikit-Image
- Matplotlib
- Numpy
