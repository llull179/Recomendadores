# Sistemas de recomendadores - Practica 1 

Lluís Llull, Pablo Verde, Pablo Martín

---
[Link al repositorio](https://github.com/llull179/Recomendadores/settings)
[Kaggle](https://www.kaggle.com/competitions/recsys-filtrado-colaborativo-24-25/overview)

Los algoritmos probados se pueden dividir en tres clases principales, se explican a continuación estos grupos de algoritmos y los notebooks que incluyen sus experimentos.

1. **Stadistics based**: Modelos basados en estadísticos, principalmente medias, a modo de testeo y para tener referencias.
    - Stadistics_based_algorithms.ipynb
2. **MF based**: Algorítmos basados en *Matrix Factorization*. Son algoritmos que descomponen una matriz de interacciones usuario-ítem en dos matrices de factores latentes más pequeñas, permitiendo predecir valores desconocidos. Los algoritmos incluidos son MF, PMF, NMF, SVD, SVD++.
    - MF_based_algorithms.ipynb
    - NMF.ipynb
    - SVDpp.ipynb
3. **Neural Networks / ML**: (rellenar explicacion)
    - KNN.ipynb
    - MachineLearning.ipynb
    - DeepLEarning.ipynb
    - NN-withMatrix.ipynb

Se definen una serie de conceptos para entender mejor la tabla de resultados:
- **rounded**: Se refiere a que los resultados de la predicción han sido redondeados
- **custom rounded**: Se refiere a que los resultados de la predicción han sido redondeados pero de forma personalizada. Es decir, redondeando tan solo cunado nos encontramos por debajo de 0.3 o por encima de 0.7
- **cold start**: Técnica para solucionar el problema de usuarios o ítems nuevos que no aparecen en el entrenamiento, si el usuario es nuevo, predice usando solo el sesgo del ítem. Si el ítem es nuevo, predice usando solo el sesgo del usuario. Si ambos son nuevos, usa la media global.
- **media fill**:  Técnica para solucionar el problema de usuarios o ítems nuevos que no aparecen en el entrenamiento, se rellenan los casos no existentes con la media global.ios o ítems nuevos que no aparecen en el entrenamiento, se rellenan los casos no existentes con la media global.
- Todas las predicciones se han acotado entre 1 y 10.


## Tabla resultados

| Name  | Public score  | Notebook|
|---|---|---|
| Mean rating  | 1.509  |Stadistics_based_algorithms|
| Mean by users  | 1.309  |Stadistics_based_algorithms|
| Mean by items | 1.548  |Stadistics_based_algorithms|
| Agg means(0.4/0.4/0.2) | 1.547  |Stadistics_based_algorithms|
||||
| MF v1  | 1.509  |MF_based_algorithms|
| MF v2 (con sesgos de items y users y cold start)  | 1.292  |MF_based_algorithms|
| MF v2 (con sesgos de items y users y cold start) custom_round | 1.273  |MF_based_algorithms|
| PMF lr = 0.005 |  1.262 |MF_based_algorithms|
| PMF lr =0.5 | 1.390  |MF_based_algorithms|
| PMF custom_round| 1.246  |MF_based_algorithms|
| NMF|  1.526 |NMF|
| NMF con media y rounded|  1.399 |NMF|
| SVDpp |  1.270 |SVDpp|
| SVDpp con media fill y rounded|  1.237 |SVDpp|
||||
| Knn |  Na |KNN|
| ML-RandomForest | 1.452 |MachineLearning|
| ML-XGBoost |  1.429 |MachineLearning|
| ML-NaiveBayes |  1.891  |MachineLearning|
| DeepLearning |  1.259 |DeepLEarning|
| DeepLearning  media fill|  1.399 |DeepLEarning|

## Conclusiones
- Destaca como el modelo de Deep learning funciona mejor sin rellenar la media, puede ser que el propio modelo busque un valor por defecto óptimo o un patrón útil a la hora de predecir un ítem o usuario que no existe en el conjunto de train.
- Por simples que parezcan, los métodos basados en estadísticos, por ejemplo la media, no da malos resultados. Esto es importante tenerlo en consideración, ya si bien es cierto que no es una técnica robusta, es una técnica que nos puede servir para terminar de afinar diferentes modelos, como en el caso de no tener los ítems o usuarios que existen.
- SVD++ ha sido el mejor modelo obtenido con un score de 1.270


### Líneas futuras
- Voting o ensemble learning
- Modelo de NN que incluya una mayor regularización
- BNMF
