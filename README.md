# Microservicio Autores — Evaluación Parcial 1 (DOY0101)

Este repositorio contiene la implementación del microservicio de gestión de **Autores**, desarrollado como parte de la Evaluación Parcial 1 de la asignatura **Ingeniería DevOps (DOY0101)**.

El proyecto demuestra las mejores prácticas de desarrollo y operaciones: versionado estructurado de código, gestión automatizada de esquemas de base de datos y preparación para pipelines de Integración Continua (CI).

---

## 👤 Autor

* **Kevis Howard González**
* **Asignatura:** Ingeniería DevOps (DOY0101)

---
### Stack Tecnológico
* **Lenguaje:** Java 17
* **Framework:** Spring Boot
* **Gestor de Dependencias:** Apache Maven
* **Control de Versiones:** Git & GitHub
* **CI/CD:** GitHub Actions

---

## 2. Justificación Técnica del Modelo GitFlow
Para este proyecto se implementó la estrategia de ramificación **GitFlow**, respondiendo a los siguientes criterios técnicos y de estabilidad:

* **Separación de Entornos (`main` vs `develop`):**
   * `main`: Rama estrictamente protegida que contiene únicamente código estable, compilado y validado, representativo del entorno de 
   * .
   * `develop`: Rama central de integración continua donde convergen las nuevas características antes de pasar a producción.
* **Aislamiento de Funcionalidades (`feature/*`):**
   * Toda nueva funcionalidad o mejora (como `feature/actualizar-documentacion` y `feature/mejora-dto`) se desarrolla en ramas aisladas que 
   * nacen y se fusionan exclusivamente hacia `develop` mediante Pull Requests.
   * Esto evita el impacto directo sobre código en producción y previene conflictos concurrentes.
* **Gestión de Contingencias (`hotfix/*`):**
   * Ante incidencias críticas detectadas en el entorno productivo, se ramifica directamente desde `main` (ej. `hotfix/ajuste-puerto`). Al resolverse, el cambio se integra a `main` desencadenando la validación del pipeline y asegurando la continuidad operativa del servicio.

---

## 3. Pipeline de Integración (GitHub Actions)
La automatización se configuró en el archivo `.github/workflows/ci.yml`. Sus funciones principales son:
* **Disparadores (Triggers):**
   * Se ejecuta automáticamente tras cada `push` hacia la rama `develop`.
   * Se activa ante cada evento `pull_request` con destino a la rama `main`.
* **Fases del Job:**
   1. *Checkout del repositorio:* Descarga del código fuente en el runner `ubuntu-latest`.
   2. *Setup JDK 17:* Configuración del entorno de ejecución Java con Temurin y caché de dependencias Maven.
   3. *Build y Validación:* Ejecución de `./mvnw clean compile test` para garantizar que no existan errores de sintaxis, 
  4. dependencias rotas o fallos en pruebas unitarias antes de autorizar fusiones.

---

## 4. Reflexión Ética y Profesional sobre DevOps
La implementación de una cultura DevOps va más allá de la simple automatización de herramientas; representa un compromiso directo 
con la calidad, la seguridad y la transparencia del software entregado al usuario final.



* **Responsabilidad Profesional:** Automatizar pruebas y compilaciones tempranas previene que fallos estructurales lleguen a producción,
* garantizando la continuidad operativa y la confiabilidad del servicio.
* **Ética y Gobernanza:** Establecer revisiones por medio de Pull Requests y control de versiones asegura trazabilidad absoluta sobre qué
* cambios se aplican, quién los autoriza y por qué motivo, evitando malas prácticas o vulnerabilidades no auditadas en los sistemas.