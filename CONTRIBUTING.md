# Cómo contribuir a los proyectos de Obsernia

Gracias por ayudar a mejorar los proyectos de código abierto de Obsernia relacionados con observabilidad, monitorización de sistemas y ciberseguridad. Son bienvenidas las contribuciones de código, documentación, pruebas, informes de errores, experiencia operativa y propuestas de diseño.

Este documento establece las normas generales de la organización. Si un repositorio contiene instrucciones propias, estas tendrán prioridad.

## Antes de contribuir

- Lee el `README`, la documentación, la licencia y las instrucciones específicas del repositorio.
- Busca en los issues y pull requests existentes antes de crear uno nuevo.
- Para cambios importantes, abre primero una propuesta o discusión para acordar el alcance y el diseño.
- Respeta nuestro [Código de conducta](CODE_OF_CONDUCT.md) en todos los espacios del proyecto.
- No incluyas credenciales, claves privadas, tokens, datos de clientes, nombres internos de equipos, registros sin anonimizar ni otra información sensible.

## Informar de errores

Utiliza la plantilla de informe de errores del repositorio cuando exista. Un buen informe debe incluir:

- Un título claro y descriptivo.
- La versión, el commit o la etiqueta de imagen afectada.
- El sistema operativo, entorno de ejecución, modelo de despliegue y dependencias relevantes.
- Los pasos mínimos necesarios para reproducir el problema.
- El comportamiento esperado y el comportamiento observado.
- Registros, trazas, métricas, capturas o un ejemplo mínimo, siempre debidamente anonimizados.
- Cualquier solución temporal conocida y una valoración del impacto operativo.

Reduce el caso al ejemplo reproducible más pequeño posible. Elimina secretos y cualquier dato que identifique infraestructuras, usuarios o clientes.

Si el problema pudiera exponer datos, eludir controles de acceso, comprometer un sistema o constituir una vulnerabilidad, **no abras un issue público**. Sigue las instrucciones de [SECURITY.md](SECURITY.md).

## Proponer mejoras

Abre una solicitud de funcionalidad en el repositorio correspondiente e indica:

- El problema o necesidad operativa que quieres resolver.
- Los usuarios y entornos afectados.
- El resultado deseado y las alternativas consideradas.
- Las implicaciones de compatibilidad, rendimiento, privacidad, seguridad y migración.
- Ejemplos de telemetría, flujos de trabajo o integraciones, sin datos sensibles.

Los mantenedores podrán pedir aclaraciones, proponer un alcance menor o rechazar propuestas que no encajen con la dirección o la capacidad de mantenimiento del proyecto.

## Preparar un cambio

1. Haz un fork del repositorio, salvo que tengas permiso para crear ramas directamente.
2. Crea una rama a partir de la rama predeterminada actual.
3. Realiza un cambio concreto e incluye las pruebas y la documentación necesarias.
4. Ejecuta las comprobaciones de formato, análisis, pruebas, compilación y seguridad indicadas por el repositorio.
5. Abre un pull request contra la rama predeterminada, salvo que el proyecto indique otra cosa.

### Ramas

Respeta las reglas del repositorio cuando existan. En caso contrario, utiliza un nombre breve y descriptivo con un prefijo de categoría, por ejemplo:

- `feat/add-prometheus-exporter`
- `fix/alert-deduplication`
- `docs/deployment-guide`
- `test/parser-edge-cases`
- `chore/update-dependencies`

No publiques exploits ni detalles de vulnerabilidades en ramas normales o forks públicos. Coordina las correcciones de seguridad mediante el proceso privado descrito en [SECURITY.md](SECURITY.md).

### Commits

- Mantén los commits pequeños, coherentes y fáciles de revisar.
- Utiliza un asunto descriptivo en imperativo, por ejemplo: `Corrige la gestión de timeouts del planificador`.
- Explica en el cuerpo el motivo de los cambios que no resulten evidentes.
- Haz referencia al issue correspondiente cuando proceda.
- Evita mezclar cambios de formato, refactorizaciones, archivos generados y cambios funcionales sin una razón clara.
- Conserva las atribuciones necesarias y respeta las licencias de todo material de terceros.

Utiliza Conventional Commits únicamente si el repositorio lo exige o ya sigue esa convención. Antes de solicitar una revisión, elimina los commits temporales o accidentales sin perder información útil para la revisión.

### Pruebas y calidad

Añade o actualiza pruebas para cualquier comportamiento modificado. Según el proyecto, pueden ser pruebas unitarias, de integración, extremo a extremo, de regresión, compatibilidad, rendimiento o seguridad.

Las pruebas deben ser deterministas, estar aisladas y ser seguras. No deben depender de credenciales de producción, sistemas de clientes ni acciones destructivas. Utiliza datos sintéticos y anonimizados. En los cambios de monitorización y observabilidad, ten en cuenta fallos parciales, ausencia de datos, entradas de alta cardinalidad, timeouts, reintentos, diferencias de reloj y dependencias degradadas.

Si no puedes añadir o ejecutar una prueba relevante, explica el motivo en el pull request e indica cómo has validado el cambio.

## Pull requests

Un pull request debe:

- Tener un título claro y explicar qué cambia y por qué.
- Limitarse a un alcance razonable para su revisión.
- Enlazar los issues relacionados cuando corresponda.
- Describir las pruebas realizadas y los entornos utilizados.
- Identificar efectos sobre compatibilidad, despliegue, configuración, migración, rendimiento, privacidad y seguridad.
- Actualizar la documentación, ejemplos, esquemas y notas de versión cuando sea necesario.
- Incluir capturas o resultados anonimizados si hay cambios visibles.
- Superar todas las comprobaciones automáticas obligatorias.

Marca como borrador el trabajo que todavía no esté listo. Responde de forma constructiva a las revisiones y resuelve las conversaciones únicamente cuando el asunto se haya corregido o exista un acuerdo. Los mantenedores podrán reorganizar o cerrar una contribución para preservar la calidad y el alcance del proyecto.

Al enviar una contribución, confirmas que tienes derecho a aportarla y que podrá distribuirse bajo la licencia del repositorio. No envíes código o recursos copiados sin una licencia compatible y las atribuciones necesarias.

## Contribuciones relacionadas con la seguridad

Considera especialmente sensibles los cambios que afecten a autenticación, autorización, criptografía, secretos, límites de red, analizadores, agentes, recolectores, ejecución privilegiada o telemetría con datos personales o de infraestructura.

No reveles posibles vulnerabilidades en issues, discusiones, pull requests, forks públicos, mensajes de commit ni canales de chat. Utiliza el proceso privado definido en [SECURITY.md](SECURITY.md). Los mantenedores coordinarán con la persona informante la validación, corrección y divulgación.

## Revisión y aceptación

Enviar una contribución no garantiza que sea aceptada. Los mantenedores valorarán su corrección, seguridad, facilidad de mantenimiento, compatibilidad, alineación con el proyecto y coste de soporte a largo plazo. Podrán solicitar cambios o cerrar contribuciones inactivas. El desacuerdo respetuoso es bienvenido; la decisión final corresponde a los mantenedores del repositorio afectado.

Gracias por contribuir a crear sistemas más seguros y fiables.
