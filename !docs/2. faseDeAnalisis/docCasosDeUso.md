# **Casos de Uso - SmartStock**

## **Índice**
1. [Introducción](#introducción)
2. [Actores](#actores)
3. [Diagrama de Casos de Uso](#diagrama-de-casos-de-uso)
4. [Casos de Uso](#casos-de-uso)
   - [CU01 - Registro de Usuario](#cu01---registro-de-usuario)
   - [CU02 - Inicio de Sesión](#cu02---inicio-de-sesión)
   - [CU03 - Gestión de Inventarios](#cu03---gestión-de-inventarios)
   - [CU04 - Registro de Movimientos de Stock](#cu04---registro-de-movimientos-de-stock)
   - [CU05 - Generación de Reportes](#cu05---generación-de-reportes)
   - [CU06 - Configuración de Alertas de Stock Bajo](#cu06---configuración-de-alertas-de-stock-bajo)
   - [CU07 - Gestión de Roles y Permisos](#cu07---gestión-de-roles-y-permisos)
5. [Glosario](#glosario)
6. [Aprobaciones](#aprobaciones)
7. [Historial de Versiones](#historial-de-versiones)

---

## **Introducción**
Este documento describe los casos de uso del sistema **SmartStock**, detallando las interacciones entre los actores y el sistema para garantizar una correcta implementación de los requisitos.

## **Actores**
- **Usuario Invitado:** Puede registrarse en el sistema, pero no tiene acceso hasta que sea aprobado por la empresa.
- **Empleado:** Puede gestionar el inventario y registrar movimientos de stock.
- **Administrador:** Gestiona usuarios, permisos, reportes y alertas.

## **Diagrama de Casos de Uso**
![UML - Diagrama Casos De Uso de SmartStock](https://imgur.com/a/gEtKAEA)


---

## **Casos de Uso**

### **CU01 - Registro de Usuario**
**Descripción:** Un usuario se registra proporcionando su información personal.

**Actores:** Usuario Invitado

**Flujo Principal:**
1. El usuario accede al formulario de registro.
2. Introduce su correo electrónico (solo Gmail u Outlook) y una contraseña segura.
3. Completa los datos requeridos.
4. Envía la solicitud.
5. El sistema valida la información y crea el usuario con rol "Invitado".
6. La empresa revisa la solicitud y aprueba o rechaza el acceso.

---

### **CU02 - Inicio de Sesión**
**Descripción:** Un usuario inicia sesión en el sistema.

**Actores:** Todos los usuarios registrados.

**Flujo Principal:**
1. El usuario accede a la pantalla de inicio de sesión.
2. Introduce su correo y contraseña.
3. El sistema valida las credenciales.
4. Si son correctas, accede al sistema con su rol correspondiente.

---

### **CU03 - Gestión de Inventarios**
**Descripción:** El usuario administra productos y categorías del inventario.

**Actores:** Administrador, Empleado.

**Flujo Principal:**
1. El usuario accede al módulo de inventarios.
2. Puede registrar, modificar o eliminar productos y categorías.
3. Se permite agregar una imagen al producto.
4. El sistema actualiza los datos en la base de datos.

---

### **CU04 - Registro de Movimientos de Stock**
**Descripción:** Se registran entradas y salidas de productos.

**Actores:** Administrador, Empleado.

**Flujo Principal:**
1. El usuario accede al módulo de movimientos de stock.
2. Selecciona un producto y el tipo de movimiento (entrada o salida).
3. Introduce la cantidad y confirma la acción.
4. El sistema actualiza el inventario.

---

### **CU05 - Generación de Reportes**
**Descripción:** Se generan reportes de productos más vendidos y stock bajo.

**Actores:** Administrador.

**Flujo Principal:**
1. El usuario accede al módulo de reportes.
2. Selecciona el tipo de reporte (más vendidos, stock bajo o en 0).
3. Se visualiza una tabla con degradación de colores (verde a rojo).
4. Puede exportar el reporte en PDF o Excel.

---

### **CU06 - Configuración de Alertas de Stock Bajo**
**Descripción:** Configuración y personalización de alertas de stock bajo.

**Actores:** Administrador.

**Flujo Principal:**
1. El usuario accede al módulo de alertas.
2. Configura los umbrales de stock mínimo.
3. Define si las alertas se enviarán por correo o solo en la aplicación.
4. Guarda la configuración.

---

### **CU07 - Gestión de Roles y Permisos**
**Descripción:** El administrador gestiona los roles y permisos de los usuarios.

**Actores:** Administrador.

**Flujo Principal:**
1. Accede al módulo de gestión de usuarios.
2. Crea nuevos roles o edita roles existentes.
3. Define los permisos asociados a cada rol.
4. Guarda la configuración.

---

## **Glosario**
- **CRUD:** Operaciones de Crear, Leer, Actualizar y Eliminar.
- **Stock:** Cantidad disponible de un producto en inventario.
- **Usuario Invitado:** Usuario sin permisos hasta que la empresa lo apruebe.
- **Administrador:** Usuario con control total sobre la aplicación.

---

## **Aprobaciones**
| **Rol**             | **Nombre**         | **Fecha**   | **Firma**       |
|----------------------|--------------------|-------------|-----------------|
| Product Owner        | SmartStock         | 15/10/2023  | [Digital]       |
| Líder Técnico        | [Nombre]           | [Fecha]     | [Firma]         |

---

## **Historial de Versiones**
| **Versión** | **Fecha**   | **Cambios**                     | **Autor**      |
|-------------|-------------|---------------------------------|----------------|
| 1.0         | 10/10/2023  | Versión inicial                 | SmartStock     |
| 1.1         | [Fecha]     | Se añaden CU05 a CU07           | [Autor]        |
