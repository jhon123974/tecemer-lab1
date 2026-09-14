# tecemer-lab1

Proyecto de práctica del curso Tecnologías Emergentes (ISO46B) — UNCP.
Semana 1: consume una API pública de chistes como ejercicio de configuración de entorno.
Semana 2: construye un pipeline de datos con NumPy, requests y Pandas.

## Instalación

```bash
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -e .
```

## Uso

```bash
python -m tecemer_lab1.app
```

## Estructura del repositorio

```
tecemer-lab1/
├── src/tecemer_lab1/          # código fuente (Semana 1)
├── numpy_demo.py               # Semana 2: fundamentos de NumPy
├── clima.py                    # Semana 2: consumo de API Open-Meteo
├── analisis.py                 # Semana 2: análisis con Pandas
├── pyproject.toml              # metadatos y dependencias
├── requirements.txt
├── README.md
└── .gitignore
```

## Flujo de datos (Semana 2)

- **Fuente:** API pública Open-Meteo (`https://api.open-meteo.com/v1/forecast`), pronóstico de 7 días para Huancayo (temperatura máxima, mínima y precipitación).
- **Transformación:** los datos crudos en JSON se guardan en `pronostico_huancayo.json` y se convierten a `pronostico_huancayo.csv`. Luego, con Pandas, se calculan columnas derivadas (amplitud térmica, día lluvioso, categoría de clima) y se agregan estadísticas por categoría con `groupby`.
- **Salida:** `pronostico_huancayo_procesado.csv` (datos enriquecidos) y `resumen_por_categoria.csv` (resumen agregado por categoría de clima).

## Autor

Curso: Tecnologías Emergentes (ISO46B) — Facultad de Ingeniería de Sistemas, UNCP.
