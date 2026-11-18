# Modelo de Base de Datos - Viajes Aventura

Este documento describe la estructura del modelo físico de la base de datos relacional para el sistema de gestión de la agencia, diseñado para soportar la administración de destinos, paquetes turísticos, usuarios y reservas.

## Tablas Principales

1. **`users` (Usuarios / Clientes)**
   * Almacena la información de los clientes y administradores.
   * Campos principales: `id` (PK), `name`, `email` (único), `password_hash`.

2. **`destinations` (Destinos)**
   * Registra los lugares turísticos disponibles.
   * Campos principales: `id` (PK), `name`, `description`, `location`.

3. **`packages` (Paquetes Turísticos)**
   * Combina múltiples destinos con fechas y costos definidos.
   * Campos principales: `id` (PK), `name`, `start_date`, `end_date`, `cost`, `available_slots`.

4. **`package_destinations` (Tabla Intermedia N:M)**
   * Relaciona los paquetes turísticos con sus respectivos destinos.
   * Campos principales: `package_id` (FK), `destination_id` (FK).

5. **`reservations` (Reservas)**
   * Vincula a los clientes con los paquetes turísticos que desean contratar.
   * Campos principales: `id` (PK), `user_id` (FK), `package_id` (FK), `reservation_date`, `status`.

---

## Diagrama Entidad-Relación (Mermaid)

```mermaid
erDiagram
    USERS ||--o{ RESERVATIONS : "realiza"
    PACKAGES ||--o{ RESERVATIONS : "incluido_en"
    PACKAGES ||--o{ PACKAGE_DESTINATIONS : "contiene"
    DESTINATIONS ||--o{ PACKAGE_DESTINATIONS : "parte_de"

    USERS {
        int id PK
        string name
        string email
        string password_hash
    }

    RESERVATIONS {
        int id PK
        int user_id FK
        int package_id FK
        datetime reservation_date
        string status
    }

    PACKAGES {
        int id PK
        string name
        date start_date
        date end_date
        float cost
        int available_slots
    }

    PACKAGE_DESTINATIONS {
        int package_id PK, FK
        int destination_id PK, FK
    }

    DESTINATIONS {
        int id PK
        string name
        text description
        string location
    }
