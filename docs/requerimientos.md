# Requerimientos del Sistema - Viajes Aventura

## Requerimientos Funcionales

### RF-01: Gestión de Destinos
* **Prioridad:** Alta
* **Descripción:** El administrador de la agencia debe poder registrar, modificar, eliminar y listar los destinos turísticos disponibles.
* **Criterio de aceptación:** Al registrar un nuevo destino con sus datos obligatorios, este queda guardado y aparece de inmediato en el listado general.

### RF-02: Gestión de Paquetes Turísticos
* **Prioridad:** Alta
* **Descripción:** El sistema debe permitir combinar destinos, definir fechas de inicio y término, calcular costos y consultar la disponibilidad de cupos.
* **Criterio de aceptación:** Al crear un paquete con uno o más destinos y fechas válidas, el sistema calcula el costo total y muestra los cupos disponibles.

### RF-03: Registro y Autenticación de Clientes
* **Prioridad:** Alta
* **Descripción:** Los clientes deben poder registrarse en la plataforma e iniciar sesión para gestionar sus viajes.
* **Criterio de aceptación:** Un cliente registrado puede iniciar sesión con sus credenciales y acceder a su perfil e historial de reservas.

### RF-04: Reserva de Paquetes e Historial
* **Prioridad:** Alta
* **Descripción:** Los clientes autenticados pueden reservar paquetes con cupos disponibles y consultar su historial de reservas.
* **Criterio de aceptación:** Al confirmar una reserva, se descuenta un cupo del paquete y la reserva aparece registrada en el historial del cliente.

---

## Requerimientos No Funcionales

### RNF-01: Seguridad y Almacenamiento de Contraseñas
* **Prioridad:** Alta
* **Descripción:** El sistema debe almacenar las contraseñas de los usuarios cifradas mediante un algoritmo de hash seguro.
* **Criterio de aceptación:** Al inspeccionar el registro de un usuario en la base de datos, el campo de contraseña contiene un hash y nunca el texto plano original.

### RNF-02: Persistencia y Arquitectura por Capas
* **Prioridad:** Media
* **Descripción:** El sistema debe separar la lógica en capas (presentación, negocio y persistencia) utilizando SQLite como motor inicial de base de datos.
* **Criterio de aceptación:** La prueba de conexión a SQLite se ejecuta correctamente desde la capa de persistencia siguiendo las instrucciones del README.
