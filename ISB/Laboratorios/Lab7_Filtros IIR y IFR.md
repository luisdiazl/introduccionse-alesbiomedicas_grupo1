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

Existen diferentes criterios para clasificar a los filtros, pueden ser según el tipo de señal procesada, según la función que lleven a cabo o según la aproximación matemática empleada. 
Según el tipo de señal procesada pueden ser filtros analógicos o digitales. El primero, es un bloque básico de procesamiento de señales y está diseñado para trabajar en una señal continua, dentro de estos se puede ser pasivo (diseñados exclusivamente con elementos pasivos R,L,C) o activo (diseñado exclusivamente con condensadores, resistencias y amplificadores operacionales). 
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
