# Modelos de Machine Learning aplicados a Dataset de Tamizajes de Salud

Proyecto universitario que aplica cuatro algoritmos de aprendizaje supervisado sobre un dataset real de tamizajes de salud, con el objetivo de predecir y clasificar casos clínicos.

---

## Descripción

El dataset `tamizajes.csv` contiene registros de tamizajes médicos con variables como Sexo, Etapa, GrupoTamizaje, DetalleTamizaje y número de Casos. Sobre este dataset se implementaron y compararon cuatro modelos de Machine Learning para tareas de regresión y clasificación.

---

## Modelos implementados

### 1. Regresión Lineal
Predice la cantidad de casos (`Casos`) a partir de las variables categóricas codificadas.

- **Variables predictoras:** Sexo, Etapa, GrupoTamizaje, DetalleTamizaje
- **Métricas obtenidas:** R² = 0.72 · MAE = 3.45 · RMSE = 4.38
- **Hallazgo:** DetalleTamizaje y Etapa son las variables con mayor coeficiente de influencia.

### 2. Regresión Logística
Clasifica si un registro es un caso relevante (`Casos > 5` → target = 1).

- **Variables predictoras:** Sexo, Etapa, GrupoTamizaje, DetalleTamizaje
- **Accuracy:** 0.81
- **Hallazgo:** Buen balance entre Precision, Recall y F1-score para ambas clases.

### 3. Árbol de Decisión
Detecta si un caso corresponde a situación de violencia a partir del campo `DetalleTamizaje`.

- **Variables predictoras:** Sexo\_cod, Etapa\_cod, GrupoTamizaje\_cod
- **Profundidad máxima:** 4
- **Accuracy:** 0.84
- **Hallazgo:** GrupoTamizaje es la característica más relevante para la clasificación.

### 4. Máquinas de Soporte Vectorial (SVM)
Clasifica casos de violencia usando un kernel lineal, con validación cruzada y análisis de vectores de soporte.

- **Variables predictoras:** Sexo\_cod, Etapa\_cod, GrupoTamizaje\_cod
- **Accuracy CV (5 folds):** 0.82 ± 0.02
- **Hallazgo:** El modelo es estable entre distintos subconjuntos del dataset.

---

## Tecnologías utilizadas

- Python 3
- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn

---

## Estructura del proyecto

```
├── examenParcial.ipynb   # Notebook principal con los 4 modelos
├── tamizajes.csv         # Dataset de tamizajes (no incluido por privacidad)
└── README.md
```

> **Nota:** El archivo `tamizajes.csv` no se incluye en el repositorio por contener datos de salud. Para reproducir los resultados, coloca el archivo en la raíz del proyecto.

---

## Cómo ejecutar

1. Clona el repositorio:
   ```bash
   git clone https://github.com/tu-usuario/tu-repositorio.git
   cd tu-repositorio
   ```

2. Instala las dependencias:
   ```bash
   pip install pandas numpy scikit-learn matplotlib seaborn
   ```

3. Coloca el archivo `tamizajes.csv` en la raíz del proyecto.

4. Abre el notebook:
   ```bash
   jupyter notebook examenParcial.ipynb
   ```

---

## Resultados comparativos

| Modelo               | Tarea          | Métrica principal     |
|----------------------|----------------|-----------------------|
| Regresión Lineal     | Regresión      | R² = 0.72             |
| Regresión Logística  | Clasificación  | Accuracy = 0.81       |
| Árbol de Decisión    | Clasificación  | Accuracy = 0.84       |
| SVM                  | Clasificación  | Accuracy CV = 0.82    |

---
Conclusiones 

Los modelos permiten identificar patrones críticos en la salud pública peruana, demostrando que el Árbol de Decisión es la herramienta más efectiva para la detección rápida de situaciones de violencia debido a su alta interpretabilidad.

## Autor
Juan Jose H.
