# Incident simulation

- detected_at: 2026-10-23T15:03:56.464295+00:00
- signal: recall gap exceeded
- containment: REVIEW and safe baseline
- evidence: preserved report and model version
- communication: REPL# Incident Simulation — Postmortem

## 1. Detección y clasificación

- **Fecha de ejecución:** 2026-10-23T15:03:56.464295+00:00
- **Tipo de evento:** Simulación de incumplimiento de una puerta de equidad.
- **Señal:** Brecha de sensibilidad (*recall gap*) superior al umbral de gobernanza.
- **Clasificación:** Incidente hipotético de equidad que requiere revisión humana.
- **Alcance:** Entorno académico con datos sintéticos, sin afectación real de personas o servicios.

## 2. Contención

La respuesta prevista consiste en cambiar el estado operativo a `REVIEW`, suspender el uso de recomendaciones predictivas para nuevas decisiones y utilizar un procedimiento alternativo de revisión humana.

El ML Engineer ejecutaría la contención técnica y el Institutional Owner tendría la responsabilidad final de autorizar las medidas correspondientes.

## 3. Preservación de evidencia

Se identifican como evidencias relevantes el archivo de decisión de despliegue, las métricas de equidad, la configuración de gobernanza, la versión del modelo y el historial de Git.

La conservación de estas evidencias deberá verificarse durante la gestión de un incidente real. La ejecución del simulacro, por sí sola, no demuestra que se haya realizado una copia de seguridad o una reversión efectiva.

## 4. Comunicación

Ante un incidente real, el ML Engineer comunicaría la alerta al Institutional Owner y al Data Scientist, indicando el control incumplido, la versión afectada y las medidas de contención.

El Institutional Owner coordinaría la comunicación institucional y, cuando corresponda, la información dirigida a las personas potencialmente afectadas, con apoyo del área legal.

En este ejercicio no se realizaron notificaciones reales, debido al carácter sintético del escenario.

## 5. Rollback y continuidad segura

La medida propuesta consiste en mantener suspendidas las recomendaciones predictivas hasta completar la investigación y repetir las pruebas correspondientes.

Si existiera una versión anterior validada y autorizada, se evaluaría su restauración controlada. En ausencia de esa versión, se utilizaría una revisión humana basada en criterios documentados y sin automatización predictiva.

No se ejecutó un rollback técnico durante este simulacro.

## 6. Acciones correctivas y responsables

| Acción propuesta | Responsable | Plazo propuesto |
|---|---|---|
| Verificar las métricas y reproducir la alerta | Data Scientist | 2 días hábiles desde la detección |
| Revisar datos, grupos e intersecciones | Data Scientist y Data Engineer | 5 días hábiles |
| Evaluar medidas de mitigación y sus efectos | Data Scientist | 7 días hábiles |
| Repetir pruebas y documentar resultados | ML Engineer | 2 días hábiles después de implementar correcciones |
| Autorizar continuidad, modificación o suspensión | Institutional Owner | Después de revisar la evidencia |

Los plazos son propuestas académicas para el simulacro y no compromisos institucionales aprobados.

## 7. Análisis posterior y cierre

El escenario evidencia la importancia de vincular las métricas de equidad con mecanismos de alerta, responsables definidos y procedimientos de respuesta documentados.

La principal medida preventiva consiste en mantener la evaluación desagregada por grupos, verificar periódicamente los umbrales y exigir autorización humana antes de reactivar un sistema que haya incumplido sus controles.

**Estado del ejercicio:** Simulacro documentado. No se registró un incidente operativo real ni se autorizó un despliegue en producción.-ACE
- corrective actions, owners and dates: REPLACE
