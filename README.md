<img width="1774" height="887" alt="regals-v2" src="https://github.com/user-attachments/assets/8799ee9e-1cda-4533-a6f2-77de057f9f5a" />
# Reglas genéricas para asistentes de IA

Biblioteca para planificar, construir, diagnosticar, corregir y revisar software. No depende de un proveedor, aplicación, sistema operativo, infraestructura ni nombres personales. Su cumplimiento depende de las capacidades y el comportamiento del modelo; no garantiza resultados idénticos entre distintas IA.

Esta guía sirve para elegir las reglas. **No la adjuntes entera en cada tarea.**

## Qué enviar

Envía **00-base.md + la etapa actual + petición concreta + contexto pertinente del proyecto**. No envíes todas las etapas. Si el contenido ya está disponible y vigente en la conversación, no lo dupliques; recárgalo si falta o cambió.

- **Chat sin acceso a tus archivos:** adjunta los documentos o pega su contenido. Una ruta escrita no permite leer tu disco.
- **Asistente con herramientas:** facilita el proyecto y las ubicaciones reales a las que tiene acceso; especifica qué puede modificar o ejecutar. No presupongas que dispone de todas las herramientas.
- **Sin capacidad de ejecución:** puede preparar código o propuestas, pero debe indicar qué queda pendiente de aplicar y probar. No aceptes una prueba imaginada como verificación.

## Elegir etapa

| Archivo | Para qué sirve |
|---|---|
| [00-base.md](00-base.md) | Criterio, capacidades, permisos, protección, lectura, simplicidad y evidencia comunes. |
| [10-brief.md](10-brief.md) | Aclarar la idea y entregar un plan para aprobar, sin código. |
| [20-begin.md](20-begin.md) | Implementar el cambio autorizado y probarlo, o proponerlo si no hay acceso. |
| [30-diagnostico.md](30-diagnostico.md) | Inventario, mapa, auditoría e informe; no corrige. |
| [40-fix.md](40-fix.md) | Corregir únicamente hallazgos seleccionados y aprobados. |
| [50-review.md](50-review.md) | Revisar cambios en contexto separado, sin modificarlos. |

**Proyecto nuevo:** plan → aprobación → implementación → pruebas/ajustes autorizados → revisión independiente.

**Proyecto existente:** diagnóstico → selección y aprobación → correcciones → revisión independiente.

Cada pase es deliberado; no autoriza el recorrido completo. Una orden directa clara puede autorizar un cambio pequeño sin otro plan formal.

## Peticiones listas para adaptar

Adjunta los archivos nombrados o facilita un acceso real a ellos. Sustituye los campos entre corchetes:

| Necesidad | Petición |
|---|---|
| Definir una idea | «Aplica 00-base.md y 10-brief.md. Ayúdame a definir [idea y contexto]; pregunta solo lo que falte. No construyas todavía». |
| Crear o modificar | «Aplica 00-base.md y 20-begin.md. Implementa solo [cambio aprobado] en [proyecto/entorno], con [criterios de aceptación]». |
| Diagnosticar | «Aplica 00-base.md y 30-diagnostico.md. Audita [material o proyecto] dentro de [alcance], sin corregirlo». |
| Corregir | «Aplica 00-base.md y 40-fix.md. Corrige solo [IDs aprobados] del diagnóstico adjunto, dentro de [alcance]». |
| Revisar | «Aplica 00-base.md y 50-review.md. Revisa [comparación anterior/actual] contra [requisitos], con el código relacionado adjunto, sin modificarlo». |

## Continuar sin empezar de cero

Al cambiar de etapa o conversación, facilita solo lo necesario o referencia un entregable accesible que ya lo contenga:

- Objetivo y alcance autorizados.
- Estado o versión del código, y archivos afectados.
- Pruebas ejecutadas, entorno, resultados y dónde está la evidencia.
- Pendientes, límites y bloqueos.
- Siguiente acción autorizada.

No presupongas memoria entre conversaciones. Esta ficha no sustituye evidencia; los cambios pertinentes pueden invalidar pruebas anteriores.

Para revisión independiente, abre otra conversación o un contexto realmente separado y proporciona base, revisión, requisitos, comparación y código relacionado. Pedir «construye y luego revísate» en el mismo contexto no crea independencia. Si no puedes separar contextos, declara esa limitación; no añadas agentes ni servicios por defecto.

## Licencia y colaboración

Publicado bajo licencia MIT — ver [LICENSE](LICENSE). Si quieres proponer mejoras o traducciones, revisa [CONTRIBUTING.md](CONTRIBUTING.md). Inspirado en los principios YAGNI de [ponytail](https://github.com/DietrichGebert/ponytail) (MIT).
