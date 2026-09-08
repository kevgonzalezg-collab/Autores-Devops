# Microservicio Autores - DevOps

Este repositorio contiene el trabajo realizado para el microservicio de autores, utilizando herramientas y prácticas de DevOps para organizar el desarrollo y mantener el código controlado.

## 1. Justificación del Modelo de Ramificación

Se decidió utilizar **GitFlow** porque permite organizar mejor el trabajo del equipo y evitar que los cambios en desarrollo afecten directamente al código principal.

Se utilizan diferentes ramas dependiendo del tipo de trabajo:

* `main`: contiene la versión principal y estable del proyecto.
* `develop`: contiene los cambios que están en desarrollo.
* `feature/*`: se utiliza para crear nuevas funcionalidades.
* `hotfix/*`: se utiliza para solucionar problemas importantes.

De esta manera, cada integrante puede trabajar en sus cambios de forma más ordenada y luego integrarlos al proyecto principal.

## 2. Buenas Prácticas y Convenciones

Para mantener el proyecto organizado, se utilizan las siguientes reglas:

### Ramas

* `main`: versión principal.
* `develop`: desarrollo del proyecto.
* `feature/<nombre>`: nuevas funciones.
* `hotfix/<nombre>`: correcciones urgentes.

### Mensajes de Commit

Se utilizan mensajes que permiten entender fácilmente qué cambio se realizó:

* `feat:` para agregar una nueva función.
* `fix:` para corregir un error.
* `docs:` para modificar la documentación.
* `ci:` para cambios relacionados con la automatización.

### Organización de Carpetas

* `.github/workflows/`: contiene la configuración de las acciones automáticas.
* `autores/`: contiene el código del microservicio.

Los cambios importantes deben realizarse mediante **Pull Requests**, permitiendo revisar el código antes de incorporarlo a las ramas principales.

## 3. Pipeline de CI/CD

El proyecto utiliza **GitHub Actions** para realizar algunas tareas automáticamente.

Cada vez que se realizan determinados cambios en el repositorio, se ejecuta un proceso que:

1. Utiliza un sistema Ubuntu.
2. Configura Java 21.
3. Ejecuta Maven.
4. Comprueba que el proyecto pueda compilar correctamente.

Esto ayuda a detectar problemas antes de integrar los cambios al proyecto principal.

## 4. Uso de Inteligencia Artificial

Se utilizó Inteligencia Artificial como apoyo para comprender algunos conceptos, organizar la documentación y revisar comandos utilizados en Git.

Las decisiones finales y el trabajo realizado fueron revisados por los integrantes del equipo.

### Estrategia de Revisión

Los Pull Requests permiten revisar los cambios antes de integrarlos a `develop` o `main`. Se verifica que los cambios correspondan al objetivo de la rama y que no generen problemas en el proyecto.

### 5. Reflexión Individual

**Kevis Howard Gonzalez**

Durante este trabajo aprendí a utilizar Git y GitHub de una manera más ordenada. También aprendí cómo funcionan las ramas y cómo ayudan a organizar los cambios del proyecto. Además, pude conocer mejor herramientas como GitHub Actions y entender cómo se puede comprobar automáticamente que el proyecto funcione correctamente.

Este trabajo me ayudó a comprender mejor cómo se organiza un proyecto de desarrollo y la importancia de mantener el código ordenado y controlado.


