# Requisitos de Kiin v2

## Definiciones & Reglas de Negocio

- **Facultad**. Una facultad es una escuela donde se imparten licenciaturas del mismo área de conocimiento: matemáticas, arquitectura, derecho, antropología, etc. Una facultad por consiguiente, está integrada por carreras del mismo área de conocimiento.

- **Carrera**. Una carrera corresponde a una enseñanza concreta del área de estudios, por ejemplo, en la facultad de matemáticas, la licenciatura en enseñanza de las matemáticas. Una carrera, está asociada con uno o más planes de estudios.
- **Plan de Estudios (PE)**. Un plan de estudios, está ligado a una carrera y está integrada por materias.
- **Materia**. Unidad de enseñanza del plan de estudios, una materia es el conjunto conocimientos, de un área del conocimiento específico de la carrera, y su estructura y naturaleza está dictaminada por el PE correspondiente. La materia es independiente del profesor, y por consiguiente del grupo. Pueden haber varios grupos de la misma materia. Una materia está ubicada en un semestre en concreto en el **PE**. Una materia tiene créditos. Una materia tiene un tipo: Obligatoria (ligada al PE), Optativa (pueden haber varios PE)
- **Profesor**. Un profesor es un experto de una o varias áreas del conocimiento específicas de una o varias carreras. Un profesor por lo tanto puede impartir clases de varias materias de varias carreras. Un profesor puede dar la misma materia a varios grupos. 
- **Grupo**. Conjunto de espacios disponibles que pueden ser ocupados por estudiantes en su inscripción para una materia en específico.
  - Pueden haber varios grupos de la misma materia. 
  - Un grupo tiene asignado un profesor. Por lo tanto un grupo es: Materia-#Grupo-Profesor. 
  - Un grupo además tiene designado sesiones a lo largo de la semana. 
    - Un grupo puede tener más de una sesión al día.
  - Un grupo tiene una modalidad: esta es: Regular o Acompañamiento
- **Sesión**. Intervalo de tiempo asignado, en un día de la semana, en un aula en concreto para la impartición de una materia. Ej. Lunes, 5-6:30, H5.
- **Aula.** Espacio físico designado, en una sesión para la impartición de una materia. Ej. Aula H5.
- **Horario como Materias-Grupos.** Un horario es un conjunto de grupos, donde no hay repetición de materias en los grupos (solo puede haber un grupo de una materia por horario), y no hay conflicto de sesiones entre los grupos (no hay solapamiento de sesiones).
  - Ej: $\{(Geometría, Grupo1, Mendiburu), (POO, Grupo2, Mendoza),\dots \}$
- **Horario como Sesiones**. Conjunto de sesiones derivado de un conjunto de grupos.
  - Ej: $\{(Lunes, 9-11:30, 14-15:30, 17-16:30), (Martes, 12-13:30, 14-15:30), \dots\}$

## Funciones

### Estudiantes

#### Selección inicial

- Un estudiante puede seleccionar su facultad de un listado, y solo su facultad (no puede haber selección múltiple)

- Un estudiante puede seleeccionar su carrera de un listado, y solo su carrera (no puede haber selección múltiple)

- Un estudiante puede seleccionar sus materias correspondientes a su carrera de un listado (selección múltiple: distintos semestres, obligatorias, optativas, libres, acompañamientos, recursamientos)

#### Generación de horarios & Navegación

- El estudiante debe obtener, con base en su selección de materias, todas las posibles combinaciones de sus respectivos grupos, una posible combinación es un horario.

- El estudiante debe poder visualizar los horarios en formato de calendario semanal, donde pueda ver las sesiones como bloques de tiempo.

- El estudiante debe poder visualizar los detalles de cada horario generado: Materias, profesor de la materia, créditos, modalidad, tipo.

- El estudiante puede filtrar los horarios generados por número de materias por horario.

- El estudiante puede visualizar por horario, aquellos grupos/materias que entran en conflicto con el horario actual que está visualizando.

#### Fijación de Profesores y Materias

La fijación de profesores y materias son filtros post-generación, se aplican a los horarios generados, no sobre las materias selecciondas en la selección inicial.

- El estudiante puede "fijar" una materia de su conjunto de materias seleccionadas inicialmente. Esto es, que el sistema mostrará solo los horarios que sí o sí contengan esa materia "fijada".

- El estudiante puede "fijar" un profesor de en una materia. Esto es, que el sistema mostrará solo los horarios que tienen a esa materia, con ese profesor fijado en concreto.
  
  - Nota: este filtro es independiente del filtro de "fijar materia", es decir, si una materia NO es fijada, los horarios en donde no esté la materia donde el profesor fue fijado, no se usará por obviedad, pero si sí está la materia, el filtro hará su trabajo y mostrar solo horarios donde la materia esté siendo impartida por el profesor "fijado".  
  
  - "fijar" un profesor es entonces la unión de materia-profesor, lo adquiere el nombre de pivote.

####  Compartición y exportación Parte I.

- El estudiante puede exportar su horario en formato JPG, PDF, ICS.

- El estudiante puede compartir su horario por medio de un link donde otros pueden ver el horario que estudiante compartió.

### Estudiantes Registrados

#### Compartición y exportación Parte II. 

- El estudiante registrado puede exportar su horario directamente a Google Calendar mediante su cuenta vinculada a su cuenta de Google.

#### Guardados

- El estudiante registrado puede guardar su horario en su cuenta del sistema para futuras consultas sin tener que pasar por el proceso de selección y generado.

- El esutudainte registrado puede ver los horarios que guardó, y puede darles un nombre: "Ej. Opción A, Opción B"

### Administrador

- El administrador debe poder seleccionar la escuela a la que quiere actualizar los datos de su horario de un listado.

- El administrador puede subir/actualizar los datos de los horarios de la escuela previamente seleccionada.
