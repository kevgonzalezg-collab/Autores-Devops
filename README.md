# Microservicio Autores — Evaluación Parcial 1 (DOY0101)

Este repositorio contiene la implementación del microservicio de gestión de **Autores**, desarrollado como parte de la Evaluación Parcial 1 de la asignatura **Ingeniería DevOps (DOY0101)**.

El proyecto demuestra las mejores prácticas de desarrollo y operaciones: versionado estructurado de código, gestión automatizada de esquemas de base de datos y preparación para pipelines de Integración Continua (CI).

---

## 👤 Autor

* **Kevis Howard González**
* **Asignatura:** Ingeniería DevOps (DOY0101)

---
---

## 🏗️ Justificación del Modelo de Ramificación (GitFlow)

Para este proyecto se implementó la estrategia **GitFlow** debido a las siguientes razones técnicas:
* **Separación de entornos:** Mantiene el código estable y listo para producción aislado en la rama `main`, mientras que la integración continua de cambios se realiza en `develop`.
* **Control mediante Pull Requests:** Permite auditar y revisar cada cambio antes de ser fusionado, reduciendo riesgos de errores en la rama principal.
* **Manejo estructurado de incidentes:** Facilita la creación de ramas temporales `feature/*` para nuevas funcionalidades y `hotfix/*` para correcciones urgentes directas sobre `main`.

---

## 📋 Guía de Buenas Prácticas y Convenciones

### Naming de Ramas
* `main`: Código productivo, estable y probado.
* `develop`: Rama base de desarrollo e integración.
* `feature/<nombre>`: Funcionalidades nuevas (ejemplo: `feature/actualizar-documentacion`).
* `hotfix/<nombre>`: Correcciones críticas en producción (ejemplo: `hotfix/corregir-puerto`).

### Convenciones de Commits (Conventional Commits)
Los mensajes de commit siguen el formato estándar: `<tipo>: <descripción>`
* `feat:` Nueva funcionalidad añadida.
* `fix:` Corrección de fallos o errores.
* `docs:` Cambios o mejoras en la documentación.
* `ci:` Modificaciones en flujos de automatización (GitHub Actions).

### Flujo de Integración
* Ningún cambio directo a `main` o `develop`.
* Todo cambio se realiza en ramas auxiliares y se integra mediante **Pull Requests**.

---

## ⚙️ Automatización con GitHub Actions

Se implementó un pipeline en `.github/workflows/ci.yml` configurado con los siguientes disparadores (*triggers*):
* `push` hacia la rama `develop`.
* `pull_request` hacia la rama `main`.

**Función en el flujo CI/CD:** Descarga el código fuente, prepara el entorno con OpenJDK 21 (Eclipse Temurin) y compila el microservicio mediante Apache Maven (`mvn clean package -DskipTests`), validando la integridad del proyecto de forma automática.


## 📝 Reflexión Individual de Aprendizaje

### Kevis Howard González
En este encargo apliqué los conceptos fundamentales de DevOps gestionando el ciclo de vida de un 
microservicio Spring Boot. Aprendí a utilizar Git de forma profesional mediante la estrategia GitFlow, 
comprendiendo el rol de aislar ramas para proteger el código productivo en `main` y colaborar mediante Pull Requests. 
Además, comprendí cómo configurar e implementar la integración continua usando GitHub Actions para automatizar 
tareas con eventos de push y pull request. Mi aporte personal abarcó la totalidad del desarrollo: la preparación del 
microservicio, la inicialización del repositorio, la creación y fusión de ramas (`feature` y `hotfix`) y 
la configuración del archivo CI.
```[cite: 3, 5, 6]



