<div align="center">
    <h1>Fundamentos Prácticos de Machine Learning</h1>
    <img src="https://imgur.com/mMOJlOo.png" width="">
</div>

## Tabla de contenido

- [Fundamentos prácticos](#fundamentos-prácticos)
  - [Introducción al Curso](#introducción-al-curso)
  - [Introduccón a Numpy](#introduccón-a-numpy)
  - [Introducción y manipulación de datos con Pandas](#introducción-y-manipulación-de-datos-con-pandas)
  - [Introducción a Scikit Learn](#introducción-a-scikit-learn)
- [Regresión Lineal y Logística](#regresión-lineal-y-logística)
  - [¿Qué es la predicción de datos?](#qué-es-la-predicción-de-datos)
  - [Sobreajuste (Overfiting) y Subajuste (Underfiting) en los datos](#sobreajuste-overfiting-y-subajuste-underfiting-en-los-datos)
    - [Sobreajunte (overfiting)](#sobreajunte-overfiting)
    - [Subajuste (underfiting)](#subajuste-underfiting)
  - [Regresión lineal simple y regresión lineal múltiple](#regresión-lineal-simple-y-regresión-lineal-múltiple)
  - [Regresión lineal simple con Scikit-Learn | Predicción de salarios en función de la experiencia](#regresión-lineal-simple-con-scikit-learn--predicción-de-salarios-en-función-de-la-experiencia)
  - [Regresión logística con Scikit-Learn | Clasificar si un paciente tiene o no diabetes](#regresión-logística-con-scikit-learn--clasificar-si-un-paciente-tiene-o-no-diabetes)
- [Árboles de decisión](#árboles-de-decisión)
  - [¿Qué es un árbol de decisión?](#qué-es-un-árbol-de-decisión)
  - [Decision Tree en Scikit-Learn | Clasificar si un persona en el titanic muere o no](#decision-tree-en-scikit-learn--clasificar-si-un-persona-en-el-titanic-muere-o-no)
- [K-Means](#k-means)
- [Aprendizaje profundo](#aprendizaje-profundo)

# Fundamentos prácticos

## Introducción al Curso

- **Machine Learning**
  - Capacidad de un algoritmo de adquirir conocimiento a partir de los datos recolectados para mejorar, describir y predecir o clasificar resultados.

- **Estrategias de Aprendizaje**:
  - **Aprendizaje Supervisado**: Permite al algoritmo aprender a partir de datos previamente etiquetados.
  - **Aprendizaje no Supervisado**: El algoritmo aprende de datos sin etiquetas, es decir encuentra similitudes y relaciones, agrupando y clasificando los datos.
  - **Aprendizaje Profundo (Deep Learning)**: Está basado en redes Neuronales.

- **Importancia del ML**
  - Permite a los algoritmos aprender a partir de datos históricos recolectados por las empresas permitiendo así tomar mejores decisiones.

- **Pasos a Seguir para Desarrollar un modelo en ML**
  - **Definición del Problema**: Es necesario definir previamente el problema que va a resolver nuestro algoritmo
  - **Construcción de un modelo y Evaluación**: Una vez definido el problema procedemos a tratar los datos y a entrenar nuestro modelo que debe tener una evaluación cercana al 100%
  - **Deploy y mejoras**: El algoritmo es llevado a producción (aplicación o entorno para el que fue creado), en este entorno podemos realizar las mejoras pertinentes de acuerdo al comportamiento con los usuario e incluso aprovechando los datos generados en esta interacción

## Introduccón a Numpy

NumPy es un paquete de Python que significa “Numerical Python”, es la librería principal para la informática científica, proporciona potentes estructuras de datos, implementando matrices y matrices multidimensionales. Estas estructuras de datos garantizan cálculos eficientes con matrices.

- [Numpy apuntes de la clase en colab](1.fundamentos-practicos/numpy.ipynb)

- [Numpy Cheat Sheet](https://s3.amazonaws.com/assets.datacamp.com/blog_assets/Numpy_Python_Cheat_Sheet.pdf)

## Introducción y manipulación de datos con Pandas

Pandas (Panel Data)

Es una librería derivada de numpy pensada para el manejo de datos en forma de panel. Trabaja con series, data frames y panels, generan indices a los arreglos (a manera de panel o tabla de excel), en una (Series), dos (DataFrames) o tres dimensiones (Panels)

- [Pandas apuntes de la clase en colab](1.fundamentos-practicos/pandas.ipynb)

- [Pandas Cheat Sheet](http://datacamp-community-prod.s3.amazonaws.com/dbed353d-2757-4617-8206-8767ab379ab3)

## Introducción a Scikit Learn

[Scikit-Learn](https://scikit-learn.org/stable/) es una librería open-source para Python. Cuenta con algoritmos de clasificación, regresión, clustering y reducción de dimensionalidad. Además, presenta la compatibilidad con otras librerías de Python como NumPy, SciPy y matplotlib.

La gran variedad de algoritmos y utilidades de Scikit-learn la convierten en la herramienta básica para empezar a programar y estructurar los sistemas de análisis datos y modelado estadístico. Los algoritmos de Scikit-Learn se combinan y depuran con otras estructuras de datos y aplicaciones externas como Pandas o PyBrain.

La ventaja de la programación en Python, y Scikit-Learn en concreto, es la variedad de módulos y algoritmos que facilitan el aprendizaje y trabajo del científico de datos en las primeras fases de su desarrollo. La formación de un Máster en Data Science hace hincapié en estas ventajas, pero también prepara a sus alumnos para trabajar en otros lenguajes. La versatilidad y formación es la clave en el campo tecnológico.

- [Scikit Learn cheat sheet](https://s3.amazonaws.com/assets.datacamp.com/blog_assets/Scikit_Learn_Cheat_Sheet_Python.pdf)

# Regresión Lineal y Logística

## ¿Qué es la predicción de datos?

El análisis predictivo agrupa una variedad de técnicas estadísticas de modelización, aprendizaje automático y minería de datos (algoritmos en sí) que analiza los datos actuales e históricos reales para hacer predicciones acerca del futuro o acontecimientos no conocidos.

En el ámbito de los negocios los modelos predictivos extraen patrones de los datos históricos y transaccionales para identificar riesgos y oportunidades. Los modelos predictivos identifican relaciones entre diferentes factores que permiten valorar riesgos o probabilidades asociadas sobre la base de un conjunto de condiciones, guiando así a la/s persona/as que toma decisiones durante las operaciones de la organización.

**Para entrenar estos modelos/algoritmos:**

1. Es importante comprender el problema que se quiere solucionar o que es lo que se quiere aplicar.
2. Obtener un conjunto de datos para entrenar el modelo.
3. Hay que saber que modelo es el adecuado para solucionar el problema.
4. Se entrena un modelo supervisado o no supervisado con un histórico de datos.

Cuando entrenamos un modelo para llevar a cabo una prueba, es importante cuidar la información que se le suministra, es decir, debemos verificar si existen datos no validos o nulos, si las series de datos esta completa, etc.

[Ejemplos de aplicación en Wikipedia](https://es.wikipedia.org/wiki/An%C3%A1lisis_predictivo#Aplicaciones)

## Sobreajuste (Overfiting) y Subajuste (Underfiting) en los datos

La capacidad de generalización nos indica qué tan bien los conceptos aprendidos por un modelo de aprendizaje automático se aplican a ejemplos específicos que el modelo no vio cuando estaba aprendiendo. El objetivo de un buen modelo de aprendizaje automático es generalizar bien los datos de entrenamiento. Esto nos permite hacer predicciones en el futuro sobre los datos que el modelo nunca ha visto. Sobreajuste y subajuste son terminologías empleados en el aprendizaje automático para hacer referencia a qué tan bien un modelo generaliza nuevos datos ya que el ajuste excesivo y el ajuste insuficiente son las dos causas principales del rendimiento deficiente de los algoritmos de aprendizaje automático.

![](https://imgur.com/ujGH5cj.png)

### Sobreajunte (overfiting)

El sobreajuste hace referencia a un modelo que se sobre-entrena considerando cada mínimo detalle de los datos de entrenamiento. Esto significa que el ruido o las fluctuaciones aleatorias en los datos de entrenamiento son recogidos y aprendidos como conceptos por el modelo. El problema es que estos conceptos no se aplican a nuevos datos y tienen un impacto negativo en la capacidad de los modelos para generalizar.

Este sobre-entrenamiento suele darse con mayor probabilidad en modelos no lineales, por ello muchos de estos algoritmos de aprendizaje automático también incluyen parámetros o técnicas para limitar y restringir la cantidad de detalles que aprende. Algunos ejemplos de algoritmos no lineales son los siguientes:

- Decision Trees
- Naive Bayes
- Support Vector Machines
- Neural Networks

### Subajuste (underfiting)

El subajuste hace referencia a un modelo que no puede modelar los datos de entrenamiento ni generalizar a nuevos datos. Un modelo de aprendizaje automático insuficiente no es un modelo adecuado. Las estrategias para mitigar un ajuste insuficiente son variadas y dependen del contexto.

Como puede deducirse, el subajuste suele darse con mayor probabilidad en modelos lineales, como por ejemplo:

- Logistic Regression
- Linear Discriminant Analysis
- Perceptron

[Overfiting y Underfiting by DotCSV](https://www.youtube.com/watch?v=7-6X3DTt3R8)

## Regresión lineal simple y regresión lineal múltiple

El algoritmo de **regresión lineal** nos ayuda a conseguir tendencia en los datos, este es un algoritmo de tipo **supervisado** ya que debemos de usar datos previamente etiquetados.

En la regresión lineal generamos, a partir de los datos, una recta y es a partir de esta que podremos encontrar la tendencia o predicción.

Generalmente es importante tener en cuenta **varias dimensiones o variables** al considerar los datos que estamos suministrando al modelo, recordando siempre cuidar este set de **sobreajuste o subajuste**.

Cuando nuestro modelo considera más de dos variables el algoritmo de regresión que usamos se conoce como **Regresión Lineal Múltiple** y este trabaja sobre un sistema de referencia conocido como **hiperplano**.

Los algoritmos de regresión, tanto lineal como múltiple trabajan únicamente con datos de tipo cuantitativos.

## Regresión lineal simple con Scikit-Learn | Predicción de salarios en función de la experiencia

Dado un conjunto de puntos, el algoritmo de regresión establecerá un modelo para ajustar la relación de dependencia entre una característica específica independiente (un valor de la variable independiente x) y el valor “resultado”correspondiente (un valor de la variable dependiente y).

Al realizar nuestro modelo con datos de trabajadores con respectivas experiencias y salarios. El objetivo es saber si a medida que el trabajador tiene mas experiencia en un campo su salario aumenta acorde a esta.

Lo que hicimos fue:

- División de los datos
- Creación del modelo

--------
- [Notebook Regresión Lineal | Predicción de salarios en función de la experiencia](2.regresión-lineal-y-logistica/regresión_lineal_simple_scikitlearn.ipynb)
- [Dataset de salarios.csv](2.regresión-lineal-y-logistica/salarios.csv)

--------

[Fundamentos de la Regresión Lineal en Medium](https://medium.com/datos-y-ciencia/machine-learning-supervisado-fundamentos-de-la-regresi%C3%B3n-lineal-bbcb07fe7fd)

## Regresión logística con Scikit-Learn | Clasificar si un paciente tiene o no diabetes

La Regresión Logística es un método estadístico para predecir clases binarias. El resultado o variable objetivo es de naturaleza dicotómica. Dicotómica significa que solo hay dos clases posibles. Por ejemplo, se puede utilizar para problemas de detección de cáncer o calcular la probabilidad de que ocurra un evento.

Es decir que el algoritmo de Regresión Logística se utiliza para proyectos de **clasificación**, si queremos conocer si una persona vive o no el naufragio del Titanic, o si una acción de la bolsa de valores va a subir o no.

En este caso utilizamos queremos predecir si una person tendrá o no diabetes en bases a ciertos datos de personas que ya tienen diabetes como pueden ser embarazos, insulina, glucosa, presión arterial, edad, entre otras variables.

- Definición y división de datos
- Evaluación del modelo, utilizando matriz de confusión.

--------
- [Notebook de Regresión logística | Clasificar si un paciente tiene o no diabetes](2.regresión-lineal-y-logistica/regresión_logistica_scikitlearn_ipynb.ipynb)
- [Dataset de diabetes.csv](2.regresión-lineal-y-logistica/diabetes.csv)

--------

[Regresion Logistica - Teoria](https://aprendeia.com/regresion-logistica-multiple-machine-learning-teoria/)

# Árboles de decisión

## ¿Qué es un árbol de decisión?

Árboles de decisión: Es una forma gráfica y analítica de representar sucesos y posibilidades

![arbol](https://imgur.com/ZAKpg3P.png)

- Ventajas
  - Claridad de datos → Podemos ver claramente los caminos tomados
  - Tolerantes al ruido y valores faltantes → Aunque no es recomendable podemos hacer nuestro análisis con ruido (con cierto éxito)
  - Permite hacer predicciones a través de las reglas extraídas
- Desventajas
  - El criterio de división puede llegar a ser deficiente
  - Se puede llegar a un sobreajuste
  - Pueden aparecer ramas poco significativas
- Criterios de División de un árbol de decisión:
  - Ganancia de información
  - Crear pequeños árboles
- Optimización de nuestro modelo:
  - Evitar el sobreajuste
  - Selección de atributos → Seleccionar sólo los atributos relevantes para nuestro modelo
  - Campos nulos → Es mejor evitar los campos nulos

[Ampliando la teoria sobre arboles de decisión](https://aprendeia.com/arboles-de-decision-clasificacion-teoria-machine-learning/)

## Decision Tree en Scikit-Learn | Clasificar si un persona en el titanic muere o no

1. Comprendiendo nuestro data set para la creación de un árbol de decisión

Utilizaremos el dataset **[Titanic](3.decision-tree/titanic-train.csv)**, el cual tiene una lista de pasajeros que se encontraron en este con diferentes caracteristicas. El objetivo es saber si el pasajero pudo o no sobrevivir.

Se trabajó con un archivo previamente procesado, al cual le haremos un tratamiento simple y nos podamos enfocarn en el algoritmo en si.

Tiene variedad de datos y algo de complejidad al trabajar con ellos

2. Tratamiento de datos
   - Completaremos los valores nulos
   - Eliminamos la columnas que no consideramos necesarias.
   - Separamos las columnas categóricas de las numéricas

3. Entrenamiento del modelo de clasificación
   - Generamos nuestras variables de entrenamiento
   - Defino modelo

4. Evaluo el modelo
  - Utilizamos unicamente el Accuracy.
 
5. Visualización del árbol de decisión.
  - Exporto arbol de decision completo - [titanic.png](3.decision-tree/titanic.png)

--------
- [Notebook de Decision Tree en Scikit-Learn | Clasificar si un persona en el titanic muere o no](3.decision-tree/decision_trees_sklearn_clasificador.ipynb)
- [Dataset de titanic.csv](3.decision-tree/titanic-train.csv)

--------
# K-Means

# Aprendizaje profundo
