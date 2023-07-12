# Preliminary results of the development of an algorithm based on ECG parameters as a complement for the detection of metabolic syndrome in a population 20-35 years old

## Introducción 
Las enfermedades cardiovasculares (ECV) son un conjunto de trastornos que afectan al corazón y a los vasos sanguíneos, representando una de las principales causas de morbilidad y mortalidad a nivel global. Según la OMS, en 2019, 2.0 millones de personas murieron a causa de las enfermedades cardiovasculares [1], y en Perú la tasa fue de 73.5 muertes por cada 100.000 habitantes [2]. Estas enfermedades incluyen condiciones como la enfermedad coronaria, la hipertensión arterial, los accidentes cerebrovasculares y la insuficiencia cardíaca, los cuales representan una preocupación de salud pública de gran magnitud. 
Paralelamente, el síndrome metabólico (MetS) se ha reconocido como un factor de riesgo significativo para el desarrollo de enfermedades cardiovasculares y diabetes tipo 2. Las definiciones más ampliamente utilizadas han sido las formuladas por el European Group for the Study of Insulin Resistance (EGIR) y por el Adult Treatment Panel III (ATP-III) del National cholesterol Education Program (NCEP) [3]. Esta condición se caracteriza por la presencia de múltiples anomalías metabólicas, como la obesidad abdominal, la resistencia a la insulina, hipertensión arterial y los niveles de anomalías de lípidos en la sangre [4]. 
Por otro lado, el electrocardiograma (ECG) es una prueba no invasiva que registra la actividad eléctrica del corazón. Se utiliza ampliamente para evaluar la salud cardiovascular, diagnosticar trastornos del ritmo cardíaco y detectar posibles problemas en el corazón [5]. El procedimiento de ECG se realiza mediante la colocación de electrodos en el cuerpo y registra ondas P, complejo QRS y ondas T, que representan la repolarización auricular, despolarización ventricular y la repolarización ventricular, respectivamente [6]. Aunque sus características no proporcionan información directa sobre el MetS en sí mismo, el ECG puede proporcionar indicios o hallazgos que están relacionados con esta condición [7]. 
En vista de la complejidad y el impacto del síndrome metabólico en la salud cardiovascular, resulta necesario investigar nuevas herramientas y enfoques para evaluar y detectar el riesgo asociado a esta condición. En este trabajo, se plantea el uso de machine learning como un complemento que permite identificar el riesgo de síndrome metabólico. Al utilizar la información presente en el ECG, se busca mejorar la detección temprana y la estratificación del riesgo relacionado con MetS, lo cual podría tener un impacto significativo en la prevención y el manejo de enfermedades cardiovasculares y la diabetes tipo 2.

## Problemática
El síndrome metabólico se considera una amenaza sanitaria moderna debido a su significativa expansión global [8]. Entre las principales causas del incremento de su prevalencia se encuentra el alto consumo de comidas rápidas con elevado contenido calórico y bajo contenido de fibra, así como la disminución de la actividad física debido a estilos de vida sedentarios [8]. Según estadísticas publicadas por la International Diabetes Foundation (IDF), la prevalencia mundial del MetS se estima en alrededor de 25% [8]. En Perú, un estudio hecho en el Hospital I Florencia de Mora de EsSalud, ubicado en Trujillo, La Libertad, la prevalencia del MetS es del 38.97% en sus pacientes y del 42.10% en la población adulto joven. [9].

Generalmente, el diagnóstico del síndrome metabólico se basa en la identificación de características físicas y evaluación de análisis de laboratorio [10]. Un estudio en Perú analizó la prevalencia de factores en riesgo para síndrome metabólico en una población de Lima en el que los criterios de diagnóstico más comunes fueron el  sobrepeso,  la  obesidad  abdominal, colesterol alto, C-HDL bajo, hipertrigliceridemia e hipertensión arterial para una población entre 20 a 59 años [11].
En la actualidad, existen investigaciones que evalúan el uso del ECG como una posible herramienta de criterio para la detección de MetS dado que las anomalías en las señales electrocardiográficas para la evaluación de ECVs son más comunes en este tipo de pacientes [12][13]. Un estudio de cohorte realizado en una población iraní evaluó la relación entre anomalías en la señal del ECG y el MetS [14]. Se analizaron parámetros del ECG como la frecuencia cardiaca, duración de la onda P (mS), intervalo PR, duración QRS, amplitud R (mV), eje P (°), eje QRS (°), etc. dentro de una población total de 6958 participantes, de los cuales 3001 eran hombres y 3957 mujeres [14]. 

Es difícil atender y solucionar todos los factores causales del MetS; no obstante, el refuerzo de la importancia de estilos de vida activos, la promoción de los alimentos saludables sobre la comida chatarra y la educación a las poblaciones sobre el MetS potencialmente contribuirían a su control. En este contexto, es también importante tener métodos de detección certeros y eficientes que asistan al personal médico a detectar y tratar el síndrome metabólico. 

Por ello, proponemos el uso de algoritmos de machine learning para evaluar señales ECG de pacientes y detectar la existencia de síndrome metabólico en la población de jóvenes adultos entre 20-35 años. Además, el propósito del proyecto es evaluar y comprobar que el modelo de clasificación con mayor desempeño resultante demuestre resultados que permitan asegurar que es un robusto complemento para la detección de síndrome metabólico. 

## Propuesta de solución
## Dataset
La adquisición de data relevante se extrajo de un estudio realizado por GBBA (Grupo de Bioingeniería y Biofísica Aplicada), y se ejecutó la extracción de datos de forma manual, con el objetivo del registro de nuevas bases de datos electrocardiográficos de síndrome metabólico (MetS).

Asimismo, se definió una **población de estudio**, el cual poseía un rango de edad de **20 a 35 años**, son no fumadores, sin tratamiento médico, sin deterioro físico o alguna enfermedad cardiovascular evidente. 

A continuación, se muestra **características** de los dos grupos de personas que alberga la base de datos. 
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/main/imges/descridata.jpg" width="50%" height="50%">
</p> 

En el caso de la extracción manual de datos, se obtuvieron 9 muestras en total: 6 sin MetS y 3 con MetS. Asimismo, se consideró como **criterios de diagnóstico** para clasificar esta data a parámetros como circunferencia abdombinal y presión arterial. 

Dentro de las particularidades de las señales electrocardiográficas (ECG), se encuentran las siguientes:
* 5 registros por paciente
* Duración entre **10 - 15 minutos**
* 3 archivos .csv
  - Complejo QRS (ms)
  - Tiempo de intervalos RR (ms)
  - Registro ECG
* 12 derivaciones con frecuencia de muestreo de 1000 muestras/segundo, con resolución de 16 bits

En el proyecto, se tomó en cuenta los **últimos 20 segundos** de las señales ECG de forma que 

## Procesamiento

### Preprocesamiento
Consiste en la etapa de filtrado de las señales ECG, compuesta por 3:
- **Filtro Butterworth paso alto de 1 Hz**, para eliminar componente DC de ECG
- **Filto Notch rechaza banda de 60 Hz**, para evitar interferencia eléctrica
- **Filtro Butterworth paso bajo de 25 Hz**, para eliminar ruido de alta frecuencia

### Extracción de Características
A través de la **Transformada Wavelet Discreta (DWT)**, es posible analizar este tipo de señales a través del método de ventanas. Es asi como se obtienen las características o criterios electrocardiográficos a evaluar para el modelo, los cuales se dividen en **grupos de características** de:
* Intervalos de latidos
* Intervalos RR
* Amplitud de ondas de los latidos

Asimismo, se aplica una **técnica de escalado estándar** que tiene por objetivo estandarizar los picos de onda, de forma que no se halle una gran dispersión de datos. 

### Creación de Base de Datos
A partir de los datos extraídos de la etapa anterior, es posible la creación de base de datos que permite la implementacion de modelos de **Machine Learning**.
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
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/main/imges/distribu.jpg" width="50%" height="100%">
</p>

Cada algoritmo se somete a un análisis mediante 5 métricas las cuales son: precisión, sensibilidad, especificidad, constante _'Kappa'_, y constante _'Silhouette'_.
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/main/imges/tabla1.jpg" width="50%" height="50%">
</p> 

Se observa que todos los valores de las métricas son bajos, por lo que se indicaría que un **modelo de aprendizaje no supervisado no sería el más adecuado** para el caso en cuestión. De igual forma, es posible deducir visualmente que en las gráficas de distribución no se observan agrupaciones de clasificación de datos de manera notoria, quedando en duda su eficiencia cuando se requiera predecir una nueva entrada.  

En el caso de análisis de la gráfica de confusión, se reitera que el modelo realizado no es óptimo para los datos obtenidos puesto que las predicciones que se obtiene son bastante erróneas y representan casi el 50% del total, lo cual se evidencia con las métricas anteriormente colocadas.
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/main/imges/matrizconfu1.jpg" width="50%" height="50%">
</p> 

### Aprendizaje Supervisado
Se aplicó la técnica de PCA con la finalidad de reducir dimensionalidad de datos. (PCA = 2, 3). Por lo tanto, se tendrían 4 algoritmos de predicción:
* K-nearest Neighbors (KNN)
* Regresión Logística (RL)
* Random Forest (RF)
* Super Vector Machine (SVM)

Cada algoritmo se somete a un análisis donde las métricas resultan ser la precisión, sensibilidad, especificidad, constante _'Kappa'_ y puntuación F1.
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/main/imges/tabla2.jpg" width="50%" height="50%">
</p> 

Se aprecia que el **mejor modelo para este entrenamiento es el K-Nearest Neighbor (KNN)**, ya que su valor es el mayor en la mayoría de los valores de métricas, siendo la especificidad la única excepción. Sin embargo, este último valor sigue siendo bastante alto.

Si se observa los resultados del modelo KNN en la matriz de confusión, se puede observar que el modelo predice 19 valores de forma errónea de los más de 100 datos analizados, en los que 12 son predichos como negativos cuando era positivos (falsos negativos) y 7 valores fueron predichos como positivos siendo estos negativos (falsos positivos).
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/main/imges/matrizconfu2.jpg" width="50%" height="50%">
</p> 

A partir de ambos modelos se observa cómo el **algoritmo de aprendizaje supervisado arroja mejores resultados de precisión** tanto en la identificación de casos positivos como negativos, además de mostrar una óptima concordancia en sus clasificaciones que permitan indicar que los resultados no son productos del azar.

## Conclusiones
1. Resultados preliminares son prometedores, sugiriendo que podría ser un complemento para la detección del Síndrome Metabólico.
2. Ciertas anormalidades evidenciadas en el ECG se encuentran relacionadas con la predicción de la enfermedad coronaria, independientemente de los factores de riesgo.
3. Es necesario una mayor investigación para la validación del modelo o algoritmo, en los que se debe considerar:
   * Ampliar base de datos de ECG de forma que se incluya una mayor cantidad de pacientes con MetS, considerando diferentes edades, etnias y niveles de salud.
   * Posibilidad de incorporación de otras características de ECG para mejorar la predicción del modelo.
   * Investigación de integración de este tipo de algoritmos en los sistemas de salud existentes para una detección temprana de MetS, y posterior tratamiento.
   * Ejecutar estudios longitudinales con el fin de evaluar su eficacia en la predicción de enfermedades cardiovasculares a largo plazo en pacientes con MetS.
  
## Bibliografía
[1] OPS. La carga de las enfermedades cardiovasculares en la Región de las Américas, 2000-2019. Portal de Datos de NMH. Organización Panamericana de la Salud; 2021. Available: https://www.paho.org/es/enlace/carga-enfermedades-cardiovasculares

[2] Global Health Estimates Technical Paper WHO/DDI/DNA/GHE/2020.2. “WHO methods and data sources for country-level causes of death 2000-2019”. Available: https://cdn.who.int/media/docs/default-source/gho-documents/global-health-estimates/ghe2019_cod_methods.pdf?sfvrsn=37bcfacc_5

[3] P. Zimmet, M. Alberti, and Manuel Pardo Ríos, “Una nueva definición mundial del síndrome metabólico propuesta por la Federación Internacional de Diabetes: fundamento y resultados,” vol. 58, no. 12, pp. 1371–1376, Dec. 2005, doi: https://doi.org/10.1016/s0300-8932(05)74065-3.

[4] MedlinePlus.gov. "Síndrome metabólico". Available: https://medlineplus.gov/spanish/metabolicsyndrome.html

[5] Sattar Y, Chhabra L. “Electrocardiogram”. StatPearls. Publishing; 2023. Available from: https://www.ncbi.nlm.nih.gov/books/NBK549803/

[6] Sujadevi VG and Soman K.P, “Towards identifying most important leads for ECG classification. A data driven approach employing deep learning,” Procedia Computer Science. 2020. 171: 602-608. doi: https://doi.org/10.1016/j.procs.2020.04.065

[7] Abiodun A, Oladimeji A, Bamidele T, Adewole A, Mayowa O. "Prevalence of ECG abnormalities among adults with metabolic syndrome in a Nigerian Teaching Hospital". Afr Health Sci. 2019 Dec;19(4):2829-2838. doi: 10.4314/ahs.v19i4.4

[8] Saklayen MG. "The Global Epidemic of the Metabolic Syndrome". Curr Hypertens Rep. 2018 Feb 26;20(2):12. doi: 10.1007/s11906-018-0812-z.

[9] Y. O. T. López, G. M. C. Zambrano, E. del S. Goicochea Ríos, J. E. V. Villacorta, and O. Y. G. Aybar, “Perfil Clínico-Epidemiológico del Síndrome Metabólico en Adultos Atendidos en el hospital i Florencia de Mora Essalud,” Horizonte Médico (Lima). doi: https://doi.org/10.24265/horizmed.2020.v20n4.06

[10] Hopkinsmedicine.org “Metabolic syndrome,” https://www.hopkinsmedicine.org/health/conditions-and-diseases/metabolic-syndrome

[11] Adams KJ, Chirinos JL. "Prevalencia de factores de riesgo para síndrome metabólico y sus componentes en usuarios de comedores populares en un distrito de Lima, Perú". Rev. Peru Med. Exp. Salud Publica. 2018;35(1):39-45. 10.17843/rpmesp.2018.351.3598

[12] Ebong IA, Bertoni AG, Soliman EZ, Guo M, Sibley CT, Chen YD, Rotter JI, Chen YC, Goff DC Jr. “Electrocardiographic abnormalities associated with the metabolic syndrome and its components: the multi-ethnic study of atherosclerosis”. Metab Syndr Relat Disord. 2012 Apr;10(2):92-7. doi: 10.1089/met.2011.0090.

[13] Ebong IA, Bertoni AG, Soliman EZ, Guo M, Sibley CT, Chen YD, Rotter JI, Chen YC, Goff DC Jr. Electrocardiographic abnormalities associated with the metabolic syndrome and its components: the multi-ethnic study of atherosclerosis. Metab Syndr Relat Disord. 2012 Apr;10(2):92-7. doi: 10.1089/met.2011.0090

[14] Yazdanpanah MH, Sayyadipoor S, Hojati SR, Nikmanesh A, Farjam M, Homayounfar R. "The Association of Metabolic Syndrome and Its Components with Electrocardiogram Parameters and Abnormalities Among an Iranian Rural Population: The Fasa PERSIAN Cohort Study". Diabetes Metab Syndr Obes. 2020 Aug 24;13:2975-2987. doi: 10.2147/DMSO.S263093.
