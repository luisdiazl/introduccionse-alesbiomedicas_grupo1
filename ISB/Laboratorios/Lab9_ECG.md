# LABORATORIO 9
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
- Diseñar un filtro pasa banda a partir del dataset de ECG obtenido en las últimas sesiones de laboratorio.
- Diseñar un filtro pasa bajo a partir del dataset de ECG obtenido en la últimas sesiones de laboratorio.
- Obtener los complejos QRS de la señal ECG inicial.

## Materiales y equipos <br />
| Modelo         | Descripción       | Cantidad |
| ---            |     ---           |  ---     |
| -              | Laptop o PC       |     1    |
|    -           |    Google collab  |     1    |

## Metodología <br />
Primero se carga el dataset de ECG obtenido en anteriores laboratorios, estos serán almacenados en un diccionario para su posterior uso. Luego se muestran las señales recolectadas crudas mediante una gráfica.

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/main/imges/Lab9/b1.PNG" width="100%" height="100%">
</p> 

Para generar las gráficas, primero separamos la data en 3 secciones que vienen a ser la fase de estado basal, la fase de aguantar la respiración y la fase de post-ejercicio.

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab9/b2.PNG" width="100%" height="100%">
</p> 

Analizamos primero la señal de estado basal y recortamos en los puntos donde valen cero.

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab9/b3_a.PNG" width="100%" height="100%">
</p> 
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab9/b3_b.PNG" width="100%" height="100%">
</p> 

Analizamos la señal de estado de respiración y recortamos en los puntos donde valen cero.

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab9/b4_a.PNG" width="100%" height="100%">
</p> 
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab9/b4_b.PNG" width="100%" height="100%">
</p>

Analizamos la señal de estado de post-ejercicio y recortamos en los puntos donde valen cero.

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab9/b5_a.PNG" width="100%" height="100%">
</p> 
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab9/b5_b.PNG" width="100%" height="100%">
</p>

Se unen las 3 señales obtenidas previamente en el orden mencionado, se puede observar como en la gráfica muestra 3 comportamientos diferentes en la señal provenientes de las 3 fases.

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab9/b6_a.PNG" width="100%" height="100%">
</p> 
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab9/b6_b.PNG" width="100%" height="100%">
</p>

Se analizará la gráfica de la señal en función de su frecuencia.

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab9/b7_a.PNG" width="100%" height="100%">
</p> 
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab9/b7_b.PNG" width="100%" height="100%">
</p>

Se analizará a partir de la frecuencia de 1Hz para evitar el pico pronunciado que aparece entre 0 y 1Hz. 

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab9/b8_a.PNG" width="100%" height="100%">
</p> 
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab9/b8_b.PNG" width="100%" height="100%">
</p>

Se procede a usar el filtro de Notch para eliminar el pico de 60Hz y los armónicos vistos en la gráfica de frecuencia.

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab9/b9_a.PNG" width="100%" height="100%">
</p> 
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab9/b9_b.PNG" width="100%" height="100%">
</p>
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab9/b9_c.PNG" width="100%" height="100%">
</p> 
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab9/b9_d.PNG" width="100%" height="100%">
</p>

Se muestra la gráfica de la señal entera filtrada sin tomar en cuenta el pico gigante entre 0-1Hz.

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab9/b10_a.PNG" width="100%" height="100%">
</p> 
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab9/b10_b.PNG" width="100%" height="100%">
</p>

Se usará un filtro pasa banda y pasa alto en la señal, primero se procede a crear y aplicar el filtro pasa banda.

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab9/b11_a.PNG" width="100%" height="100%">
</p> 
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab9/b11_b.PNG" width="100%" height="100%">
</p>

Se muestra una gráfica con mejor visualización en el que la señal está suavizada y con una menor amplitud debido a que se suprime una parte del ruido.

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab9/b11_c.PNG" width="100%" height="100%">
</p>

Ahora se procede a crear el filtro pasa alto.

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab9/b12_a.PNG" width="100%" height="100%">
</p> 
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/95e011456c60085f6e6d9c259e9cd4a5a1307044/imges/Lab9/b12_b.PNG" width="100%" height="100%">
</p
  


## Archivos <br />
