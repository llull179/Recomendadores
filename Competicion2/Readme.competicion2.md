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
    - LLM_trans_sentiment_clas.ipynb
    - LLM_lora_trans_sentiment_clas.ipynb

5. **Ensemble**: Aquí se intentan combinar diferentes modelos para obtener una mayor robustez y resultados.
    - Voting.ipynb


    
| Name  | Public score  | Notebook|
|---|---|---|
| Mean rating  | 1.2587  |metodos_estadísticos|
| Mean by users  | 1.2028 |metodos_estadísticos|
| Mean by busines | 1.2589  |metodos_estadísticos|
| Mean user & busines combined | 1.0873 |metodos_estadísticos|
|---|---|---|
|SVDpp|1.024|SVDpp|
|---|---|---|
|XGBoost variables simples|0.7293|arboles_decision|
|XGBoost variables simples + ciudad + categories|0.7266|arboles_decision|
|XGBoost variables simples + atributes|0.7261|arboles_decision|
|---|---|---|
|Red neuronal limited|0.5166|DL|
|Red neuronal categorizando|0.4755|DL|
|Red neuronal categorizando rounded|0.4092|DL|
|Red neuronal texto|0.4755|DL|
|Red neuronal texto rounded|0.4092|DL|
|---|---|---|
|Aprendizaje automático ridge|0.6479|ML|
|Aprendizaje automático ridge rounded|0.6194|ML|
|---|---|---|
|bert-base-multilingual-uncased-sentiment|0.4067|trans_sentiment_clas|
|lora-bert-base-multilingual-uncased-sentiment|0.2918|lora_trans_sentiment_clas|
|---|---|---|
|mean ensemble|0.3507|Voting|
|voting ensemble|0.3507|Voting|


## Conclusiones

- Vemos que los *Transformers* y técnicas que atacan NLP es lo que mejor funciona, ya que los datos de texto parecen ser los más importantes. Aun así Fine-Tunear un modelo concreto es muy costoso, por eso LoRa cobra sentido.
- LoRa da unos resultados excelentes, el problema es que tanto entrenar como realizar inferéncia es muy costoso. Por lo tanto, en la vida real dependiendo del caso a aplicar podría no ser útil.
- Los métodos de ensemble utilizados no aportan más valor al modelo ya existente. Estaría bien probar con otras técnicas de ensemble más elaboradas, aun así para esto proyecto se han descartado por el coste de realizar inferencia de algunos modelos a todo el conjunto de trian.
- Los modelos basados en MF carecen de sentido y son muy débiles
- Al realizar los embedings del texto, horarios o categorias ha constatado la gran cantidad de recursos en cuanto a RAM o GPU que se necesita en este enfoque. Estos embedings son importantes sobre todo en la parte de DL y ML, ya que se ve una gran mejora al utilizar estos vectores multidimensionales.

## Lineas futuras

- Redes neuronales basadas en grafos a partir de los amigos.
- Ensemble learning más elaborado (aprovechar el modelo de LoRa pero incluir los otros datos).
- Realizar Grid Search más profundo de las Neural Networks
- Provar otras arquitectura como AutoEncoders