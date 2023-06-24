# LABORATORIO 13
------------------------------------------------

## Tabla de contenidos
- [Participantes](#Participantes)
- [Materiales y equipos](#Materiales-y-equipos)
- [Conclusiones](#Conclusiones)
- [Bibliografía](#Bibliografía)

## Participantes <br />
- Luis Daniel Jesús Diaz Leguizamon (colaborador) - luis.diaz.l@upch.pe <br />
- Giancarlo Arian Guarnizo Bellido (colaborador) - a20191812@pucp.edu.pe <br />
- Diego Fernando Segura Contreras (colaborador) - diego.segura.c@upch.pe <br />
- Alexys Caytano Melendez (colaborador) - alexys.caytano@upch.pe <br />
- Nicolle Muñoz Huamán (colaborador) - nicolle.munoz@upch.pe <br />
- Yereli Karol García Palomino (colaborador) - a20191706@pucp.edu.pe <br />

## Materiales y equipos <br />
| Modelo         | Descripción      | Cantidad |
| ---            |     ---          |  ---     |
| Google Collab |      |     1    |
| -              | Laptop o PC      |     1    |
| Teachable Machine |      |     1    |

## Metodología <br />
Para este aprendizaje se han hecho 4 clases que consisten en 3 libros y una caja, cada uno con diferentes fotografías en diferentes posiciones para mayor aprendizaje y para que exista una mayor capacidad de predicción correcta.

(Libros.jpeg) (Flashcard_cámara.jpeg)

Posterior a ello, se procede a prepara el modelo ya implementado, de forma que esté listo para realizar la clasificación con información de testeo. 

(preparamod1.jpeg) (preparamod2.jpeg) (preparamod3.jpeg)

Una vez conseguido el "Modelo Preparado", se procede a testear mostrando los libros y/o caja, es decir, las clases, a la cámara web para que se pueda comprobar la eficacia del modelo de Machine Learning. 

(sol1).

El modelo logra predecir el "Libro de anatomía" con un alto porcentaje, no un 100%. Es un ligero menor de porcentaje de predicción.

(sol2)

Por otra parte, con el "Libro de Biología", se da una correcta clasificación con un porcentaje de predicción de 100%. El caso anterior, podría deberse a que son libros del mismo color. 

(sol3)

Sin embargo, en el caso de "Atlas de Anatomía Humana", se aprecia un cambio en el porcentaje de predicción. Si bien en un inicio logra predecir que es la clase correcta, cuando se muestra el borde del libro, se observa un constante cambio en el porcentaje de predicción, que suele ser ligero. En el momento de la captura de la imagen se dió con 50%, pero en el video se observa como va variando. Luego, cuando se muestra la parte trasera del libro, lo hace de forma correcta. 

(sol4) (sol5) (sol6)

Por último, se muestra el "Flashcard Anatomía", que finaliza con un alto porcentaje de predicción de un 98%, significativamente alto y que comprueba que el modelo empleado presenta alta eficiencia. 

(sol7)


## Archivos
Samples usados: <br />
- [Libro de anatomía (samples)](https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/main/Software/Lab13_files/Libro%20de%20Anatom%C3%ADa-samples.zip)
- [Libro de Biología (samples)](https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/main/Software/Lab13_files/Libro%20de%20Biolog%C3%ADa-samples.zip)
- [Atlas de Anatomía Humana (samples)](https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/main/Software/Lab13_files/Atlas%20de%20Anatom%C3%ADa%20Humana-samples.zip)
- [FlashCard Anatomía (samples)](https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/main/Software/Lab13_files/FlashCard%20Anatom%C3%ADa-samples.zip)  <br />

Modelo usado:
[Modelo](https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/main/Software/Lab13_files/tm-my-image-model.zip)

Video con los resultados:
[Video](https://drive.google.com/file/d/1sSOJDd9BZkdz_VQvExq8YvTJDlHv7mth/view?usp=sharing)

## Conclusiones
El modelo muestra resultados relevantes que indican un correcto desempeño en la clasificación de objetos. Pese a que aún presente dificultades en la identificación de objetos con similares características y tomas en donde se obtenga menos detalles y características, estás pueden mejorarse esto colocando una mayor data de entrenamiento. Para el trabajo realizado, sería necesario el uso de más fotografías de aprendizaje con diferentes perspectivas de luz, cercanía a la cámara, posicionamiento, entre otros.

## Bibliografía
[1] Teachable Machine. Available: https://teachablemachine.withgoogle.com/models/W7tLJMBc8/
