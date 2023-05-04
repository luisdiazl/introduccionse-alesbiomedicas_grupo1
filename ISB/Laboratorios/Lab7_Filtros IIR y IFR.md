# LABORATORIO 7
------------------------------------------------

## Tabla de contenidos
- [Participantes](#Participantes)
- [Öbjetivos](#Objetivos)
- [Materiales y equipos](#Materiales-y-equipos)
- [Introducción](#Introducción)
- [Metodología](#Metodología)
- [Tabla resumen](#Tabla-resumen)
- [Archivos](#Archivos)
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
- Diseñar un filtro IIR a partir del dataset de ECG obtenido en la última sesión de laboratorio.
- Diseñar un filtro IIR a partir del dataset de ECG obtenido en la última sesión de laboratorio.
- Elaborar una tabla resumen que permita visualizar y comparar las señales crudas con las señales filtradas utilizando filtros IIR y FIR

## Materiales y equipos <br />
| Modelo         | Descripción       | Cantidad |
| ---            |     ---           |  ---     |
| -              | Laptop o PC       |     1    |
|    -           |    Google collab  |     1    |

## Introducción <br />
Un filtro se define como un sistema que permite el paso de señales eléctricas dentro de un rango de frecuencias específico y limitado, bloqueando o impidiendo el paso de todas aquellas señales que se encuentran fuera de este rango. La aplicación de estos destacan en las telecomunicaciones (TV, radio, módem, etc) y en la instrumentación electrónica (sistemas de adquisición de datos, procesamiento de señales, etc)  [1]. 
En el procesamiento de señales, se utiliza el término “filtro” para referirse a un dispositivo o proceso responsable de suprimir parcial o totalmente ciertas características o componentes no deseados de una señal. En la práctica, esto puede significar eliminar ciertas frecuencias de la señal para reducir el ruido de fondo y suprimir las señales de interferencia que pueden afectar la calidad de la señal. [2]

Existen diferentes criterios para clasificar a los filtros, pueden ser según el tipo de señal procesada, según la función que lleven a cabo o según la aproximación matemática empleada. Según el tipo de señal procesada pueden ser filtros analógicos o digitales. El primero, es un bloque básico de procesamiento de señales y está diseñado para trabajar en una señal continua, dentro de estos se puede ser pasivo (exclusivamente con elementos pasivos R,L,C) o activo (con condensadores, resistencias y amplificadores operacionales).

Por otro lado, los filtros digitales son aplicados en señales que representan un sonido, y transforman las muestras en nuevas secuencias numéricas, de forma que presentan características diferentes a la señal original. [3] Existe una clasificación de filtros digitales, donde la componen filtros FIR e IIR. Los filtros FIR son los que presentan respuesta finita al impulso, solo consta de la parte no recursiva, por tanto, muestra las partes actuales y anteriores de la señal de entrada. Formados por depresiones o anti-resonancias, que son los “ceros” del filtro. Como no existe recursividad en este tipo de filtros, siempre son estables. Mientras que, los filtros IIR son los que poseen respuesta infinita al tiempo, y se compone de solo la parte recursiva o ambas partes. En su ecuación en diferencia, cada término muestra una realimentación que conforma un “polo” del filtro. Ello representa una retroalimentación en la señal de salida. [4] En la elección de filtros, es importante considerar sus características de diseño. En el caso de filtros FIR, estos se diseñan con diferentes técnicas como métodos de ventana, método minimax o método de mínimos cuadrados. Mientras que, para los filtros IIR, su diseños son a partir de métodos tradicionales de diseño de filtros analógicos empleando la transformada de Z bilineal para la discretización del sistema.

Dentro de los tipos de filtros FIR, se encuentran los obtenidos por métodos de ventanas, como son rectangular, triangular, Hamming, Kaiser, Bartlett, Hanning, Blackman, entre otros. Estos se caracterizan por emplear un enventanado que determina la calidad de resultados, de forma que cumple con amortiguar los efectos del fenómeno de Gibbs. [5]  

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/963c82e980a83150bfa0edad5b545cf0a29a90eb/imges/Lab%207/FIR_tipos.jpg" width="50%" height="50%">
</p> 
<p align="center">
  Figura 1. Ventanas comúnes en filtros FIR
</p> 

En el caso del diseño de filtros IIR, se permite crear un filtro de cualquier orden con configuración de paso bajo, paso alto, paso banda o eliminación de banda, por funciones de diseño de filtros. Se encuentran filtros como Chebyshev (proporciona respuesta de banda de parada lo más plana posible), Eliptic (minimiza anchura de transición y cumple requisitos de filtrado con el orden más bajo posible), Bessel (paso bajo analógico con orden de filtro superior a otros), y Butterworth (brinda la mejor aproximación en serie de Taylor a la respuesta ideal de filtro paso bajo en frecuencias analógicas para cualquier orden). [6]

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/963c82e980a83150bfa0edad5b545cf0a29a90eb/imges/Lab%207/IIR_tipos.jpg" width="50%" height="50%">
</p> 
<p align="center">
  Figura 2. Comparación de filtros IIR
</p> 

## Metodología
A continuación, se realizarán dos espacios de trabajo o “notebooks” por separado, con el fin de comparar resultados, uno siendo por filtros con parámetros proporcionados en la guía, y otro diseñado por los integrantes del equipo. 

Primero se carga el dataset de ECG obtenido en anteriores laboratorios, estos serán almacenados en un diccionario para su posterior uso.
Luego se muestra la señal recolectada cruda mediante una gráfica en el que se observa las 3 fases que se evaluarán. La fase de estado basal, la fase de aguantar la respiración y la fase de post-ejercicio.

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab%207/bloque1.PNG" width="100%" height="100%">
</p> 

Luego se muestra la señal recolectada cruda mediante una gráfica en el que se observa las 3 fases que se evaluarán. La fase de estado basal, la fase de aguantar la respiración y la fase de post-ejercicio.

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab%207/bloque2.PNG" width="100%" height="10%">
</p> 

 Esta señal se cortará para que no muestre zonas en donde no se tiene un valor cero y además se recortará la detección de post-ejercicio para solo quedarnos con 20 segundos de la toma. De esta manera nos queda que del tiempo 0 al tiempo 30 es la detección del estado basal de usuario, del tiempo 30 al tiempo 40 es la detección del usuario aguantando la respiración, y del tiempo 40 al 60 es la detección post-ejercicio.

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab%207/bloque3.PNG" width="100%" height="100%">
</p>

A continuación se muestra una toma de la señal ecg que representará cada estado.
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab%207/bloque4a.PNG" width="100%" height="100%">
</p>

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab%207/bloque4b.PNG" width="100%" height="100%">
</p>

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab%207/bloque4c.PNG" width="100%" height="100%">
</p>

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab%207/bloque4d.PNG" width="100%" height="100%">
</p>

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab%207/bloque4e.PNG" width="100%" height="100%">
</p>

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab%207/bloque4f.PNG" width="100%" height="100%">
</p>

Ahora se muestra estas señales en su dominio de frecuencia, se muestra un pico alto de frecuencia y posterior a ello un pequeño pico.

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab%207/bloque5.PNG" width="100%" height="100%">
</p>

Ahora se aplicará el filtro FIR en los 3 estados adquiridos. Como se puede observar en la gráfica, la linea azul representa el filtro que se aplicará, un hamming, que eliminará los pequeños picos que vienen luego de la frecuencia deseada, por lo que actuará como un filtro pasabajo.

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab%207/bloque6a.PNG" width="100%" height="100%">
</p>

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab%207/bloque6b.PNG" width="100%" height="100%">
</p>

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab%207/bloque6c.PNG" width="100%" height="100%">
</p>

Ahora se visualizará las señales filtradas con FIR, se observa una clara mejora en el suavizado de la señal ya que no hay mucho rizado.

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab%207/bloque7a.PNG" width="100%" height="100%">
</p>

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab%207/bloque7b.PNG" width="100%" height="100%">
</p>

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab%207/bloque7c.PNG" width="100%" height="100%">
</p>

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab%207/bloque7d.PNG" width="100%" height="100%">
</p>

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab%207/bloque7e.PNG" width="100%" height="100%">
</p>

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab%207/bloque7f.PNG" width="100%" height="100%">
</p>

Por último se usará un filtro IIR basado en Butterworth que se aplicará a la señal recortada. 

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab%207/bloque8a.PNG" width="100%" height="100%">
</p>

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab%207/bloque8b.PNG" width="100%" height="100%">
</p>

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab%207/bloque8c.PNG" width="100%" height="100%">
</p>

De igual manera, se obtiene un suavizado a lo largo de la señal, pasando por los 3 estados evaluados tal y como se representa en la gráfica.

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab%207/bloque9a.PNG" width="100%" height="100%">
</p>

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab%207/bloque9b.PNG" width="100%" height="100%">
</p>

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab%207/bloque9c.PNG" width="100%" height="100%">
</p>

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab%207/bloque9d.PNG" width="100%" height="100%">
</p>

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab%207/bloque9e.PNG" width="100%" height="100%">
</p>

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab%207/bloque9f.PNG" width="100%" height="100%">
</p>

En cuanto al segundo notebook, en este archivo se obtiene primero la señal ECG cruda en el que se observa los 3 casos a analizar: El estado basal, el ejercicio de aguantar la respiración y post-ejercicio. De igual forma cuando se grafica en función de la frecuencia se puede observar un pico pronunciado entre 0 y 1Hz, esta se omitirá. Para filtrar mediante IIR se usarán los filtros pasabajo de 100Hz, filtro Notch en 60Hz y un filtro pasa altas en 0.01Hz. Analizando los resultados de la señales vemos que el filtrado con un pasa altas es adecuado ya que muestra una señal suave a comparación de los otros usados. 
Con respecto al FIR se aplican los mismos tipos de filtro, en el que se destaca una misma relación siendo el filtro pasaalto una correcta opción de filtrado.



## Tabla resumen  <br />

| Campo |Señal Cruda|Filtro IIR | Filtro FIR|
| ---   |     ---           |  ---     | ---     |
|Basal  | <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/c0eadbc4a3c77b88653d4576dd2bacc788098ff1/imges/Lab%207/Cruda_Basal.png" width="100%" height="100%"> | <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/c0eadbc4a3c77b88653d4576dd2bacc788098ff1/imges/Lab%207/IIR_Basal.png" width="100%" height="100%">  |  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/c0eadbc4a3c77b88653d4576dd2bacc788098ff1/imges/Lab%207/FIR_Basal.png" width="100%" height="100%"> |
|  Respiración | <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/c0eadbc4a3c77b88653d4576dd2bacc788098ff1/imges/Lab%207/Cruda_Respiracion.png" width="100%" height="100%">|<img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/c0eadbc4a3c77b88653d4576dd2bacc788098ff1/imges/Lab%207/IIR_Respiracion.png" width="100%" height="100%">  |  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/c0eadbc4a3c77b88653d4576dd2bacc788098ff1/imges/Lab%207/FIR_Respiracion.png" width="100%" height="100%"> |
| Post-Ejercicio | <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/c0eadbc4a3c77b88653d4576dd2bacc788098ff1/imges/Lab%207/Cruda_postEjercicio.png" width="100%" height="100%"> |      <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/c0eadbc4a3c77b88653d4576dd2bacc788098ff1/imges/Lab%207/IIR_posEjercicio.png" width="100%" height="100%">   |      <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/c0eadbc4a3c77b88653d4576dd2bacc788098ff1/imges/Lab%207/FIR_postEjercicio.png" width="100%" height="100%">    |

Esta tabla de resumen fue basado en el [notebook 1](https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/efeb337f481dd875f25ecdaf905151210980e37f/Software/Filtrado_Se%C3%B1alCompleta%20(1).ipynb), los parámetros que se están utilizando en la guía no proporcionan suficiente información para comparar filtros FIR e IIR. En su lugar, se propone crear filtros analizando el espectro de frecuencia en un siguiente notebook utilizando pyFDAx, los cuales se pueden observar en el [notebook 2](https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/Software/Copia_de_Filtros.ipynb)


## Conclusiones
En conclusión, el diseño de filtros es fundamental en el procesamiento de señales y especialmente en la limpieza de señales de interferencias y ruido de fondo. En este caso, el diseño de un filtro IIR y FIR a partir de un dataset de ECG, elaborado el laboratorio pasado, permitió reducir las interferencias y mejorar la calidad de la señal. Además, la elaboración de una tabla resumen para comparar las señales crudas con las señales filtradas utilizando filtros IIR y FIR, permitió visualizar y evaluar la efectividad de ambos tipos de filtros. 
A partir de esto, se considera que el filtro IIR es más eficiente que el filtro FIR, en un mismo orden de filtro. Esto puede deberse a su naturaleza de filtro IIR que considera la retroalimentación, y realiza los “polos” y “ceros” del sistema. Mientras que el filtro FIR se encuentra limitado a solo poseer “ceros”. Por tanto, es posible decirse que si se requiere características o resultados de filtro IIR en cierto número de orden, equivale a un filtro FIR de varios cientos de etapas. Asimismo, otra de sus desventajas es que el filtro FIR es más costoso a nivel de hardware que un filtro IIR. [4] Estos consumen menos recursos y son la mejor opción para aplicarse cuando se requiere mayores velocidades de procesamiento. 

#### Archivos
- [Dataset obtenido anteriormente](https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/ISB/Laboratorios/Lab6_Creaci%C3%B3n_Dataset_ECG.ipynb)

- [Notebook 1](https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/efeb337f481dd875f25ecdaf905151210980e37f/Software/Filtrado_Se%C3%B1alCompleta%20(1).ipynb)

- [Notebook 2](https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/Software/Copia_de_Filtros.ipynb)

## Bibliografía.
[1] J. Cabrera Peña, “Filtros Activos.” Disponible en: https://www2.ulpgc.es/hege/almacen/download/29/29861/filtros.pdf

[2] DEWESoft d.o.o, “Signal filtering, Signal suppression, Signal processing | Dewesoft,” Dewesoft.com, 2023. https://training.dewesoft.com/online/course/filters#introduction-1 (accessed May 03, 2023).

[3] P. Cetta, P. Teóricos, and D. Los, “UNIVERSIDAD CATÓLICA ARGENTINA ‘Santa María de los Buenos Aires’ Facultad de Artes y Ciencias Musicales FILTROS DIGITALES.” Accessed: May 04, 2023. [Online]. Available: https://repositorio.uca.edu.ar/bitstream/123456789/9195/1/principios-teoricos-filtros-digitales.pdf

[4] J. Manuel and M. De La Rosa, “FUNDAMENTOS TEÓRICOS 7 FUNDAMENTOS TEÓRICOS 1.1. FUNDAMENTOS TEÓRICOS: FILTROS.” Available: https://biblus.us.es/bibing/proyectos/abreproy/11375/fichero/MEMORIA%252FFundamentos+teoricos.pdf

[5] “Diseño de Filtros FIR” Mathworks.com, 2023. https://la.mathworks.com/help/signal/ug/fir-filter-design.html#f4-1285  (accessed May 03, 2023).

[6] “Diseño de Filtros IIR” Mathworks.com, 2023. https://la.mathworks.com/help/signal/ug/iir-filter-design.html  (accessed May 03, 2023).
