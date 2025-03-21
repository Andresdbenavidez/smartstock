# **Modelo de Dominio - SmartStock**

## **1. Introducción**
El modelo de dominio de **SmartStock** representa los conceptos clave del sistema y sus relaciones. Este modelo sirve como base para la comprensión del sistema y su estructura de datos.

## **2. Descripción del Modelo de Dominio**
El sistema **SmartStock** se centra en la gestión de inventarios de pequeñas empresas, asegurando el control de productos, movimientos de stock, usuarios y roles. Se identifican las siguientes entidades clave:

- **Usuario:** Representa a los usuarios que interactúan con el sistema, incluyendo administradores, empleados e invitados.
- **Rol:** Define los permisos y restricciones de cada usuario en el sistema.
- **Producto:** Representa los artículos registrados en el inventario.
- **Categoría:** Agrupación de productos para una mejor organización.
- **Movimiento de Stock:** Registra las entradas y salidas de productos del inventario.
- **Reporte:** Genera informes sobre productos más vendidos, niveles de stock y tendencias.
- **Alerta:** Notificaciones internas y por correo sobre productos con stock bajo.

## **3. Diagrama del Modelo de Dominio**
![Descripción](https://i.imgur.com/Xufj7Uu.png)

## **4. Definición de Entidades, Métodos y Relaciones**
### **4.1 Usuario**
- **Atributos:**
  - -ID_Usuario (PK, INT)
  - +Nombre (VARCHAR)
  - +Correo Electrónico (VARCHAR, únicamente Gmail o Outlook)
  - -Contraseña (VARCHAR, cifrada)
  - +Estado (ENUM: Invitado, Activo, Inactivo)
  - +ID_Rol (FK, INT)
- **Métodos:**
  - +registrarUsuario()
  - +autenticarUsuario()
  - +cambiarContraseña()
  - +solicitarAcceso()
- **Relaciones:**
  - Un usuario tiene un único rol asignado (1 a 1).
  - Un usuario puede generar múltiples reportes (1 a muchos).
  - Un usuario registra movimientos de stock (1 a muchos).

### **4.2 Rol**
- **Atributos:**
  - -ID_Rol (PK, INT)
  - +Nombre (VARCHAR)
  - +Permisos (TEXT)
- **Métodos:**
  - +crearRol()
  - +asignarPermisos()
  - +modificarRol()
- **Relaciones:**
  - Un rol puede tener múltiples usuarios (1 a muchos).

### **4.3 Producto**
- **Atributos:**
  - -ID_Producto (PK, INT)
  - +Nombre (VARCHAR)
  - +Descripción (TEXT)
  - +Precio (DECIMAL)
  - +Cantidad Disponible (INT, mínimo 0)
  - +ID_Categoría (FK, INT)
  - +Imagen (VARCHAR, 1 por producto)
- **Métodos:**
  - +registrarProducto()
  - +actualizarProducto()
  - +eliminarProducto()
  - +consultarProducto()
- **Relaciones:**
  - Un producto pertenece a una categoría (1 a muchos).
  - Un producto puede tener múltiples movimientos de stock (1 a muchos).
  - Un producto puede estar asociado a una alerta (1 a 1).

### **4.4 Categoría**
- **Atributos:**
  - -ID_Categoría (PK, INT)
  - +Nombre (VARCHAR)
  - +Descripción (TEXT)
- **Métodos:**
  - +agregarCategoria()
  - +modificarCategoria()
  - +eliminarCategoria()
- **Relaciones:**
  - Una categoría puede tener múltiples productos (1 a muchos).

### **4.5 Movimiento de Stock**
- **Atributos:**
  - -ID_Movimiento (PK, INT)
  - +Tipo (ENUM: Entrada, Salida)
  - +Cantidad (INT)
  - +Fecha (DATETIME)
  - +ID_Producto (FK, INT)
  - +ID_Usuario (FK, INT)
- **Métodos:**
  - +registrarEntrada()
  - +registrarSalida()
  - +consultarMovimientos()
- **Relaciones:**
  - Un movimiento de stock está asociado a un producto (1 a muchos).
  - Un usuario registra movimientos de stock (1 a muchos).

### **4.6 Reporte**
- **Atributos:**
  - -ID_Reporte (PK, INT)
  - +Tipo de Reporte (VARCHAR)
  - +Fecha de Generación (DATETIME)
  - +Formato (ENUM: PDF, Excel)
- **Métodos:**
  - +generarReporte()
  - +exportarPDF()
  - +exportarExcel()
- **Relaciones:**
  - Un usuario puede generar múltiples reportes (1 a muchos).

### **4.7 Alerta**
- **Atributos:**
  - -ID_Alerta (PK, INT)
  - +Tipo de Alerta (VARCHAR)
  - +Estado (ENUM: Activa, Inactiva)
  - +Notificación por Correo (BOOLEAN)
- **Métodos:**
  - +generarAlerta()
  - +enviarNotificacion()
  - +modificarAlerta()
  - +desactivarAlerta()
- **Relaciones:**
  - Una alerta está asociada a un único producto (1 a 1).

## **5. Conclusión**
El modelo de dominio de **SmartStock** define las entidades fundamentales, sus métodos y su interacción, proporcionando una base clara para el desarrollo del sistema y su base de datos.

