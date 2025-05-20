# Practica 2

## 🎓 Sistema de Evaluación Docente - Universidad

Este proyecto es una **aplicación web desarrollada en Java con Spring Boot** orientada a gestionar los procesos académicos relacionados con la **evaluación docente** dentro de una universidad. El sistema permite registrar estudiantes, materias, docentes y evaluaciones, además de gestionar la autenticación de usuarios mediante un sistema de seguridad robusto basado en JWT (JSON Web Tokens).

La aplicación está diseñada para ser escalable, modular y segura, dividiendo la lógica en capas bien definidas bajo principios de **arquitectura limpia**, **programación orientada a objetos**, y **buenas prácticas de desarrollo backend**.

### 🧩 Características principales

* 📋 **Gestión de estudiantes:** Registro, validación y consulta de información estudiantil.
* 📘 **Administración de materias:** Creación y edición de asignaturas vinculadas a los docentes.
* 🧑‍🏫 **Módulo de docentes:** Registro de docentes y asociación con materias y evaluaciones.
* ✅ **Evaluación docente:** Registro y procesamiento de evaluaciones realizadas por estudiantes a los docentes.
* 🔐 **Autenticación y autorización:** Sistema de login y roles (usuarios y administradores) con seguridad basada en JWT.
* 🛡️ **Validaciones y manejo de errores:** Implementación de validaciones personalizadas y gestión global de excepciones.
* 📦 **API RESTful:** Diseño claro y estructurado de endpoints para facilitar la integración con frontend u otros servicios.
* 📚 **Documentación Swagger:** Integración de Swagger para visualizar y probar los endpoints de forma interactiva.

### 🏗️ Estructura del proyecto

La aplicación está organizada en paquetes que representan distintos módulos funcionales:

#### 🔹 `controller/`

Contiene los controladores REST que gestionan las peticiones HTTP entrantes y devuelven respuestas JSON. Cada entidad principal (Estudiante, Materia, Evaluación, etc.) tiene su propio controlador.

#### 🔹 `dto/`

Los DTO (Data Transfer Objects) son clases intermedias entre el modelo y la capa de presentación, utilizados para estructurar los datos que se envían y reciben en la API.

#### 🔹 `model/`

Define las entidades JPA que representan las tablas de la base de datos: estudiantes, docentes, materias, evaluaciones, usuarios, roles, etc.

#### 🔹 `repository/`

Contiene las interfaces que extienden `JpaRepository`, permitiendo el acceso y manipulación de datos en la base de datos de forma abstracta y eficiente.

#### 🔹 `service/`

Define la lógica de negocio de la aplicación. Contiene interfaces y clases `impl` que encapsulan las operaciones relacionadas con las entidades principales.

#### 🔹 `registro/`

Este módulo maneja la seguridad y autenticación de usuarios:

* `config/`: Configuración del sistema, como seguridad (JWT), Swagger y carga inicial de datos.
* `controller/`: Endpoints para autenticación (login, registro de usuario).
* `model/`: Entidades relacionadas con usuarios y roles.
* `repository/`: Repositorios para usuarios y roles.
* `security/`: Filtros y utilidades para la validación de tokens JWT.
* `service/`: Servicio que implementa la lógica de autenticación y autorización.

#### 🔹 `validation/`

Contiene clases para validar datos personalizados y manejar errores globales en toda la aplicación.

### ⚙️ Tecnologías utilizadas

* **Java 17**
* **Spring Boot**
* **Spring Security**
* **JWT (JSON Web Tokens)**
* **JPA / Hibernate**
* **H2 / PostgreSQL / MySQL** (dependiendo de configuración)
* **Swagger/OpenAPI**
* **Maven**

### 🚀 Cómo iniciar el proyecto

1. Clona el repositorio.
2. Configura la base de datos en el archivo `src/main/resources/application.properties`.
3. Ejecuta el proyecto con tu IDE o mediante:

```bash
./mvnw spring-boot:run
```

4. Accede a Swagger para probar la API en:

```
http://localhost:8080/swagger-ui.html
```

### 📌 Notas finales

Este proyecto es una base sólida para aplicaciones universitarias que requieran procesos de gestión académica, autenticación segura y evaluaciones internas. Puede ser extendido fácilmente para incluir funcionalidades como generación de reportes, notificaciones, historial académico, entre otras.