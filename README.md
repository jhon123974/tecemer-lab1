# tecemer-lab1

Proyecto de práctica que consume una API pública (chistes aleatorios) para validar un entorno de desarrollo Python profesional: entorno virtual, control de versiones con Git y estructura de proyecto estándar.

## Instalación

1. Clonar el repositorio y ubicarse en la carpeta del proyecto.
2. Crear el entorno virtual:
   ```
   python -m venv .venv
   ```
3. Activar el entorno virtual:
   ```
   .venv\Scripts\activate      # Windows
   source .venv/bin/activate   # Linux/macOS
   ```
4. Instalar el proyecto en modo editable:
   ```
   pip install -e .
   ```

## Uso

Ejecutar el script principal:
```
python -c "from tecemer_lab1 import app"
```

## Estructura del repositorio

```
tecemer-lab1/
├── src/
│   └── tecemer_lab1/
│       ├── __init__.py
│       └── app.py
├── .gitignore
├── pyproject.toml
├── requirements.txt
└── README.md
```

## Autor y curso

Jhon — Tecnologías Emergentes (ISO46B)

## Flujo de datos (Semana 2)

- **Fuente:** API pública Open-Meteo (`https://api.open-meteo.com/v1/forecast`), pronóstico de 7 días para Huancayo (temperatura máxima, mínima y precipitación).
- **Transformación:** los datos crudos en JSON se guardan en `pronostico_huancayo.json` y se convierten a `pronostico_huancayo.csv`. Luego, con Pandas, se calculan columnas derivadas (amplitud térmica, día lluvioso, categoría de clima) y se agregan estadísticas por categoría con `groupby`.
- **Salida:** `pronostico_huancayo_procesado.csv` (datos enriquecidos) y `resumen_por_categoria.csv` (resumen agregado por categoría de clima).
