### Matriz de confusión

|               | **Predicted: NO** | **Predicted: YES** |
|----------------|-------------------|--------------------|
| **Actual: NO** | 11286 (TN)        | 11382 (FP)         |
| **Actual: YES**| 1419 (FN)         | 1442 (TP)          |

### Métricas de evaluación

#### Valores base
- **True Positives (TP)**: 1442
- **True Negatives (TN)**: 11286
- **False Positives (FP)**: 11382
- **False Negatives (FN)**: 1419

#### Métricas calculadas

**Sensitivity (Sensibilidad / Recall / True Positive Rate)**
$$\text{Sensitivity} = \frac{TP}{TP + FN} = \frac{1442}{1442 + 1419} = \frac{1442}{2861} = 0.5040 = 50.40\%$$

**Specificity (Especificidad / True Negative Rate)**
$$\text{Specificity} = \frac{TN}{TN + FP} = \frac{11286}{11286 + 11382} = \frac{11286}{22668} = 0.4979 = 49.79\%$$

**Precision (Precisión / Positive Predictive Value)**
$$\text{Precision} = \frac{TP}{TP + FP} = \frac{1442}{1442 + 11382} = \frac{1442}{12824} = 0.1125 = 11.25\%$$

**Negative Predictive Value (Valor Predictivo Negativo)**
$$\text{NPV} = \frac{TN}{TN + FN} = \frac{11286}{11286 + 1419} = \frac{11286}{12705} = 0.8883 = 88.83\%$$

**Accuracy (Exactitud)**
$$\text{Accuracy} = \frac{TP + TN}{TP + TN + FP + FN} = \frac{1442 + 11286}{1442 + 11286 + 11382 + 1419} = \frac{12728}{25529} = 0.4986 = 49.86\%$$

**F1-Score**
$$\text{F1-Score} = 2 \times \frac{\text{Precision} \times \text{Sensitivity}}{\text{Precision} + \text{Sensitivity}} = 2 \times \frac{0.1125 \times 0.5040}{0.1125 + 0.5040} = 0.1847 = 18.47\%$$

**Type I Error (Error Tipo I)**: False Positive Rate
$$\text{Type I Error} = \frac{FP}{TN + FP} = \frac{11382}{22668} = 0.5021 = 50.21\%$$

**Type II Error (Error Tipo II)**: False Negative Rate
$$\text{Type II Error} = \frac{FN}{TP + FN} = \frac{1419}{2861} = 0.4960 = 49.60\%$$