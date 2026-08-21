# reglas-vibe-coding — Reglas en español para trabajar con asistentes de IA

> **Reglas en español para trabajar con asistentes de IA en proyectos de código — para vibe coders y no programadores.**

¿No sabés programar pero construís con IA? Estas reglas le enseñan a tu asistente a trabajar con orden: **primero entender, después actuar, siempre con lo mínimo que funciona.**

---

## 🚀 Cómo usarlo en 10 segundos

1. **Copiá esta carpeta** a tu proyecto (o guardá los `.md` donde quieras).
2. **Invocá por referencia de path** en tu prompt de IA:

```
Basándote en [ruta]/00-base.md y [ruta]/10-brief.md, ayúdame a armar el brief para: [tu idea]
```

3. **Seguí el pipeline** (abajo) y tu IA trabajará por fases, pidiéndote aprobación en cada paso. Nada es automático: **vos decidís** cuándo usar cada regla.

> 💡 **Tip AGENTS.md:** si tu orquestador lee `AGENTS.md` (el estándar de contexto de 2026: opencode, Cursor, Claude Code, etc.), podés copiar el contenido de `00-base.md` como base del sistema y referenciar las demás por path. Es la capa general de tus reglas; cada proyecto agrega su propia capa local.

---

## El pipeline (orden sugerido)

```
NUEVO código:      00-base + 10-brief → 20-begin → (probás y ajustás) → 50-review
Código EXISTENTE:  00-base + 30-diagnostico (fases) → 40-fix → 50-review
```

La base (`00-base.md`) se invoca **SIEMPRE** junto a la regla específica. Nada es automático: el usuario decide cuándo usar cada una.

## Qué hace cada archivo

- **`00-base.md`** → La **BASE común**: protocolo (criollo, no asumir, cuestionar, recomendar-recortar), stack como plano de construcción, escalera YAGNI, líneas rojas, cobertura garantizada, fases con aprobación. Invocala SIEMPRE como base.
- **`10-brief.md`** → **Paso 1:** idea vaga → brief aprobado. **No se escribe código hasta que el brief esté aprobado.**
- **`20-begin.md`** → **Paso 2:** escribir/modificar código con la escalera. En ejecución obedece el brief; líneas rojas mandan.
- **`30-diagnostico.md`** → **Paso 3a:** entender + auditar código existente, en **fases con aprobación del usuario** (inventario → mapa → auditoría → informe).
- **`40-fix.md`** → **Paso 3b:** aplicar **SOLO** lo señalado por el diagnóstico, de a uno, mínimo.
- **`50-review.md`** → **Paso 4:** revisar el diff final, con ejemplos few-shot y cierre medible.

## Cómo usar (invocación por referencia)

Las reglas se invocan por **referencia de path** en el prompt, para que cualquier asistente de IA las cargue:

```
Basándote en [ruta]/00-base.md y [ruta]/10-brief.md, [tu pedido]
```

Si el orquestador tiene un sistema de skills/instrucciones persistentes (AGENTS.md, CLAUDE.md, etc.), se puede copiar el contenido de `00-base.md` como base del sistema y referenciar las demás por path.

## Plantillas de prompts (copiar-pegar)

Cambiá lo que está entre `[corchetes]` y la `[ruta]` donde estén las reglas.

**0. Base — SIEMPRE junto a la regla específica**
```
Basándote en [ruta]/00-base.md y [regla], [tu pedido]
```

**1a. Sacar idea vaga**
```
Basándote en [ruta]/00-base.md, ayúdame a sacar la idea para: [tema vago]
```

**1b. Brief (idea ya clara → plan)**
```
Basándote en [ruta]/00-base.md y [ruta]/10-brief.md, armá el brief PARA ESTA idea ya definida: [resumen 2 líneas]
```

**2. Código (escribir / modificar)**
```
Basándote en [ruta]/00-base.md y [ruta]/20-begin.md, crea el código para: [lo que necesitas]
Basándote en [ruta]/00-base.md y [ruta]/20-begin.md, modifica [archivo] para que haga: [X]
```

**3. Entender + auditar código existente (en fases)**
```
Basándote en [ruta]/00-base.md y [ruta]/30-diagnostico.md, entendé y auditá la carpeta [ruta del proyecto]
```

**4. Aplicar correcciones (después del diagnóstico)**
```
Basándote en [ruta]/00-base.md y [ruta]/40-fix.md, aplicá las recomendaciones del diagnóstico en: [archivo/carpeta]
```

**5. Revisar lo hecho (después de ajustar / antes de otro modelo)**
```
Basándote en [ruta]/00-base.md y [ruta]/50-review.md, revisá el diff de lo que acabamos de hacer.
```

## Notas

- La base (`00-base.md`) dice lo transversal **UNA sola vez**: protocolo, escalera, criterios y verificación, líneas rojas, cobertura garantizada, fases con aprobación. Las reglas específicas la **referencian, no la repiten**. Si una regla parece repetir algo de la base, es un error.
- **Web con criterio:** verificar vigencia solo cuando se tocan tecnologías, librerías, APIs o versiones — y el entregable lleva versiones exactas + fecha de verificación.
- **Cobertura garantizada:** nunca saltar un archivo en silencio; HTML/CSS/config son parte del sistema, no decoración.
- **Análisis grandes:** por fases con aprobación (contexto fresco); proyectos chicos: entrega directa.
- **Sesión limpia:** la revisión (`50-review.md`) se hace con contexto fresco — el que escribió el código no lo revisa en la misma conversación.
- **"Listo":** toda tarea termina con un comando de verificación exitoso, no por palabra propia. Si falla, el error completo se devuelve para corregir bien.
- Si querés combinar varias reglas en un mismo prompt, encadenalas.

---

## Licencia

MIT — ver [LICENSE](LICENSE). Hecho con la filosofía **ponytail** (MIT, github.com/DietrichGebert/ponytail): el mejor código es el que nunca se escribió · adaptado al trabajo con asistentes de IA: sin redundancia, stack como plano de construcción, cobertura garantizada, fases con aprobación — EARS, listo = comando exitoso, error completo, stack con fecha, QA en sesión limpia.
