# Declaración de uso de IA

# Declaración de uso de IA

## 1. Herramienta utilizada

ChatGPT, desarrollado por OpenAI.

## 2. Finalidad del uso

Se utilizó inteligencia artificial generativa como herramienta de apoyo para desarrollar la evaluación de impacto ético del sistema de apoyo a decisiones (DSS), correspondiente al LAB11 de la Unidad 04.

La herramienta facilitó la interpretación de las instrucciones, la redacción de instrumentos de gobernanza, la identificación de riesgos éticos y la resolución de un error de programación.

## 3. Fragmentos afectados

El apoyo de IA se utilizó en los siguientes archivos:

- `student_inputs/lab11_impact.yml`: redacción de los campos de la evaluación de impacto ético.
- `student_inputs/stakeholders.csv`: descripción de beneficios, daños potenciales y mecanismos de participación.
- `student_inputs/risk_register.csv`: formulación de ocho escenarios de riesgo, controles, responsables y evidencias requeridas.
- `scripts/lab11_impact.py`: corrección de un error de sintaxis relacionado con una cadena de texto de varias líneas.
- `reports/lab11/DECISION_RECORD.md`: elaboración del registro de decisión ética, incluyendo riesgos prioritarios, incertidumbres y condiciones para continuar.

## 4. Verificaciones humanas

La estudiante revisó los contenidos propuestos, incorporó los cambios en los archivos del proyecto y ejecutó los comandos de validación.

Se realizaron las siguientes comprobaciones:

- Ejecución de `uv run python scripts/lab11_impact.py`.
- Identificación de los riesgos prioritarios R02, R01 y R07.
- Ejecución de `uv run pytest -q tests/test_impact.py tests/test_privacy.py`.
- Resultado obtenido: 3 pruebas aprobadas.

## 5. Errores detectados y correcciones

Durante la ejecución del script `lab11_impact.py` se detectó el error `SyntaxError: unterminated string literal`.

El problema se encontraba en la instrucción que genera el archivo `DECISION_RECORD.md`, debido al uso de comillas dobles normales para delimitar un texto de varias líneas.

Se corrigió utilizando comillas triples de Python, conservando el contenido previsto por el script.

Después de la corrección, el programa se ejecutó correctamente y las pruebas específicas finalizaron sin errores.

## 6. Limitaciones y responsabilidad

La IA se utilizó como herramienta de asistencia y no como sustituto de la revisión humana.

Los riesgos, controles y decisiones documentados corresponden a un ejercicio académico con datos sintéticos. La aprobación de las pruebas automatizadas no demuestra que el sistema sea adecuado para su implementación en un entorno real.

La responsabilidad por la revisión, interpretación y entrega final del trabajo corresponde a la estudiante.

### Uso de inteligencia artificial en LAB13

Durante el desarrollo del LAB13 se utilizó ChatGPT como herramienta de apoyo para interpretar las instrucciones del laboratorio, estructurar la documentación de gobernanza y orientar la corrección de errores de programación.

Las consultas realizadas estuvieron relacionadas con la interpretación de las puertas de calidad, la elaboración del Model Card, la documentación del Runbook, el análisis del simulacro de incidentes y la corrección de un error `SyntaxError: unterminated f-string literal` en el archivo `simulate_incident.py`.

La intervención de la herramienta consistió en proponer explicaciones, textos técnicos y ajustes de código. La verificación humana incluyó la ejecución del pipeline de gobernanza, la revisión del archivo `deployment_decision.json`, la ejecución del simulacro, la comprobación visual del tablero Streamlit y la ejecución de las pruebas automatizadas.

Como resultado, el pipeline generó un estado técnico `GO` con cinco controles aprobados y las pruebas finalizaron satisfactoriamente (`10 passed`). No obstante, se mantuvo la distinción entre el cumplimiento de umbrales técnicos y la autorización institucional para utilizar el sistema en un entorno real.

La responsabilidad sobre la revisión, ejecución y presentación de los resultados corresponde a la estudiante. Las propuestas de la herramienta se contrastaron con las salidas del proyecto y las instrucciones académicas.
