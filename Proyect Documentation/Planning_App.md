# Planning_App

[Descargar este documento](Planning_App.md)

## 1. Propósito del proyecto
Desarrollar una aplicación web orientada al control de estudios y al récord académico, pensada como un sistema de gestión institucional para inscribir estudiantes, administrar evaluaciones, generar reportes y mantener trazabilidad del proceso académico.

## 2. Objetivo general
Implementar una plataforma que permita registrar, consultar y administrar la información académica de estudiantes, docentes y personal administrativo desde un entorno web accesible desde escritorio, tablet o teléfono.

## 3. Alcance inicial
El sistema abarcará, en una primera etapa, los procesos de:
- Inscripción de nuevos alumnos.
- Validación y aplicación de prelaciones de materias.
- Agrupación de estudiantes por año y sección.
- Gestión de evaluaciones continuas.
- Registro y transcripción de notas.
- Preparación y seguimiento de exámenes finales.
- Generación de reportes, constancias y récord académico.
- Comunicación institucional mediante un área de anuncios y observaciones.

## 4. Usuarios principales
- Control de Estudios / Dirección Académica.
- Docentes y profesores.
- Estudiantes.
- Administradores del sistema.

## 5. Reglas de negocio clave
- El docente no podrá publicar notas sin verificación previa de Control de Estudios o Dirección Académica.
- El docente es responsable de planificar y publicar a tiempo sus evaluaciones continuas.
- Cada evaluación continua debe registrar la nota mínima aprobatoria.
- Toda evaluación continua debe contar con un campo obligatorio de observación o detalle.
- La tabla de alumnos debe incluir los campos:
  - registration_process
  - continuing_education_program
  - course_of_study
- El esquema del nombre del alumno debe separarse en:
  - primer_nombre
  - segundo_nombre
  - primer_apellido
  - segundo_apellido
- Todas las tablas deben incluir un campo id autoincrementable.
- Todas las tablas deben contar con historial de auditoría para operaciones de inserción, actualización y eliminación.

## 6. Flujo de trabajo propuesto
1. Registro y validación de alumnos.
2. Inscripción al período académico actual.
3. Aplicación de prelación cuando sea necesaria.
4. Asignación a grupos, años y secciones.
5. Planificación de evaluaciones continuas por parte del docente.
6. Publicación y verificación de notas.
7. Registro de notas finales y generación de récord.
8. Emisión de reportes, constancias y comunicaciones institucionales.

## 7. Módulos funcionales
### 7.1 Gestión de alumnos
- Registro de datos personales.
- Gestión de modalidad de inscripción.
- Gestión de régimen de estudio y continuidad institucional.
- Historial académico.

### 7.2 Gestión académica
- Catálogo de carreras, períodos, materias y secciones.
- Prelaciones entre materias.
- Asignación de estudiantes a grupos.

### 7.3 Evaluaciones continuas
- Creación de evaluaciones por materia.
- Definición de porcentaje, nota mínima aprobatoria y descripción obligatoria.
- Aprobación y publicación controlada.

### 7.4 Exámenes finales
- Planeación de fechas y jornadas.
- Captura de resultados finales.
- Transcripción al récord académico.

### 7.5 Reportes y constancias
- Reportes académicos personalizados.
- Encabezado y pie de página configurables.
- Soporte para logo en encabezado y pie.
- Exportación a PDF o impresión.

### 7.6 Comunicación institucional
- Área de anuncios y observaciones compartidas.
- Historial de publicaciones.
- Notificaciones internas y externas.

## 8. Modelo de datos propuesto
### Base de datos recomendada
- Motor principal: PostgreSQL 16.
- Alternativa: Microsoft SQL Server u Oracle.

### Tablas sugeridas
- users
- roles
- people
- students
- teachers
- academic_periods
- careers
- subjects
- courses
- enrollments
- prerequisites
- groups
- evaluations
- grades
- final_exams
- reports_customization
- announcements
- audit_logs

### Estándares de diseño
- Cada tabla debe tener un campo id.
- Se recomienda usar claves primarias enteras con identidad.
- Todos los cambios deben quedar registrados en tablas de auditoría o columnas de control.
- Se deben definir llaves foráneas para relaciones entre entidades.
- Se recomienda el uso de índices en columnas frecuentes para búsquedas y filtros.

## 9. Personalización de reportes
La tabla report_customization deberá permitir:
- Definir un encabezado con hasta 5 líneas de 80 caracteres.
- Definir un pie de página con hasta 3 líneas de 80 caracteres.
- Cargar imágenes para logo y pie de página.
- Ajustar el formato del reporte según el tipo de documento.

## 10. Internacionalización
Se recomienda soportar los idiomas:
- Español (por defecto)
- Inglés
- Checo

## 11. Arquitectura técnica propuesta
- Frontend: Astro.
- UI adicional: React para componentes interactivos.
- Estilos: Tailwind CSS.
- Backend: Node.js con API REST o GraphQL opcional.
- Base de datos: PostgreSQL 16.
- ORM: Prisma o Drizzle.
- Control de versiones: Git.
- Editor recomendado: Visual Studio Code.
- Contenedores: Docker opcional para entorno de desarrollo.

## 12. Fases de desarrollo
### Fase 1: Fundación
- Configuración del proyecto.
- Diseño de base de datos.
- Autenticación y roles.

### Fase 2: Módulos core
- Gestión de alumnos.
- Gestión académica.
- Inscripción y prelación.

### Fase 3: Evaluaciones y reportes
- Evaluaciones continuas.
- Notas finales.
- Reportes y constancias.

### Fase 4: Comunicación y mejora
- Área de anuncios.
- Optimización UX/UI.
- Implementación de internacionalización.

## 13. Entregables esperados
- Aplicación web funcional.
- Base de datos recreable desde cero.
- Documentación técnica y funcional.
- Prototipos de menú y flujos.
- Reportes configurables.

## 14. Recomendación final
Este proyecto debe construirse con una arquitectura escalable, modular y mantenible, priorizando la claridad del proceso académico y la trazabilidad de todas las operaciones.
