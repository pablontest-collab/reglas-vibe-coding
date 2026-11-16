# 30-diagnostico — Comprender y auditar

Requiere [00-base.md](00-base.md), proyecto o material accesible y alcance de auditoría. No apliques correcciones: esta etapa es de lectura del proyecto; las pruebas serán no destructivas o en copias aisladas. Otros efectos requieren autorización.

## Recorrido

Conserva estas cuatro funciones. En trabajos pequeños pueden integrarse en una entrega; en grandes acuerda los bloques y los puntos de aprobación de la base.

1. **Inventario:** lista completa del árbol y subcarpetas dentro del alcance accesible, con exclusiones explícitas. Si es extenso, deja el inventario íntegro disponible y resume en el chat; no lo reproduzcas en cada bloque. Distingue inventario de lectura y declara cobertura conforme a la base. Señala el material faltante, sin inventar su estructura.
2. **Mapa, antes de juzgar:** propósito; rol de cada archivo del alcance; flujo de datos; dependencias, APIs y servicios; requisitos de credenciales sin sus valores; puntos de entrada y riesgos que luego investigarás. Aplica la vigencia técnica de la base.
3. **Auditoría:** identifica duplicación, código muerto o innecesario, defectos, riesgos y mejoras mínimas. Separa hechos comprobados, sospechas pendientes y opciones. No confundas protecciones necesarias con basura ni propongas migraciones por moda.
4. **Informe:** resumen de salud y hallazgos priorizados como **bloqueante / importante / opcional**, según impacto. Cada ítem: **ID + archivo:líneas → problema → por qué importa → solución concreta → evidencia y límites de lo comprobado**. Si falla una prueba, aplica el tratamiento de errores de la base.

Separa los **candidatos a eliminación**, con evidencia de falta de uso y riesgos, considerando referencias dinámicas o integraciones cuando corresponda. Una propuesta de borrado no es autorización para ejecutarlo: exige aprobación y verificación al aplicarse.

Entrega al terminar cada bloque aprobado; pide el pase al siguiente sin continuar automáticamente. El informe final permite seleccionar correcciones, no aprueba toda la lista por defecto.
