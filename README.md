# NovaCorp — Company Management Platform

**NovaCorp Platform** is an internal web application for managing companies and their associated comments. It supports three roles (`admin`, `owner`, `user`) with different access levels.

Este proyecto implementa un ciclo de vida de desarrollo seguro (SDLC) para la plataforma NovaCorp.

## Controles de Seguridad (CI/CD)
Este repositorio integra análisis automáticos en cada 'push':
- **SCA (Software Composition Analysis):** Ejecutado con `pip-audit` para detectar dependencias vulnerables.
- **SAST (Static Application Security Testing):** Ejecutado con `Semgrep` para identificar fallos de seguridad en el código fuente.

## Despliegue
- **URL Pública:** 
- **Entorno:** Contenedor Docker (Python 3.11-slim)

---

## Installation

```bash
pip install -r requirements.txt
python main.py
```

Visit: `http://127.0.0.1:5000`

The database is automatically initialized on first run.

---

## Default Users

| Username | Password   | Role   | Notes                      |
|----------|------------|--------|----------------------------|
| `alice`  | password1  | user   | Standard employee          |
| `bob`    | password2  | owner  | Owns "Insegura Corp"       |
| `admin`  | admin123   | admin  | Full access                |

---

## Project Structure


```

.
├── .github/workflows/       # Pipelines de GitHub Actions (Seguridad)
├── app/                     # Código fuente de la aplicación
│   ├── main.py              # Punto de entrada del módulo
│   ├── server.py            # Configuración de Flask (WSGI)
│   ├── db/                  # Inicialización y lógica de base de datos
│   ├── routes/              # Rutas y controladores (Blueprints)
│   ├── templates/           # Vistas (Jinja2)
│   └── static/              # Archivos estáticos (CSS/JS)
├── Dockerfile               # Configuración del contenedor de producción
├── requirements.txt         # Dependencias del proyecto (Remediadas)
├── .gitignore               # Exclusiones de Git (db, venv, pycache)
└── README.md                # Documentación del proyecto


```

---

## Technologies

- Python 3.11 + Flask
- Gunicorn (WSGI HTTP Server)
- SQLite
- Semgrep (SAST) y pip-audit (SCA)
- Bootstrap 5.3
- Jinja2 + Bootstrap Icons
- Docker + Render.com
