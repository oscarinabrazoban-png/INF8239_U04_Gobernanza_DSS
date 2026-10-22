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
