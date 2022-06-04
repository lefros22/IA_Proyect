# Prediccion de valores futuros en una planta por ciclos de trabajo
Mi nombre es Luis Fernando Riveros Orozco.
## INTRODUCCION
Se tienen datos que corresponden 16 series de tiempo para la altura de un tanque en funcion del ciclo de trabajo de una bomba. Cada serie de tiempo posee diferente cantidad de muestras, entre 15-20.
![image](https://user-images.githubusercontent.com/71291574/171816041-ac0dbfdb-a462-481c-84c8-81f7c202e840.png)

Los datos fueron obtenidos a partir de un modelo desarrollado en SIMSCAPE un toolbox de simulink-Matlab.

Las etiquetas iniciales son, Altura del tanque, Ciclo de trabajo de la bomba, Numero de muestra.

Se planea, aplicar control predictivo a diferentes parametros de un tanque, por eso los datos se deben usar para poder modelar la funcion de transferencia de la planta.

Para esto, se plantea usar redes neuronales por series de tiempo.

## Desarrollo
Se planteo que para 


En primer lugar, se hizo la conversion de datos a entradas y salidas interpretables por una red neuronal usando series de tiempo. 

Se generaron 3 conjuntos de datos.
-Datos para el entrenamiento y prueba con cross validation de 5 particiones-
-Datos de evaluacion, correspondiente a un 5%
-Datos de prediccion, correspondiente a las muestras de la serie de tiempo con un ciclo de trabajo de 57%.

Se normalizaron los datos usando un standarScaler.

Se realizo un analisis por PCA, para reducir la dimensionalidad de 3 a 2 manteniendo el 99.99% de la varianza.

Se aplico la tecnica de gridSearch

Se eligio el mejor conjunto de hiperparametros

Se reentreno la red usando todo el conjunto

Se valido la red usando R2

Por ultimo se realizo una prediccion interativa a partir de el dato incial de la serie, para comprobar el alcance de prediccion de la red.

## RESULTADOS

Resultado de la evaluacion:

![image](https://user-images.githubusercontent.com/71291574/171814809-2644a378-8498-4faa-b851-0cd47d7f6b96.png)

Resultado de las predicciones: 

![image](https://user-images.githubusercontent.com/71291574/171815144-60603de3-d9ad-4c0a-bca5-99ac2fc421ea.png)


## Conclusiones

Para el caso de esta planta, se pudo comprobar la efectividad de una red neuronal al poder modelar el comportamiento de una planta, lo que permitiria aplicar de manera satisfactoria estrategias de control por redes neuronales.

Las tecnicas aplicadas como PCA me permiten agilizar el proceso de busqueda de hiperparametros, pues el grid search puede ser un poco demorado dependiendo del tamaño de la red y la cantidad de datos y al reducir la dimensionalidad, reduzco el tamaño de la capa de entrada y agilizo los procesos de iteracion en el entrenamiento.

## Video

Link:
https://youtu.be/VtLhmKSB7Io
