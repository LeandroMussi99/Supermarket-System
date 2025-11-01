# 🛒 Supermarket System

**Supermarket System** es una aplicación web desarrollada en **Spring Boot** y **Thymeleaf** que permite administrar el stock de un supermercado, gestionar ventas y mantener el control del inventario.  
Incluye autenticación de usuarios con roles, manejo de productos, compras, alertas de bajo stock e informes de inventario.

---

## ✨ Características principales

- 🔐 **Autenticación con roles (Spring Security)**  
  Acceso diferenciado para administradores y clientes.
- 📦 **Gestión de productos y stock**  
  Altas, bajas, modificaciones y actualización automática de stock.
- ⚠️ **Alertas de bajo stock**  
  Página dedicada a mostrar productos por debajo del mínimo establecido.
- 🧾 **Gestión de compras**  
  Los usuarios registrados pueden generar compras y afectar el inventario en forma transaccional.
- 📊 **Informes de inventario**  
  Vista general del estado actualizado de todos los productos.

---

## 🧱 Arquitectura y tecnologías

- **Backend:** Spring Boot 3, Spring Data JPA, Spring Security  
- **Frontend:** Thymeleaf, Bootstrap, jQuery  
- **Base de datos:** MySQL (Hibernate con `ddl-auto: update`)  
- **Build tool:** Maven  
- **Java version:** 17

---

## ⚙️ Requisitos previos

- JDK 17 instalado  
- Maven 3.9 o superior  
- Servidor MySQL en ejecución

---

## 🚀 Configuración e instalación

1. Crear una base de datos vacía llamada `supermarket` en MySQL.  
2. Configurar las credenciales en variables de entorno:

   ```bash
   export DB_URL="jdbc:mysql://localhost:3306/supermarket"
   export USERNAME="root"
   export PASSWORD="tu_password"
   
3. Compilar y ejecutar la aplicación: ./mvnw spring-boot:run

4. Acceder en el navegador a http://localhost:8080
/login → pantalla de inicio de sesión
/index → panel principal (una vez autenticado)

🧭 Rutas principales

| Ruta                    | Descripción                            |
| ----------------------- | -------------------------------------- |
| `/producto`             | Listado y mantenimiento de productos   |
| `/producto/new`         | Formulario de alta de producto         |
| `/stock/alta`           | Alta de lotes y actualización de stock |
| `/alerta/bajoStockPage` | Alertas de productos con stock bajo    |
| `/compras/nueva`        | Formulario para registrar compras      |
| `/informe/informes1`    | Informe general de inventario          |

Estructura del proyecto

src/
 ├─ main/
 │   ├─ java/com/unla/grupo22/tpc/
 │   │   ├─ controllers/        # Controladores MVC
 │   │   ├─ entities/           # Entidades JPA
 │   │   ├─ repositories/       # Interfaces Spring Data
 │   │   ├─ services/           # Interfaces de servicio
 │   │   └─ services/implementation/  # Lógica de negocio
 │   └─ resources/
 │       ├─ templates/          # Vistas Thymeleaf
 │       ├─ static/             # Archivos CSS y JS
 │       └─ application.yml     # Configuración de Spring Boot
 └─ test/                       # Pruebas unitarias

