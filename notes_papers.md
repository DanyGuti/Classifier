## Preprocesado

Tipos de ruido:
* Ruido amplificador (Ruido Gaussiano)
  * Forma idealizada del ruido blanco causado por fluctuaciones de señal. Puede haber más ruido en el canal azul que en el rojo y verde. 
* Ruido de impulsivo (Ruido de sal y pimienta)
  * Cuando hay "puntos" que pueden ser "pixeles muertos" encontrados en la imagen.
* Ruido de tiro
  * Sigue distribución Poisson, no tan diferente a la Gaussiana. Se identifica cuando el ruido es causado por los puntos con mayor luz "photon shot noise" y en áreas oscuras "dark shot noise" o "dark-current shot noise".
* Ruido de cuantización (ruido uniforme)
  * Causado al cuanitificar los pixelexs de una imagen percibida hacia un número discreto de niveles.
* Film grain
  * El grano de una "película" fotográfica es una señal de ruido dependiente, relacionada con el ruido de tiro. 
* Ruido on-isotropico
* Ruido de mancha (Ruido Multiplicativo)
  * Ruido granular, que inherentemente existe dentro y degrada la calidad del radar activo y la apertura sintética de las de imágenes (SAR). Puede ser modelado con valores aleatorios multiplicados por cada valor de pixel, por eso el nombre. 
* Ruido periódico [2]


Realce de contraste
Mejoramiento de la calidad de una imagen por medio de la equivalencia de histogramas. No se borran los detalles importantes. Incrementan la identificación del punto clave dentro de la imagen, mejorando la modificación de la imagen.
Existen ADE, CLAHE y AHE.
Con CLAHE, la imagen de entrada original es dividida en contextos de componentes no sobre-puestos llamados "sub-imágenes", celdas, o bloques utilizando el procedimiento CLAHE. Los dos parámetros de CLAHE que regulan la calidad de la imagen son bloques con tamaño y limitan el recorte. El histograma original es recortado, y se los pixeles recortados son redistribuidos en un nivel gris. La intensidad de cada pixel en la re-distribución del histograma está restricto a un máximo específico, no como el histograma estándar. El nivel de fuerza de los valores del pixel en la región del contexto del histograma es el pixel de salida con valor CLAHE. El histograma verdadero es dispersado hacia todas las intenisdades dentro del rango registrado de la iagen, cuando el histograma se concentra en los pixeles recortados en una altura en específico.[1]

Segmentación
Tarea de suma importancia para un problema de visión de computación, que consiste en particionar la imagen en múltiples segmentos o regiones basadas en ciertas características como su color, intensidad, textura o moción.
La meta de la segmentación es simplificar la representación de la imagen al agrupar los pixeles y regiones que comparten propiedades similares, haciendo más eficiente y sencillo la extracción de "features" de una imagen (datos importantes
de una imagen). Al aplicar esta técnica, se conseguirán regiones segmentadas que habilitan la eficiencia en el análisis e interpretación de los datos de una imagen. Puntos que pueden ser la iluminación de la imagen, en veces llamado bordes
de la imagen. Técnica ampliamente utilizada para procesado de imagenes digitales, modelo de reconocimiento, morfología de imágenes, extracción de recursos. [1]


Algorithm to get the basic area of the image, it is also necessary to carry out image grayscale, histogram equalization, image filtering, size normalizatio

Referencias
[1] A. Demelash and E. Derb, “Habesha Cultural Cloth Classification Using Deep Learning,” Scientific Reports, vol. 15, no. 1, Apr. 2025, doi: https://doi.org/10.1038/s41598-025-98269-5.
[2] A. Hambal, Z. Pei, and F. Libent, “Image Noise Reduction and Filtering Techniques,” International Journal of Science and Research (IJSR) ISSN, vol. 6, no. 3, pp. 2319–7064, Mar. 2017, doi: https://doi.org/10.21275/25031706.he
[3] H. Wang, “Garbage Recognition and Classification System Based on Convolutional Neural Network VGG16,” 2020 3rd International Conference on Advanced Electronic Materials, Computers and Software Engineering (AEMCSE), Apr. 2020, doi: https://doi.org/10.1109/aemcse50948.2020.00061. (IMAGE PRE-PROCESSING, OpenCV to crop objects)
[4] B. Gan and C. Zhang, “Research on the algorithm of urban waste classification and recycling based on deep learning technology,” Research on the algorithm of urban waste classification and recycling based on deep learning technology, Jul. 2020, doi: https://doi.org/10.1109/cvidl51233.2020.00-95.




# Utilizar un algorithmo contra Ruido de sal y pimienta


## Al entrenar el modelo
Se ha llegado a que, probablemente hay un desbalance en los datos de las clases, por lo que se ha intentado solucionar este problema
con el uso de one hot encoding