# Predict Students' Dropout & Academic Success (UCI) — Clasificación (3 clases)

Proyecto personal de Data Science para **predecir el estado académico del estudiante**:
- **Dropout**
- **Enrolled**
- **Graduate**

El objetivo es construir un modelo interpretable y útil para **alerta temprana** y priorización de intervenciones.

## Dataset
- Fuente: **UCI Machine Learning Repository** — “Predict Students’ Dropout and Academic Success”
- Tamaño: **4,424** registros
- Variables: **36 features** + **1 target** (3 clases)

Distribución del target (en el notebook):
- Graduate: 49.93%
- Dropout: 32.12%
- Enrolled: 17.95%

## Enfoque
1. **Carga del dataset** vía `ucimlrepo`.
2. **Preparación**:
   - Renombrado de columnas para claridad.
   - Tratamiento simple de outliers (criterio de dominio).
   - Segmentación de variables (p.ej., modo de ingreso, formación, ocupación).
   - Codificación ordinal + One-Hot Encoding en nominales.
   - Escalado de numéricas.
   - Balanceo con **SMOTE**.
3. **Modelado**:
   - Baseline: **KNN**
   - Modelo final: **Red Neuronal (MLP)** con Early Stopping.
4. **Evaluación**:
   - Accuracy, Precision/Recall/F1 (weighted)
   - Matriz de confusión
   - Interpretabilidad con **Permutation Importance**
   - Evaluación adicional con **matriz de costos** (impacto de errores)

## Resultados principales (Test)
Modelo final (Momento 1 — RNA/MLP):
- **Accuracy:** 0.7167  
- **F1 (weighted):** 0.7010  
- **Precision (weighted):** 0.6948  
- **Recall (weighted):** 0.7167  

Baseline (KNN — Momento 1):
- **Accuracy:** 0.5667

## Variables más influyentes (Permutation Importance — top)
En mi ejecución, destacan (top):
- Aprobadas_1S
- Pagos_al_día_1
- Evaluaciones_1S
- Becado_1
- Creditos_1S
- Nota_promedio_1S
- (entre otras)

## Estructura del repositorio
- `Proyecto_Integrador.ipynb`: notebook principal (EDA → preparación → modelos → evaluación).
- `assets/`: imágenes para README/LinkedIn (matriz de confusión, importancia de variables, etc.).

## Cómo ejecutar
```bash
pip install -r requirements.txt
jupyter notebook
