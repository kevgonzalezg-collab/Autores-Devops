# Microservicio Autores — Evaluación Parcial 1 (DOY0101)

Este repositorio contiene la implementación del microservicio de gestión de **Autores**, desarrollado como parte de la Evaluación Parcial 1 de la asignatura **Ingeniería DevOps (DOY0101)**.

El proyecto demuestra buenas prácticas de desarrollo y operaciones, incluyendo versionado estructurado de código, gestión del código mediante Git y GitHub y preparación para procesos de Integración Continua (CI).

---

## 👤 Autor

* **Kevis Howard González**
* **Asignatura:** Ingeniería DevOps (DOY0101)

---

## 🛠️ Stack Tecnológico

* **Lenguaje:** Java 17
* **Framework:** Spring Boot
* **Gestor de Dependencias:** Apache Maven
* **Control de Versiones:** Git & GitHub
* **CI/CD:** GitHub Actions

---

## 1. Justificación del Modelo de Ramificación (GitFlow)

Para este proyecto se implementó la estrategia **GitFlow** debido a las siguientes razones técnicas:

* **Separación de entornos:** Mantiene el código estable y listo para producción aislado en la rama `main`, mientras que la integración de cambios se realiza en `develop`.

* **Control mediante Pull Requests:** Permite revisar y auditar cada cambio antes de ser fusionado, reduciendo riesgos de errores en las ramas principales.

* **Aislamiento de funcionalidades:** Las nuevas funcionalidades o mejoras se desarrollan en ramas `feature/*`, creadas desde `develop`, y posteriormente se integran mediante Pull Requests.

* **Manejo de incidentes:** Las correcciones urgentes se desarrollan en ramas `hotfix/*`, creadas desde `main`, y posteriormente se integran mediante Pull Request.

---

## 📋 2. Buenas Prácticas y Convenciones

### Naming de Ramas

* `main`: Código principal, estable y probado.
* `develop`: Rama base de desarrollo e integración.
* `feature/<nombre>`: Nuevas funcionalidades o mejoras.
* `hotfix/<nombre>`: Correcciones urgentes.

### Convenciones de Commits

Los mensajes de commit siguen el formato:

`<tipo>: <descripción>`

* `feat:` Nueva funcionalidad.
* `fix:` Corrección de errores.
* `docs:` Cambios en la documentación.
* `ci:` Modificaciones relacionadas con GitHub Actions.

### Flujo de Integración

* No se realizan cambios directamente sobre `main` o `develop`.
* Los cambios se desarrollan en ramas auxiliares.
* Las funcionalidades se integran mediante Pull Requests hacia `develop`.
* Los hotfix se integran mediante Pull Requests hacia `main`.
* Después de un hotfix, los cambios deben mantenerse sincronizados con `develop`.

---

## ⚙️ 3. Automatización con GitHub Actions

Se implementó un pipeline en `.github/workflows/ci.yml` configurado con los siguientes disparadores:

* `push` hacia la rama `develop`.
* `pull_request` hacia la rama `main`.

El pipeline descarga el código fuente, configura el entorno Java y ejecuta Maven para comprobar automáticamente que el proyecto pueda compilar correctamente.

Esto permite detectar errores antes de integrar los cambios a las ramas principales.

---

## 📝 4. Reflexión Individual de Aprendizaje

### Kevis Howard González

En este encargo apliqué los conceptos fundamentales de DevOps gestionando el ciclo de vida de un microservicio Spring Boot. Aprendí a utilizar Git de forma profesional mediante la estrategia GitFlow, comprendiendo el rol de aislar ramas para proteger el código productivo en `main` y colaborar mediante Pull Requests.

Además, comprendí cómo configurar e implementar la integración continua usando GitHub Actions para automatizar tareas con eventos de push y pull request. Mi aporte personal abarcó la totalidad del desarrollo: la preparación del microservicio, la inicialización del repositorio, la creación y fusión de ramas (`feature` y `hotfix`) y la configuración del archivo CI.
