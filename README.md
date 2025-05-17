# Clasificador de Basura con uso de Inteligencia Artificial
## Fines Reservados del Tecnológico de Monterrey Campus Querétaro

### Autor: Daniel Gutiérrez Gómez | A01068056
### Profesores: Benjamín Valdés Aguirre, Pedro Oscar Pérez Murueta y Manuel Iván Casillas del Llano
### Herramientas y librerías: Jupyter Notebook, Keras, Tensorflow, matplot, pydot, numpy

El mini-proyecto desarrollado, consiste en la resolución al problema de clasificación de basura.

Dicho problema, será resuelto con el uso de Inteligencia Artificial, más en concreto un modelo clasificatorio del tipo supervisado.
El anterior, puede ser un modelo con arquitectura de tipo CNN (Convolutional Neural Network). Además del modelo anterior, y dadas
las condiciones del problema y sus variables (investigaciones en el libro de "Introduction to Deep Learning With Python", así como varios reportes de investigación y la cantidad pequeña de datos)
no es posible el uso únicamente de un modelo CNN, por lo cual, es necesario utilizar herramientas externas. En este caso, el uso de un modelo ya pre-entrenado, llamado VGG16.

---
Las clasificaciones del modelo son las siguientes:
* Vegetación
* Basura de textil
* Plástico
* Papel
* Basura miscelánea
* Metal
* Vidrio
* Comida Orgánica
* Cartón

---
#### Metodología
1. Recolección de datos (dataset) en: [https://archive.ics.uci.edu/dataset/908/realwaste]
2. Verificación y validación de (dataset) de manera local
3. Recolección de datos (dataset) en: [https://www.kaggle.com/datasets/alistairking/recyclable-and-household-waste-classification?resource=download] y [https://www.kaggle.com/datasets/alexanderuzhinskiy/moss-species-classification-dataset]
4. Uso de scripts en shell para organización de imagenes por categorías ({clase}_{i}.jpg)
5. Merge y separación de datos en batch de manera local
6. Data splitting 70% training, 15% validation y 15% testing (se aplicó shuffle disminuyendo el bias por ciertas imágenes)
7. Pre-procesado de datos (Siguiendo ideas de procesos de papers, ver sección abajo Ruido Gaussiano, Detección de border con Canny, étc)
8. Data augmentation (balanceo de clases en disco)
9. Data splitting, a nuevo directorio
10. Feature engineering (feature extraction) con modelo pre-entrenado VGG16
11. Construcción y entrenamiento del modelo con arquitectura CNN
12. Muestra de gráficas (entrenamiento vs precisión de validación y entrenamiento vs pérdida de validación)
13. Iteración del paso 11 en adelante

---
### Recursos utilizados
[1] F. Chollet, “Deep Learning with Python, Second Edition,” O’Reilly Online Learning, Dec.
 07, 2021. https://learning.oreilly.com/library/view/deep-learning-with/9781617296864/Text/
 08.htm#heading_id_14 (accessed May 15, 2025).

[2] T. Kaur and T. K. Gandhi, “Automated Brain Image Classification Based on VGG-16 and
 Transfer Learning,” 2019 International Conference on Information Technology (ICIT), 
 Dec. 2019, doi: https://doi.org/10.1109/icit48102.2019.00023.

[3] A. Demelash and E. Derb, “Habesha Cultural Cloth Classification Using Deep Learning,”
 Scientific Reports, vol. 15, no. 1, Apr. 2025, doi: https://doi.org/10.1038/s41598-025-98269-5.

[4] A. Patil, A. Tatke, N. Vachhani, M. Patil, and P. Gulhane, “Garbage Classifying Application 
Using Deep Learning Techniques,” IEEE Xplore (Scopus), Aug. 01, 2021. https://ieeexplore.ieee.org/
document/9573599 (accessed Oct. 20, 2022).

---

### Uso
1. Crear un ambiente de entorno para procesar código escrito en jupyter notebook, así como selección de un kernel con versión de python mayor a 3.10.
2. Leer y correr cada una de las celdas del libro de Jupyter Notebook llamado: AI_Classifier.ipynb (no correr la celda de código correspondiente a Data Splitting)
3. Generar los gráficos de precisión del modelo
4. Generar el mapa de calor del modelo