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
  Figura 1. Uso del electrocardiograma[1]
</p> 

La gráfica de ECG es la señal recogida de cada latido a lo largo del tiempo. El patrón básico se divide en distintas ondas y complejos. La primera onda es la P, que corresponde a la despolarización auricular, sigue el intervalo PR que abarca entre el inicio de la onda P y el complejo QRS. Luego sigue el complejo QRS que abarca la despolarización ventricular y la repolarización auricular, el intervalo ST y finalmente la onda T que representa la repolarización ventricular (Figura 2) [2].
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/631e1b445f34188d7eeaa96be649867731d8a29c/imges/Lab4/grafica_ecg.jpg" width="40%" height="40%">
</p> 
<p align="center">
  Figura 2. Gráfica ECG[2]
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
#### Observaciones
De la señal ECG en estado de reposo se puede observar que para 5 segundos existen 6  “complejos QRS” por lo que en un minuto son 72 latidos. Esto se encuentra dentro del rango de frecuencia cardiaca en reposo que es de 60 a 100 latidos por segundo [10].
De la señal se puede observar que posee mucho ruido en los intervalos “PQ” y “ST”, en dondes la señal se ve con muchos abruptos en donde esto picos de ruidos interfieren con la onda característica del ECG, específicamente las ondas “T” y “U” se pierden. Por otro lado “la onda P” se encuentra con una magnitud mayor que se puede diferenciar del ruido.  Por lo que la información de Despolarización tanto auricular como ventricular producen un cambio que se puede diferenciar en el ECG, a diferencia de la repolarización de ventrículos y el sistema Purkinje que por ser un potencial de menor magnitud y la velocidad en que se genera repolariza, no se puede distinguir con el ruido.
Experimentalmente se pudo notar que se amplificaba con los movimientos corporales, musculares y de respiración, siendo los ruidos por artefactos más característicos [11]. Este tipo de artefactos podían ser ciertamente controlados, pero de igual manera se presenta el ruido. En un principio, la persona que se estaba monitorizando tenía elementos metálicos en su vestimenta, por lo que este otro artefacto tuvo un grado de interferencia en la señal ECG que pudo ser controlada de cierta manera [12].
Existió una tercera fuente de ruido durante la prueba, consiste en los aparatos electrónicos conectados a la fuente de alimentación de corriente alterna, este ruido característico de 60 Hz, se hacía evidente cuando estaba cerca de laptop o tablet cerca del voluntario [13].

#### Archivos

- [Datos obtenidos de la señal](https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/files/11218129/Reposo1.txt)
- [Notebook de ploteo en python](https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/a29d152ccfffc936e5ca5f186bc7be3d2d932c49/Software/lectura_se%C3%B1al_txt.ipynb)

## ECG (Contiene la respiración) <br />
  ### Video de señal en silencio eléctrico, que se muestre las conexiones electrodos-cuerpo y señal ploteada
https://user-images.githubusercontent.com/128627851/231618205-96b098d9-fb4b-4c45-b358-3ea908cac398.mp4
  ### Ploteo de la señal en OpenSignals
  
  <p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/32bbaaea36003405c8a650fdeb2fe89687367cdb/imges/Lab4/opensigrespiracion.png" width="80%" height="80%">
</p> 

  ### Resumen y explicación de la señal ploteada
La captación de la señal ECG luego de inhalaciones profundas y periodos de pausas en la respiración sirve para comparar el efecto respiratorio ante la señal detectada. Teóricamente, la respiración profunda en general afecta el sistema cardiaco, en parte por la cercanía entre los órganos controladores (corazón y pulmones) [14]. En nuestro caso experimental, se incrementó notablemente la cantidad de ruido en la señal. Sin embargo, no hubo cambios notoriamente mayores en la frecuencia de cada onda. El incremento en la cantidad de ruido potencialmente provenga de mayores movimientos corporales durante la inhalación y exhalación. De la misma manera, la FFT nos ayuda a comparar las señales en el dominio de la frecuencia.

  ### Ploteo de la señal en Python
  
  <p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/5520a8b4bb46ec18034c00fee6f305c5e433701e/imges/Lab4/Aguantando_img.png" width="80%" height="80%">
</p> 
Tras la realización de la segunda experiencia, se procedió a la obtención de las siguientes gráficas, en las cuales se evidencia un mayor nivel de ruido durante la diástole, tanto en la gráfica completa como en el intervalo. A partir de la señal obtenida, se pudo observar que se presentan 33 pulsaciones en un lapso de 30 segundos, lo que se asemeja notablemente a las pulsaciones registradas en el estado basal, además su amplitud es menor teniendo un valor máximo promedio de 630 mV y  un valor mínimo de 400 mV (amplitud de 230 mV). En relación al intervalo de la señal, se pudo constatar un incremento significativo del ruido en comparación con la señal previa, lo cual se debe a las condiciones experimentales.

En cuanto al análisis de la gráfica FFT, se identificó la presencia de picos notorios en 0 Hz, 60 Hz y 120 Hz, lo cual coincide con las frecuencias detectadas en la experiencia anterior.

#### Archivos

- [Datos obtenidos de la señal](https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/files/11218102/Aguantar10seg_1.txt)
- [Notebook de ploteo en python](https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/a29d152ccfffc936e5ca5f186bc7be3d2d932c49/Software/lectura_se%C3%B1al_txt.ipynb)

## ECG (Tras activida8d física de 4 minutos) <br />
  ### Video de señal en silencio eléctrico, que se muestre las conexiones electrodos-cuerpo y señal ploteada
https://user-images.githubusercontent.com/128627851/231618268-c4b7d6ac-de9e-43c5-9e7e-06375430ce43.mp4
  ### Ploteo de la señal en OpenSignals
  
  <p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/32bbaaea36003405c8a650fdeb2fe89687367cdb/imges/Lab4/opensigejercicio.png" width="80%" height="80%">
</p> 

  ### Resumen y explicación de la señal ploteada
  Se procedió a captar la señal con el BITalino, teniendo en cuenta las anteriores fuentes de ruido comentadas anteriormente, se hizo lo necesario para evadirlo de cierta manera. Pero la señal aún poseía algo de ruido, se pudo observar que su frecuencia cardiaca aumentaba a simple vista, de igual manera se pudo obtener que en 5 segundos existen 12  “complejos QRS” por lo que en un minuto son 144 latidos. Esto se encuentra dentro del rango de frecuencia cardiaca para el entrenamiento aeróbico que es 123 a 184 pulsaciones por minuto [12].
  ### Ploteo de la señal en Python 
  
  <p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/5520a8b4bb46ec18034c00fee6f305c5e433701e/imges/Lab4/Ejercicios_img.png" width="80%" height="80%">
</p> 
Después de llevar a cabo la última experiencia, la cual implicó la medición posterior a la realización de actividad física por parte del participante, se obtuvieron las siguientes gráficas que evidencian una marcada diferencia respecto a las dos experiencias previas (estado basal y apnea).

A partir de la gráfica de la señal completa, se pudo identificar la presencia de 72 pulsaciones por minuto, lo que representa casi el doble de la frecuencia observada en las experiencias previas. Es importante destacar que la amplitud de la señal se encuentra en torno a los 360 mV, con un valor máximo de 770 mV y un valor mínimo de 310 mV. En relación a la gráfica del intervalo de la señal, se observa un mayor número de pulsaciones debido a que el tiempo de diástole es menor, lo que genera un mayor número de picos (pulsaciones).

Por último, en la gráfica FFT se detectaron picos en las mismas frecuencias que en las experiencias previas, aunque con una magnitud menor. Asimismo, se aprecian picos negativos en frecuencias como 70 Hz o 118 Hz.

### OBservaciones
Para la captura de señal ECG al realizar ejercicio físico, se requirió que la persona realicé el ejercicio de “Burpees” es un ejercicio que mide la resistencia anaeróbica, consiste en realizar una flexión de pecho y posteriormente se realiza un salto vertical elevando las manos [15]
Se realizó este ejercicio debido a que un estudio demuestra que un protocolo que incluía burpees indujo aumentos similares en la frecuencia cardíaca y una calificación más baja de esfuerzo percibido en comparación a el entrenamiento de intervalos de sprint [16].
El protocolo fue realizar burpees de dos series de 40 burpees cada uno. Este ejercicio se logró hacer en un minuto y medio y un minuto con diez segundos para cada serie respectivamente.
<p align="center">
  <img src="https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/653b956bd5c3e80ba1443d7df9402832d1b14332/imges/Lab4/ejerciciow.png" width="50%" height="50%">
</p> 

<p align="center">
  Figura 5. Ejercicio Burpees 
</p> 
#### Archivos

- [Datos obtenidos de la señal](https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/files/11218111/Ejercicio.30segundos.txt)
- [Notebook de ploteo en python](https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/a29d152ccfffc936e5ca5f186bc7be3d2d932c49/Software/lectura_se%C3%B1al_txt.ipynb)

## Conclusiones <br />
En conclusión, los objetivos de adquirir señales biomédicas de ECG, hacer una correcta configuración del BiTalino y extraer la información de las señales ECG del software OpenSignals (r)evolution son fundamentales para obtener datos precisos y confiables en el análisis de las señales ECG. La adquisición adecuada de señales ECG mediante el uso de dispositivos como BiTalino y el uso del software adecuado como OpenSignals (r)evolution permiten a los investigadores y profesionales de la salud obtener información valiosa y precisa para el diagnóstico y tratamiento de enfermedades cardiovasculares. Además, una correcta configuración de los dispositivos de adquisición de señales, garantiza la calidad y la integridad de los datos, lo que es esencial para realizar análisis precisos y confiables. De lo contrario, se pueden obtener señales con mucho ruido debido a diferentes factores como la cercanía de dispositivo tecnologicos, metálicos en el participante.

## Bibliografía <br />
[1] Breen C, Kelly G, Kernohan W. ECG interpretation skill acquisition: A review of learning, teaching and assessment [Online]. J Electrocardiol. 73:125-128. 2019. doi: 10.1016/j.jelectrocard.2019.03.010.

[2] Ashley E, Niebauer J. Explicación de la cardiología. Londres: Remedica; 2004. Capítulo 3, Conquistando el ECG. Disponible en: https://www.ncbi.nlm.nih.gov/books/NBK2214/

[3] D. Batista, H. Plácido da Silva, A. Fred, C. Moreira, M. Reis, and H. A. Ferreira, “Benchmarking of the BITalino biomedical toolkit against an established gold standard,” Healthcare Technology Letters, vol. 6, no. 2, pp. 32–36, Mar. 2019, doi: https://doi.org/10.1049/htl.2018.5037.
‌

[4] “Derivaciones Cardiacas, significado,” My-ekg.com, 2018. https://www.my-ekg.com/generalidades-ekg/derivaciones-cardiacas.html (accessed Apr. 12, 2023).

[5] R. P. Girardeau, “Einthoven’s Triangle Unlocks 12-Lead ECG Interpretation - JEMS: EMS, Emergency Medical Services - Training, Paramedic, EMT News,” JEMS: EMS, Emergency Medical Services - Training, Paramedic, EMT News, Mar. 13, 2012. https://www.jems.com/training/einthoven-s-triangle-unlocks-12-lead-ecg/#:~:text=Lead%20I%20extends%20horizontally%20from,leg%20being%20the%20positive%20pole (accessed Apr. 12, 2023).

[6] “BITalino (r)evolution Lab Guide.” Available: https://support.pluxbiosignals.com/wp-content/uploads/2022/04/HomeGuide2_ECG.pdf

[7] A. Němcová, L. Maršánová, R. Smisek, and M. Vitek, “Recommendations for ECG acquisition using Bitalino,” https://www.researchgate.net/. [Online]. Available: https://www.researchgate.net/publication/308984068_RECOMMENDATIONS_FOR_ECG_ACQUISITION_USING_BITALINO. [Accessed: 13-Apr-2023]. 

 [8] Y. Kaolawanich, R. Thongsongsang, T. Songsangjinda, and T. Boonyasirinant, “Clinical values of resting electrocardiography in patients with known or suspected chronic coronary artery disease: A stress perfusion cardiac MRI study - BMC cardiovascular disorders,” BioMed Central, 28-Dec-2021. [Online]. Available: https://bmccardiovascdisord.biomedcentral.com/articles/10.1186/s12872-021-02440-5. [Accessed: 12-Apr-2023]. 

 [9] A. Kumar, R. Ranganatham, R. Komaragiri, and M. Kumar, “Efficient QRS complex detection algorithm based on Fast Fourier transform,” Biomedical engineering letters, 25-Oct-2018. [Online]. Available: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6431324/. [Accessed: 12-Apr-2023].

[10] Kenney WL, et al. Cardiorespiratory responses to acute exercise. In: Physiology of Sport and Exercise. 6th ed. Champaign, Ill.: Human Kinetics; 2015.

[11] CORREA, Carlos Adrián; BOLAÑOS, Ricardo Andrés; ESCOBAR, Antonio. Análisis de esquemas de filtrado análogo para Señales ecg. Scientia et technica, 2007, vol. 1, no 37.

[12] Altuve, M., Casanova, O., Wong, S., Passariello, G., Hernandez, A., & Carrault, G. (2008). Evaluación de dos Métodos para la Segmentación del Ancho de la Onda T en el ECG. In IV Latin American Congress on Biomedical Engineering 2007, Bioengineering Solutions for Latin America Health: September 24th–28th, 2007 Margarita Island, Venezuela (pp. 1254-1258). Springer Berlin Heidelberg.

[13] González, J. B., & Barrero, J. P. (2006). Implementación de filtros adaptativos en DSP aplicados al tratamiento de interferencia de 60 hz y desplazamiento de la línea de base del ECG.

[14] R. Pallas-Areny, J. Colominas i Balagué, and X. Rosell, “The effect of respiration-induced heart movements on the ECG ,” https://www.researchgate.net/. [Online]. Available: https://www.researchgate.net/publication/33421650_The_effect_of_respiration-induced_heart_movements_on_the_ECG. [Accessed: 13-Apr-2023].

[15] BINGLEY, S., et al. The Burpee Enigma: Literature Review. Abstracts/Journal of Science and Medicine in Sport, 2019, vol. 22, no S2, p. S75-S115.
