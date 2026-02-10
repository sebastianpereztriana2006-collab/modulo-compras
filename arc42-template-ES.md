---
date: Febrero 2026
title: Arquitectura de Software – Sistema ERP
---

# Documentación de Arquitectura – Sistema ERP

Este documento describe la arquitectura del sistema ERP empresarial utilizando la plantilla arc42.

---

# Introducción y Metas

## Vista de Requerimientos

El sistema ERP permitirá a la empresa gestionar de manera integrada sus procesos de:

- Compras  
- Facturación  
- Inventario y costos  
- Activos fijos  
- Gestión de empleados  
- Reportes ejecutivos (EIS)

El objetivo principal es centralizar la información para mejorar el control operativo, reducir errores manuales y facilitar la toma de decisiones.

## Metas de Calidad

| Prioridad | Meta de Calidad | Descripción |
|----------|-----------------|-------------|
| Alta | Usabilidad | El sistema debe ser fácil de usar para personal administrativo |
| Alta | Disponibilidad | El sistema debe estar disponible durante el horario laboral |
| Media | Seguridad | Protección de datos financieros y de empleados |
| Media | Rendimiento | Respuesta menor a 3 segundos en operaciones comunes |
| Baja | Escalabilidad | Posibilidad de agregar nuevos módulos en el futuro |

## Partes interesadas (Stakeholders)

| Rol | Contacto | Expectativas |
|-----|----------|--------------|
| Gerente General | Dirección | Reportes claros y toma de decisiones |
| Encargado de Compras | Área de compras | Registrar proveedores y órdenes fácilmente |
| Contador | Área financiera | Control de facturación y activos |
| RRHH | Recursos Humanos | Gestión de empleados |
| Administrador TI | Sistemas | Sistema estable y seguro |

---

# Restricciones de la Arquitectura

- El sistema será una aplicación web
- Se utilizará una base de datos relacional
- Debe funcionar en navegadores modernos
- Presupuesto limitado para infraestructura
- Uso de tecnologías open source

---

# Alcance y Contexto del Sistema

## Contexto de Negocio

El ERP interactúa con:

- Proveedores
- Clientes
- Empleados
- Gerencia

El sistema centraliza la información de todas las áreas.

## Contexto Técnico

El sistema estará compuesto por:

- Frontend web
- Backend con API REST
- Base de datos relacional

---

# Estrategia de solución

Se implementará una arquitectura en capas:

1. Capa de presentación (Frontend)
2. Capa de lógica de negocio (Backend)
3. Capa de datos (Base de datos)

Esto permite mantenimiento, escalabilidad y separación de responsabilidades.

---

# Vista de Bloques

## Sistema General de Caja Blanca

**Bloques principales del sistema:**

- Módulo de Compras
- Módulo de Facturación
- Módulo de Inventario
- Módulo de Activos Fijos
- Módulo de Empleados
- Módulo de Reportes (EIS)
- Base de Datos

### Módulo de Compras
Gestiona proveedores y órdenes de compra.

### Módulo de Facturación
Administra facturas emitidas a clientes.

### Módulo de Inventario
Controla productos, stock y costos.

### Módulo de Activos Fijos
Registra bienes de la empresa y su depreciación.

### Módulo de Empleados
Gestiona la información del personal.

### Módulo EIS
Genera reportes ejecutivos y estadísticas.

---

# Vista de Ejecución

## Escenario: Registrar Orden de Compra

1. Usuario ingresa al módulo de compras
2. Crea una orden con productos
3. El sistema valida datos
4. Se guarda en base de datos
5. Se genera número de orden

---

# Vista de Despliegue

## Nivel de infraestructura 1

El sistema se desplegará en:

- Servidor web
- Servidor de base de datos

Los usuarios accederán mediante navegador web.

---

# Conceptos Transversales

## Seguridad
Autenticación mediante usuario y contraseña.

## Control de acceso
Roles: Administrador, Compras, Contador, RRHH, Gerencia.

## Persistencia
Base de datos relacional para almacenar información.

---

# Decisiones de Diseño

- Arquitectura en capas
- Aplicación web centralizada
- Base de datos relacional
- Separación por módulos funcionales

---

# Requerimientos de Calidad

## Escenarios de calidad

**Disponibilidad:** El sistema debe estar disponible al menos el 95% del tiempo laboral.

**Rendimiento:** Las consultas de reportes no deben tardar más de 5 segundos.

**Seguridad:** Solo usuarios autenticados pueden acceder.

---

# Riesgos y deuda técnica

- Falta de experiencia en algunos módulos
- Posibles retrasos en integración entre módulos
- Limitaciones de infraestructura

---

# Glosario

| Término | Definición |
|--------|------------|
| ERP | Sistema de planificación de recursos empresariales |
| Orden de compra | Documento para solicitar productos a un proveedor |
| Factura | Documento de venta a un cliente |
| Inventario | Registro de productos disponibles |
| EIS | Sistema de información ejecutiva |
