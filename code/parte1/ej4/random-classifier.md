# Ejercicio 4 – Clasificador Aleatorio

## a) Generación de probabilidades aleatorias
Se implementó una función `add_random_probs()` que agrega una columna `prediction_prob` con valores aleatorios uniformes entre 0 y 1 para cada observación.

## b) Clasificador aleatorio
La función `random_classifier()` genera una columna `prediction_class` aplicando la regla:

if prediction_prob > 0.5 → 1
else → 0

## c) Aplicación sobre el dataset de validación
El clasificador se aplicó al archivo `arbolado-mendoza-dataset-validation.csv`, produciendo predicciones aleatorias para cada árbol.

## d) Evaluación y matriz de confusión

| Tipo | Descripción | Valor |
|------|--------------|------:|
| **TP** | Árboles peligrosos correctamente predichos como peligrosos | 1442 |
| **TN** | Árboles no peligrosos correctamente predichos como no peligrosos | 11286 |
| **FP** | Árboles no peligrosos predichos incorrectamente como peligrosos | 11382 |
| **FN** | Árboles peligrosos predichos incorrectamente como no peligrosos | 1419 |
| **Total (n)** |  | 25529 |

### Matriz de confusión

|               | **Predicted: NO** | **Predicted: YES** |
|----------------|-------------------|--------------------|
| **Actual: NO** | 11286 (TN)        | 11382 (FP)         |
| **Actual: YES**| 1419 (FN)         | 1442 (TP)          |
