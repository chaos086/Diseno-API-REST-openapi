# 📌 API PQRS - Sistema de Gestión de Solicitudes

## 📖 Descripción del Proyecto

Este proyecto corresponde al desarrollo de un sistema de **Peticiones, Quejas, Reclamos y Sugerencias (PQRS)** para la **Universidad del Quindío**, implementado como parte del curso de **Programación Avanzada**.

El sistema permite a estudiantes, docentes y personal administrativo registrar solicitudes que posteriormente son gestionadas por coordinadores y profesores responsables hasta su resolución.

La solución está diseñada bajo principios de **Domain-Driven Design (DDD)** y una **arquitectura hexagonal**, lo que garantiza:

* Alta mantenibilidad
* Separación de responsabilidades
* Escalabilidad del sistema

---

## 🧩 Arquitectura y Enfoque

### 🔷 Arquitectura

* **Hexagonal (Ports & Adapters)**
* Separación clara entre dominio, aplicación e infraestructura

### 🔷 Patrón utilizado

* **Domain-First (DTOs basados en el dominio)**

### 🔷 Agregados principales

* **Usuario** → Manejo de roles y estados
* **Solicitud** → Gestión completa del ciclo de vida
* **Historial** → Auditoría de todas las acciones

---

## 🔄 Ciclo de Vida de una Solicitud

Las solicitudes siguen el siguiente flujo:

```
REGISTRADA → CLASIFICADA → EN_ATENCION → ATENDIDA → CERRADA
```

Cada transición está controlada por reglas de negocio específicas, por ejemplo:

* Solo solicitudes **REGISTRADAS** pueden clasificarse
* Solo el responsable asignado puede marcar como **ATENDIDA**
* Una solicitud **CERRADA** no puede modificarse

---

## 👥 Roles del Sistema

El sistema maneja diferentes tipos de usuarios:

* **ESTUDIANTE**
* **PROFESOR**
* **ADMINISTRATIVO**
* **COORDINADOR**

Cada uno tiene responsabilidades específicas dentro del flujo de las solicitudes.

---

## ⚙️ Funcionalidades Principales

### 👤 Usuarios

* Crear usuarios
* Activar / desactivar usuarios
* Consultar información

### 📄 Solicitudes

* Crear solicitudes
* Clasificar y priorizar
* Asignar responsables
* Atender y cerrar solicitudes

### 📊 Historial

* Registro completo de auditoría
* Consulta por:

  * Usuario
  * Solicitud
  * Tipo de acción

---

## 📌 Reglas de Negocio Destacadas

* Un usuario no puede tener más de **5 solicitudes pendientes**
* Un profesor no puede tener más de **10 solicitudes en atención**
* Las transiciones de estado son estrictas
* Validaciones de longitud en descripciones y justificaciones

---

## 🚀 Cómo visualizar la API

Para entender mejor la estructura y probar los endpoints, puedes usar Swagger Editor:

🔗 https://editor.swagger.io/

### Pasos:

1. Copia el archivo OpenAPI (YAML)
2. Pégalo en el editor
3. Explora los endpoints y modelos interactivos

---

## 🛠️ Tecnologías y Conceptos

* OpenAPI 3.0.3
* REST API
* Domain-Driven Design (DDD)
* Arquitectura Hexagonal
* DTOs

---

## 👨‍💻 Integrantes

* María José Vásquez Betancur
* Diego Hernán Giraldo Cifuentes
* Jack Alejandro Marín Hernández

---

## 📌 Notas Finales

Este proyecto no solo busca implementar una API funcional, sino también aplicar buenas prácticas de diseño de software, enfocándose en la claridad del dominio y la correcta separación de capas.

Es una base sólida para sistemas empresariales que requieren trazabilidad, control de procesos y escalabilidad.
