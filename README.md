# ActIntegradora3

### Jorge Alberto Padilla Gutiérrez  A01635346
### Rodolfo Humberto Tamayo González A01282633
### Adrian Marcelo Suárez Ponce      A01197108
### Marcos Leroy Salazar Skinner     A01039743
### Jorge Antonio Ruiz Zavalza       A01411162
### Guillermo Sáenz González         A00823049

Este repositorio contiene nuestra implementación de la segunda y tercera actividad integradora de la materia de Procesamiento de Lenguaje Natural, la cual consiste en un analizador de sentimientos

## Librerias

Para la actividad integradora 2, la principal libreria utilizada en este proyecto es Natural Language Toolkit (NLTK), la cual es una librería de Python que incorpora muchas funcionalidades estadísticas para procesar texto, así como scikit-learn, la cual es una libreria que cuenta con funciones basicas de aprendizaje automático, tambien se requiere tweepy, para acceder a twitter, numpy para trabajar mejor con numeros y estructuras de datos, matplotlib para poder graficar datos, y finalmente json para trabajar con estos archivos.

Como agregado para la actividad integradora 3, se requieren mas librerias. Primeramente re, la cual ayuda a trabajar con expresiones regulares, tambien se necesita praw que es el API de Reddit.

Toda la información referente a los requerimientos del ambiente estan presentes en el archivo requirements.txt, por lo que este se puede utilizar

```shell
pip install -r requirements.txt
```

## Archivos

Para la actividad integradora 2, los archivos presentes .txt y .pickle en este git son necesarios para la ejecución rapida de este algoritmo, estos son generados en el mismo, pero el contar con ellos para la ejecucion general salva hasta 40 minutos de ejecución, estos archivos son:

- BernouliNB_classifier.pickle
- LinearSVC_classifier.pickle
- LogisticRegression_classifier.pickle
- MNB_classifier.pickle
- naivebayes.pickle
- SGDClassifier_classifier.pickle
- negative.txt
- positive.txt

## Desarrollo

El desarrollo de la actividad integradora 2 esta fuertemente basado en los tutoriales de Sentdex: https://www.youtube.com/playlist?list=PLQVvvaa0QuDf2JswnfiGkliBInZnIC4HL

## Utilidad

El analizador de sentimientos funciona con twitter y reddit, y tambien es puede trabajar con audios; este es capaz de clasificar tweets entre positivos y negativos

## Uso

Para trabajar con este analizador de sentimientos, primero se debe clonar el repositorio, ya sea mediante la opcion de clone de la interfaz de GitHub o desde terminal
```shell
git clone https://github.com/Jorge-Padilla/ActIntegradora3
```

Presente en el archivo .ipynb se encuentran los recuadros de cada tutorial, y al final de los tutoriales de la actividad integradora 2 estan presentes 5 recuadros con toda la funcionalidad concreta del algoritmo, por lo que para trabajar con este de forma general nos referiremos a estos recuadros.

Después de estos recuadros estan presentes los agregados de la actividad integradora 3, donde primeramente tenemos una base de datos que tiene texto etiquetado como positivo o negativo, una funcionalidad para transcribir audio a texto, la funcionalidad de buscar Tweets por usuarios, la funcionalidad de buscar posts en Reddit por usuarios, Tres arquitecturas diferentes de RNN para la clasificación de texto como positivo o negativo y métricas  de  evaluación de  cada  uno  de  sus  clasificadores.

### Actividad Integradora 2

Una vez obtenido el codigo, lo primero que debes hacer es contar con las librerias utilizadas mencionadas anteriormente, despues de esto, se debe descargar el paquete de NLTK, esto se hace mediante la ejecución del comando
```python
nltk.download()
```
Aparecerá en terminal el siguiente texto
```shell
NLTK Downloader
---------------------------------------------------------------------------
    d) Download   l) List    u) Update   c) Config   h) Help   q) Quit
---------------------------------------------------------------------------
Downloader>
```
Se debe ingresar primeramente d para descargar NLTK
```shell
Download which package (l=list; x=cancel)?
  Identifier>
```
Ingrese all para descargar NLTK en su totalidad.
Una vez terminada la descarga, ingrese q para salir del instalador

En caso de tener el instalador grafico, con seleccionar la celda de all descargara todo lo necesario, y despues se puede cerrar la ventana

El siguiente recuadro requiere los archivos .pickle para reducir el tiempo de ejecución, por lo que recomendamos mantenerlos en el mismo directorio en el que esta presente el archivo .ipynb

Los recuadros que vienen despues de los tutoriales corren el algoritmo, estos requieren una palabra clave, la cual puede ser modificada a gusto de ejecución, por default viene presente "Amazing"

```python
twitterStream.filter(track=["Amazing"])
```

La ejecución de este recuadro es infinita, por lo que se debe pausar manualmente para no agotar el recurso de Twitter Developer

### Actividad Integradora 3

Los recuadros de _Get User posts from reddit_ cuentan con dicha funcionalidad, la cual utiliza el API de reddit para buscar usuarios y con ella sus publicaciones que se obtienen con la rutina submitions()

```python
submissions = redditor.submissions.new(limit=100)
```

Con esto necesitamos un usuario, el cual es pedido al usuario mediante una entrada, esto puede modificarse para directamente escribirlo en el codigo reemplazando el input()

```python
user = input("Insert user to get posts from: ")
posts = get_posts(user)
```

## Twitter Developer

Este algoritmo utiliza una cuenta de Twitter Developer para poder obtener la información de los tweets, estas cuentan con limites de hasta medio millon de tweets.

La cuenta ingresada por un colaborador esta presente para disponibilidad, pero en el momento en el que esta llegue al limite se deberá cambiar a otra cuenta de desarrollador a elección del usuario
