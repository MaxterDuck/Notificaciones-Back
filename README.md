📘 Estructura recomendada para el README.md
1. 🏁 Introducción
Breve descripción del proyecto.

md
# Comunidad Riwi - Backend

Este repositorio contiene el backend de la red social Comunidad Riwi, construido con Node.js y Express. Incluye autenticación con JWT, gestión de perfiles, publicaciones, comentarios y notificaciones.
2. ⚙️ Instalación
Pasos para levantar el proyecto localmente.

md
## Instalación

1. Clona el repositorio:
   ```bash
   git clone https://github.com/Deko25/backend_comunidad.git
Instala dependencias:

bash
npm install
Configura el archivo .env:

env
PORT=3000
DB_NAME=riwi_db
DB_USER=root
DB_PASS=tu_password
JWT_SECRET=clave_secreta
Ejecuta el servidor:

bash
npm run dev
Código

---

### 3. 🧩 Estructura del Proyecto

Resumen de carpetas y su propósito.

```md
## Estructura del Proyecto

backend_comunidad/ ├── config/ # Configuración de Sequelize y entorno ├── controllers/ # Lógica de negocio por entidad ├── models/ # Definición de modelos Sequelize ├── routes/ # Rutas agrupadas por entidad ├── middlewares/ # Autenticación, validación, etc. ├── utils/ # Funciones auxiliares ├── app.js # Punto de entrada del servidor

Código
4. 🔐 Autenticación
Explicación del flujo JWT y cómo se usa.

md
## Autenticación

El sistema usa JWT para proteger rutas. Al iniciar sesión, se genera un token con el `profile_id` en el payload. Este token debe enviarse en el header `Authorization` como:

Authorization: Bearer <token>

Código

Middleware: `verifyToken.js` valida el token y lo decodifica para uso en controladores.
5. 📮 Endpoints
Tabla con los endpoints disponibles y su propósito.

md
## Endpoints

| Método | Ruta | Descripción |
|--------|------|-------------|
| POST   | /auth/register | Registro de usuario |
| POST   | /auth/login    | Login y generación de JWT |
| GET    | /users/:id     | Obtener perfil |
| PUT    | /users/:id     | Editar perfil |
| GET    | /posts         | Ver publicaciones |
| POST   | /posts         | Crear publicación |
| POST   | /posts/:id/like | Dar like |
| POST   | /posts/:id/comments | Comentar |
| GET    | /notifications | Ver notificaciones del usuario |
6. 🧪 Pruebas
Cómo usar Postman para validar los flujos.

md
## Pruebas

Usa Postman para probar los siguientes flujos:

- Registro y login
- Creación de publicaciones
- Likes y comentarios
- Recepción de notificaciones

Valida tokens en [jwt.io](https://jwt.io) para verificar el `profile_id`.
7. 📌 Contribuciones y ramas
Guía para colaborar y usar ramas correctamente.

md
## Contribuciones

Usamos ramas por funcionalidad. Ejemplos:

- `feature-back-log-reg`: autenticación
- `feature-feed_publicaciones`: feed
- `feature-notificaciones-funcionales-am`: notificaciones

Haz pull requests hacia `main` solo cuando la funcionalidad esté probada y validada.
