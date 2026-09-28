# Machine Learning Projects

Repositorio que reúne dos proyectos de aprendizaje automático desarrollados durante mis estudios de Ingeniería Informática en la Universidad Carlos III de Madrid (UC3M).

Los proyectos abordan dos tipos diferentes de problemas de aprendizaje automático: clasificación supervisada y clustering no supervisado. En ambos casos se realiza el proceso completo de análisis de los datos, preprocesamiento, entrenamiento, evaluación y comparación de distintos métodos.

## Proyectos

### Employee Attrition Prediction

Proyecto de clasificación cuyo objetivo es analizar los factores relacionados con la rotación de empleados y construir modelos capaces de predecir si un empleado abandonará la empresa.

El trabajo incluye análisis exploratorio de los datos, tratamiento de valores faltantes, análisis de variables, codificación de variables categóricas y tratamiento del desbalanceo de clases mediante SMOTE.

Se entrenan y comparan distintos modelos de clasificación:

- K-Nearest Neighbors (KNN)
- Decision Tree
- Logistic Regression
- Random Forest
- Support Vector Machine (SVM)
- LightGBM

También se utilizan técnicas de búsqueda de hiperparámetros mediante GridSearchCV y RandomizedSearchCV, empleando principalmente Balanced Accuracy para evaluar los modelos debido al desbalanceo de la variable objetivo.

El análisis permite comparar el comportamiento de los distintos algoritmos y estudiar el efecto del balanceo de clases y del ajuste de hiperparámetros sobre los resultados.

[Ver proyecto](./employee-attrition/)

---

### Seeds Classification

Proyecto de aprendizaje no supervisado centrado en estudiar la estructura interna de un conjunto de datos formado por distintas variedades de semillas a partir de sus características físicas.

Se comparan diferentes técnicas de clustering:

- K-Means
- Clustering jerárquico
- DBSCAN

Antes de realizar el clustering se estudian diferentes métodos de escalado y se utiliza PCA para reducir la dimensionalidad y facilitar la representación de los datos.

El número de clusters se analiza mediante el método del codo, dendrogramas y Silhouette Score. Finalmente, los grupos obtenidos se comparan con las clases reales mediante tablas de contingencia y el Adjusted Rand Index (ARI).

Los resultados muestran que los clusters encontrados presentan una relación clara con las variedades reales de semillas, a pesar de que esta información no se utiliza durante el proceso de clustering.

[Ver proyecto](./seeds-classification/)

## Tecnologías utilizadas

- Python
- Jupyter Notebook
- pandas
- NumPy
- scikit-learn
- imbalanced-learn
- LightGBM
- Matplotlib
- Seaborn
- SciPy

## Estructura del repositorio

```text
Machine-Learning-Projects/
│
├── employee-attrition/
│   └── employee_attrition_analysis.ipynb
│
├── seeds-classification/
│   └── seeds_classification.ipynb
│
└── README.md
```

Cada directorio contiene el notebook correspondiente con el desarrollo completo del análisis, incluyendo el preprocesamiento de los datos, entrenamiento o aplicación de los modelos, evaluación y visualización de resultados.

## Autor

Ana Claver Miranda  
Ingeniería Informática  
Universidad Carlos III de Madrid (UC3M)
