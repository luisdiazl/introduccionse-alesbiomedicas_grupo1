# Laboratorio 3
------------
## Tabla de contenidos
- [¿Qué es EMG?](#¿Qué-es-EMG)
- [BITalino (Conceptos)](#BITalino-(Conceptos))
- [Ejercicio 1 Músculo Biceps](#Ejercicio-1-Músculo-Biceps)
- [Ejercicio 2 Músculo](#Ejercicio-2-Músculo)
<p class="text-justify">
## ¿Qué es EMG? (nicolle)
Breve descripción de EMG con imágenes

## BITalino (Conceptos) (nicolle)
Descripción de sus componentes y conexiones

## Ejercicio 1 Músculo Biceps 
- Imágenes y videos CONEXIÓN USADA 
- Video de señal en silencio eléctrico o reposo 
- Ploteo de señal en OpenSignals 
- Resumen y explicación de señal (2) <br />
Como primer ejercicio, se realizó una medición de EMG en el músculo bíceps braquial del miembro superior izquierdo. Se realizaron 3 tipos de mediciones: Brazo en reposo, brazo en movimiento de flexión y brazo en movimiento de extensión. <br />
En la primera medición, el brazo permaneció en reposo encima de una mesa con la finalidad de que los músculos del usuario estén relajados. Esto se representa como un señal constante y pequeña en la gráfica obtenida que viene a ser ruido ya que no hay una actividad eléctrica presente en el músculo. El ruido puede provenir de distintas fuentes como el ruido inherente de fuentes eléctricas, ruido del medio ambiente, movimiento involuntario del usuario, un mal contacto entre el electrodo y la piel, entre otros [a]. <br />
https://www.ijsrp.org/research-paper-0517.php?rp=P656368 <br />
Señal obtenida del ejercicio de flexión cuando el músculo está en reposo: <br />
![Image7](imges/Lab3/EMG_biceps_flexion1.PNG) <br /><br />
En la segunda medición, el brazo realiza una flexión de forma gradual y con una cierta fuerza que va aumentando de intensidad a medida que va realizándose el movimiento. En la gráfica obtenida muestra como las amplitudes van aumentando hasta llegar a unos picos altos debido a que al final del movimiento se le pide al usuario que aplique toda la fuerza posible. <br />
En la tercera medición se tiene un procedimiento y resultado parecido, el brazo realiza una extensión de forma continua y constante. Para ello empieza ejerciendo una fuerza pequeña hasta alcanzar la máxima intensidad posible. La gráfica EMG muestra cómo el tamaño de la señal va aumentando ligeramente hasta llegar a unos picos altos; sin embargo, se puede observar que la amplitud máxima obtenida es mucho menor a la alcanzada en la segunda medición. <br />
Esta diferencia de resultados es debido a la función que cumple ciertas regiones del músculo al realizar un movimiento. La zona evaluada es el bíceps braquial, este músculo está activo durante la flexión ya que se contrae. Cuando se realiza una flexión, el bíceps braquial contribuye mediante una contracción, lo que significa que se genera una alta actividad muscular representándose como la detección de una alta actividad eléctrica dependiente de la intensidad a lo largo del tiempo. En una extensión sucede lo contrario, el tríceps braquial es el músculo que realiza una mayor actividad muscular mientras que el bíceps tenderá a relajarse generando una menor actividad eléctrica en todo el proceso [b].
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7500348/



- ### Archivo de datos de señal (pon en repositorio)
- ### Ploteo de señal en Python (una breve descripción de de que se ve en la señal) <br />
Como se mencionón anteriormente, la primera señal medida fue la del músculo del bíceps. En esta primera imagen se puede observar la gráfica completa medida en nuestro compañero, la cual tiene una duración de aproximadamente 600 segundos, por tal motivo hay algunos valores que se encuentran superior a 1000 Hz (Frecuencia de sampleo); sin embargo, estas mediadas son productos de movimeintos ajenos a la experiencia, por tal motivo no se toma en cuenta. <br />
![Image1](imges/Lab3/Imagen_1.png) <br /><br />


Se presenta las gráficas de extensión, con una fuerza en contra del movimiento realizado Esta es la gráfica de la flexión del brazo, la cual tuvo una duración de 1 segundo:<br />
![Image2](imges/Lab3/Señal_Biceps_1.png) <br /><br />

A continuación se muestra su gráfica FFT en decibelios:<br />
![Image3](imges/Lab3/FFT_Biceps_1.png) <br /><br />

Esta gráfica representa la extensión del brazo, la cual tuvo una duración de 5 segundos <br />
![Image4](imges/Lab3/Señal_Biceps_2.png)<br /><br />
A continuación se muestra su gráfica FFT en decibelios:<br />
![Image5](imges/Lab3/FFT_Biceps_2.png) <br /> <br />

JUSTIFICAR RUIDO POR CADENA METÁLICA (3)  <br />
<p class="text-justify">
Se observa en la de señal EMG captada por el BiTalino una distorisión en representado en la frecuencia de la actividad eléctrica del músculo del Biceps una distorción que en los casos puede deberse a que el usuario poseía en el momento de la toma de muestra una cadena de plata por lo que los electrodos de EMG captan un voltaje en la membrana de la células epiteliales distorcionados por el elemento métalico ubicado en su cuello, lo que se distorciona y se evidencia en el gráfico de las freccuencias.  <br /> <br />
</p>

## Ejercicio 2 Músculo Gastrocnemio
- ### Imagenes y Videos CONEXIÓN USADA
- ### Video de señal en silencio eléctrico o reposo 
- ### Ploteo de señal en OpenSignals 
- ### Resumen y explicación de señal (4)
<p class="text-justify">
La señal captada del gastrocnemio, a nivel basal, fue menos notoria que la del bícep braquial. No obstante, vale resaltar que esta región anatómica presentaba una mayor concentración de vello corporal lo cual puede perjudicar la captación de la señal EMG. Al momento de flexionar la extremidad del miembro inferior, notamos cambios en la amplitud de la señal captada. La amplitud, en efecto, fue mayor cuando se utilizó más fuerza para superar la resistencia infligida contra el movimiento de la pierna. Finalmente, la posición del suijeto de prueba pudo afectar la fidelidad de la señal EMG dado que la dispoción de electrodos y el BITalino dificultaron conseguir una posición totalmente en reposo. 
  <br /> <br />
</p>
- ### Archivo de datos de señal (pon en repositorio)
- ### Ploteo de señal en Python (una breve descripción de de que se ve en la señal) (6)
La segunda medición de EMG fue realizada en el músculo gastrocnemio, localizado en en plano superficial de la parte posterior de la pierna. AL igual que el caso anterior, se realizó una medición general, donde se encunetran la flexión y la extensión de la pierna para medir la actividad del músculo en cuestión, obteniendo así la siguiente gráfica:<br />
![Image6](imges/Lab3/Imagen_2.png) <br /><br />


JUSTIFICAR VA A HABER CIERTO ALGO POR TENER VELLOS EN LA PIERNA: Como ya hemos mencionado previamente, BITalino es un dispositivo compuesto por varios módulos individuales, entre los cuales se encuentra el EMG. Al analizar la señal captada, se ha detectado la presencia de ruido en la misma, lo cual puede deberse a diversos factores, tales como el ruido ambiental y las condiciones de preparación de la piel del sujeto. En este caso en particular, es importante destacar que el participante presentaba una cantidad significativa de vello en la pierna, lo que probablemente haya sido la causa del ruido observado en la señal, en contraposición con la medición realizada en el brazo, el cual no contaba con vello.

</p>
