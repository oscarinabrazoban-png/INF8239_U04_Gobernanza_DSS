# Incident Runbook — Territorial Review DSS

## 1. Detection and classification

Los incidentes podrán identificarse mediante las pruebas automatizadas, las puertas de gobernanza, el monitoreo del desempeño o los reportes realizados por usuarios y personas potencialmente afectadas.

Se consideran señales de alerta las fallas del contrato de datos, la presencia de identificadores directos prohibidos, las brechas de equidad superiores a los umbrales establecidos, la degradación del desempeño, el uso fuera del propósito autorizado y las recomendaciones que excedan la autoridad del DSS.

Los eventos se clasificarán según su gravedad, alcance y posible impacto. Una falla técnica deberá registrarse y evaluarse antes de continuar utilizando el sistema.

## 2. Containment authority

El ML Engineer será responsable de ejecutar las acciones técnicas de contención. El Institutional Owner tendrá la responsabilidad final sobre las decisiones de respuesta a incidentes, conforme a la matriz RACI.

Las medidas podrán incluir la suspensión temporal del sistema, el bloqueo de nuevas recomendaciones, la restricción de acceso o la desactivación de una versión del modelo.

Cuando exista un riesgo significativo, se priorizará la protección de las personas y la preservación de la evidencia sobre la continuidad operativa.

## 3. Evidence preservation

Se conservarán los registros de ejecución, la versión del código, la configuración de gobernanza, las métricas de evaluación, los resultados de las pruebas y los archivos asociados con la decisión automatizada.

Cada incidente deberá documentar, como mínimo, la fecha de detección, la descripción del evento, los controles afectados, las personas responsables, las medidas adoptadas y el estado de resolución.

La evidencia se almacenará bajo controles de acceso apropiados, evitando incorporar datos personales o información sensible innecesaria.

## 4. Internal and affected-party communication

El Institutional Owner coordinará la comunicación institucional del incidente, con apoyo de los equipos técnico y legal cuando corresponda.

La comunicación interna deberá describir el evento, su posible impacto, las acciones de contención y las medidas pendientes.

Cuando existan personas potencialmente afectadas, se evaluará la necesidad de informarles mediante canales apropiados, explicando las vías disponibles para solicitar revisión o presentar una reclamación.

Las comunicaciones deberán distinguir entre hechos confirmados, hipótesis de investigación y acciones correctivas propuestas.

## 5. Rollback or safe baseline

Si una versión del modelo incumple los controles de gobernanza o presenta un riesgo no aceptable, se suspenderá su utilización hasta completar la revisión correspondiente.

Cuando exista una versión anterior validada y autorizada, podrá evaluarse una reversión controlada (*rollback*). En caso contrario, se utilizará un procedimiento alternativo de revisión humana sin recomendaciones predictivas automatizadas.

La reactivación del sistema requerirá repetir las pruebas pertinentes, revisar las métricas de desempeño y equidad, y documentar la aprobación del responsable correspondiente.

## 6. Postmortem, owner and due date

Una vez contenido el incidente, se elaborará un informe *postmortem* que documente la secuencia de acontecimientos, las causas identificadas, las consecuencias, la efectividad de la respuesta y las oportunidades de mejora.

El Institutional Owner será responsable final del cierre del incidente. El ML Engineer y el Data Scientist participarán en el análisis técnico y en la ejecución de las acciones correctivas.

Para cada acción se establecerá un responsable, una fecha límite y una evidencia verificable de cumplimiento. El incidente solo se considerará cerrado cuando se hayan documentado los resultados de la revisión y las medidas de prevención de recurrencia.

**Nota:** Este documento establece el procedimiento previsto para el ejercicio. La evidencia del simulacro se incorporará después de ejecutar `scripts/simulate_incident.py`.
