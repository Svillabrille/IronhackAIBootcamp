# IronhackAIBootcamp
Ironhack AI Bootcamp

En este repositorio está la descripción y explicación del modelo cats and dogs de Kaggle (https://www.kaggle.com/code/juanluisrosa/dogs-and-cats-classifications-using-cnn/notebook).

1. En la primera iteración se importan todas las librerias de Python necesarias para el cálculo matemático, redes neuronales artificiales (Keras) y machine learning (TensorFlow), además de diferentes capas para las librerías que hemos mencionado.
Para comprobar que ha ido bien se hace un print que nos devuelve los archivos del directorio que hemos dado de alta.

2. Se dan de alta las constantes y se genera el tamaño final de las imágenes. De esta manera, cuando más adelante se generen imágenes, se podrá hacer referencia a este tamaño final, en forma de variable, para que todas tengan la misma dirección.
3. Se cargan los dos data sets, el de test y el de entrenamiento del modelo.
   Se extraen los archivos comprimidos ya que anteriormente se subieron en formato Zip.
4. Se establece la variable train_images como todo el archivo train (con este archivo entrenaremos el modelo). A continuación se establece la variable CATEGORIES como un array vacío y después se establece un bucle para iterar sobre todas las imágenes y establecer una         etiqueta (0 o 1) en función de si la imagen contiene gatos o perros, basados en el nombre que tuviese la imagen. Con estas imágenes se "llenará" el array. Básicamente si empieza por cat se le atribuye un 0 y en caso contrario un 1.
   Para comprobar que todo ha ido bien pintamos una tabla con los 5 primeros items donde devolverá el nombre de la imagen en una columna y la diferenciación que hayamos hecho en 0 o 1 de dichas imágenes en la otra columna.
   Lo mismo que hemos hecho anteriormente con las 5 primeras, lo haremos con las 5 últimas.
   Además, extraemos cuántas imágenes hemos cargado y cuántas hay de cada tipo, habiendo 12500 de cada tipo (gatos y perros). Una vez hecho, lo podemos visualizar utilizando un método que nos devuelve los gráficos de ambos datos.
   A continuación veremos las dimensiones de las imágenes. Crearemos un array vacío al que luego introduciremos todas las dimensiones de las imágenes dentro.
   Después prepararemos los datos para que hagamos el match por strings y no por integers. Anteriormente establecimos 0 y 1 para determinar si eran perros o gatos pero ahora necesitamos pasar a eso a strings "cat" y "dog" para que el modelo pueda entender correctamente       cómo qué tipo de imagen es, así es como está definido dicho modelo.
   Lo que haremos después es clasificar las imágenes. Aquí lo que realizamos con el código es establecer qué tido de imagen es. En total salen 10044 gatos y 9956 perros en un barrido y 2544 perros y 2456 gatos en el segundo. El primero corresponde a las fotos en eje X y      el segundo a las fotos en eje Y (horizontal y vertical).
   Lo siguiente que haremos es el Data Augmentation, que consiste en generar nuevos datos a partir de datos existentes para entrenar un modelo de Machine Learning (ML). Además de eso, en el siguiente paso, validaremos los datos que hemos encontrado en los dos barridos que    hicimos antes.
   Después de esto generaremos imágenes y veremos cómo funciona nuestro generador de imágenes.
5. Construcción del modelo
   En nuestro modelo tendremos 3 capas y dentro de cada capa una serie de procesos que son:
   * Conversor de la imagen, que se encargará de sacar las características de las imágenes.
   * Pooling, que reducirá el volumen de la imagen una vez hecha la convolución (primer proceso)
   Después de estas 3 capas habrá una que conectará todas y que será la encargada de establecer la decisión de si la imagen es un perro o un gato.
   Pasaremos a entrenar ahora el modelo, donde previamente se hará una normalización (estandarización de imágenes) del modelo, utilizando los procesos descritos anteriormente, que luego se compilará y nos devolverá un resumen del modelo
   A continuación tenemos los callbacks, que son resortes, o avisos que indican cuándo deberá dejar de entrenar el modelo. Normalmente cuando deje de mejorar su precisión. Algunos de ellos son el EarlyStop o el LearningRate.
   En esta zona aparecen los epochs, que es la cantidad de veces que un data set pasa a través del algoritmo creado. Los epochs e establecerán como 3 en velocidad rápida de procesado y sino como 10.
   La visualización del rendimiento es muy importante ya que en ella podremos ver si los datos que hemos cargado están generando un precisión alta o baja con un contenido "perdido" alto o bajo. Si la precisión es alta y el contenido perdido es bajo, seguiremos adelante,    en caso contrario podemos aumentar el número de epochs o disminuirlo para ver cómo fluctúan nuestros datos, ya que hay veces que se puede generar un sobreentrenamiento que vaya en detrimento de los resultados esperados. Además de esto se generarán tamaños de imágenes    y otros datos necesarios para la creación de las imágenes durante el entrenamiento y test posterior.
   Por último se generá el test del modelo, creando un generador de test del archivo test que dimos de alta en el punto 1 y que predecirá dichos datos (12500 imágenes en total).
   Numpy nos devolverá la predicción en formato 0 o 1, que convertiremos utilizando el conversor del que hablamos anteriormente en el punto 4 para saber si las imágenes son perros o gatos.
6. Como último paso tenemos la visualización de las imágenes en un gráfico que muestre la cantidad de perros y gatos que ha detectado el modelo.
   
   




Gracias Jarko (@CarlosGaLo) por todo el curro del bootcamp y las clases que te has currado todos los días.
   
