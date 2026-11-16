# 50-review — Revisar de forma independiente

Requiere [00-base.md](00-base.md), requisitos originales y comparación real del código anterior con el actual —el diff—. No modifiques el código revisado.

## Preparación

- Revisa en un contexto separado del constructor, con acceso al código pertinente, no solo a su informe. El constructor puede probar; eso no sustituye esta revisión. Si no existe un contexto separado, declara la limitación y prepara el pase, sin fingir independencia.
- Obtén el diff real con las herramientas disponibles; si falta la comparación, solicita los archivos anterior y actual o un diff completo. Una lista de archivos modificados no la reemplaza. Identifica el estado del código revisado.
- Céntrate en los cambios y sus efectos: lee funciones completas, consumidores, configuración y pruebas relacionados cuando hagan falta. No audites todo por defecto; organiza bloques según la base si el alcance lo requiere.

## Comprobación

1. Contrasta **cada criterio** con **CUMPLE / NO CUMPLE / NO PUDE VERIFICAR**, aportando evidencia. Si faltan requisitos para decidir, pide aclaración; no los inventes. Distingue comprobaciones propias de resultados ajenos: el informe del constructor es una pista, no prueba suficiente. Si un criterio requiere ejecutar algo y no puedes hacerlo, deja esa verificación pendiente.
2. Busca defectos funcionales, fallos introducidos, riesgos de seguridad/datos y accesibilidad. Aplica simplicidad y vigencia de la base. No inventes hallazgos para llenar una lista ni propongas sustituciones por tamaño: demuestra equivalencia de comportamiento, casos límite y usos antes de recomendar recortes.
3. Prioriza por impacto: **bloqueante / importante / opcional**. Cada observación: **archivo:líneas + categoría → problema → por qué importa → acción concreta → evidencia y límites**. Para simplificación puedes usar `eliminar`, `biblioteca estándar`, `plataforma`, `innecesario` o `simplificar`; no son las únicas categorías.

## Ejemplos hipotéticos de formato

No describen hallazgos del proyecto actual:

- **Útil:** `guardado.py:42: funcional → una prueba de escritura fallida recibe éxito → el usuario cree que guardó → propagar el error y comprobar ese caso`.
- **Útil:** `fechas.js:8: plataforma → dependencia usada para un formato → comparación confirma misma salida y zona en los casos exigidos, sin otros usos → sustituir por la función nativa comprobada`.
- **Insuficiente:** «Esta clase quizá sobra»: faltan ubicación, efecto, evidencia y acción. Una sola implementación, idempotencia o menos líneas no demuestran que algo sea innecesario.

## Veredicto

Resume criterios cumplidos, fallos y pendientes con evidencia; añade observaciones priorizadas. Si no hay hallazgos, dilo. No declares listo si falta comprobar algo pertinente. Las líneas recortadas son un dato secundario medido, nunca el criterio de aprobación. Entrega para decidir correcciones o cierre; no las apliques en esta etapa.
