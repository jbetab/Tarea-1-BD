# Red Social Pascualina — Modelo conceptual de base de datos

Reto 1 del curso de Bases de Datos: diseño del modelo entidad-relación (MER) que soportará una red social estudiantil.

## Integrantes del equipo

| Integrante | Rol |
|---|---|
| Jerónimo Betancur | Análisis, modelado MER y documentación |

## Descripción del caso

La comunidad estudiantil cuenta con plataformas institucionales, pero son formales y no facilitan la conexión casual entre pares: el intercambio de conocimiento, la formación de grupos de estudio o la organización de actividades informales. La Red Social Pascualina busca cubrir ese vacío con un espacio donde los estudiantes puedan crear un perfil con su área de estudio, intereses y habilidades; encontrar y seguir a compañeros afines o a estudiantes de cursos avanzados que ofrezcan mentoría; publicar preguntas sobre tareas, recursos y noticias, y comentarlos o reaccionar a ellos; crear grupos de estudio, equipos para hackatones o clubes de interés y unirse a ellos; y programar eventos como reuniones de estudio, talleres o actividades sociales, confirmando asistencia.

El reto consiste en diseñar la base de datos que soporta esas cinco necesidades. Este repositorio entrega el **modelo conceptual**: identificación de entidades, atributos, relaciones y cardinalidades, con la justificación de cada decisión de modelado. Quedan fuera del alcance el modelo lógico, el modelo físico y la implementación.

El modelo resultante tiene **13 entidades y 19 relaciones**, expresadas en **notación pata de gallo (crow's foot)**. `ESTUDIANTE` es la entidad central; las relaciones muchos a muchos —intereses, habilidades, seguimiento, membresías, asistencias y reacciones— se resuelven mediante entidades asociativas que además almacenan los atributos propios de cada vínculo.

## Contenido del repositorio

| Archivo | Descripción |
|---|---|
| `MER_Red_Social_Pascualina.drawio` | Diagrama editable para draw.io / diagrams.net |
| `MER_Red_Social_Pascualina.png` | Diagrama en alta resolución para presentaciones |
| `MER_Red_Social_Pascualina.svg` | Diagrama vectorial |
| `MER_Red_Social_Pascualina.html` | Versión web del diagrama con tablas de apoyo |
| `Memoria_MER_Red_Social_Pascualina.docx` | Memoria justificativa: análisis de necesidades, criterios de modelado, diccionario de datos, cardinalidades, decisiones y reglas de negocio |

## Cómo leer el diagrama

Los símbolos de cardinalidad se leen en el extremo cercano a cada entidad e indican cuántas ocurrencias de **esa** entidad participan en la relación:

| Símbolo | Significado |
|---|---|
| Raya perpendicular | Uno y sólo uno — (1,1) |
| Círculo + raya | Cero o uno — (0,1) |
| Pata de gallo + raya | Uno o muchos — (1,N) |
| Pata de gallo + círculo | Cero o muchos — (0,N) |

En los atributos, `PK` marca la llave primaria, `FK` la llave foránea, `PK,FK` los componentes de una clave compuesta heredada y `U` los atributos de valor único. Las entidades en gris son las que resuelven relaciones muchos a muchos.
