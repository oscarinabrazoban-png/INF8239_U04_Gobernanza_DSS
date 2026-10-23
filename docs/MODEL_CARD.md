# Model Card — Territorial Review DSS

## Intended use

El modelo forma parte de un sistema de apoyo a decisiones (DSS) desarrollado con fines académicos para priorizar la revisión humana de casos territoriales sintéticos. Su función consiste en generar estimaciones que faciliten la organización de casos y la presentación de evidencia a los responsables de su evaluación.

El sistema no sustituye el criterio profesional ni tiene autoridad para ejecutar intervenciones. Toda recomendación debe ser revisada por una persona responsable antes de adoptar cualquier decisión.

## Out-of-scope use

Se prohíbe utilizar el modelo para:

- Ejecutar intervenciones automáticas.
- Determinar elegibilidad o denegar servicios.
- Declarar emergencias.
- Imponer sanciones o atribuir responsabilidades.
- Aplicar el sistema directamente a personas o comunidades reales sin una evaluación adicional de riesgos, calidad de datos y autorización institucional.

## Data and split

Se utilizó el conjunto de datos `territorial_risk_synthetic.csv`, compuesto por 640 observaciones y 9 variables. La variable objetivo presenta una proporción aproximada de 55.2 % de casos positivos y 44.8 % de negativos.

La evaluación se realizó mediante una partición temporal, con fecha de cierre del entrenamiento el 24 de septiembre de 2026 e inicio del período de prueba el 25 de septiembre de 2026. El conjunto de prueba contiene 160 observaciones.

Se excluyeron del entrenamiento las variables `case_id`, `received_date`, `protected_group` y `target`, de acuerdo con la configuración del ejercicio. La variable `protected_group` se conservó para realizar el análisis de equidad.

## Global and subgroup evaluation

Se compararon dos algoritmos de clasificación: regresión logística y árbol de decisión.

La regresión logística obtuvo una exactitud de 71.88 % y una sensibilidad de 71.74 %. La brecha de sensibilidad entre los grupos evaluados fue de 13.76 puntos porcentuales, mientras que la brecha de falsos positivos alcanzó 12.50 puntos porcentuales.

El árbol de decisión obtuvo una exactitud de 70.63 %, con una brecha de sensibilidad de 18.13 puntos porcentuales y una brecha de falsos positivos de 16.83 puntos porcentuales.

El análisis por grupos e interseccional permitió identificar diferencias de desempeño y subgrupos con pocas observaciones, lo que limita la estabilidad y generalización de algunas métricas.

En LAB13, la regresión logística superó las cinco puertas técnicas configuradas: sensibilidad mínima, brechas máximas de sensibilidad y falsos positivos, latencia y tamaño del modelo. El resultado automatizado fue `GO`, condicionado a la revisión y decisión humana final.

## Green AI evidence

La comparación de alternativas consideró el desempeño predictivo y los recursos computacionales utilizados.

| Indicador | Regresión logística | Árbol de decisión |
|---|---:|---:|
| Exactitud | 71.88 % | 70.63 % |
| Sensibilidad | 71.74 % | 71.74 % |
| Tiempo de entrenamiento, LAB12 | 0.1000 s | 0.0543 s |
| Tamaño del modelo | 3.56 KB | 7.87 KB |

La regresión logística presentó una mejor exactitud, menores brechas de equidad y un menor tamaño del modelo, aunque el árbol de decisión registró un menor tiempo de entrenamiento en la comparación del LAB12.

Estas mediciones constituyen indicadores aproximados de eficiencia computacional y no equivalen a una estimación directa del consumo energético o de la huella de carbono.

## Limitations, human oversight and appeal

El sistema fue evaluado exclusivamente con datos sintéticos. Por tanto, sus resultados no permiten establecer conclusiones sobre personas, territorios o comunidades reales.

Las diferencias de desempeño entre grupos, el tamaño reducido de algunas intersecciones y la ausencia de validación externa requieren precaución al interpretar los resultados.

Aunque el pipeline LAB13 produjo un estado técnico `GO`, se mantiene la recomendación académica de revisión (`REVIEW`) antes de considerar cualquier uso fuera del entorno experimental.

La supervisión humana debe incluir la posibilidad de revisar, modificar, rechazar o detener una recomendación. Asimismo, cualquier aplicación futura deberá contemplar mecanismos accesibles de revisión y apelación.

## Owner and review date

- **Responsable institucional final:** Institutional Owner, conforme a la matriz RACI para respuesta a incidentes.
- **Responsable de validación y seguimiento técnico:** Data Scientist.
- **Responsable de despliegue técnico:** ML Engineer.
- **Fecha de revisión académica:** 23 de octubre de 2026.
- **Estado:** Uso académico y experimental; sin autorización para despliegue real.
