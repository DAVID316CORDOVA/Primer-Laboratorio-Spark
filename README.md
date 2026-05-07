# LabSpark00 - Introduccion a Apache Spark con PySpark

## Pontificia Universidad Javeriana
**Materia:** Procesamiento de Alto Volumen de Datos  
**Autor:** Felix David Cordova Garcia  
**Fecha:** Abril - Mayo 2026

---

## Descripcion

Laboratorio introductorio de Apache Spark ejecutado sobre un cluster con Hadoop HDFS. El notebook cubre desde la creacion y manipulacion de RDDs hasta el uso de DataFrames para analisis de datos, utilizando PySpark como interfaz de programacion.

## Contenido del notebook

**1. Configuracion del entorno**  
Creacion de la sesion de Spark (SparkSession), contexto de Spark (SparkContext) y contexto SQL. Se utilizan las librerias findspark, pyspark, pandas, numpy, seaborn y matplotlib.

**2. Resilient Distributed Datasets (RDD)**  
- Creacion de RDDs vacios, con datos mixtos y con rangos numericos.
- Control de particiones con getNumPartitions(), repartition() y coalesce().
- Visualizacion de la distribucion interna de datos con glom().
- Ordenamiento con takeOrdered() y funciones lambda.
- Almacenamiento de RDDs en disco con saveAsTextFile().
- Inspeccion del plan de ejecucion (DAG) con toDebugString().

**3. Operaciones sobre RDDs**  
- Reduce para suma y producto de elementos.
- Transformaciones con map(), flatMap() y filter().
- Funciones definidas por el usuario (UDF) para filtrado y transformacion de texto.
- Conteo de frecuencias con countByValue().

**4. Interaccion con HDFS**  
- Listado de archivos en el sistema de archivos distribuido.
- Carga del dataset Titanic (test.csv y train.csv) desde HDFS.
- Procesamiento tipo MapReduce: split, map con tupla (valor, 1) y reduceByKey para conteo de ocurrencias.
- Parseo de CSV y seleccion de campos especificos.

**5. DataFrames en Spark**  
- Creacion manual de un DataFrame con createDataFrame().
- Carga del dataset Wine Quality Red desde HDFS con lectura de cabecera y delimitador.
- Casting de tipos de datos (String a Double, Float, Integer).
- Estadisticas descriptivas con describe().
- Seleccion de columnas, ordenamiento con orderBy().
- Deteccion de valores nulos e imposibles.
- Slicing de filas con limit() y de columnas por indice.
- Filtros con condiciones AND, OR, NOT, LIKE y comparaciones.
- Conversion a Pandas con toPandas().

## Datasets utilizados

| Dataset | Fuente | Ubicacion HDFS |
|---------|--------|----------------|
| Titanic (test.csv, train.csv) | Kaggle | /csv/titanic/ |
| Wine Quality Red | UCI ML Repository | /csv/winequality-red.csv |

## Tecnologias

- Python 3
- Apache Spark (PySpark)
- Apache Hadoop (HDFS)
- Jupyter Notebook
- Bibliotecas: pandas, numpy, seaborn, matplotlib

## Como ejecutar

1. Tener un cluster con Hadoop y Spark configurado.
2. Verificar que los datasets esten cargados en HDFS en las rutas indicadas.
3. Abrir el notebook en Jupyter y ejecutar las celdas en orden secuencial.
4. La sesion de Spark se crea en la segunda celda; todas las demas dependen de ella.

## Resultados principales

- Se verifico el funcionamiento de RDDs como estructura base de Spark, incluyendo su particionamiento y persistencia.
- Se demostro que las operaciones MapReduce clasicas se implementan de forma mas compacta con la API de Spark.
- Se cargo y proceso un dataset real desde HDFS, aplicando casting de tipos, estadisticas descriptivas y filtros combinados sobre DataFrames.
- Se confirmo que Spark permite transitar entre procesamiento de bajo nivel (RDDs) y analisis estructurado (DataFrames) segun la necesidad del problema.
