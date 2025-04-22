# Sistemas de recomendadores - Practica 2 

Lluís Llull, Pablo Verde, Pablo Martín

Todo el material se encuentra dentro de la carpeta *Competición 2*

---
[Link al repositorio](https://github.com/llull179/Recomendadores/settings)
[Kaggle](https://www.kaggle.com/competitions/recsys-filtrado-basado-en-contenido-2425/leaderboard)


Los algoritmos probados se pueden dividir en varias clases principales, se explican a continuación estos grupos de algoritmos y los notebooks que incluyen sus experimentos.

1. **Stadistics based**: Modelos basados en estadísticos, principalmente medias, a modo de testeo y para tener referencias.
    - Stadistics_based_algorithms.ipynb
2. **MF based**: Algorítmos basados en *Matrix Factorization*. Son algoritmos que descomponen una matriz de interacciones usuario-ítem en dos matrices de factores latentes más pequeñas, permitiendo predecir valores desconocidos. Los algoritmos incluidos son MF, PMF, NMF, SVD, SVD++.
    - MF_based_algorithms.ipynb
    - NMF.ipynb
    - SVDpp.ipynb
3. **Neural Networks / ML**: Estos son los modelos más utilizados desde el punto de vista de Machine Learning y Deep Learning. Para la mayoria de problemas en los que se utiliza la IA estos son modelos que funcionan bien y por lo que se ve también se adaptan relativamente bien a los sitemas de recomendación.
    - KNN.ipynb
    - MachineLearning.ipynb
    - DeepLEarning.ipynb
    - NN-withMatrix.ipynb
4. **Trasnformers**: Se usan técnicas basadas en *Transformers* que utilizan NLP para realizar las predicciones en función de los textos proporcionados:
    - Modelos de clasificacion de sentimiento exsitentes
    - LoRa


    
| Name  | Public score  | Notebook|
|---|---|---|
| Mean rating  | 1.2587  |metodos_estadísticos|
| Mean by users  | 1.2028 |metodos_estadísticos|
| Mean by busines | 1.2589  |metodos_estadísticos|
| Agg means(0.4/0.4/0.2) | 1.0873 |metodos_estadísticos|
|---|---|---|
|Red neuronal limited|0.5166|DL|
|Red neuronal|0.4755|DL|
|Red neuronal rounded|0.4092|DL|
|---|---|---|
|bert-base-multilingual-uncased-sentiment|0.4067|trans_sentiment_clas|
|lora bert-base-multilingual-uncased-sentiment|0|lora_trans_sentiment_clas|