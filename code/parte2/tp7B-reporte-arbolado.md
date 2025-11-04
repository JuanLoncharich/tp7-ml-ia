# TP7 – Parte II – Desafío Kaggle: Arbolado público de Mendoza

## 1. Preprocesamiento
- Normalización de nombres de columnas (minusculización, recorte de espacios, reemplazo por `_`).
- Imputación de faltantes numéricos con mediana del train (`outputs/preproc_params.rds`). # TODO: cambiar imputación si se usa modelo más sensible.
- Agrupación de especies raras en la categoría `OTRA` (frecuencia < 20).
- Conversión de `especie` y `seccion` a factor (`seccion_f` creado en preprocesamiento). # TODO: probar convertir seccion a factor (puede mejorar).
- Creación de variables derivadas (`anio_modif`, `mes_modif`, `altura_rel`, `densidad_seccion`). # TODO: evaluar importancia.
- Eliminación de columna `id` del set de entrenamiento (se preserva para envíos).
- Guardado de parámetros y datos limpios (`outputs/train_clean.rds`, `outputs/test_clean.rds`, `outputs/preproc_params.rds`).

## 2. Resultados sobre conjunto de validación (80/20)
- Baseline rpart: AUC = __(completar desde `outputs/metrics/val_results.csv`)__.
- Baseline rpart (control): AUC = __(idem)__.
- Random forest (si disponible): AUC = __(idem / comentar si faltó)__.
- Comentario: se selecciona el modelo con mayor AUC. # TODO: probar balanceo simple: samplear más la clase 1 en el train.

## 3. Resultados en Kaggle
- Archivo enviado: `outputs/submissions/arbolado-envio-baseline.csv`.
- AUC reportado por Kaggle: __(completar)__.
- Comparación con objetivo (> 0.69): __(completar)__.
- # TODO: comparar AUC local vs AUC Kaggle para ver fuga de datos.

## 4. Descripción del algoritmo propuesto
- Modelo base seleccionado: árbol de decisión con control (o random forest si mejora). # TODO: guardar importancia de variables (varImp) si se usa random forest.
- Variables de entrada: altura, circ_tronco_cm, lat, long, seccion, `seccion_f`, especie, derivadas (`altura_rel`, `densidad_seccion`, `anio_modif`, `mes_modif`). # TODO: probar dejar fuera lat/long si el modelo se sobreajusta.
- Justificación: combinación de variables estructurales y geográficas para explicar inclinación. # TODO: probar usar nombre_seccion como categoría si la cardinalidad no es alta.
- Posibles mejoras: tuning de hiperparámetros, modelos de boosting (`xgboost`), ingeniería adicional. # TODO: probar un modelo con solo variables numéricas para xgboost.

