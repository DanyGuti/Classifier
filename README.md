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
1. Recolección de datos (dataset) en lugar de inicio o principal: [https://archive.ics.uci.edu/dataset/908/realwaste]
2. Verificación y validación de (dataset) de manera local
3. Recolección de datos (dataset) en: [https://www.kaggle.com/datasets/alistairking/recyclable-and-household-waste-classification?resource=download], [https://www.kaggle.com/datasets/alexanderuzhinskiy/moss-species-classification-dataset], algunas imágenes de [https://www.kaggle.com/datasets/aashidutt3/waste-segregation-image-dataset], algunas imágenes de [https://www.kaggle.com/datasets/ichhadhari/leaf-images], algunas imágenes de [https://www.kaggle.com/c/cassava-disease/overview], algunas imágenes de [https://www.kaggle.com/datasets/wasifmahmood01/custom-waste-classification-dataset]
4. Uso de scripts en shell para organización de imagenes por categorías ({clase}_{i}.jpg)
5. Merge y separación de datos en batch de manera local
6. Data splitting 70% training, 15% validation y 15% testing (se aplicó shuffle disminuyendo el bias por ciertas imágenes)
7. Pre-procesado de datos (Siguiendo ideas de procesos de papers, ver sección abajo Ruido Gaussiano, Detección de border con Canny, étc)
8. Data augmentation (no se aplicó ninguna estandarización VGG16 además de estandarizar las fotos a 224, 244). 
9. Balanceo de clases en disco (no se aplicó ninguna estandarización VGG16 además de estandarizar las fotos a 224, 244), este paso involucró hacer dos iteraciones de los pasos 2-8, ya que lo mejor es que las clases estén balanceadas con el número de datos por categoría. En este caso, las clases más difíciles de encontrar datos fueron : Vegetación, textiles, basura miscelánea y comida orgánica (encontradas en los URLs de Kaggle). Se buscó que para datos de training, se mantuviera un número de 1,000 imágenes por clase, sino, se aplicaría el aumento de datos, normalizando los pixeles entre 0 y 1, rotando imágenes de manera random entre 0 y 20 grados, mover la imagen de manera horizontal y/o vertical en un 20% máximo, aplicando forma como de trapezoide a la imagen en máximo un 20%, aplicar zoom en máximo un 20%, y de manera aleatoria voltear una imagen de manera horizontal. Se hizo un calculo, para que se tomara las imagenes faltantes para llegar a 1000 para cada clase, divido por 5 y después se aplico un batch por imagen, en un rango de 5 como generador de imagenes a disco.
10. Data splitting, a nuevos directorios con el ya balanceo de clases (aplicado el paso 10)
11. Feature engineering (feature extraction) con modelo pre-entrenado VGG16
12. Construcción y entrenamiento del modelo con arquitectura CNN
13. Muestra de gráficas (entrenamiento vs precisión de validación y entrenamiento vs pérdida de validación)
14. Iteración del paso 11 en adelante

---
### Recursos utilizados
[1] F. Chollet, “Deep Learning with Python, Second Edition,” O’Reilly Online Learning, Dec.
 07, 2021. https://learning.oreilly.com/library/view/deep-learning-with/9781617296864/Text/
 08.htm#heading_id_14 (accessed May 15, 2025).

[2] T. Kaur and T. K. Gandhi, “Automated Brain Image Classification Based on VGG-16 and
 Transfer Learning,” 2019 International Conference on Information Technology (ICIT), 
 Dec. 2019, doi: https://doi.org/10.1109/icit48102.2019.00023
 (accessed May 15, 2025).

[3] A. Demelash and E. Derb, “Habesha Cultural Cloth Classification Using Deep Learning,”
 Scientific Reports, vol. 15, no. 1, Apr. 2025, doi: https://doi.org/10.1038/s41598-025-98269-5,
 (accessed May 15, 2025).

[4] A. Patil, A. Tatke, N. Vachhani, M. Patil, and P. Gulhane, “Garbage Classifying Application 
Using Deep Learning Techniques,” IEEE Xplore (Scopus), Aug. 01, 2021. https://ieeexplore.ieee.org/
document/9573599 (accessed May 15, 2025).

[5] A. Grzybowski, K. Pawlikowska – Łagód, and W. C. Lambert, “A History of Artificial Intelligence,” Clinics in Dermatology, vol. 42, no. 3, Jan. 2024, doi: https://doi.org/10.1016/j.clindermatol.2023.12.016.

[6] “UCI Machine Learning Repository,” Uci.edu, 2023. https://archive.ics.uci.edu/dataset/908/realwaste (accessed May 22, 2025).

[7] H. Wang, “Garbage Recognition and Classification System Based on Convolutional Neural Network VGG16,” 2020 3rd International Conference on Advanced Electronic Materials, Computers and Software Engineering (AEMCSE), Apr. 2020, doi: https://doi.org/10.1109/aemcse50948.2020.00061.

[8] A. Hambal, Z. Pei, and F. Libent, “Image Noise Reduction and Filtering Techniques,” International Journal of Science and Research (IJSR) ISSN, vol. 6, no. 3, pp. 2319–7064, Mar. 2017, doi: https://doi.org/10.21275/25031706

[9] S. Tammina, “Transfer learning using VGG-16 with Deep Convolutional Neural Network for Classifying Images,” International Journal of Scientific and Research Publications (IJSRP), vol. 9, no. 10, p. p9420, Oct. 2019, doi: https://doi.org/10.29322/ijsrp.9.10.2019.p9420

---

### Uso
1. Crear un ambiente de entorno para procesar código escrito en jupyter notebook, así como selección de un kernel con versión de python mayor a 3.10.
2. Leer y correr cada una de las celdas del libro de Jupyter Notebook llamado: AI_Classifier.ipynb (no correr la celda de código correspondiente a Data Splitting)
3. Generar los gráficos de precisión del modelo
4. Generar el mapa de calor del modelo