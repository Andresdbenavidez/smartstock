# ***Documento de Alcance***

Este documento define el alcance del proyecto **SmartStock**, detallando sus características, funcionalidades, usuarios y limitaciones.

## **1. Descripción del Proyecto**
**SmartStock** es un software de gestión de inventarios diseñado para pequeñas empresas. Su objetivo es optimizar el control de productos, minimizar pérdidas y mejorar la eficiencia operativa mediante una plataforma intuitiva y escalable.

## **2. Objetivos del Proyecto**
- Facilitar la administración del inventario mediante un sistema **CRUD** (Crear, Leer, Actualizar, Eliminar).
- Permitir la asignación y gestión de roles con diferentes niveles de permisos.
- Automatizar el seguimiento de entradas y salidas de productos.
- Generar reportes y alertas sobre el estado del inventario.
- Implementar un sistema de autenticación seguro con control de acceso basado en roles.

## **3. Stakeholders (Interesados del Proyecto)**
Los siguientes actores tienen interés directo en el desarrollo y funcionamiento de **SmartStock**:

### **3.1 Internos**
- **Dueño del Proyecto**: Responsable de la dirección y financiamiento del desarrollo.
- **Equipo de Desarrollo**: Programadores, diseñadores y testers encargados de la implementación.
- **Administradores del Sistema**: Usuarios con permisos avanzados para gestionar SmartStock.

### **3.2 Externos**
- **Usuarios Finales**: Empresas que utilizarán SmartStock para gestionar su inventario.
- **Empleados de las Empresas Usuarias**: Personal que interactuará con el sistema para actualizar inventarios y generar reportes.
- **Proveedores**: En caso de futuras integraciones con gestión de pedidos y stock.
- **Entidades Regulatorias**: Si el sistema requiere cumplir con normativas de almacenamiento y trazabilidad.

## **4. Funcionalidades Principales**
- **Gestión de Inventarios**: Registro, actualización y eliminación de productos y categorías.
- **Roles y Permisos**: Creación de administradores y empleados con permisos personalizados.
- **Movimientos de Stock**: Registro de entradas y salidas de productos.
- **Reportes y Alertas**: Generación de informes sobre niveles de stock y productos críticos.
- **Autenticación y Seguridad**: Registro, login y control de acceso basado en roles.
- **Usuarios Invitados**: Los usuarios nuevos se registran como invitados y pueden solicitar acceso a una empresa.

## **5. Usuarios del Sistema**
- **Administrador**: Usuario con control total sobre la configuración, permisos y gestión del inventario.
- **Empleado**: Usuario con permisos limitados para gestionar productos y movimientos de stock.
- **Invitado**: Usuario con acceso restringido que puede solicitar ser agregado a una empresa.

## **6. Alcance del Desarrollo**
- **Plataforma Web**: Accesible desde navegadores modernos.
- **Base de Datos MySQL**: Para almacenamiento seguro de la información.
- **Interfaz Intuitiva**: Diseñada para facilitar la navegación y gestión de inventarios.
- **Escalabilidad**: Preparado para adaptarse a empresas en crecimiento.

## **7. Limitaciones del Proyecto**
- **No incluye versión móvil nativa**: La plataforma estará optimizada para dispositivos móviles, pero no se desarrollará una aplicación móvil en esta fase.
- **Integraciones externas limitadas**: No contempla conexión con sistemas de facturación o ERP en la primera versión.
- **Soporte inicial restringido**: El soporte técnico estará limitado a documentación y asistencia básica.

## **8. Conclusión**
El software **SmartStock** se enfoca en la gestión eficiente de inventarios para pequeñas empresas, asegurando escalabilidad y facilidad de uso. Su desarrollo se ajustará a los objetivos definidos, priorizando las funcionalidades esenciales en su primera versión.

