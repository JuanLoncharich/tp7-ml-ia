# TP7 – Parte II – Flujo en R

Este directorio contiene el flujo reproducible para la Parte II del TP7 (desafío Kaggle de arbolado público de Mendoza). Cada script se ejecuta en orden y produce los artefactos necesarios para entrenar un modelo base con AUC objetivo mayor a 0.69.

## Requisitos previos
- R >= 4.0.
- Paquetes: `tidyverse`, `lubridate`, `rpart`, `pROC`. Si están disponibles se utilizan además `randomForest` y `xgboost` (instalación opcional, dejada como comentario en los scripts).
- Directorio de datos esperado (relativo al repo): `data/`
  - `data/arbolado-mza-dataset-train-80.csv`
  - `data/arbolado-mza-dataset-test-20.csv`

## Orden sugerido de ejecución
Los scripts detectan automáticamente su carpeta, por lo que podés correr `Rscript 0X_...R` estando dentro de `code/parte2/code` sin preocuparte por las rutas relativas.

1. `code/01_load_and_preprocess.R`: limpia los datos, genera imputaciones y guarda `train_clean.rds`, `test_clean.rds` y `preproc_params.rds`.
2. `code/02_eda_quick.R`: genera diagnósticos rápidos y gráficos en `outputs/eda/`. # TODO: generar curva ROC y guardarla en `outputs/eda/roc_baseline.png`.
3. `code/03_train_validate_baselines.R`: entrena baselines con split 80/20 y guarda `outputs/metrics/val_results.csv`.
4. `code/04_cross_validation.R`: realiza validación cruzada 10-fold y guarda `outputs/metrics/cv_10fold.csv` y `cv_10fold_summary.csv`.
5. `code/05_train_final_and_predict.R`: ajusta el modelo final y crea `outputs/submissions/arbolado-envio-baseline.csv`.

## Próximos pasos sugeridos
- # TODO: comparar AUC local vs AUC Kaggle para ver fuga de datos.
- # TODO: escribir en el reporte las limitaciones (desbalance, variables muy categóricas).
