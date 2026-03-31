# ProDe API Collection

Colección de requests [Bruno](https://www.usebruno.com/) para la API de ProDe. Permite gestionar **Partidos** y **Resultados** del torneo.

## Requisitos

- [Bruno](https://www.usebruno.com/downloads) v1.0+

## Estructura

```
ProDe API/
├── environments/
│   └── local.yml               # Variables de entorno local
├── Partidos/
│   ├── Get partidos.yml        # Listar partidos con filtros
│   ├── Get partido by id.yml   # Obtener un partido por ID
│   ├── Post partido.yml        # Crear un nuevo partido
│   ├── Put partido by id.yml   # Reemplazar un partido
│   ├── Patch partido by id.yml # Actualizar parcialmente un partido
│   └── Delete partido by id.yml# Eliminar un partido
├── Resultados/
│   └── Put resultado.yml       # Registrar resultado de un partido
├── Predicciones/
│   └── Post prediccion.yml     # Registrar una predicción para un partido
├── Usuarios/
│   ├── Get usuarios.yml        # Listar usuarios
│   ├── Get usuario by id.yml   # Obtener un usuario por ID
│   ├── Post usuario.yml        # Crear un usuario
│   ├── Put usuario by id.yml   # Reemplazar un usuario
│   └── Delete usuario by id.yml# Eliminar un usuario
└── Ranking/
    └── Get ranking.yml         # Obtener el ranking de usuarios
```

## Endpoints

### Partidos

| Método | Endpoint | Descripción |
|--------|----------|-------------|
| `GET` | `/prode_api/partidos` | Lista partidos con filtros opcionales |
| `GET` | `/prode_api/partidos/:id` | Obtiene un partido por ID |
| `POST` | `/prode_api/partidos` | Crea un nuevo partido |
| `PUT` | `/prode_api/partidos/:id` | Reemplaza todos los campos de un partido |
| `PATCH` | `/prode_api/partidos/:id` | Actualiza parcialmente un partido |
| `DELETE` | `/prode_api/partidos/:id` | Elimina un partido |

#### Filtros disponibles en GET /partidos

| Parámetro | Descripción | Ejemplo |
|-----------|-------------|---------|
| `fecha` | Fecha del partido | `2022-11-22` |
| `equipo` | Nombre del equipo | `ARGENTINA` |
| `fase` | Fase del torneo | `GRUPOS` |
| `_offset` | Paginación — inicio | `0` |
| `_limit` | Paginación — cantidad | `10` |

### Resultados

| Método | Endpoint | Descripción |
|--------|----------|-------------|
| `PUT` | `/prode_api/partidos/:id/resultado` | Carga el resultado de un partido |

### Predicciones

| Método | Endpoint | Descripción |
|--------|----------|-------------|
| `POST` | `/prode_api/partidos/:id/prediccion` | Registra una predicción para un partido |

### Usuarios

| Método | Endpoint | Descripción |
|--------|----------|-------------|
| `GET` | `/prode_api/usuarios` | Lista usuarios |
| `GET` | `/prode_api/usuarios/:id` | Obtiene un usuario por ID |
| `POST` | `/prode_api/usuarios` | Crea un nuevo usuario |
| `PUT` | `/prode_api/usuarios/:id` | Reemplaza todos los campos de un usuario |
| `DELETE` | `/prode_api/usuarios/:id` | Elimina un usuario |

### Ranking

| Método | Endpoint | Descripción |
|--------|----------|-------------|
| `GET` | `/prode_api/ranking` | Obtiene el ranking de usuarios |

## Variables de entorno

El entorno `local` incluye las siguientes variables configurables:

| Variable | Valor por defecto | Descripción |
|----------|-------------------|-------------|
| `protocol` | `http` | Protocolo |
| `host` | `localhost:5000` | Host y puerto |
| `path_api` | `/prode_api` | Base path de la API |
| `fecha` | `2022-11-22` | Fecha de ejemplo |
| `equipo` | `ARGENTINA` | Equipo de ejemplo |
| `fase` | `GRUPOS` | Fase de ejemplo |
| `partido_id` | `1` | ID de partido de ejemplo |
| `usuario_id` | `1` | ID de usuario de ejemplo |

## Uso

1. Clonar el repositorio
2. Abrir Bruno y seleccionar **Open Collection**
3. Navegar hasta la carpeta del proyecto
4. Seleccionar el entorno **local** desde el selector de entornos
5. Ajustar las variables de entorno según sea necesario
