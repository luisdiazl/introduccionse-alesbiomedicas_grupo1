# LABORATORIO 7
------------------------------------------------

## Tabla de contenidos
- [Participantes](#Participantes)
- [Öbjetivos](#Objetivos)
- [Materiales y equipos](#Materiales-y-equipos)
- [Introducción](#Introducción)
- [Metodología](#Metodología)
- [Tabla resumen](#Tabla-resumen)
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

<img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/c0eadbc4a3c77b88653d4576dd2bacc788098ff1/imges/Lab%207/FIR_tipos.jpg" width="100%" height="100%">

En el caso del diseño de filtros IIR, se permite crear un filtro de cualquier orden con configuración de paso bajo, paso alto, paso banda o eliminación de banda, por funciones de diseño de filtros. Se encuentran filtros como Chebyshev (proporciona respuesta de banda de parada lo más plana posible), Eliptic (minimiza anchura de transición y cumple requisitos de filtrado con el orden más bajo posible), Bessel (paso bajo analógico con orden de filtro superior a otros), y Butterworth (brinda la mejor aproximación en serie de Taylor a la respuesta ideal de filtro paso bajo en frecuencias analógicas para cualquier orden). [6]

<img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/c0eadbc4a3c77b88653d4576dd2bacc788098ff1/imges/Lab%207/IIR_tipos.jpg" width="100%" height="100%">

## Metodología
## Tabla resumen  <br />

| Campo |Señal Cruda|Filtro IIR | Filtro FIR|
| ---   |     ---           |  ---     | ---     |
|Basal  | <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/c0eadbc4a3c77b88653d4576dd2bacc788098ff1/imges/Lab%207/Cruda_Basal.png" width="100%" height="100%"> | <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/c0eadbc4a3c77b88653d4576dd2bacc788098ff1/imges/Lab%207/IIR_Basal.png" width="100%" height="100%">  |  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/c0eadbc4a3c77b88653d4576dd2bacc788098ff1/imges/Lab%207/FIR_Basal.png" width="100%" height="100%"> |
|  Respiración | <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/c0eadbc4a3c77b88653d4576dd2bacc788098ff1/imges/Lab%207/Cruda_Respiracion.png" width="100%" height="100%">|<img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/c0eadbc4a3c77b88653d4576dd2bacc788098ff1/imges/Lab%207/IIR_Respiracion.png" width="100%" height="100%">  |  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/c0eadbc4a3c77b88653d4576dd2bacc788098ff1/imges/Lab%207/FIR_Respiracion.png" width="100%" height="100%"> |
| Post-Ejercicio | <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/c0eadbc4a3c77b88653d4576dd2bacc788098ff1/imges/Lab%207/Cruda_postEjercicio.png" width="100%" height="100%"> |      <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/c0eadbc4a3c77b88653d4576dd2bacc788098ff1/imges/Lab%207/IIR_posEjercicio.png" width="100%" height="100%">   |      <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/c0eadbc4a3c77b88653d4576dd2bacc788098ff1/imges/Lab%207/FIR_postEjercicio.png" width="100%" height="100%">    |

## Conclusiones
En conclusión, el diseño de filtros es fundamental en el procesamiento de señales y especialmente en la limpieza de señales de interferencias y ruido de fondo. En este caso, el diseño de un filtro IIR a partir de un dataset de ECG, elaborado el laboratorio pasado, permitió reducir las interferencias y mejorar la calidad de la señal. Además, la elaboración de una tabla resumen para comparar las señales crudas con las señales filtradas utilizando filtros IIR y FIR, permitió visualizar y evaluar la efectividad de ambos tipos de filtros. 
## Bibliografía
