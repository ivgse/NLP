# NLP

Desarrollo de un sistema para clasificar reseñas de películas y detectar las reseñas negativas de forma automática..

En el analisis explotario, se usan gráficas para ver el número de peliculas y reseñas por año. Para ver la distribución del número de reseñas por pelicula, utilizamos histogramas y también KDE(Kernel Density Estimator). Despues, graficamos la distribución de puntuaciones tanto en el conjunto de prueba como en el conjunto de entrenamiento para confirmar que son similares en ambos. Explorando un poco más, también hacemos graficos para ver la distribución de reseñas positivas y negativas en ambos datasets, confirmarmos que la distribución es similar.

Para evaluar el modelo, se utiliza una función personalizada que calcula Accuracy y calcula y grafica 3 metricas F1, ROC y PRC.

Para el preprocesamiento, primero se normalizan los datos para que sean procesados correctamente por el modelo y evitar ruido. Este paso se hace mediante lematización e ingenieria de caracteristicas.

Para la creación de modelos, se utiliza un modelo dummy como referencia. Un modelo con NLTK, TF-IDF y LR. Un modelo con spaCy, TF-IDF y LR. Estos ultimos 2 tienen metricas practicamente iguales y bastante buenas. Otro modelo con spaCy, TF-IDF y LGBMClassifier, el cual tuvo las mejores puntuaciones.

Se probo tambien un modelo con BERT, aunque solo con 200 reseñas por la limitación de capacidad computacional. Este modelo no tiee tantas probabilidades de clasificar correctamente, la hipotesis es que se necesita entrenar con un conjunto mayor para aprender correctamente, pero esto no es posible con los recursos actuales.

Todos los modelos se probaron en reseñas nuevas escritas por mí. De todos los modelos el mejor y el que se selecciona para analisis real de sentimiento es el hecho con spaCy, TF-IDF y LGBMClassifier.
