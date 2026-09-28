# Seeds Classification

Proyecto de aprendizaje automático no supervisado centrado en analizar la estructura de un conjunto de datos de semillas a partir de sus características físicas.

El objetivo es comprobar si diferentes técnicas de clustering son capaces de identificar agrupaciones naturales en los datos y estudiar posteriormente su relación con las variedades reales de semillas.

## Desarrollo

El proyecto comienza con el análisis y preparación de los datos. Antes de aplicar los algoritmos de clustering se comparan diferentes métodos de escalado y se utiliza Principal Component Analysis (PCA) para reducir la dimensionalidad y facilitar la representación de los datos.

Se comparan tres técnicas principales de clustering:

- K-Means
- Clustering jerárquico
- DBSCAN

La selección de las configuraciones se realiza utilizando diferentes herramientas como el método del codo, dendrogramas y Silhouette Score.

## Preprocesamiento y PCA

Se estudian tres métodos de escalado:

- StandardScaler
- MinMaxScaler
- RobustScaler

Al aplicar PCA, los dos primeros componentes conservan aproximadamente:

| Escalado | Varianza explicada |
| --- | ---: |
| StandardScaler | 88,98 % |
| MinMaxScaler | **91,81 %** |
| RobustScaler | 86,91 % |

MinMaxScaler presenta la mayor proporción de varianza conservada en los dos primeros componentes principales.

## K-Means

Se estudian diferentes valores de `k` mediante el método del codo y Silhouette Score.

El análisis posterior se realiza con **k = 3**, permitiendo obtener tres grupos que pueden compararse con las tres clases originales del conjunto de datos.

Para esta configuración se obtiene:

```text
Silhouette Score = 0,503
```

## Clustering jerárquico

También se analiza el comportamiento del clustering jerárquico utilizando diferentes métodos de enlace:

- Average
- Complete
- Ward

Los dendrogramas permiten estudiar visualmente la estructura de los datos y la posible elección del número de clusters.

Para la solución final de tres clusters se obtiene un Silhouette Score de aproximadamente:

```text
0,471
```

## DBSCAN

Finalmente se utiliza DBSCAN para estudiar la existencia de clusters basados en densidad y detectar posibles observaciones consideradas ruido.

La configuración seleccionada es:

```text
eps = 0.12
min_samples = 4
```

Con ella se obtienen:

```text
Clusters encontrados: 3
Outliers encontrados: 18
Silhouette Score: 0,353
```

## Comparación de métodos

Los resultados obtenidos para las configuraciones finales son:

| Método | Silhouette Score |
| --- | ---: |
| K-Means (k=3) | **0,503** |
| Clustering jerárquico (3 clusters) | 0,471 |
| DBSCAN (eps=0.12, min_samples=4) | 0,353 |

Además de estudiar la calidad interna de los clusters, se comparan las agrupaciones obtenidas mediante K-Means con las clases originales del conjunto de datos.

El **Adjusted Rand Index (ARI)** obtenido es:

```text
ARI = 0.705
```

Este resultado muestra una correspondencia considerable entre los grupos encontrados de forma no supervisada y las variedades reales de semillas.

## Tecnologías

- Python
- Jupyter Notebook
- pandas
- NumPy
- scikit-learn
- SciPy
- Matplotlib
- Seaborn

## Archivo principal

El análisis completo se encuentra en:

```text
seeds_classification.ipynb
```

El notebook contiene el preprocesamiento, análisis mediante PCA, desarrollo de los diferentes métodos de clustering, selección de parámetros, visualizaciones y comparación de resultados.

## Autor

Ana Claver Miranda  
Ingeniería Informática  
Universidad Carlos III de Madrid (UC3M)
