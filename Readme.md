# Sistemas de recomendadores - Practica 1 

Lluís Llull, Pablo Verde, Pablo Martín

---

[Kaggle](https://www.kaggle.com/competitions/recsys-filtrado-colaborativo-24-25/overview)

Los algoritmos probados se pueden dividir en tres clases principales, se explican a continuación estos grupos de algorítmos y los notebooks que incluyen sus experimentos.

1. Stadistics based: Modelos basados en estadísticos, principalmente medias, a modo de testeo y para tener referéncias.
    - Stadistics_based_algorithms.ipynb
2. MF based:
    - MF_based_algorithms.ipynb
    - NMF.ipynb
    - SVDpp.ipynb
3. Neural Networks / ML
    - KNN.ipynb
    - MachineLearning.ipynb
    - DeepLEarning.ipynb
    - NN-withMatrix.ipynb

Se definien una serie de conceptos para entender mejor la tabla de resultados:
- **rounded**: Se refiere a que los resultados de la predicción han sido redondeados
- **custom rounded**: Se refiere a que los resultados de la predicción han sido redondeados pero de forma personalizada. Es decir redondeando tan solo cunado dnos encontramos por debajo de 0.3 o por encima de 0.7
- **cold start**: Téncia para solucionar el problema de usuarios o ítems nuevos que no aparecen en el entrenamiento, si el usuario es nuevo, predice usando solo el sesgo del ítem. Si el ítem es nuevo, predice usando solo el sesgo del usuario. Si ambos son nuevos, usa la media global.
- **media fill**:  Téncia para solucionar el problema de usuarios o ítems nuevos que no aparecen en el entrenamiento, se rellenan los casos no existentes con usa la media global.


| Name  | Public score  |
|---|---|
| Mean rating  | 1.509  |
| Mean by users  | 1.309  |
| Mean by items | 1.548  |
| Agg means(0.4/0.4/0.2) | 1.547  |
|||
| MF v1  | 1.509  |
| MF v2 (con sesgos de items y users y cold start)  | 1.292  |
| MF v2 (con sesgos de items y users y cold start) custom_round | 1.273  |
| PMF lr = 0.005 |  1.262 |
| PMF lr =0.5 | 1.390  |
| PMF custom_round| 1.246  |
| NMF|  1.526 |
| NMF con media y rounded|  1.399 |
| SVDpp |  1.270 |
| SVDpp con media fill y rounded|  1.237 |
|||
| Knn |  Na |
| ML-RandomForest | 1.452 |
| ML-XGBoost |  1.429 |
| ML-NaiveBayes |  1.891  |
| DeepLearning |  1.259 |




### Lineas futuras
- Voting o ensemble learning
- MOdelo de NN que incluya una mayor regularización
