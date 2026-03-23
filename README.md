# Práctica de POO: Sistema de Alumnos

Este repositorio está pensado como una práctica simple para trabajar dos cosas al mismo tiempo:

1. **Modelado con Programación Orientada a Objetos (POO)**
2. **Flujo básico de trabajo con Git y GitHub**

La idea del ejercicio no es hacer algo profesional, ni productivo, ni completo.  
La idea es practicar, equivocarse, corregir y entender cómo se modelan clases y cómo se trabaja con ramas en un repositorio.

---

## Objetivos del repositorio

Este repositorio tiene dos objetivos principales.

### 1. Practicar POO

Se busca modelar un sistema académico simple que incluya:

- personas
- alumnos
- profesores
- cursos
- inscripciones

El objetivo no es usar frameworks ni bases de datos ni APIs.  
El foco está puesto en:

- pensar clases
- pensar responsabilidades
- definir atributos
- definir métodos
- relacionar objetos
- aplicar encapsulación, abstracción, herencia y polimorfismo

---

### 2. Empezar a entender trabajo con Git

Además del ejercicio de clases, este repo también sirve para practicar un flujo de trabajo básico con Git y GitHub.

Se busca entender:

- qué es una rama
- para qué sirve `main`
- para qué sirve `develop`
- cómo crear branches para features
- cómo abrir un Pull Request
- por qué no se trabaja directo sobre ramas protegidas
- cómo escribir commits razonables
- qué es versionado y qué es SemVer


IMPORTANTE: Antes de trabajar con git, leer las siguiente bibliografia:

- https://www.conventionalcommits.org/en/v1.0.0/

---

## Alcance del ejercicio

Acá solo interesa practicar:

- POO
- modelado
- relaciones entre objetos
- estructura básica del código
- flujo básico de ramas con Git

---

## Conceptos de POO a practicar

El ejercicio está pensado para practicar los 4 pilares clásicos de la POO.

### Encapsulación

Cada objeto debe manejar su propio estado y comportamiento.

Ejemplos:

- un alumno sabe si está activo o no
- un curso sabe qué alumnos tiene
- una inscripción sabe en qué estado está
- un profesor sabe qué cursos dicta

La idea es evitar que todo se modifique “desde afuera” sin criterio.

---

### Abstracción

Cada clase debe representar una idea concreta del dominio.

Ejemplos:

- `Persona` representa lo común a cualquier persona
- `Alumno` representa a un estudiante
- `Profesor` representa a un docente
- `Curso` representa una materia o curso
- `Inscripcion` representa la relación entre un alumno y un curso

La abstracción apunta a modelar bien el problema, no a meter código porque sí.

---

### Herencia

Se espera que exista una clase base con atributos y comportamientos comunes.

Ejemplo sugerido:

- `Persona`
  - `Alumno`
  - `Profesor`

Esto permite evitar duplicación de cosas como:

- nombre
- apellido
- dni
- email

---

### Polimorfismo

Distintas clases pueden responder al mismo mensaje de forma distinta.

Ejemplo:

- `Alumno.presentarse()`
- `Profesor.presentarse()`

Los dos pueden tener el método `presentarse()`, pero cada uno devolver algo diferente.

---

## Enunciado del ejercicio

Se debe modelar un sistema académico simple con las siguientes clases.

---

## Clase `Persona`

Clase base para representar una persona dentro del sistema.

### Atributos sugeridos

- nombre
- apellido
- dni
- email

### Métodos sugeridos

- `nombre_completo()`
- `presentarse()`

### Observación

Esta clase concentra lo común a alumnos y profesores.

---

## Clase `Alumno`

Hereda de `Persona`.

### Atributos sugeridos

- legajo
- activo
- cursos_inscriptos

### Métodos sugeridos

- `inscribirse(curso)`
- `dar_de_baja()`
- `activar()`
- `esta_inscripto(curso)`
- `presentarse()`

### Idea general

Un alumno puede estar activo o inactivo, puede inscribirse a cursos y debe poder validar si ya está o no inscripto en uno.

---

## Clase `Profesor`

Hereda de `Persona`.

### Atributos sugeridos

- legajo_docente
- especialidad
- cursos_dictados

### Métodos sugeridos

- `asignar_curso(curso)`
- `presentarse()`

### Idea general

Un profesor puede dictar uno o más cursos.

---

## Clase `Curso`

Representa una materia o curso.

### Atributos sugeridos

- nombre
- codigo
- cupo_maximo
- profesor
- alumnos_inscriptos

### Métodos sugeridos

- `agregar_alumno(alumno)`
- `quitar_alumno(alumno)`
- `hay_cupo()`
- `cantidad_inscriptos()`
- `asignar_profesor(profesor)`
- `mostrar_alumnos()`

### Idea general

El curso debe poder administrar sus alumnos, validar si hay cupo y tener asignado un profesor.

---

## Clase `Inscripcion`

Representa la inscripción de un alumno a un curso.

### Atributos sugeridos

- alumno
- curso
- estado

### Estados posibles sugeridos

- pendiente
- confirmada
- cancelada

### Métodos sugeridos

- `confirmar()`
- `cancelar()`

### Idea general

Esta clase representa la relación entre alumno y curso.  
Sirve para no dejar la inscripción como una simple lista suelta sin significado.

---

## Reglas mínimas del sistema

El ejercicio debería respetar al menos estas reglas:

1. Un alumno puede inscribirse a varios cursos.
2. Un curso puede tener varios alumnos.
3. Un curso tiene un cupo máximo.
4. No se debe permitir inscribir alumnos si no hay cupo.
5. Un profesor puede estar asignado a uno o más cursos.
6. Un alumno inactivo no debería poder inscribirse.
7. Un alumno no debería poder inscribirse dos veces al mismo curso.

---

## Qué se espera implementar

Se espera que la resolución incluya:

- definición de clases
- constructores
- atributos de instancia
- métodos de instancia
- relaciones entre objetos
- herencia
- polimorfismo
- validaciones básicas
- una pequeña ejecución desde consola para probar que funciona

No hace falta una interfaz gráfica ni una API ni persistencia.

---

## Escenario de ejemplo

Un flujo posible del programa podría ser:

1. crear profesores
2. crear cursos
3. asignar profesores a cursos
4. crear alumnos
5. inscribir alumnos en cursos
6. impedir inscripciones inválidas
7. mostrar información por consola

---

## Operaciones sugeridas para probar

Al resolver el ejercicio, sería ideal probar cosas como:

- crear un alumno
- crear un profesor
- crear un curso
- asignar un profesor a un curso
- inscribir un alumno en un curso
- intentar inscribir un alumno dos veces al mismo curso
- intentar inscribir un alumno inactivo
- intentar inscribir un alumno en un curso sin cupo
- listar alumnos de un curso
- listar cursos de un alumno

---

## Sugerencia de estructura del repo

Una estructura posible podría ser esta:

```bash
poo-alumnos/
├── README.md
├── main.py
├── persona.py
├── alumno.py
├── profesor.py
├── curso.py
└── inscripcion.py