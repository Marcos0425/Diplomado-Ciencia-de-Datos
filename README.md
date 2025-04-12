# Proyecto de Aprendizaje profundo: Predicción de Ondas de Calor usando LSTM
Objetivo: El objetivo de este proyecto es predecir la ocurrencia de ondas de calor utilizando un modelo de red neuronal recurrente (LSTM). Para ello, se ha trabajado con un conjunto de datos meteorológicos, específicamente con la temperatura máxima, humedad y velocidad del viento, con el fin de identificar patrones asociados a las ondas de calor.

Pasos del Proyecto:

Carga de Datos:

Se cargaron los datos del archivo weather_data.csv y se filtraron las columnas relevantes en la práctica como: temp_max, humidity y wind_speed.

Para reducir el tamaño del conjunto de datos, se seleccionaron 10,000 muestras aleatorias. El Dataset original tenía más de 5 millones de registros.

Preprocesamiento:

Se convirtió la columna dt_txt en formato datetime para facilitar la manipulación de las fechas.

Se creó una nueva columna de etiquetas (heat_wave) para identificar la presencia de ondas de calor, basadas en un umbral de temperatura máxima (35°C).

Escalado de Datos:

Se normalizaron las variables (temp_max, humidity, wind_speed) utilizando MinMaxScaler.

Creación de Secuencias:

Se generaron secuencias temporales de 30 días como entrada para el modelo LSTM, con las etiquetas correspondientes que indican si hubo una onda de calor en los siguientes días.

Modelo LSTM:

Se construyó un modelo LSTM con dos capas LSTM y capas de Dropout para evitar el sobreajuste.

El modelo fue compilado con el optimizador Adam y la función de pérdida binary_crossentropy debido a que se trata de una clasificación binaria (predecir la ocurrencia o no de una onda de calor).

Entrenamiento y Evaluación:

El modelo fue entrenado durante 10 épocas con un tamaño de batch de 32. Se visualizó la precisión y la pérdida durante el entrenamiento.

El rendimiento del modelo se evaluó en un conjunto de prueba.
