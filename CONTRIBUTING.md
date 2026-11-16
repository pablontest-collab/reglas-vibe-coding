# Guía para colaborar (CONTRIBUTING)

Gracias por tu interés en mejorar esta biblioteca de reglas en español para trabajar con asistentes de IA.

## Antes de enviar cambios: abre un Issue

1. Explica en un **Issue** qué quieres proponer (corregir un error, afinar una regla o traducir la biblioteca a otro idioma).
2. Espera la confirmación antes de abrir un Pull Request (PR).

## Cómo enviar tu aporte

1. Haz un **Fork** del repositorio en tu cuenta de GitHub.
2. Realiza los cambios en tu copia manteniendo la brevedad y claridad del conjunto.
3. Abre un **Pull Request** indicando qué cambiaste, por qué y qué comprobaste.

## Reglas del repositorio

- **Respeta la numeración y nombres de archivos:** `00-base.md`, `10-brief.md`, `20-begin.md`, `30-diagnostico.md`, `40-fix.md`, `50-review.md` y `README.md`. La estructura modular es parte del diseño.
- **Mantén la concisión:** evita unir las etapas en un solo archivo extenso o añadir texto redundante que degrade la atención del modelo.
- **Sin datos personales ni rutas privadas:** no incluyas nombres propios, rutas locales de tu equipo, credenciales ni referencias a servidores o proyectos privados.
- **No debilites las protecciones de `00-base.md`:** validación en límites de confianza, manejo de errores contra pérdida de datos, seguridad, privacidad de credenciales y accesibilidad son innegociables.
- **Conserva el aviso de copyright** en [LICENSE](LICENSE).

## Traducciones

- Coloca las traducciones en `translations/<idioma>/` (por ejemplo, `translations/en/`), **sin reemplazar** los archivos originales en español.
- Mantén la misma estructura y numeración dentro de la carpeta del idioma.
