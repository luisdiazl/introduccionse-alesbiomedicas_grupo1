# LABORATORIO 4
------------------------------------------------

## Tabla de contenidos
- [Participantes](#Participantes)
- [Öbjetivos](#Objetivos)
- [Materiales y equipos](#Materiales-y-equipos)
- [¿Qué es ECG?](#¿Qué-es-ECG?)
- [BiTalino](#Bitalino)
- [Metodología](#Metodología)
- [ECG (En reposo)](#ECG-(En-reposo))
- [ECG (Contiene la respiración)](#ECG-(Contiene-la-respiración))
- [ECG (Tras actividad física)](#ECG-(Tras-actividad-física))
- [Conclusiones](#Conclusiones)
- [Bibliografía](#Bibliografía)

## Participantes <br />
- Luis Daniel Jesús Diaz Leguizamon (colaborador) - luis.diaz.l@upch.pe <br />
- Giancarlo Arian Guarnizo Bellido (colaborador) - a20191812@pucp.edu.pe <br />
- Diego Fernando Segura Contreras (colaborador) - diego.segura.c@upch.pe <br />
- Alexys Caytano Melendez (colaborador) - alexys.caytano@upch.pe <br />
- Nicolle Muñoz Huamán (colaborador) - nicolle.munoz@upch.pe <br />
- Yereli Karol García Palomino (colaborador) - a20191706@pucp.edu.pe <br />

## Objetivos <br />
- Adquirir señales biomédicas de ECG. <br />
- Hacer una correcta configuración de BiTalino. <br />
- Extraer la información de las señales ECG del software OpenSignals (r)evolution. <br />

## Materiales y equipos <br />
| Modelo         | Descripción      | Cantidad |
| ---            |     ---          |  ---     |
| (R)EVOLUTION   | Kit BiTalino     |     1    |
| -              | Laptop o PC      |     1    |

## ¿Qué es ECG? <br />
El electrocardiograma (ECG) es un examen no invasivo en el que se registra la actividad eléctrica del corazón debido a los potenciales de acción generados a lo largo de un pulso. Es una herramienta ampliamente usada para el monitoreo y diagnóstico clínico de alguna enfermedad cardiovascular [1]. Esto se realiza colocando unos electrodos al paciente que irán conectados a un dispositivo encargado de mostrar en pantalla el valor del pulso cardiaco del paciente, así como su gráfica que muestra su comportamiento (Figura 1).
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/631e1b445f34188d7eeaa96be649867731d8a29c/imges/Lab4/electrocardiograma.jpg" width="40%" height="40%">
</p> 
<p align="center">
  Figura 1. Uso del electrocardiograma
</p> 

La gráfica de ECG es la señal recogida de cada latido a lo largo del tiempo. El patrón básico se divide en distintas ondas y complejos. La primera onda es la P, que corresponde a la despolarización auricular, sigue el intervalo PR que abarca entre el inicio de la onda P y el complejo QRS. Luego sigue el complejo QRS que abarca la despolarización ventricular y la repolarización auricular, el intervalo ST y finalmente la onda T que representa la repolarización ventricular (Figura 2) [2].
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/631e1b445f34188d7eeaa96be649867731d8a29c/imges/Lab4/grafica_ecg.jpg" width="40%" height="40%">
</p> 
<p align="center">
  Figura 2. Gráfica ECG
</p> 

## BiTalino <br />
BITalino es un módulo "todo en uno", considerado como placa de desarrollo de adquisición de datos biomédicos de bajo costo, que permite la realización de proyectos mediante herramientas, sin necesidad de tener conocimientos electrónicos con respecto a bioseñales. [3]

Como se observa en la imagen, los sensores que lo componen consta de electromiografía (EMG), encefalografía (EEG), electrocardiografía (ECG), actividad electrodérmica (EDA), acelerómetro (ACC) y luz (LUX). Estos son algunos de sus "bloques" extraíbles, junto con un microcontrolador ATMega328, el mismo que el de Arduino, con una frecuencia de muestreo configurable hasta 1000 Hz. Posee la capacidad de admitir 6 entradas de tipo analógico (4 de 10 bits, y 2 de 6 bits), 4 entradas digitales y 4 salidas digitales. Asimismo, se encuentra equipado con comunicación Bluetooth y/o Bluetooth Low Energy (BLE) y conectores UC-E6.

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/d1ec54cfd1f2c9ab3eba0d320451eb65a0968e51/imges/Lab4/Bitalino.png" width="90%" height="90%">
</p> 
<p align="center">
  Figura 3. BiTalino [3]
</p> 

## Metodología <br />
Existen diferentes opciones de posicionamiento de electrodos superficiales para la adquisición de señales ECG. En este caso, se implementó según la derivación I de Einthoven. Es una de las derivaciones estándar para extremidades (bipolares) del Triángulo de Einthoven, como se observa en la Figura 4.
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/dbbb3e7eb989f969109284c60f7fd46e39f54735/imges/Lab4/derivacion1.png" width="40%" height="40%">
</p> 
<p align="center">
  Figura 4. Triángulo de Einthoven [4]
</p> 

Los cables correspondientes a este tipo de derivación se emplean para la producción de un gráfico de diferencial de potencial entre dos extremidades a la vez, por tanto su nombre es "bipolares". El tipo de derivación I se extiende desde el brazo derecho hacia el izquierdo, con electrodos de polo negativo y positivo, respectivamente, y corresponde a mostrar el lado izquierdo del corazón con un vector en dirección a 0°. [5]
En el caso de BITalino, la ubicación de estos electrodos propone que sea en las muñecas derecha e izquierda, con electrodos negativo (negro) y positivo (rojo), mientras que un tercer electrodo denominado de referencia (blanco) se localizará en la cresta iliaca izquierda del usuario, como se visualiza en la Figura 4. [6]
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/23e52ac80b31e7cccbecc5b3d63016557680c9eb/imges/Lab4/confi.png" width="70%" height="70%">
</p> 
<p align="center">
  Figura 5. Posicionamiento de electrodos del Laboratorio 3 (a) y del ejemplo de BITalino (b)
</p> 

## ECG (En reposo) <br />
  ### Video de señal en silencio eléctrico, que se muestre las conexiones electrodos-cuerpo y señal ploteada
https://user-images.githubusercontent.com/128627851/231618162-0a5c990a-805b-4fc2-ad8b-5f3aa96515f5.mp4
  ### Ploteo de la señal en OpenSignals
  
  <p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/32bbaaea36003405c8a650fdeb2fe89687367cdb/imges/Lab4/opensigreposo.png" width="80%" height="80%">
</p> 

  ### Resumen y explicación de la señal ploteada
 La señal obtenida mediante la plataforma BITalino demuestra ruido significativo; no obstante, evidencia una señal ECG con características resaltantes comunes como el intervalo QRS. La cantidad de ruido presente es potencialmente a causa de la frecuencia de muestreo (fs) de 1000 hz; no obstante, disminuir fs puede resultar en la ausencia de cambios bruscos en la señal lo cual es importante para propósitos de diagnóstico [7]. Asimismo y particularmente en este caso, el ECG en reposo es comúnmente utilizado para detectar anormalidades en el ritmo cardiaco bajo la ausencia de estrés lo cual es útil para la detección de afecciones subyacentes [8]. La presencia de ruido en la señal es detrimental para una lectura de alta precisión por no demostrar las características de las ondas en su totalidad. Por otro lado, la FFT sirve para representar la señal en el dominio de la frecuencia y aislar la señal nativa del ECG del ruido de fondo [9].
  ### Ploteo de la señal en Python
  
  <p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/5520a8b4bb46ec18034c00fee6f305c5e433701e/imges/Lab4/Basal_img.png" width="80%" height="80%">
</p> 
Tras la adquisición de los datos, se llevó a cabo su procesamiento, lo que permitió obtener las siguientes gráficas. Se observa un pico máximo de aproximadamente 700 mV tanto en la señal completa como en el intervalo de 5 segundos. Asimismo, se registraron un total de 35 picos durante la totalidad de la experimentación, lo que equivale a 35 pulsaciones. En cuanto al intervalo obtenido, se evidenció la presencia de ruido en la diástole, atribuible a diversas fuentes, tales como la utilización de metales o la proximidad a enchufes eléctricos. Cabe destacar que el pico mínimo de la diástole fue de alrededor de 380 mV obteniendo una amplitud de 320 mV.

Por otra parte, al analizar la gráfica FFT, se identifican picos en las frecuencias de 0 Hz, 60 Hz y 120 Hz. Sin embargo, se aprecia que estos están en constante oscilación en todo momento.

## ECG (Contiene la respiración) <br />
  ### Video de señal en silencio eléctrico, que se muestre las conexiones electrodos-cuerpo y señal ploteada
https://user-images.githubusercontent.com/128627851/231618205-96b098d9-fb4b-4c45-b358-3ea908cac398.mp4
  ### Ploteo de la señal en OpenSignals
  
  <p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/32bbaaea36003405c8a650fdeb2fe89687367cdb/imges/Lab4/opensigrespiracion.png" width="80%" height="80%">
</p> 

  ### Resumen y explicación de la señal ploteada
La captación de la señal ECG luego de inhalaciones profundas y periodos de pausas en la respiración sirve para comparar el efecto respiratorio ante la señal detectada. Teóricamente, la respiración profunda en general afecta el sistema cardiaco, en parte por la cercanía entre los órganos controladores (corazón y pulmones) [ ]. En nuestro caso experimental, se incrementó notablemente la cantidad de ruido en la señal. Sin embargo, no hubo cambios notoriamente mayores en la frecuencia de cada onda. El incremento en la cantidad de ruido potencialmente provenga de mayores movimientos corporales durante la inhalación y exhalación. De la misma manera, la FFT nos ayuda a comparar las señales en el dominio de la frecuencia.
  ### Ploteo de la señal en Python
  
  <p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/5520a8b4bb46ec18034c00fee6f305c5e433701e/imges/Lab4/Aguantando_img.png" width="80%" height="80%">
</p> 
Tras la realización de la segunda experiencia, se procedió a la obtención de las siguientes gráficas, en las cuales se evidencia un mayor nivel de ruido durante la diástole, tanto en la gráfica completa como en el intervalo. A partir de la señal obtenida, se pudo observar que se presentan 33 pulsaciones en un lapso de 30 segundos, lo que se asemeja notablemente a las pulsaciones registradas en el estado basal, además su amplitud es menor teniendo un valor máximo promedio de 630 mV y  un valor mínimo de 400 mV (amplitud de 230 mV). En relación al intervalo de la señal, se pudo constatar un incremento significativo del ruido en comparación con la señal previa, lo cual se debe a las condiciones experimentales.

En cuanto al análisis de la gráfica FFT, se identificó la presencia de picos notorios en 0 Hz, 60 Hz y 120 Hz, lo cual coincide con las frecuencias detectadas en la experiencia anterior.

## ECG (Tras activida8d física) <br />
  ### Video de señal en silencio eléctrico, que se muestre las conexiones electrodos-cuerpo y señal ploteada
https://user-images.githubusercontent.com/128627851/231618268-c4b7d6ac-de9e-43c5-9e7e-06375430ce43.mp4
  ### Ploteo de la señal en OpenSignals
  
  <p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/32bbaaea36003405c8a650fdeb2fe89687367cdb/imges/Lab4/opensigejercicio.png" width="80%" height="80%">
</p> 

  ### Resumen y explicación de la señal ploteada
  
  ### Ploteo de la señal en Python 
  
  <p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/5520a8b4bb46ec18034c00fee6f305c5e433701e/imges/Lab4/Ejercicios_img.png" width="80%" height="80%">
</p> 
Después de llevar a cabo la última experiencia, la cual implicó la medición posterior a la realización de actividad física por parte del participante, se obtuvieron las siguientes gráficas que evidencian una marcada diferencia respecto a las dos experiencias previas (estado basal y apnea).

A partir de la gráfica de la señal completa, se pudo identificar la presencia de 72 pulsaciones por minuto, lo que representa casi el doble de la frecuencia observada en las experiencias previas. Es importante destacar que la amplitud de la señal se encuentra en torno a los 360 mV, con un valor máximo de 770 mV y un valor mínimo de 310 mV. En relación a la gráfica del intervalo de la señal, se observa un mayor número de pulsaciones debido a que el tiempo de diástole es menor, lo que genera un mayor número de picos (pulsaciones).

Por último, en la gráfica FFT se detectaron picos en las mismas frecuencias que en las experiencias previas, aunque con una magnitud menor. Asimismo, se aprecian picos negativos en frecuencias como 70 Hz o 118 Hz.

## Conclusiones <br />
En conclusión, los objetivos de adquirir señales biomédicas de ECG, hacer una correcta configuración del BiTalino y extraer la información de las señales ECG del software OpenSignals (r)evolution son fundamentales para obtener datos precisos y confiables en el análisis de las señales ECG. La adquisición adecuada de señales ECG mediante el uso de dispositivos como BiTalino y el uso del software adecuado como OpenSignals (r)evolution permiten a los investigadores y profesionales de la salud obtener información valiosa y precisa para el diagnóstico y tratamiento de enfermedades cardiovasculares. Además, una correcta configuración de los dispositivos de adquisición de señales, garantiza la calidad y la integridad de los datos, lo que es esencial para realizar análisis precisos y confiables. De lo contrario, se pueden obtener señales con mucho ruido debido a diferentes factores como la cercanía de dispositivo tecnologicos, metálicos en el participante.

## Bibliografía <br />
