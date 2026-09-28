# Employee Attrition Prediction

Proyecto de aprendizaje automático centrado en el análisis y predicción de la rotación de empleados (*employee attrition*).

El objetivo es estudiar qué información puede utilizarse para predecir si un empleado abandonará la empresa y comparar distintos algoritmos de clasificación para este problema.

## Desarrollo

El proyecto comienza con un análisis exploratorio del conjunto de datos, estudiando las variables disponibles, valores faltantes, variables constantes, cardinalidad de las variables categóricas, correlaciones y distribución de la variable objetivo.

Al tratarse de un problema con clases desbalanceadas, se utiliza una división estratificada de los datos y se toma **Balanced Accuracy** como una de las principales métricas de evaluación.

El proceso incluye:

- Análisis exploratorio de los datos.
- Preparación y transformación de variables.
- Análisis del desbalanceo de clases.
- División estratificada en entrenamiento y prueba.
- Validación cruzada.
- Aplicación de SMOTE.
- Entrenamiento de distintos algoritmos de clasificación.
- Búsqueda y ajuste de hiperparámetros.
- Comparación de los resultados obtenidos.

## Modelos evaluados

Durante el proyecto se prueban diferentes algoritmos:

- K-Nearest Neighbors (KNN)
- Decision Tree
- Logistic Regression
- Random Forest
- Support Vector Machine (SVM)
- LightGBM

Para algunos modelos se comparan distintas configuraciones, incluyendo versiones con y sin SMOTE y diferentes estrategias de ajuste de hiperparámetros mediante GridSearchCV y RandomizedSearchCV.

## Resultados

Las distintas configuraciones muestran diferencias importantes en su capacidad para tratar el desbalanceo existente en los datos.

Como referencia, un `DummyClassifier` obtiene una Balanced Accuracy de **0,500**, mientras que las configuraciones ajustadas de los modelos consiguen mejorar claramente este resultado.

Entre los resultados obtenidos destacan:

| Modelo | Balanced Accuracy |
| --- | ---: |
| DummyClassifier | 0,500 |
| Regresión logística sin GridSearch | 0,712 |
| Árbol de decisión sin GridSearch | 0,784 |
| Random Forest + GridSearch | 0,794 |
| LightGBM con SMOTE | 0,841 |
| KNN con GridSearch | 0,888 |
| KNN con SMOTE + GridSearch | 0,892 |
| LightGBM con ajuste del umbral a 0,3 | **0,897** |

Los experimentos muestran además la importancia de no limitar la evaluación al *accuracy* convencional cuando existe un desbalanceo entre las clases.

## Tecnologías

- Python
- Jupyter Notebook
- pandas
- NumPy
- scikit-learn
- imbalanced-learn
- LightGBM
- Matplotlib
- Seaborn

## Archivo principal

El desarrollo completo del proyecto se encuentra en:

```text
employee_attrition_analysis.ipynb
```

El notebook contiene el análisis exploratorio, preprocesamiento, entrenamiento de los modelos, búsqueda de hiperparámetros y evaluación de resultados.

## Autor

Ana Claver Miranda  
Ingeniería Informática  
Universidad Carlos III de Madrid (UC3M)
