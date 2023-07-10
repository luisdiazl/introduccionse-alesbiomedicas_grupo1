# Preliminary results of the development of an algorithm based on ECG parameters as a complement for the detection of metabolic syndrome in a population 20-35 years old

## Dataset
La adquisición de data relevante se extrajo de un estudio realizado por GBBA (Grupo de Bioingeniería y Biofísica Aplicada), y se ejecutó la extracción de datos de forma manual, con el objetivo del registro de nuevas bases de datos electrocardiográficos.

Asimismo, se definió una población de estudio, el cual poseía un rango de edad de 20 a 35 años, son no fumadores, sin tratamiento médico, sin deterioro físico o alguna enfermedad cardiovascular evidente. 

A continuación, se muestra características de los dos grupos de personas que alberga la base de datos. 
IMAGEN TABLA

En el caso de la extracción manual de datos, se obtuvieron 9 muestras en total: 6 sin MetS y 3 con MetS. Asimismo, se consideró como criterios de diagnóstico para clasificar esta data a parámetros como circunferencia abdombinal y presión arterial. 

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

- Aprendizaje Supervisado: Asume conjunto de datos de entrenamientos conocidos, a priori, y construye el modelo que permite predecir el valor de un dato no observado.
Se consideraron 4 estimadores: K-nearest neighbors (KNN), Regresión Logística (RL), Random Forest (RF) y Super Vector Machine (SVM)
  
- Aprendizaje No Supervisado: Conjunto de datos sin etiquetas atraviesa el proceso de entrenamiento de data, mediante agrupamiento o _´clustering´_.
Se consideraron 2 estimadores: K-means y Mean Shift

## Resultados
