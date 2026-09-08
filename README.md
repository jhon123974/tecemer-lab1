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
