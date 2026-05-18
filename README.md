# 🖥️ Mercado Tech

## 👥 Autores

| **Nombre** | **Código** |
|--------|--------|
| Johan Emanuel Rodriguez Romero | 20222578102 |
| Carlos Mauricio Pinilla Benavides | 20212578154 |

---

## 📁 Estructura del proyecto

```
mercado-tech/
├── index.html                   ← Pantalla de inicio (Comprador / Administrador)
├── package.json
├── .env                         ← Credenciales de MySQL (NO subir a Git)
├── .gitignore
│
├── pages/
│   ├── mercado.html             ← Catálogo de productos y carrito
│   ├── crear-factura.html       ← Checkout con selección de empleado
│   ├── facturas.html            ← Ver facturas registradas
│   └── admin.html               ← Panel de administrador
│
├── js/
│   ├── api.js                   ← Comunicación con el backend (fetch)
│   ├── mercado.js               ← Lógica de productos y carrito
│   ├── factura.js               ← Lógica de creación de factura
│   ├── facturas.js              ← Lógica de visualización de facturas
│   └── admin.js                 ← Lógica del panel admin
│
├── css/
│   └── style.css
│
├── imag/                        ← Imágenes de productos
│
└── server/
    ├── server.js                ← Servidor Express (punto de entrada)
    ├── models/
    │   ├── index.js             ← Instancia de Sequelize
    │   ├── Empleado.js
    │   ├── Factura.js
    │   └── DetalleFactura.js
    └── routes/
        ├── empleados.js         ← GET /api/empleados  y  GET /api/empleados/stats
        └── facturas.js          ← GET /api/facturas   y  POST /api/facturas
```

---

## 🚀 Pasos para correr el proyecto

### 1. Instalar Node.js (si no lo tienes)
Descarga desde https://nodejs.org  (versión LTS)

### 2. Crear la base de datos en MySQL
Abre MySQL Workbench o la terminal de MySQL y ejecuta:
```sql
CREATE DATABASE mercado_tech;
```

### 3. Configurar credenciales
Edita el archivo `.env`:
```
PORT=3000
DB_HOST=localhost
DB_PORT=3306
DB_NAME=mercado_tech
DB_USER=root
DB_PASS=tu_contraseña_aqui
```
> Si MySQL no tiene contraseña (instalación por defecto), deja `DB_PASS=` vacío.

### 4. Instalar dependencias
```bash
npm install
```

### 5. Correr el servidor
```bash
# Modo normal
npm start

# Modo desarrollo (se reinicia automático con cambios)
npm run dev
```

### 6. Abrir en el navegador
```
http://localhost:3000
```

---


## 🗄️ Tablas que Sequelize crea automáticamente

```
Empleados      → id, nombre, createdAt, updatedAt
Facturas       → id, cliente, correo, telefono, pagoTarjeta,
                 totalNeto, iva, recargo, total, EmpleadoId,
                 createdAt, updatedAt
DetalleFacturas → id, producto, precio, FacturaId,
                  createdAt, updatedAt
```

---
