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
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/631e1b445f34188d7eeaa96be649867731d8a29c/imges/Lab4/electrocardiograma.jpg" width="60%" height="60%">
</p> 

La gráfica de ECG es la señal recogida de cada latido a lo largo del tiempo. El patrón básico se divide en distintas ondas y complejos. La primera onda es la P, que corresponde a la despolarización auricular, sigue el intervalo PR que abarca entre el inicio de la onda P y el complejo QRS. Luego sigue el complejo QRS que abarca la despolarización ventricular y la repolarización auricular, el intervalo ST y finalmente la onda T que representa la repolarización ventricular (Figura 2) [2].
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/631e1b445f34188d7eeaa96be649867731d8a29c/imges/Lab4/grafica_ecg.jpg" width="60%" height="60%">
</p> 

## BiTalino <br />
BITalino es un módulo "todo en uno", considerado como placa de desarrollo de adquisición de datos biomédicos de bajo costo, que permite la realización de proyectos mediante herramientas, sin necesidad de tener conocimientos electrónicos con respecto a bioseñales. [][] 

Como se observa en la imagen, los sensores que lo componen consta de electromiografía (EMG), encefalografía (EEG), electrocardiografía (ECG), actividad electrodérmica (EDA), acelerómetro (ACC) y luz (LUX). Estos son algunos de sus "bloques" extraíbles, junto con un microcontrolador ATMega328, el mismo que el de Arduino, con una frecuencia de muestreo configurable hasta 1000 Hz. Posee la capacidad de admitir 6 entradas de tipo analógico (4 de 10 bits, y 2 de 6 bits), 4 entradas digitales y 4 salidas digitales. Asimismo, se encuentra equipado con comunicación Bluetooth y/o Bluetooth Low Energy (BLE) y conectores UC-E6.

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/d1ec54cfd1f2c9ab3eba0d320451eb65a0968e51/imges/Lab4/Bitalino.png" width="100%" height="100%">
</p> 

## Metodología <br />
## ECG (En reposo) <br />
  ### Video de señal en silencio eléctrico, que se muestre las conexiones electrodos-cuerpo y señal ploteada
https://user-images.githubusercontent.com/128627851/231618162-0a5c990a-805b-4fc2-ad8b-5f3aa96515f5.mp4
  ### Ploteo de la señal en OpenSignals
  
  <p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/32bbaaea36003405c8a650fdeb2fe89687367cdb/imges/Lab4/opensigreposo.png" width="80%" height="80%">
</p> 

  ### Resumen y explicación de la señal ploteada
  ### Ploteo de la señal en Python
  
  <p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/5520a8b4bb46ec18034c00fee6f305c5e433701e/imges/Lab4/Basal_img.png" width="80%" height="80%">
</p> 

## ECG (Contiene la respiración) <br />
  ### Video de señal en silencio eléctrico, que se muestre las conexiones electrodos-cuerpo y señal ploteada
https://user-images.githubusercontent.com/128627851/231618205-96b098d9-fb4b-4c45-b358-3ea908cac398.mp4
  ### Ploteo de la señal en OpenSignals
  
  <p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/32bbaaea36003405c8a650fdeb2fe89687367cdb/imges/Lab4/opensigrespiracion.png" width="80%" height="80%">
</p> 

  ### Resumen y explicación de la señal ploteada
  ### Ploteo de la señal en Python
  
  <p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/5520a8b4bb46ec18034c00fee6f305c5e433701e/imges/Lab4/Aguantando_img.png" width="80%" height="80%">
</p> 

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

## Conclusiones <br />
En conclusión, los objetivos de adquirir señales biomédicas de ECG, hacer una correcta configuración del BiTalino y extraer la información de las señales ECG del software OpenSignals (r)evolution son fundamentales para obtener datos precisos y confiables en el análisis de las señales ECG. La adquisición adecuada de señales ECG mediante el uso de dispositivos como BiTalino y el uso del software adecuado como OpenSignals (r)evolution permiten a los investigadores y profesionales de la salud obtener información valiosa y precisa para el diagnóstico y tratamiento de enfermedades cardiovasculares. Además, una correcta configuración de los dispositivos de adquisición de señales, garantiza la calidad y la integridad de los datos, lo que es esencial para realizar análisis precisos y confiables. De lo contrario, se pueden obtener señales con mucho ruido debido a diferentes factores como la cercanía de dispositivo tecnologicos, metálicos en el participante(mejorar).

## Bibliografía <br />
