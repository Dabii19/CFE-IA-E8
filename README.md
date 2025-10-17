# CFE-IA-E8

# Clasificación Logística de Rumores

## Este proyecto utiliza un conjunto de publicaciones y metadatos para predecir si un texto corresponde o no a un rumor, aplicando técnicas de procesamiento de texto y un modelo de Regresión Logística.

# Objetivo

## Entrenar un modelo de clasificación que determine si un texto es un rumor (1) o no rumor (0), en función del contenido del texto y algunos datos complementarios, generando un archivo final con las predicciones.

# Datos

## Variables utilizadas en el modelo:

### text: contenido textual de la publicación o noticia.

### is_rumor: variable objetivo (0 = no es rumor, 1 = es rumor).

### user.handle: identificador del usuario que publicó el texto (rellenado con “unknown” en caso de valores faltantes).

# Variables eliminadas:

### topic: no aportaba información relevante al modelo y fue descartada.

# Pasos realizados
### Carga y preprocesamiento de datos

### Se cargó el dataset principal dataset_train_val.csv.

### Se revisó la estructura del dataset con df.info() y se identificaron valores nulos.

### Se eliminaron columnas irrelevantes (topic).

### Se reemplazaron los valores faltantes:

### is_rumor → se completó con 0.

### user.handle → se completó con 'unknown'.

# Preparación del modelo

### Se separaron los datos en entrenamiento y prueba con train_test_split (10% para prueba).

### Se aplicó un CountVectorizer para transformar el texto en una matriz de conteo de palabras (representación numérica del lenguaje natural).

# Entrenamiento del modelo de Regresión Logística

### Se entrenó un modelo LogisticRegression() con las variables vectorizadas (text).

### Se generaron predicciones sobre el conjunto de prueba.

### Se calculó la exactitud del modelo (accuracy_score), expresada como porcentaje de éxito en la clasificación.

# Predicciones y generación de submission

### Se cargó el conjunto de datos sin etiquetas (dataset_test_sin_etiqueta.csv).

### Se aplicó el mismo preprocesamiento: eliminación de la columna topic y relleno de valores nulos en user.handle.

### Se transformaron los textos con el mismo vectorizador utilizado en el entrenamiento.

### Se generaron las predicciones de rumor/no rumor.

### Se creó el archivo de salida datastet_test.csv con las columnas:
### - ID
### - etiqueta

# Resultados

### El modelo logra un porcentaje de acierto competitivo en la clasificación de rumores, mostrando una buena capacidad para distinguir entre texto verídico y rumores según su contenido.

### El porcentaje promedio de éxito fue de  91.6225900017062 %
