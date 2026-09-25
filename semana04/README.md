# Semana 4 — Fundamentos de Redes Neuronales Artificiales

Laboratorio que introduce la construcción de una red neuronal (MLP) con Keras/TensorFlow, aplicada a un clasificador binario de lluvia para Huancayo.

## Contenido

- `ampliar_dataset.py`: amplía `pronostico_huancayo.csv` con 90 días de historial real (API histórica de Open-Meteo), ya que el dataset original de la Semana 2 (7 días) era insuficiente para una partición train/test estratificada.
- `preparar_dataset.py`: carga el CSV, construye la variable objetivo `dia_lluvioso` y la característica derivada `amplitud_termica`, limpia, escala y particiona los datos (guarda `dataset_preparado.npz`).
- `perceptron_sintetico.py`: MLP de práctica sobre datos sintéticos (scikit-learn), como plantilla de arquitectura y flujo de entrenamiento en Keras.
- `clasificador_lluvia.py`: compara un modelo baseline (regresión logística) contra un MLP entrenado sobre los datos reales de Huancayo, y guarda el modelo (`modelo_lluvia.keras`).
- `predecir.py`: carga el modelo guardado y predice sobre observaciones nuevas de ejemplo.
- `tests/test_preparacion.py`: pruebas unitarias de la función `calcular_dia_lluvioso`.

## Resultados

- Precisión del baseline (regresión logística): **0.7368**
- Precisión del MLP: **0.5263**

El MLP no superó al baseline. Esto es esperado con un dataset pequeño (91 días de una sola estación meteorológica): un modelo más complejo no siempre es mejor cuando hay poca cantidad de datos disponibles para entrenar.

## Uso

```bash
python ampliar_dataset.py
python preparar_dataset.py
python perceptron_sintetico.py
python clasificador_lluvia.py
python predecir.py
python -m pytest tests/ -v
```

## Limitaciones identificadas conscientemente

- Al importar `preparar_dataset` en las pruebas, Python ejecuta todo el script (incluida la carga del CSV). Funciona porque el CSV está en la misma carpeta, pero en un proyecto profesional la lógica reutilizable se separaría en un módulo sin efectos secundarios al importarse.
- El escalador (`StandardScaler`) no se guarda junto al modelo; `predecir.py` usa valores ya aproximados a la escala estandarizada como demostración. En producción, se guardaría el escalador (por ejemplo con `joblib.dump`) para transformar datos nuevos de forma consistente.