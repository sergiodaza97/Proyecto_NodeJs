#  Sistema de Gestión de Eventos

## Descripción

Este proyecto, desarrollado durante el bootcamp, es una aplicación web que permite a los usuarios organizar y gestionar eventos. Los usuarios pueden crear eventos, registrarse para asistir a eventos, gestionar la lista de asistentes y recibir notificaciones de eventos. El sistema soporta la gestión de diferentes tipos de eventos, como conferencias, talleres y reuniones, y ofrece una interfaz intuitiva tanto para organizadores como para asistentes.

## Objetivos de Aprendizaje

- Utilizar Node.js y Express.js para desarrollar una aplicación web completa.
- Implementar un patrón MVC para estructurar la aplicación.
- Utilizar MongoDB y Mongoose para la gestión de datos.
- Implementar autenticación de usuarios utilizando sesiones, cookies y JWT.
- Diseñar y consumir APIs RESTful.
- Integrar servicios de notificaciones por correo electrónico.
- Refactorizar y optimizar el código para un mejor rendimiento.

---


## Instrucciones para la instalación y configuración del entorno de desarrollo

### Clonar el repositorio

Primero, clona el repositorio del proyecto desde GitHub:

bash
git clone <URL_del_repositorio>
cd <nombre_del_repositorio>


### Instalar las dependencias

A continuación, instala las dependencias del proyecto usando npm:

bash
npm install

npm install express express-validator


### Configurar el entorno

Crea un archivo .env en la raíz del proyecto y añade las variables de entorno necesarias. Por ejemplo:

bash
MONGODB_URI=mongodb_uri
APP_PORT=3000
JWT_SECRET=your_secret
EMAIL_USER=example@gmail.com
EMAIL_PASS=kjhkicv


### Iniciar la aplicación

Finalmente, inicia la aplicación:

bash
npm run dev


---

## Guía de Uso

Esta guía explica cómo utilizar las principales funcionalidades del sistema a través de la API y cómo consultarlas usando Postman.

### 1. Registro de Nuevos Usuarios
Endpoint: POST /api/usuarios/register

Descripción: Registra un nuevo usuario en el sistema.

json
{
  "nombre": "Juan Pérez",
  "email": "juan.perez@example.com",
  "contraseña": "contraseña_segura"
}


### 2. Autenticación de Usuario
Endpoint: POST /api/usuarios/login

Descripción: Autentica a un usuario mediante sesiones y cookies o JWT.

json
{
  "email": "usuario@example.com",
  "contraseña": "contraseña_segura"
}


### 3. Gestión de Eventos
## a. Crear un Evento
Endpoint: POST /api/eventos

Descripción: Crea un nuevo evento.

json
{
  "titulo": "Título del Evento",
  "descripcion": "Descripción del Evento",
  "fecha": "2024-08-15T18:00:00Z",
  "tipo": "conferencia"
}


## b. Editar un Evento
Endpoint: PUT /api/eventos/:id

Descripción: Edita un evento existente.

json
{
  "titulo": "Nuevo Título del Evento",
  "descripcion": "Nueva Descripción del Evento",
  "fecha": "2024-08-16T18:00:00Z",
  "tipo": "taller"
}


## c. Eliminar un Evento
Endpoint: DELETE /api/eventos/:id

Descripción: Elimina un evento existente.

json
{
  "mensaje": "Evento eliminado exitosamente"
}


## d. Visualizar la Lista de Eventos
Endpoint: GET /api/eventos

Descripción: Obtiene la lista de eventos disponibles.

json
[
  {
    "id": "67890",
    "titulo": "Título del Evento",
    "descripcion": "Descripción del Evento",
    "fecha": "2024-08-15T18:00:00Z",
    "tipo": "conferencia"
  }
]
