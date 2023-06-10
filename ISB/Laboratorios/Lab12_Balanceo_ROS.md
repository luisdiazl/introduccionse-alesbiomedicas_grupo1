# LABORATORIO 12
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

## Archivos
-[Notebook](https://github.com/luisdiazl/introduccionse-alesbiomedicas_grupo1/blob/main/ISB/Laboratorios/Lab12_Balanceo_ROS.ipynb)

## Conclusiones
En estos ejerecicios se destaca la importancia de escoger un correcto modelo, en este caso de regresión lineal, que permitan no solo a predecir de manera óptima las clases de determinados inputs, sino que los resultados obtenidos tengan una significancia estadística que permita verificar si el clasificador es eficiente y que los resultados no hayan sido hechos al azar. Además, se pudo corroborar como la aplicación de un balance ROS mejora en gran medida el desempeño del modelo permitiendo obtener predicciones más fiables. 
Para el ejercicio elaborado, se concluye que el mejor modelo predictivo es el obtenido a partir de 3 variables: C', 'PIP' y 'P_ventilador' tras pasar por un balance ROS. Los resultados de este modelo fueron estadísticamente significativos por su p-value menor a 0.05, con una presición de 83% y con la menor cantidad de falsos positivos y negativos, así como de una variabilidad en la selección de las clases.

## Bibliografía
1. https://ceur-ws.org/Vol-710/paper37.pdf
2. https://home.iitk.ac.in/~shalab/regression/Chapter2-Regression-SimpleLinearRegressionAnalysis.pdf
3. https://www.analyticsvidhya.com/blog/2020/04/confusion-matrix-machine-learning/
