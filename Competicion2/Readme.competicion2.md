# Sistemas de recomendadores - Practica 2 

Lluís Llull, Pablo Verde, Pablo Martín

Todo el material se encuentra dentro de la carpeta *Competición 2*

---
[Link al repositorio](https://github.com/llull179/Recomendadores/settings)
[Kaggle](https://www.kaggle.com/competitions/recsys-filtrado-basado-en-contenido-2425/leaderboard)


Los algoritmos probados se pueden dividir en varias clases principales, se explican a continuación estos grupos de algoritmos y los notebooks que incluyen sus experimentos.

1. **Stadistics based**: Modelos basados en estadísticos, principalmente medias, a modo de testeo y para tener referencias.
    - metodos_estadisticos.ipynb
2. **MF based**: Algorítmos basados en *Matrix Factorization*. Son algoritmos que descomponen una matriz de interacciones usuario-ítem en dos matrices de factores latentes más pequeñas, permitiendo predecir valores desconocidos. Para ello se ha utilizado el algoritmo de SVD++.
    - SVDpp.ipynb
3. **Neural Networks / ML**: Estos son los modelos más utilizados desde el punto de vista de Machine Learning y Deep Learning. Para la mayoria de problemas en los que se utiliza la IA estos son modelos que funcionan bien y por lo que se ve también se adaptan relativamente bien a los sitemas de recomendación.
    - DL_categorizando_embedings.ipynb
    - DL_texto_embedings.iynb
    - arboles_Decision
4. **Transformers**: Se usan técnicas basadas en *Transformers* que utilizan NLP para realizar las predicciones en función de los textos proporcionados:
    - Modelos de clasificacion de sentimiento exsitentes
    - LoRa
5. **Ensemble**:
    - Voting.ipynb


    
| Name  | Public score  | Notebook|
|---|---|---|
| Mean rating  | 1.2587  |metodos_estadísticos|
| Mean by users  | 1.2028 |metodos_estadísticos|
| Mean by busines | 1.2589  |metodos_estadísticos|
| Agg means(0.4/0.4/0.2) | 1.0873 |metodos_estadísticos|
|---|---|---|
|SVDpp|1.024|SVDpp|
|---|---|---|
|XGBoost|0.7261|arboles_decision|
|---|---|---|
|Red neuronal limited|0.5166|DL|
|Red neuronal categorizando|0.4755|DL|
|Red neuronal categorizando rounded|0.4092|DL|
|Red neuronal texto|0.4755|DL|
|Red neuronal textorounded|0.4092|DL|
|---|---|---|
|bert-base-multilingual-uncased-sentiment|0.4067|trans_sentiment_clas|
|lora-bert-base-multilingual-uncased-sentiment|0.2918|lora_trans_sentiment_clas|
|---|---|---|
|mean ensemble|0.3507|Voting|
|voting ensemble|0.3507|Voting|
