# Preliminary results of the development of an algorithm based on ECG parameters as a complement for the detection of metabolic syndrome in a population 20-35 years old

## Dataset
La adquisición de data relevante se extrajo de un estudio realizado por GBBA (Grupo de Bioingeniería y Biofísica Aplicada), y se ejecutó la extracción de datos de forma manual, con el objetivo del registro de nuevas bases de datos electrocardiográficos.

Asimismo, se definió una **población de estudio**, el cual poseía un rango de edad de 20 a 35 años, son no fumadores, sin tratamiento médico, sin deterioro físico o alguna enfermedad cardiovascular evidente. 

A continuación, se muestra **características** de los dos grupos de personas que alberga la base de datos. 
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/main/imges/descridata.jpg" width="50%" height="50%">
</p> 

En el caso de la extracción manual de datos, se obtuvieron 9 muestras en total: 6 sin MetS y 3 con MetS. Asimismo, se consideró como **criterios de diagnóstico** para clasificar esta data a parámetros como circunferencia abdombinal y presión arterial. 

Dentro de las particularidades de las señales electrocardiográficas (ECG), se encuentran las siguientes:
* 5 registros por paciente
* Duración entre 10 - 15 minutos
* 3 archivos .csv
  - Complejo QRS (ms)
  - Tiempo de intervalos RR (ms)
  - Registro ECG
* 12 derivaciones con frecuencia de muestreo de 1000 muestras/segundo, con resolución de 16 bits

En el proyecto, se tomó en cuenta los últimos 20 segundos de las señales ECG de forma que 

## Procesamiento

### Preprocesamiento
Consiste en la etapa de filtrado de las señales ECG, compuesta por 3:
- Filtro Butterworth paso alto de 1 Hz, para eliminar componente DC de ECG
- Filto Notch rechaza banda de 60 Hz, para evitar interferencia eléctrica
- Filtro Butterworth paso bajo de 25 Hz, para eliminar ruido de alta frecuencia

### Extracción de Características
A través de la Transformada Wavelet Discreta (DWT), es posible analizar este tipo de señales a través del método de ventanas. Es asi como se obtienen las características o criterios electrocardiográficos a evaluar para el modelo, los cuales se dividen en grupos de características de:
* Intervalos de latidos
* Intervalos RR
* Amplitud de ondas de los latidos

Asimismo, se aplica una técnica de escalado estándar que tiene por objetivo estandarizar los picos de onda, de forma que no se halle una gran dispersión de datos. 

### Creación de Base de Datos
A partir de los datos extraídos de la etapa anterior, es posible la creación de base de datos que permite la implementacion de modelos de Machine Learning.
En este trabajo, el propósito es establecer qué tipo de modelo es el más adecuado para la problemática identificada. Entre las opciones consideradas, se contiene modelos basados en:

- **Aprendizaje No Supervisado**: Conjunto de datos sin etiquetas atraviesa el proceso de entrenamiento de data, mediante agrupamiento o _´clustering´_. Por identificación de grupos homogéneos y heterogéneos, es posible la predicción de un dato no conocido.
Se consideraron 2 estimadores: K-means y Mean Shift

- **Aprendizaje Supervisado**: Asume conjunto de datos de entrenamientos conocidos, a priori, y construye el modelo que permite predecir el valor de un dato no observado.
Se consideraron 4 estimadores: K-nearest neighbors (KNN), Regresión Logística (RL), Random Forest (RF) y Super Vector Machine (SVM)

## Resultados
Según el modelo de Machine Learning:

### Aprendizaje No Supervisado
Se aplicó la técnica de PCA con la finalidad de reducir dimensionalidad de datos. (PCA = 2, 3). Por lo tanto, se tendrían 4 algoritmos de predicción:
* K-means aplicado en PCA de 2 componentes.
* K-means aplicado en PCA de 3 componentes.
* Mean Shift aplicado en PCA de 2 componentes.
* Mean Shift aplicado en PCA de 3 componentes.

Se observa la gráfica de distribución de datos obtenidos con los 4 modelos resultantes de aprendizaje no supervisado.
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/main/imges/distribu.jpeg" width="50%" height="100%">
</p>

Cada algoritmo se somete a un análisis mediante 5 métricas las cuales son: precisión, sensibilidad, especificidad, constante _'Kappa'_, y constante _'Silhouette'_.
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/main/imges/tabla1.jpeg" width="25%" height="25%">
</p> 

Se observa que todos los valores de las métricas son bajos, por lo que se indicaría que un modelo de aprendizaje no supervisado no sería el más adecuado para el caso en cuestión. De igual forma, es posible deducir visualmente que en las gráficas de distribución no se observan agrupaciones de clasificación de datos de manera notoria, quedando en duda su eficiencia cuando se requiera predecir una nueva entrada.  

En el caso de análisis de la gráfica de confusión, se reitera que el modelo realizado no es óptimo para los datos obtenidos puesto que las predicciones que se obtiene son bastante erróneas y representan casi el 50% del total, lo cual se evidencia con las métricas anteriormente colocadas.
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/main/imges/matrizconfu1" width="25%" height="25%">
</p> 

### Aprendizaje Supervisado
Se aplicó la técnica de PCA con la finalidad de reducir dimensionalidad de datos. (PCA = 2, 3). Por lo tanto, se tendrían 4 algoritmos de predicción:
* K-means aplicado en PCA de 2 componentes.
* K-means aplicado en PCA de 3 componentes.
* Mean Shift aplicado en PCA de 2 componentes.
* Mean Shift aplicado en PCA de 3 componentes.

Cada algoritmo se somete a un análisis donde las métricas resultan ser la precisión, sensibilidad, especificidad, constante _'Kappa'_ y puntuación F1.
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/main/imges/tabla2.jpeg" width="25%" height="25%">
</p> 

Se aprecia que el mejor modelo para este entrenamiento es el K-Nearest Neighbor (KNN), ya que su valor es el mayor en la mayoría de los valores de métricas, siendo la especificidad la única excepción. Sin embargo, este último valor sigue siendo bastante alto.

Si se observa los resultados del modelo KNN en la matriz de confusión, se puede observar que el modelo predice 19 valores de forma errónea de los más de 100 datos analizados, en los que 12 son predichos como negativos cuando era positivos (falsos negativos) y 7 valores fueron predichos como positivos siendo estos negativos (falsos positivos).
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/main/imges/matrizconfu2" width="25%" height="25%">
</p> 

A partir de ambos modelos se observa cómo el algoritmo de aprendizaje supervisado arroja mejores resultados de precisión tanto en la identificación de casos positivos como negativos, además de mostrar una óptima concordancia en sus clasificaciones que permitan indicar que los resultados no son productos del azar.

