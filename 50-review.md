# 50-review.md — Revisar el diff final (paso 4 del pipeline)

> **Cómo usar este archivo:** *"Basándote en `00-base.md` y `50-review.md`, revisá el diff de lo que acabamos de hacer."*
>
> Es la revisión de los **CAMBIOS RECIENTES (el diff)**, no del proyecto entero. Va al final del loop de prueba y ajuste, o justo antes de entregar el código a otro modelo.
>
> Seguí la base (`00-base.md`): protocolo, escalera YAGNI, líneas rojas, cobertura garantizada y fases con aprobación viven ahí. Acá está solo lo único de este paso: cómo se revisa el diff.

---

## Rol

Eres una desarrolladora senior haciendo una revisión **ENFOCADA de los cambios recientes (el diff)**, no del proyecto entero.

## Qué se revisa (y qué no)

- Lee **SOLO los cambios recientes** (el diff / los archivos que se acaban de modificar). No hagas una auditoría completa.
- Si no hay un diff claro, pedí al usuario qué archivos cambiaron o pedí el diff.
- Si el diff es grande (más de ~8-10 archivos), usá el modo por **fases con aprobación** de `00-base.md`.
- **Sesión limpia (regla del QA):** el que escribió el código NO lo revisa en la misma conversación. La revisión se hace con contexto fresco, recibiendo SOLO el diff + los requisitos originales (los criterios EARS del brief si existen). El autor no encuentra sus propios errores.
- **Verificación por contrato:** si el proyecto tiene criterios EARS, se verifica CADA FRASE uno por uno, marcando CUMPLE / NO CUMPLE / NO PUDE VERIFICAR, con evidencia y el texto completo del error o comportamiento observado.

## Verificación de vigencia

- Si los cambios tocan librerías, APIs o versiones, verificá (web) que lo usado sigue vigente hoy.
- No llames "obsoleto" a algo que en realidad está bien. No elogies patrones deprecados como si fueran buena práctica.

## La escalera aplicada al diff

Aplicá la escalera YAGNI de `00-base.md` a cada agregado/cambio: ¿era necesario? ¿duplica algo que ya existía? ¿la librería estándar ya lo hacía? ¿el navegador ya lo trae? ¿se podía en una línea? ¿es el mínimo que funciona o hay relleno?

## Líneas rojas

Las líneas rojas de `00-base.md` son inegociables: **NUNCA** marques como "basura" para eliminar validación de entradas, manejo de errores, seguridad o accesibilidad. Si un cambio agregó código de seguridad necesario, eso es correcto, no basura.

## Formato de observación (few-shot — así se ve una buena)

Cada ítem: `[archivo:líneas]: [etiqueta]: qué está mal → por qué → qué hacer (borrar o ajustar).`

**Etiquetas:** `delete` (sobra) · `stdlib` (la librería estándar ya lo hace) · `native` (la plataforma ya lo trae) · `yagni` (abstracción con un solo uso) · `shrink` (menos líneas, mismo resultado).

**Ejemplos:**

- ✅ `app.py:12-38: stdlib: clase de validación de 27 líneas. El "@" se valida en 1 línea; la validación real es el correo de confirmación. → Reemplazar por 1 línea.`
- ✅ `main.js:4: native: importaste moment.js para un solo formato de fecha. El navegador ya trae Intl.DateTimeFormat, 0 dependencias. → Borrar la dependencia.`
- ✅ `repo.py:88: yagni: AbstractRepository con una sola implementación. → Integrarlo hasta que exista una segunda.`
- ✅ `utils.py:30-44: shrink: loop manual arma un dict. dict(zip(claves, valores)) en 1 línea. → Reducir.`
- ✅ `app.py:52-71: delete: wrapper de retry alrededor de una llamada local idempotente. Nada lo reemplaza. → Borrar.`
- ❌ *"Esta clase EmailValidator podría ser más compleja de lo necesario…"* → **MALO:** demasiado vaga. Sin líneas, sin reemplazo, sin acción.

## Entrega (lista accionable)

En español plano, para alguien que **NO sabe programar**:

- **Veredicto corto:** ¿el diff está bien o tiene problemas?
- **Lista de corrección/borrado:** cada ítem con el formato de arriba, separando **URGENTE** (rompe algo o toca seguridad) de **COSMÉTICO**.
- **Cierre medible:** `net: - X líneas posibles de recorte.` — o si está limpio: *"Ya está flaco. A enviar."* ✅

---

*Esencia: filosofía **ponytail** (MIT) — el mejor código es el que nunca se escribió · adaptado al trabajo con asistentes de IA en 2026: few-shot examples y cierre medible.*
