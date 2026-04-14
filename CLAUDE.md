# CLAUDE.md

Este archivo orienta a Claude Code (claude.ai/code) para trabajar con este repositorio.

## Proyecto

Herramienta de planificación quirúrgica que clasifica la alineación coronal en artroplastia total de rodilla mediante el sistema CPAK (Coronal Plane Alignment of the Knee). Introduce mediciones radiológicas (LDFA, MPTA) y calcula automáticamente el fenotipo en 9 subtipos, con recomendaciones quirúrgicas y datos de prevalencia.

## Sistema de diseño

Usa **Sistema B "Radiología Glass"** (ver `../CLAUDE.md` y `../STYLE-GUIDE.md`):
- Fuentes: Source Serif 4 + Source Sans 3 + Source Code Pro
- Header: Slate Steel con accent line sky→violet
- Glassmorphism: `backdrop-filter: blur()` + `background: rgba()` en cards/inputs
- Dark mode: `[data-theme="dark"]` con sky toggle CSS puro

## Arquitectura

App single-file (`index.html`). CSS en `<style>`, JS en `<script>`, sin build tools. Matriz visual 3×3 de fenotipos, estrategia quirúrgica y prevalencia.

Bloques principales:
- **CPAK clásico**: aHKA × JLO → 9 subtipos (MacDessi 2021).
- **JLCA**: `jlca = (mhka − 180) − aHKA`. Se calcula en [`calculateAndUpdate`](index.html) cuando se introduce mHKA.
- **Hirschmann 2024**: clasificación SD de HKA/FMA/TMA estratificada por sexo (n=11.991 no artrósicos).
- **Corrección constitucional** (función `updateHirschmann`): si `|JLCA| ≥ 2°`, reparte el JLCA entre LDFA/MPTA proporcional a su desviación vs media poblacional (heurística) y clasifica SD sobre los ángulos **constitucionales estimados**, no los medidos. Motivo: Hirschmann se deriva de rodillas sanas → los ángulos medidos de rodillas artrósicas producen falsos "aberrantes". Fórmula base: `aHKA = mHKA − JLCA` (MacDessi 2021).
- **Hint UNI**: cuando `|JLCA| ≥ 2°` y el fenotipo constitucional es ≤2 SD (neutral/normal) → banner verde sugiriendo valorar unicompartimental antes que PTR con constricción.

## Integraciones

- **knee-align** pasa `?ldfa&mpta&mhka` (no `sex` ni `jlca`). CPAK recalcula JLCA internamente → integración funcional sin cambios en knee-align.
- **Sexo por defecto**: 'M'. El toggle lo cambia a 'F'. Query param `?sex=F|M` soportado.

## Reglas al editar Hirschmann

- No clasificar sobre ángulos medidos cuando `|JLCA| ≥ 2°`.
- El alerta de mHKA aberrante sigue basándose en el medido (refleja lo que el paciente tiene hoy).
- La prevalencia OA (`getOAPrevalence`) usa mHKA medido (coherente con cohorte artrósica).
- Cuando añadas texto a banners, construir DOM con `textContent` y `createElement` — el hook de seguridad bloquea `innerHTML`.

## Autenticación

Línea 4: comprueba `cot_auth` en localStorage con TTL 24h. Redirige al hub en producción; se salta en localhost.

## Desarrollo

Sin build step. Servir localmente:

```bash
npx serve -l 8083
```

Deploy: GitHub Pages desde `main`, raíz `/`.

## Licencia

All Rights Reserved (no es MIT como el resto de herramientas).
