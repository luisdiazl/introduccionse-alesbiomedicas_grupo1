# LABORATORIO 5
------------------------------------------------

## Tabla de contenidos
- [Participantes](#Participantes)
- [Öbjetivos](#Objetivos)
- [Materiales y equipos](#Materiales-y-equipos)
- [Introducción](#Introducción)
- [Metodología](#Metodología)
- [BITalino (EEG)](#BITalino_(EEG))
- [ULTRACORTEX MARK IV](#ULTRACORTEX_MARK_IV)
- [BITalino (ADICIONAL)](#BITalino_(ADICIONAL))
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
- Adquirir señales biomédicas de EEG. <br />
- Hacer una correcta configuración de BiTalino y de ULTRA CORTEX MARK IV. <br />
- Extraer la información de las señales ECG del software OpenSignals (r)evolution. <br />

## Materiales y equipos <br />
| Modelo         | Descripción       | Cantidad |
| ---            |     ---           |  ---     |
| (R)EVOLUTION   | Kit BiTalino      |     1    |
| -              | Laptop o PC       |     1    |
| ULTRACORTEX MARK IV  |             |     1    |
| -              | Laptop o PC      |     1    |

## Introducción <br />
El cerebro es uno de los órganos más inmortales del ser humano. Está encargado del control de las emociones, memoria, sentidos, respiración, vista, entre otras funciones vitales. En conjunto con la médula espinal, el cerebro conforma el sistema nervioso central. El peso del cerebro es de aproximadamente 3 libras en un adulto promedio del cual un 60% es contenido graso existen dos tipos de materia, la gris y la blanca, que conforman el cerebro. La materia gris es la región más oscura ubicada en la superficie cerebral y la blanca es la región interna. Esta está compuesta por neuronas somáticas mientras que la blanca de axones envueltos en mielina. El cerebro se encarga de enviar y recibir señales químicas que producen una respuesta en el cuerpo; por ejemplo, las sensaciones de cansancio o sueño.[1]

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/f7602f6dc8c3d30557579873198af5517e64966b/imges/Lab5/brain1.jpg" width="60%" height="60%">
</p> 
<p align="center">
  Figura 1. Cerebro con vista de materia gris y blanca
</p> 

Adicionalmente, el cerebro contiene dos hemisferios, el derecho y el izquierdo, así como cuatro regiones llamadas lóbulos. El lóbulo frontal es el más grande y está encargado de la personalidad, toma de decisiones, pensamiento y el habla. El lóbulo parietal controla la ubicación espacial de la persona, la percepción de dolor y tacto y el entendimiento del lenguaje hablado. El lóbulo occipital está ubicado en la parte posterior de la cabeza y controla la vista. Finalmente, el lóbulo temporal maneja la memoria a corto plazo, percepción de ritmo musical y reconocimiento del olfato.[]

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/f7602f6dc8c3d30557579873198af5517e64966b/imges/Lab5/brain2.jpg" width="40%" height="40%">
</p> 
<p align="center">
  Figura 2. Los cuatro lóbulos del cerebro
</p> 

Las señales proporcionadas por el cerebro, señales EEG, son producidas por la liberación de neurotransmisores que ocasionan el cambio de voltaje a través de la membrana celular. Los campos eléctricos generados, particularmente por las neuronas piramidales, sirven para la medición de las señales dado que son lo suficientemente fuertes para atravesar los tejidos. Existen diferentes tipos de ondas presentes en un EEG. Por ejemplo, las ondas gamma que hacen presencia mientras la persona realiza tareas de concentración y recolección de problemas con una frecuencia mayor a 25 Hz. Están también las ondas beta y alfa con rangos de 12-25 Hz y 8-12 Hz respectivamente. Están encargadas de representar actividades de mente activa para las beta y reflexión o reposo para las alfa. Finalmente, están las ondas theta y delta con rangos de frecuencia de 4-8 Hz y 0-4 Hz respectivamente. Las ondas theta representan somnolencia y las ondas delta el sueño. []

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/f7602f6dc8c3d30557579873198af5517e64966b/imges/Lab5/brain4.JPG" width="40%" height="40%">
</p> 
<p align="center">
  Figura 3. Tipos de onda en EEG
</p> 

La adquisición de señales EEG está fundamentada en el sistema internacional 10-20 donde 21 electrodos se colocan en ubicaciones específicas en la cabeza para detectar las señales producidas. 

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/f7602f6dc8c3d30557579873198af5517e64966b/imges/Lab5/brain3.JPG" width="30%" height="30%">
</p> 
<p align="center">
  Figura 4. Ubicación de electrodos para EEG en sistema internacional 10-20
</p> 

## Metodología
Durante este laboratorio, usaremos el sistema Ultracortex mark iV con el sistema 10-20 mencionado. El ultracortex mark iv es un innovador sistema de auriculares imprimibles en 3D de código abierto, que han sido diseñados para ser compatibles con cualquier placa OpenBCI. Además, es capaz de registrar la actividad cerebral (EEG).  

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/bc61d23186936c60113226a5665001438ecf546b/imges/Ultracortex1.png" width="40%" height="40%">
</p> 
<p align="center">
  Figura 5. ULTRACORTEX EEG Headset
</p> 

  Después de la experiencia con el Ultracortex EEG Headset, continuamos utilizando el programa OpenBCI para configurar y observar las señales. Luego, trabajamos con el Bitalino, utilizando tres electrodos: uno de referencia ubicado en una zona ósea del cráneo, uno positivo ubicado encima del ojo y otro negativo ubicado encima del ojo del lado opuesto.

<p align="center">
  <img src="https://user-images.githubusercontent.com/128627851/233385400-7b29a7f5-35f0-4c64-8788-1b8b5408c48d.png" width="40%" height="40%">
</p> 
<p align="center">
  Figura 6. Posición de los 3 electrodos
</p> 

Posteriormente, procesamos las señales en el programa OpenSignal, el cual también fue configurado para esta función. Finalmente, llevamos los datos capturados en este programa a Google Colab para hacer un ploteo en Python.

## BITalino (EEG)
### Fotos de conexión usada (Electrodos-cuerpo/cabeza)

<p align="center">
  <img src="https://user-images.githubusercontent.com/128627851/233386048-0f1e19d1-dc79-48e7-bbf9-a55836a0b3ec.png" width="60%" height="60%">
</p> 
<p align="center">
  Figura 7. Posición de los 3 electrodos
</p> 

### Video de señal mostrando el punto 1,2 y 4 del procedimiento; que se muestre las conexiones electrodos-cuerpo/cabeza y señal ploteada

https://user-images.githubusercontent.com/128627851/233386749-102163d4-3773-4fe3-96a3-ce378df39fd9.mp4

### Ploteo de la señal en opensignal
#### Punto 1: 
<p align="center">
  <img src="https://user-images.githubusercontent.com/128627851/233387202-a88c7708-786d-49ab-b0ac-114e09c7bbad.png" width="60%" height="60%">
</p> 

#### Punto 2: 
<p align="center">
  <img src="https://user-images.githubusercontent.com/128627851/233387403-26be4463-249d-4d43-9ebb-ad776fb5232f.png" width="60%" height="60%">
</p> 

#### Punto 3: 
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/f7602f6dc8c3d30557579873198af5517e64966b/imges/Lab5/signal3_open.jpg" width="60%" height="60%">
</p> 

#### Punto 4: 
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/f7602f6dc8c3d30557579873198af5517e64966b/imges/Lab5/signal4_open.jpg" width="60%" height="60%">
</p> 

### Resumen y explicación de la señal ploteada
Como se observa en la gráficas obtenida miediante el programa BITalino, 


### Ploteo de la señal en Python 
#### Punto 1:
<p align="center">
  <img src="https://user-images.githubusercontent.com/128627851/233388733-057322a6-5a23-4214-9c61-a515a64d42c0.png" width="60%" height="60%">
</p> 

En las gráficas, se observa un pico máximo de apróximadamente 1000 mV en la gráfica completa, mientras que en la gráfica del intervalo de un tiempo, se observa un pico máximo de 700 mV aproximadamente. Para una persona que está respirando normal, sin movimiento y con los ojos cerrados, se esperan ondas EEG, donde predomina la baja frecuencia y la alta amplitud. Si es que se ejecutan las condiciones perfectamente, se debería observar una mayor actividad de ondas delta (de 0 a 4 Hz) y ondas theta (de 4 a 8 Hz) en la mayoría de las regiones del cerebro, y una menor actividad de ondas alfa (de 8 a 12 Hz) y beta (de 12 a 25 Hz) []. Estas ondas indican un estado de relajación y descanso en la persona, ya que no hay estímulos externos que afecten la actividad cerebral. Sin embargo, en este experimento no se cumplen las condicones idealmente, ya que influye el ruido externo, entre otros. Por ello, en la gráfica, se observan ondas beta (12-25 Hz).

#### Punto 2:
<p align="center">
  <img src="https://user-images.githubusercontent.com/128627851/233389473-b8ba8d16-999c-49d6-b535-b8ac16c9f20f.png" width="60%" height="60%">   
</p> 

En las gráficas, se observa un pico máximo de apróximadamente 1000 mV en la gráfica completa, mientras que en la gráfica del intervalo de un tiempo, se observa un pico máximo de 800 mV aproximadamente. Para una persona que repite un ciclo de cerrar los ojos y abrirlo durante 5 segundos, se esperan observar diferentes patrones de actividad cerebral. Cuando el participante tiene los ojos abierto, se espera que la actividad cerebral debe ser predominantemente de ondas alfa, con una frecuencia de 8 a 12 Hz, especialmente en la región occipital del cerebro, ya que se espera que la persona esté en un estado de alerta relajado con los ojos abiertos. Por otro lado, cuando el participante está con los ojos cerrados, se espera que la actividad cerebral debería ser principalmente de ondas theta y delta, con una menor actividad de ondas alfa. Estas ondas más lentas indican un estado de relajación profunda y posiblemente somnolencia en la persona. Durante la transición entre ojos abiertos y cerrados, la actividad beta (12-25 Hz) y gamma (por encima de 25 Hz) puede aumentar a medida que la persona se prepara para cambiar de estado. Es por ello, que en la gráfica, se muestra que luego de esa transición, existe un pico pronunciado.

#### Punto 3:
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/f7602f6dc8c3d30557579873198af5517e64966b/imges/Lab5/Signal3_bitalino.jpg" width="60%" height="60%">
</p> 

#### Punto 4:
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/f7602f6dc8c3d30557579873198af5517e64966b/imges/Lab5/Signal4_bitalino.jpg" width="60%" height="60%">
</p> 

#### Observaciones

#### Archivos
- [Datos obtenidos de la señal](https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/files/11287891/Signal_Basal_30s.txt)

- [Notebook de ploteo en python](https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/4e073602926fa6e8fd1bb5602128a8395ac22e5b/Software/Se%C3%B1alBasal30s.ipynb)


## ULTRACORTEX MARK IV
### Fotos de conexión usada (Electrodos-cuerpo/cabeza)
Se ajustó el ULTRACORTEX, ubicando los 16 electrodos según el Sistema Internacional de Posicionamiento 10/20. Tal como se muestra en la figura.

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/651dc796859eb572317c2f139a544e365b857e59/imges/Lab5/Sistema%20Internacional%20de%20Posicionamiento.png" width="60%" height="60%">
</p> 
<p align="center">
  Figura 8. Sistema Internacional de Posicionamiento 10/20
</p> 

Se tuvo ciertos inconvenientes como el dolor producido por las puntas de los electrodos al ajustarlo en la cabeza, Se trató de posicionar en el punto más cercano al Nasion, con las dificultades mecánicas del casco, eran muy rígidas, y los electrodos no ayudaban a encajar en los puntos deseados, por lo que se debía estar desajustando uno por uno.

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/651dc796859eb572317c2f139a544e365b857e59/imges/Lab5/Colocaci%C3%B3n%20de%20ULTRACORTEX.jpg" width="60%" height="60%">
</p> 
<p align="center">
  Figura 9. Colocación de ULTRACORTEX
</p> 

Finalmente se colocaron las tierras A1 y A2 en los pabellones auriculares. Las conexiones del EEG ya estaban predeterminadas y se conectó a la laptop mediante el usb.

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/651dc796859eb572317c2f139a544e365b857e59/imges/Lab5/Ubicaci%C3%B3n%20de%20ULTRACORTEX.jpg" width="60%" height="60%">
</p> 
<p align="center">
  Figura 10. Ubicación de ULTRACORTEX
</p> 

### Video de señal mostrando el punto 1 y 2 del procedimiento; que se muestre las conexiones electrodos-cuerpo/cabeza y señal ploteada 
https://user-images.githubusercontent.com/128627851/233271732-fe937ef3-9a47-4df1-b6c2-b58e399ca468.mp4

### Ploteo de la señal en OpenBCI GUI

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/c102c9d00e93c65e58657c718470ef2f945a693e/imges/Lab5/Ploteo%20en%20interfaz%20OpenBCI.png" width="60%" height="60%">
</p> 
<p align="center">
  Figura 11. Ploteo en interfaz OpenBCI
</p> 

### Ploteo de la señal en Python

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/c102c9d00e93c65e58657c718470ef2f945a693e/imges/Lab5/Se%C3%B1al%20Completa%20OpenBCI.png" width="60%" height="60%">
</p> 

### Duración de la prueba durante 95 segundos por canales
- EXG Channel 0

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/6a57e3f44032adc5a0b4867318b1b63cbeeff8e8/imges/Lab5/EXG_Channel_0.png" width="60%" height="60%">
</p> 

- EXG Channel 1

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/6a57e3f44032adc5a0b4867318b1b63cbeeff8e8/imges/Lab5/EXG_Channel_1.png" width="60%" height="60%">
</p> 

- EXG Channel 2

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/6a57e3f44032adc5a0b4867318b1b63cbeeff8e8/imges/Lab5/EXG_Channel_2.png" width="60%" height="60%">
</p> 

- EXG Channel 3

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/6a57e3f44032adc5a0b4867318b1b63cbeeff8e8/imges/Lab5/EXG_Channel_3.png" width="60%" height="60%">
</p> 

- EXG Channel 4

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/6a57e3f44032adc5a0b4867318b1b63cbeeff8e8/imges/Lab5/EXG_Channel_4.png" width="60%" height="60%">
</p>

- EXG Channel 5

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/6a57e3f44032adc5a0b4867318b1b63cbeeff8e8/imges/Lab5/EXG_Channel_5.png" width="60%" height="60%">
</p>

- EXG Channel 6

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/6a57e3f44032adc5a0b4867318b1b63cbeeff8e8/imges/Lab5/EXG_Channel_6.png" width="60%" height="60%">
</p>

- EXG Channel 7

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/6a57e3f44032adc5a0b4867318b1b63cbeeff8e8/imges/Lab5/EXG_Channel_7.png" width="60%" height="60%">
</p>

### Resumen y explicación de la señal ploteada. 
En 7 de los 8 canales se puede observar que existe un picos pronunciados en 60 Hz, que pertenecen a los ritmos beta del EEG, que demuestran localización en regiones frontales y temporales anteriores, muestra estados de vigilia concentrado, o nerviosismo []. El canal 3 presenta un solo pulso alrededor de los 40 segundos, pero en su espectro de frecuencias no se puede observar nada.
Un pico destacable es en el canal 2, que representa el ritmo theta, que se presenta en la meditación profunda, cuando hay acciones y procesar información interna [].
En todos los canales se puede observar que es constante la amplitud hasta llegar a los 30 segundos donde comienza a parpadear la persona y por ende cambiar la señal, indicando una actividad cerebral para ejecutar esta acción.

### Observaciones
- De acuerdo a la toma registrada, la ubicación del casco EEG en el posicionamiento 10/20 no siempre va a ser perfecto y posee cierto margen que influye en que los datos captados posean un ruido por artefacto [].

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/651dc796859eb572317c2f139a544e365b857e59/imges/Lab5/Ubicaci%C3%B3n%20de%20electrodos%20en%20maniqu%C3%AD.png" width="60%" height="60%">
</p> 
<p align="center">
  Figura 12. Ubicación 10/20 de electrodos en maniquí 
</p> 

- El otro error que se dió al momento de captar la prueba fue de seleccionar 8 canales en lugar de los 16 electrodos que había en el ULTRACORTEX. 

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/6a57e3f44032adc5a0b4867318b1b63cbeeff8e8/imges/Lab5/Selecci%C3%B3n%20de%20par%C3%A1metros%20para%20conexi%C3%B3n%20en%20Interfaz%20OpenBCI.png" width="60%" height="60%">
</p> 
<p align="center">
  Figura 13. Selección de parámetros para conexión en Interfaz OpenBCI
</p> 

Este error coloca los 8 canales en 0, y los otros 8 electrodos pueden captar una señal con flujo de corriente en el cuerpo, corrientes de desplazamientos en la etapa frontal del electrodo, inducción magnética causados por el electrodo. [][]
- El cabello del participante influye como impedancia para los electrodos EEG que distorsionan y debilitan la señal. Por ello se requirió del participante que posea el cabello más corto.

#### Archivos
- [Datos obtenidos de la señal](https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/files/11280376/OpenBCI-RAW-2023-04-19_11-29-23.txt) 
- [Notebook de ploteo en python]

## BITalino (ADICIONAL)
En este ejercicio se evaluó la impedancia en la señal EEG mediante 2 ejercicios que se enfocan en el análisis de los ojos. 
El primer ejercicio consiste en vendar al usuario por 5 segundos para luego quitárselo y encender una fuente luz que le caiga a los ojos abiertos, esta acción también durará 5 segundos.

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/7ee1efdf6f0e04d324ae0591b030d73d5e735597/imges/Lab5/EA1.PNG" hwidth="60%" height="60%">
</p> 
<p align="center">
  Figura 14. Primer ejercicio adicional de BITalino
</p>

En el segundo ejercicio el usuario se tapará los ojos con la mano por 5 segundos, luego mostrará un ojo y se le mostrará una fuente de luz directa a este por 5 segundos. Esto mismo se realiza con el otro ojo en el mismo intervalo de tiempo.

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/7ee1efdf6f0e04d324ae0591b030d73d5e735597/imges/Lab5/EA2.PNG" width="60%" height="60%">
</p> 
<p align="center">
  Figura 15. Segundo ejercicio adicional de BITalino
</p>

### Fotos de conexión usada (Electrodos-cuerpo/cabeza)
Se usaron 3 electrodos que están conectados en la cabeza. El electrodo positivo está ubicado en la frente encima de la pestaña izquierda, de igual manera el electrodo negativo está ubicado al lado derecho y el electrodo de referencia estará ubicado en la protuberancia detrás de la oreja.

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/7ee1efdf6f0e04d324ae0591b030d73d5e735597/imges/Lab5/conexion_bitalino1.jpg" width="60%" height="60%">
</p> 
<p align="center">
  Figura 16. Conexión BITalino 1. Electrodos positivo y negativo
</p>

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/7ee1efdf6f0e04d324ae0591b030d73d5e735597/imges/Lab5/conexion_bitalino2.jpg" width="60%" height="60%">
</p> 
<p align="center">
  Figura 17. Conexión BITalino 2. Electrodo de referencia
</p>

### Video de señal; que se muestre las conexiones electrodos-cuerpo/cabeza y señal ploteada. 
#### Video primer ejercicio adicional de BITalino
https://user-images.githubusercontent.com/128627851/233280819-a993fb1c-8a2a-40f1-92ba-2fbe08bab27e.mp4

#### Video segundo ejercicio adicional de BITalino
https://user-images.githubusercontent.com/128627851/233281718-238365ee-7732-46fc-9a4f-ce4500efd24a.mp4

### Ploteo de la señal en OpenSIGNAL 
#### Primer ejercicio adicional de BITalino:
#### Imagen que muestra la actividad cerebral cuando el usuario está con los ojos cerrados
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/148dd40a7d5557c5d570584edf3269804e3ae086/imges/Lab5/e1_eeg1.PNG" width="60%" height="60%">
</p> 

#### Imagen que muestra la actividad cerebral cuando al usuario le llega una fuente de luz en ambos ojos.
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/148dd40a7d5557c5d570584edf3269804e3ae086/imges/Lab5/e1_eeg2.PNG" width="60%" height="60%">
</p> 

#### Segundo ejercicio adicional de BITalino:
#### Imagen que muestra la actividad cerebral cuando el usuario está con los ojos cerrados
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/148dd40a7d5557c5d570584edf3269804e3ae086/imges/Lab5/e1_eeg1.PNG" width="60%" height="60%">
</p> 

#### Imagen que muestra la actividad cerebral cuando al usuario le llega una fuente de luz en solo un ojo
<p align="center">
  <img src="https://user-images.githubusercontent.com/128627851/233412167-ce88d286-f272-46a5-9e13-d13ffaf55951.png" width="60%" height="60%">
</p> 

### Resumen y explicación de la señal ploteada
Los datos obtenidos mediante la plataforma BITalino fueron procesados y graficados usando la interfaz de Python. Se presentan 5 gráficas ploteadas para cada ejercicio realizado en el que se tiene la gráfica de la señal completa medida, la gráfica de la señal en un intervalo de tiempo que muestre el valor más alto, la gráfica de la señal en función de la frecuencia usando la transformada de Fourier, la gráfica de regresión lineal y la gráfica de regresión polinomial de Grado 2, estos dos últimos servirán para evaluar la relación entre los datos adquiridos. 

- Primer ejercicio adicional de BITalino: 2 ojos contra luz

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/7ee1efdf6f0e04d324ae0591b030d73d5e735597/imges/Lab5/s1.PNG" "60%" width="60%" height="60%">
</p> 
<p align="center">
  Figura 18. Gráfica de señal EEG completa
</p>

En la primera gráfica se puede mostrar el comportamiento de la señal EEG en el que se muestra primero variaciones grandes hasta el segundo 5, esto debido a que en ese tiempo se tiene el ojo cerrado y vendado, pasado este tiempo se quita la venda al usuario y se le punta una linterna o flash de celular a los ojos por 5 segundo para terminar la prueba, el cual se refleja como unas variaciones de menor tamaño []. 

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/7ee1efdf6f0e04d324ae0591b030d73d5e735597/imges/Lab5/int1.PNG" width="60%" height="60%">
</p> 
<p align="center">
  Figura 19. Gráfica de señal EEG en un intervalo de tiempo
</p>

En este acercamiento entre el segundo 7 y 11 se puede observar un cambio brusco de señal, esto representa un parpadeo producido por el usuario debido a la luz que le cae directamente a los ojos, lo cual pasa a denuevo quedarse abiertos por 5 segundos tal y como se ve la variación de la amplitud posterior a esta [].

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/7ee1efdf6f0e04d324ae0591b030d73d5e735597/imges/Lab5/fft1.PNG" width="60%" height="60%">
</p> 
<p align="center">
  Figura 20. Gráfica FFT de la señal EEG
</p>

Si se observa los valores obtenidos entre la frecuencia 5 y 25 de la gráfica FFT de la señal EEG, se podrá observar 2 picos. El primer pico está ubicado en aproximadamente 6 Hz y el segundo pico en 21 Hz, los cuales corresponden a la onda alfa y beta. La onda alfa se da cuando el paciente está en reposo, en el ejercicio sucede cuando el usuario cierra los ojos; y la onda beta ocurre cuando el paciente está activo, se obtuvo cuando se le aplicó una luz a los ojos del usuario [].

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/7ee1efdf6f0e04d324ae0591b030d73d5e735597/imges/Lab5/rl1.PNG" width="60%" height="60%">
</p> 
<p align="center">
  Figura 21. Gráfica de regresión lineal de la señal EEG
</p>

A continuación se muestra la relación entre las frecuencias de la señal obtenida y su amplitud. Se tiene un coeficiente de determinación bajo de 0.736, lo que muestra que no se obtiene un ajuste lineal perfecto.

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/7ee1efdf6f0e04d324ae0591b030d73d5e735597/imges/Lab5/rp1.PNG" width="60%" height="60%">
</p> 
<p align="center">
  Figura 22. Gráfica de regresión polinómica de la señal EEG
</p>

Por el contrario, en la gráfica de regresión polinómica decreciente de Grado 2 de la señal EEG se obtuvo un alto coeficiente de determinación, lo que indica que la señal tiene una relación no lineal entre las variables dependientes e independientes. Esto se relaciona con la gráfica FFT en el que las amplitudes tienden a ser menores a medida que la frecuencia es mayor pero con variaciones bruscas y no lineales en ciertos puntos.

- Segundo ejercicio adicional de BITalino: 1 ojo contra luz

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/7ee1efdf6f0e04d324ae0591b030d73d5e735597/imges/Lab5/s2.PNG" width="60%" height="60%">
</p> 
<p align="center">
  Figura 23. Gráfica de señal EEG completa
</p>

En esta gráfica se puede mostrar de la misma forma variaciones grandes del segundo 0 al segundo 30, esto debido a que en ese tiempo se tiene ambos ojos cerrados y tapados, pasado este tiempo el usuario abre y muestra un solo ojo al que se le apunta con una linterna o flash de celular por casi 10 segundos, luego se realiza lo mismo con el otro ojo. Este ejercicio implica que haya un parpadeo en 2 ocasiones, las cuales se observan como unos picos altos en el segundo 29 y segundo 38 aproximadamente. A partir del primer pico, se tiene una variación de amplitudes menor que en un inicio debido a que un ojo permanece abierto  [].

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/7ee1efdf6f0e04d324ae0591b030d73d5e735597/imges/Lab5/int2.PNG" width="60%" height="60%">
</p> 
<p align="center">
  Figura 24. Gráfica de señal EEG en un intervalo de tiempo
</p>

En esta gráfica se puede apreciar mejor el momento en el que el usuario abre uno de los ojos por segunda vez, representado como un cambio brusco en la señal.

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/7ee1efdf6f0e04d324ae0591b030d73d5e735597/imges/Lab5/fft2.PNG" width="60%" height="60%">
</p> 
<p align="center">
  Figura 25. Gráfica FFT de la señal EEG
</p>

Con respecto a su gráfica de frecuencias se puede ver un pico en el valor de frecuencia de 10 Hz que corresponde a la onda alfa, cuando los ojos permanecen cerrados. Mientras que entre las frecuencias 20 y 25 Hz se puede ver un pico correspondiente a la onda beta, cuando uno de los ojos se abre para recibir el flash de un celular, indicando actividad []. 

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/7ee1efdf6f0e04d324ae0591b030d73d5e735597/imges/Lab5/rl2.PNG" width="60%" height="60%">
</p> 
<p align="center">
  Figura 26. Gráfica de regresión lineal de la señal EEG
</p>

<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/7ee1efdf6f0e04d324ae0591b030d73d5e735597/imges/Lab5/rp2.PNG" width="60%" height="60%">
</p> 
<p align="center">
  Figura 27. Gráfica de regresión polinómica de la señal EEG 
</p>

De la misma forma, de ambas gráficas de regresión se observa que la frecuencia y amplitud de la señal siguen una relación no lineal descendente, lo que demuestra que a mayor frecuencia se tenderá a una menor amplitud con variaciones grandes en ciertos puntos que no siguen una linealidad.

### Observaciones
En estos dos experimentos vistos se destaca la diferencia de amplitudes en el EEG debido a la actividad ocular del usuario; sin embargo, las gráficas mostradas no mostraban tan claro estos cambios de señal cuando se cierra uno o ambos ojos, esto se hace notorio en el segundo ejercicio en el que se vuelve menos notorio pero significante. Esto puede ser debido a la presencia de artefactos a lo largo de la toma producida por movimiento no intencional del usuario o que al momento de iluminar sus ojos con una luz este moviera los ojos. 

#### Archivos

- [Datos obtenidos de la señal] 
- [Notebook de ploteo en python]



## Bibliografía <br />
