# ShipNow API

API de ShipNow con Node.js, Express y MongoDB.

## Requisitos

- Node.js 18+
- MongoDB en local

## Instalación

```bash
npm install
npm run dev
```

La app se conecta a `mongodb://localhost:27017/shipnow` (valor en `src/server.js`) y escucha en el puerto `8080`.

## Endpoints

| Método | Ruta | Descripción |
| --- | --- | --- |
| GET | `/api/health` | Health check |
| GET/POST | `/api/users` | Listar / crear usuarios |
| GET/PUT/DELETE | `/api/users/:id` | Obtener / actualizar / eliminar |
| GET | `/api/products` | Listar productos con stock (`?all=true` incluye sin stock) |
| POST | `/api/products` | Crear producto |
| GET/PUT/DELETE | `/api/products/:id` | Obtener / actualizar / eliminar |
| GET | `/api/products/:id/shipping-cost` | Cotizar el envío de un producto |


## Scripts

| Comando | Uso |
| --- | --- |
| `npm run dev` | Desarrollo con nodemon |
| `npm start` | Producción |

# 🚀 ShipNow API — Pre-entrega Módulo 2 (Mocking y Carga de Datos)

API backend desarrollada en Node.js y Express para la gestión de envíos, con arquitectura por capas, autenticación JWT, manejo avanzado de errores y un **módulo de mocking y seed de datos de prueba**.

---

## 🛠️ Tecnologías y Stack
* **Node.js** (Entorno de ejecución)
* **Express** (Framework web)
* **MongoDB & Mongoose** (Base de datos y ODM)
* **Faker.js** (Generación de datos simulados)
* **dotenv** (Gestión de variables de entorno)

---

## 🏗️ Arquitectura del Proyecto
El proyecto sigue estrictamente un diseño modular **por capas**, garantizando la separación de responsabilidades:

```text
src/
├── config/         # Configuración de base de datos y entorno
├── constants/      # Constantes centralizadas (roles, estados, prioridades)
├── controllers/    # Lógica de manejo HTTP (req / res)
├── models/         # Esquemas de Mongoose
├── repository/     # Capa de abstracción de datos (persistencia)
├── routes/         # Enrutadores de Express (endpoints)
├── services/       # Lógica de negocio y reglas de la aplicación
├── utils/          # Utilidades (generadores de mocks, manejo de errores)
└── app.js          # Inicialización y configuración de Express