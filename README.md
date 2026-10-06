# Morilla Asociados Arquitectura y Diseño SL

Proyecto académico del Grupo 6, turno de las 15:30, para desarrollar una web corporativa del estudio **Morilla Asociados Arquitectura y Diseño SL**, en la asignatura GSI de la Universidad de Sevilla, curso 2026/2027.

## Objetivo y alcance inicial

La web presentará la identidad del estudio, sus servicios y proyectos de arquitectura y diseño. El trabajo incluye análisis, diseño, implementación y documentación.

Alcance inicial, pendiente de validar con los requisitos del proyecto:

- Inicio con presentación del estudio.
- Servicios de arquitectura y diseño.
- Proyectos destacados.
- Página de contacto. Su contenido y el funcionamiento de un posible formulario se definirán en los requisitos.

## Entorno de trabajo actual

Cada integrante tiene una instalación local de WordPress gestionada con WampServer. GitHub se utiliza para el control de versiones y Jira para organizar tareas y sprints. Las copias completas se exportan con All-in-One WP Migration en formato `.wpress`.


## Organización del repositorio propuesta

Actualmente se dispone de `docs/`, `db/`, `.gitignore` y `README.md`. Se propone renombrar `db/` a `backups/` y añadir documentación de sprints y pruebas cuando se utilice.

| Ruta | Contenido |
| --- | --- |
| `docs/entrevistas/` | Entrevistas y conclusiones. |
| `docs/rem/` | Requisitos, manteniendo el nombre de carpeta actual. Estructurado con REMUS. |
| `docs/uml/` | Diagramas: archivo editable y exportación para consulta. |
| `backups/` | Registro de copias y ubicación de los archivos compartidos. Las copias locales se excluyen de Git. |
| `README.md` | Guía general y acuerdos de trabajo. |

## Puesta en marcha local

### Requisitos

- Git y un editor, por ejemplo Visual Studio Code.
- WampServer instalado, con Apache y el servidor de base de datos activos.
- Una instalación local de WordPress y las versiones acordadas por el grupo.
- All-in-One WP Migration para restaurar las copias compartidas.
- Acceso a la copia integrada que el grupo haya marcado como vigente.

### Obtener la documentación y el código

```bash
git clone https://github.com/mlb3rry/TrabajoGSI.git
cd TrabajoGSI
```

### Preparar WordPress

1. Iniciar WampServer y comprobar que sus servicios están activos.
2. Crear una base de datos local para el proyecto.
3. Instalar WordPress dentro de la carpeta `www` de WampServer; si se utiliza el directorio `wordpress`, la web estará en `http://localhost/wordpress/`.
4. Completar la instalación con los datos de la base de datos local.
5. Instalar All-in-One WP Migration y restaurar la copia integrada vigente según el apartado siguiente.

El panel estará en `http://localhost/wordpress/wp-admin/` si se mantiene ese nombre de directorio. Las credenciales se comunican por un canal privado; no se incluyen en el repositorio.

## Restauración de una copia

1. Confirmar qué copia integrada debe utilizarse en el registro de backups.
2. Exportar una copia de seguridad de la instalación local si contiene trabajo que deba conservarse.
3. En el panel de WordPress, acceder a **All-in-One WP Migration → Importar** y seleccionar el `.wpress` acordado.
4. Revisar la advertencia antes de confirmar: la importación sustituye datos de la instalación de destino; no fusiona cambios de dos instalaciones.
5. Al terminar, acceder con las credenciales correspondientes a la copia importada y revisar los enlaces permanentes si hay problemas de navegación.
6. Comprobar inicio, servicios, proyectos, contacto, imágenes y acceso al panel.

Registrar también la versión del plugin y las condiciones de importación utilizadas. Si una copia no puede importarse por su tamaño o por la configuración del entorno, resolverlo y documentarlo antes de distribuirla como base del sprint.

## Convención de nombres para backups

Formato:

```text
morillaasc_YYYY-MM-DD_HHMM_sNN_tipo_autor.wpress
```

- Fecha y hora de exportación en la zona `Europe/Madrid`, con formato de 24 horas.
- `sNN`: sprint con dos dígitos; usar `s00` para la preparación inicial.
- `tipo`: `local`, `integrada` o `entrega`.
- `autor`: identificador único acordado por el grupo, en minúsculas, sin espacios ni tildes.

| Tipo | Uso | Ejemplo ilustrativo |
| --- | --- | --- |
| `local` | Copia individual; no se considera base común. | `morillaasc_2026-10-06_1100_s00_local_angel.wpress` |
| `integrada` | Copia con los cambios reunidos en la instalación de referencia y comprobados. | `morillaasc_2026-10-09_1800_s01_integrada_angel.wpress` |
| `entrega` | Copia congelada para una entrega académica. | `morillaasc_2026-10-12_1200_s01_entrega_angel.wpress` |


### Almacenamiento y registro

Indicar expresamente qué copia `integrada` es la base vigente. Mantener las entregas y una copia integrada anterior comprobada para poder recuperar el proyecto. Una copia completa puede contener cuentas y otros datos de la web: no publiquen copias sin revisar su contenido.

## Jira

- Mantener `main` como versión revisada de la documentación y del código que se incluya en Git.
- Crear una incidencia por historia o tarea técnica, con responsable y criterios de aceptación.
- Crear ramas con la clave Jira: `feature/SCRUM-6-contacto`, `fix/SCRUM-8-menu` o `docs/SCRUM-9-requisitos`.
- Incluir la clave en commits y títulos de pull request, por ejemplo `SCRUM-6: añadir página de contacto`.
- Solicitar revisión de otro integrante antes de fusionar en `main`.
- Enlazar la pull request desde Jira y la incidencia desde la descripción de la pull request. Esta trazabilidad manual funciona aunque no se haya configurado una integración automática.
- Para tareas realizadas desde el panel de WordPress, añadir a Jira la evidencia y el método de integración; una pull request de documentación no demuestra por sí sola que la web se haya integrado.

Flujo del tablero:

```text
Por hacer → En progreso → En revisión → Hecho
```
## Estado

Trabajo académico en desarrollo. Las secciones marcadas como propuestas deben validarse por el grupo; no describen configuraciones ya aplicadas.

## Integrantes

- ALESANDRO JOAQUIN ACOSTA ALFEREZ
- RAFAEL CAPITÁN DE LA TORRE
- FRANCISCO JAVIER DOMINGUEZ MUÑOZ
- FATIMA EL SAYED TORRES
- ÁNGEL MORILLA MARTÍN
