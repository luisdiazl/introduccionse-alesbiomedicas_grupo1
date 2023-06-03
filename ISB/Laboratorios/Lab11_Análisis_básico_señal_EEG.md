# LABORATORIO 11 -  Análisis básico de la señal EEG
------------------------------------------------

## Tabla de contenidos
- [Participantes](#Participantes)
- [Objetivos](#Objetivos)
- [Materiales y equipos](#Materiales-y-equipos)
- [Metodología](#Metodología)
- [Archivos](#Archivos)

## Participantes <br />
- Luis Daniel Jesús Diaz Leguizamon (colaborador) - luis.diaz.l@upch.pe <br />
- Giancarlo Arian Guarnizo Bellido (colaborador) - a20191812@pucp.edu.pe <br />
- Diego Fernando Segura Contreras (colaborador) - diego.segura.c@upch.pe <br />
- Alexys Caytano Melendez (colaborador) - alexys.caytano@upch.pe <br />
- Nicolle Muñoz Huamán (colaborador) - nicolle.munoz@upch.pe <br />
- Yereli Karol García Palomino (colaborador) - a20191706@pucp.edu.pe <br />

## Objetivos <br />
- Diseñar un filtro pasa banda a partir del dataset de EEG obtenido en las últimas sesiones de laboratorio.
- Diseñar un filtro pasa bajo a partir del dataset de EEG obtenido en la últimas sesiones de laboratorio.
- Obtener las diversas ondas de la señal EEG inicial.

## Materiales y equipos <br />
| Modelo         | Descripción       | Cantidad |
| ---            |     ---           |  ---     |
| -              | Laptop o PC       |     1    |
|    -           |    Google collab  |     1    |

## Introducción <br/>
Las señales proporcionadas por el cerebro, señales EEG, son producidas por la liberación de neurotransmisores que ocasionan el cambio de voltaje a través de la membrana celular. Los campos eléctricos generados, particularmente por las neuronas piramidales, sirven para la medición de las señales dado que son lo suficientemente fuertes para atravesar los tejidos. <br/>

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/f7602f6dc8c3d30557579873198af5517e64966b/imges/Lab9/brain4.JPG" width="40%" height="40%">
</p> 
<p align="center">
  Figura 1. Tipos de onda en EEG
</p> 

Existen diferentes tipos de ondas presentes en un EEG. Por ejemplo, las ondas Gamma se hacen presentes cuando la persona realiza tareas de concentración y recolección de problemas, con una frecuencia mayor a 25 Hz. También se encuentran las ondas Beta y Alfa con rangos de 12-25 Hz y 8-12 Hz respectivamente. Ambas están encargadas de representar actividades de mente activa en el caso de las ondas Beta, y reflexión o reposo para las ondas Alfa. Finalmente, están las ondas Theta y Delta con rangos de frecuencia de 4-8 Hz y 0-4 Hz respectivamente. Las ondas Theta representan somnolencia, y las ondas Delta al sueño. <br/>
La adquisición de señales EEG está determinada por el sistema internacional 10-20, donde 21 electrodos se colocan en ubicaciones específicas en la cabeza para detectar las señales eléctricas producidas. En este laboratorio, el dispositivo que hizo posible la addquisición de datos fue el Ultracortex EEG Headset, que sigue el sistema internacional previamente descrito. <br/>

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/f7602f6dc8c3d30557579873198af5517e64966b/imges/Lab9/brain3.JPG" width="30%" height="30%">
</p> 
<p align="center">
  Figura 2. Ubicación de electrodos para EEG en sistema internacional 10-20
</p> 

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/f7602f6dc8c3d30557579873198af5517e64966b/imges/Lab9/Ultracortex.JPEG" width="30%" height="30%">
</p> 
<p align="center">
  Figura 3. Ultracortex EEG Headset
</p> 

## Metodología <br />
Primero se importan las librerías requeridas y el dataset de señales EEG obtenidos en anteriores laboratorios.
Se procede a cargar los datos adquiridos por el Ultracortex EEG Headset, que permitió medir la actividad eléctrica del cerebro de un integrante del equipo. 

Dentro de lo que adquirió los canales de las señales EEG, se delimitó la región de interés para una mejor visualización. 
Las señales se visualizan en el espectro de frecuencias, donde se define un rango de 0.5 a 100 Hz. Se recalca que a 0 Hz había un pico muy pronunciado por lo que toma en cuenta luego de 1 Hz para analizar los picos de la gráfica restante. 

Posteriormente, se aplica el filtro para detectar tanto el ERP como el caso en que se presente un estímulo sonoro, y se extrae el índice en donde se presenta la banda Alfa. 

## Archivos <br />

- [Código](https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/main/Software/LAB_11.ipynb)
