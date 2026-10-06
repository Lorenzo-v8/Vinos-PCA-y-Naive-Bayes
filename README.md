# Vinos-PCA-y-Naive-Bayes
Proyecto de ciencia de datos que aplica PCA al dataset Wine para visualizar y entender la estructura de 13 variables químicas de vinos de tres cultivares distintos. Además compara un clasificador Bayes ingenuo (Gaussian Naive Bayes) entrenado con las 13 variables originales contra uno entrenado solo con 2 componentes principales.
Dataset
Fuente: Wine dataset (UCI Machine Learning Repository)
Tamaño: 178 muestras, 13 variables numéricas, sin valores nulos
Objetivo: Class, el cultivar de origen del vino (3 clases)
Variables: alcohol, ácido málico, ceniza, alcalinidad de la ceniza, magnesio, fenoles totales, flavonoides, fenoles no flavonoides, proantocianinas, intensidad del color, matiz, OD280/OD315 y prolina
Metodología
Exploración: forma del dataset, tipos, nulos, estadísticas descriptivas y distribución de clases.
Estandarización con StandardScaler. Es necesaria porque las variables están en escalas muy distintas (por ejemplo, prolina vs. matiz) y PCA es sensible a la escala.
Matriz de correlación de las variables originales, para ver qué redundancia justifica PCA.
PCA completo (13 componentes) y scree plot con varianza individual y acumulada (referencia al 80%).
PCA con 2 componentes y gráfico de dispersión PC1 vs. PC2 coloreado por clase.
Interpretación de las componentes: loadings (tabla y mapa de calor) y biplot.
Clasificación con Bayes ingenuo, con el mismo split estratificado 80/20 (random_state=42) en ambos enfoques:
A: 13 variables originales estandarizadas
B: solo PC1 y PC2
Fronteras de decisión de Bayes ingenuo sobre el plano PC1-PC2, graficadas junto a los puntos del conjunto de test.
Resultados
<!-- Completar con los outputs del notebook -->
Métrica	Valor
Varianza explicada PC1	[X]%
Varianza explicada PC2	[X]%
Varianza acumulada PC1 + PC2	[X]%
Componentes necesarias para 80% de varianza	[X]
Modelo	Accuracy (test)
Naive Bayes, 13 variables originales	[X]
Naive Bayes, PC1 + PC2	[X]

Variables con mayor peso (loadings):

PC1: [variables]
PC2: [variables]
Conclusiones
<!-- Cuánta varianza resumen 2 componentes y qué tan bien separan las 3 clases visualmente -->
<!-- Qué representa cada eje según los loadings -->
<!-- Comparación de accuracy entre los dos modelos y qué implica -->
Limitaciones
Dataset pequeño (178 muestras): con un test del 20% (36 muestras), cada error mueve mucho la accuracy, así que las diferencias entre modelos pueden no ser significativas.
El escalador y el PCA se ajustaron con todo el dataset antes de hacer el split. Para una evaluación estricta conviene ajustarlos solo con train (por ejemplo, dentro de un Pipeline).
Un único split; no se usó validación cruzada.
Bayes ingenuo asume independencia entre variables, y en este dataset hay variables correlacionadas (por ejemplo, flavonoides y fenoles totales).
Posibles mejoras
Usar Pipeline y validación cruzada estratificada para una comparación más robusta.
Barrido de cantidad de componentes (1 a 13) y accuracy en cada caso.
Comparar con regresión logística, SVM o random forest.
Probar LDA como alternativa supervisada de reducción de dimensionalidad.
Cómo reproducirlo
Descargar Wine.csv y subirlo al entorno (Google Colab o Jupyter).
Ejecutar las celdas del notebook en orden.

Librerías: pandas, numpy, matplotlib, seaborn, scikit-learn

Autor

Lorenzo Ciprés, estudiante de Ciencia de Datos (Universidad Nacional Guillermo Brown).
