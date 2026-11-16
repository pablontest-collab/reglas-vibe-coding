# 40-fix — Corregir hallazgos aprobados

Requiere [00-base.md](00-base.md), diagnóstico disponible e ítems seleccionados por el usuario. Un hallazgo no equivale a permiso para arreglarlo.

## Procedimiento

1. Confirma los ítems, archivos y alcance autorizados. No añadas arreglos ni refactorizaciones oportunistas. Si la causa exige tocar algo no aprobado, presenta la ampliación antes de editar; si una recomendación debilita las protecciones de la base, señálala y no la ejecutes a ciegas.
2. Confirma estado, entorno, convenciones y pruebas reales del proyecto. Reproduce el fallo cuando sea viable y usa el contexto vigente del diagnóstico, sin reconstruirlo entero. Consulta vigencia técnica según la base.
3. Aplica el cambio mínimo suficiente, de mayor impacto primero y de a un ítem; si no tienes acceso de edición, entrega el parche propuesto. Agrupa solo ítems inseparables con alcance aprobado; conserva seguimiento individual. Reutiliza o incorpora pruebas pertinentes que demuestren la corrección y sus efectos relacionados.
4. Verifica en escalera cuando tengas ejecución: comprobación rápida y prueba del fallo por cada ítem, y pruebas de impacto o conjunto al cerrar el bloque, no toda la batería por cada línea. Trata errores, bloqueos y evidencia conforme a la base.
5. Entrega una tabla breve: **ítem → aplicado/propuesto/no aplicado y motivo → cambio y razón → evidencia o pendiente**, más cambios de uso y límites si los hay. Si se pide pase a otra etapa o revisión independiente, incluye la ficha breve (alcance, estado/versión del código, archivos afectados, pruebas/entorno/resultados, pendientes/límites y siguiente acción), sin iniciarla automáticamente ni repetir el diagnóstico.
