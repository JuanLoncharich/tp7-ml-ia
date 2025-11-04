# Ejercicio 7 – Validación cruzada (k-fold) con árbol de decisión

## a) Creación de folds
Se implementó la función `create_folds()`, que divide aleatoriamente el dataset en *k = 10* subconjuntos de tamaño similar.  
Cada iteración usa 9 folds para entrenamiento y 1 fold para prueba, repitiendo el proceso hasta cubrir todos.

## b) Entrenamiento y evaluación
Se implementó la función `cross_validation()`, que entrena un modelo **rpart** en cada fold y calcula las métricas:

- **Accuracy** = (TP + TN) / Total  
- **Precision** = TP / (TP + FP)  
- **Sensitivity (Recall)** = TP / (TP + FN)  
- **Specificity** = TN / (TN + FP)

El modelo se entrenó con la siguiente fórmula:

inclinacion_peligrosa ~ altura + circ_tronco_cm + lat + long + seccion + especie

ruby
Copy code

## c) Resultados obtenidos

| Fold | Accuracy | Precision | Sensitivity | Specificity |
|:----:|:---------:|:----------:|:-------------:|:-------------:|
| 1 | 0.883 | NA | 0 | 1 |
| 2 | 0.881 | NA | 0 | 1 |
| 3 | 0.892 | NA | 0 | 1 |
| 4 | 0.896 | NA | 0 | 1 |
| 5 | 0.886 | NA | 0 | 1 |
| 6 | 0.884 | NA | 0 | 1 |
| 7 | 0.878 | NA | 0 | 1 |
| 8 | 0.893 | NA | 0 | 1 |
| 9 | 0.899 | NA | 0 | 1 |
| 10 | 0.883 | NA | 0 | 1 |

**Promedios (k = 10):**

| Métrica | Media | Desvío estándar |
|----------|--------|----------------|
| Accuracy | 0.8879 | 0.0073 |
| Precision | NA | — |
| Sensitivity | 0 | 0 |
| Specificity | 1 | 0 |

## d) Interpretación
- El modelo obtiene una **exactitud alta (~88.8%)**, pero **no predice correctamente ningún caso positivo** (Sensitivity = 0).  
- Esto sugiere que el árbol entrenado tiende a **clasificar todo como clase 0 (no peligrosa)**, probablemente por el **desbalance severo** del dataset (muchos más árboles no peligrosos que peligrosos).  
- Aunque el Accuracy parece bueno, el modelo **no tiene capacidad de detección de riesgo real**, por lo que se debe ajustar (por ejemplo, balancear clases o ajustar parámetros de `rpart`).
