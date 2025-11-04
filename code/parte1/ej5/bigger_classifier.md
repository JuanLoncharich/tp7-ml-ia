# Ejercicio 5 – Clasificador por clase mayoritaria

## a) Implementación
Se desarrolló la función **`biggerclass_classifier()`**, que identifica la clase mayoritaria en el dataset (`inclinacion_peligrosa`) y asigna ese valor a todas las observaciones en una nueva columna llamada `prediction_class`.

En este caso, la clase mayoritaria detectada fue:

Clase mayoritaria: 0 (árbol no peligroso)

# b) Resultados y matriz de confusión

| Tipo | Descripción | Valor |
|------|--------------|------:|
| **TP** | Árboles peligrosos correctamente predichos como peligrosos | 0 |
| **TN** | Árboles no peligrosos correctamente predichos como no peligrosos | 5665 |
| **FP** | Árboles no peligrosos predichos incorrectamente como peligrosos | 0 |
| **FN** | Árboles peligrosos predichos incorrectamente como no peligrosos | 718 |
| **Total (n)** |  | 6383 |

### Matriz de confusión

|               | **Predicted: NO** | **Predicted: YES** |
|----------------|-------------------|--------------------|
| **Actual: NO** | 5665 (TN)        | 0 (FP)             |
| **Actual: YES**| 718 (FN)         | 0 (TP)             |

