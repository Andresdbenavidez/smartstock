# **Documento de Requisitos de Software - SmartStock**

## **Tabla de Contenidos**
1. [Introducción](#1-introducción)  
2. [Requisitos Funcionales](#2-requisitos-funcionales)  
3. [Requisitos No Funcionales](#3-requisitos-no-funcionales)  
4. [Requisitos de Hardware y Software](#4-requisitos-de-hardware-y-software)  
5. [Glosario](#5-glosario)  
6. [Aprobaciones](#6-aprobaciones)  
7. [Historial de Versiones](#7-historial-de-versiones)  

---

## **1. Introducción**

### **1.1 Propósito**
Este documento define los requisitos para **SmartStock**, un sistema de gestión de inventarios orientado a pequeñas y medianas empresas. Servirá como guía técnica para desarrolladores, equipo de QA y stakeholders.

### **1.2 Alcance**
**Incluye**:  
- Gestión de usuarios y roles  
- Control de inventario en tiempo real  
- Módulo de reportes y análisis  
- Integración básica con proveedores  
- Sistema de alertas y notificaciones  

**Excluye**:  
- Facturación electrónica  
- Integración con hardware personalizado  
- Soporte para múltiples almacenes  

### **1.3 Definiciones y Acrónimos**
- **SKU**: Código único de identificación de productos  
- **UI**: Interfaz de usuario  
- **API**: Interfaz de programación de aplicaciones  

---

## **2. Requisitos Funcionales**

### **RF-01 - Gestión de Usuarios**
| **Atributo**       | **Detalle**                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| **Código**          | RF-01                                                                       |
| **Nombre**          | Registro y Administración de Usuarios                                       |
| **Descripción**     | Permite crear, editar y desactivar cuentas de usuarios con validación de datos. |
| **Entradas**        | Nombre, correo, contraseña, rol                                             |
| **Salidas**         | Confirmación de operación, correo de bienvenida (para nuevos usuarios)      |
| **Restricciones**   | - Formato de correo válido (RFC 5322)<br>- Contraseña: 8+ caracteres, 1 mayúscula y 1 número |
| **Prioridad**       | Alta                                                                        |

### **RF-02 - Autenticación y Seguridad**
| **Atributo**       | **Detalle**                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| **Código**          | RF-02                                                                       |
| **Nombre**          | Sistema de Autenticación                                                    |
| **Descripción**     | Mecanismo de inicio de sesión con protección contra ataques brutos.         |
| **Flujo**           | 1. Usuario ingresa credenciales<br>2. Sistema valida contra DB<br>3. Bloquea tras 5 intentos fallidos |
| **Restricciones**   | Sesiones expiran tras 30 minutos de inactividad                             |

### **RF-03 - Gestión de Roles y Permisos**
| **Rol**         | **Permisos**                                                               | **Restricciones**                          |
|------------------|---------------------------------------------------------------------------|--------------------------------------------|
| Administrador    | - Crear/eliminar usuarios<br>- Configurar sistema<br>- Acceso total       | Solo 1 administrador por organización     |
| Gerente          | - Generar reportes<br>- Ajustar inventario<br>- Ver dashboards            | Sin acceso a configuración del sistema    |
| Empleado         | - Registrar entradas/salidas<br>- Consultar stock                         | Solo operaciones asignadas                |

---

## **3. Requisitos No Funcionales**

### **RNF-01 - Rendimiento**
| **Parámetro**       | **Especificación**                                  |
|----------------------|----------------------------------------------------|
| Tiempo de Respuesta  | < 2 segundos para 95% de las transacciones         |
| Usuarios Concurrentes| Soporte para 150+ usuarios simultáneos             |
| Carga de Datos       | Importación de CSV (hasta 10,000 registros en <1 min)|

### **RNF-02 - Seguridad**
| **Aspecto**          | **Implementación**                                |
|----------------------|----------------------------------------------------|
| Cifrado de Datos     | AES-256 para datos sensibles                       |
| Protocolos           | HTTPS obligatorio, TLS 1.2+                        |
| Auditoría            | Log de todas las operaciones críticas (WHOIS)      |

### **RNF-03 - Usabilidad**
- **UI Responsive**: Compatible con móviles y tablets  
- **Curva de Aprendizaje**: <30 minutos para usuarios básicos  
- **Documentación**: Manual interactivo integrado en la UI  

---

## **4. Requisitos de Hardware y Software**

### **4.1 Entorno de Producción**
| **Componente**       | **Especificación**                                |
|----------------------|----------------------------------------------------|
| Servidor Web         | - 4 vCPU<br>- 8 GB RAM<br>- 200 GB SSD (AWS EC2 t3.large o equivalente) |
| Base de Datos        | MySQL 8.0 con replicación maestro-esclavo          |
| Backup               | Diario + incrementales cada 6 horas (retención: 30 días) |

### **4.2 Clientes**
- **Navegadores**: Chrome 90+, Firefox 88+, Edge 90+  
- **Sistemas Operativos**: Windows 10+, macOS 10.15+, Linux Ubuntu 20.04+  
- **Dispositivos Móviles**: Android 9+, iOS 13+ (solo consultas)  

---

## **5. Glosario**
- **JWT**: JSON Web Token - Estándar para autenticación  
- **CSV**: Valores Separados por Comas - Formato de importación de datos  
- **SLA**: Acuerdo de Nivel de Servicio - 99.5% de disponibilidad  

---

## **6. Aprobaciones**
| **Rol**             | **Nombre**         | **Fecha**   | **Firma**       |
|----------------------|--------------------|-------------|-----------------|
| Product Owner        | SmartStock         | 15/10/2023  | [Digital]       |
| Líder Técnico        | [Nombre]           | [Fecha]     | [Firma]         |

---

## **7. Historial de Versiones**
| **Versión** | **Fecha**   | **Cambios**                     | **Autor**      |
|-------------|-------------|---------------------------------|----------------|
| 1.0         | 10/10/2023  | Versión inicial                 | SmartStock     |
| 1.1         | [Fecha]     | Se añaden RF-08 a RF-12         | [Autor]        |