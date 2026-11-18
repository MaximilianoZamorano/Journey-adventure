```markdown
# Viajes Aventura

Sistema de gestión para agencia de viajes enfocado en la administración de destinos turísticos, creación de paquetes, control de reservas y acceso de usuarios[cite: 2].

## Estructura del Proyecto
El proyecto está estructurado bajo una arquitectura por capas para separar responsabilidades[cite: 9]:
* `docs/`: Documentación oficial, requerimientos y modelo de base de datos[cite: 4, 9].
* `src/`: Código fuente dividido en presentación, negocio y persistencia[cite: 9].
* `tests/`: Pruebas unitarias y de conexión a bases de datos[cite: 9].

## Configuración y Ejecución
1. Clonar este repositorio en tu equipo local.
2. Crear un archivo `.env` basado en el archivo de ejemplo `.env.example` en la raíz del proyecto[cite: 9].
3. Configurar la ruta de la base de datos SQLite en el archivo `.env` e iniciar el entorno de desarrollo según las pautas del curso[cite: 9].
