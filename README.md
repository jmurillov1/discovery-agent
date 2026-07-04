# Discovery Agent

Agente de Claude Code que convierte **conocimiento de negocio crudo** (entrevistas)
en **artefactos de producto** (personas, stakeholders, requisitos, user stories,
MVP Canvas) e **hipótesis con experimentos** para validarlos, antes de escribir
una sola línea de código de la aplicación.

Proyecto de la Unidad 1 de *Ingeniería de Software* (Maestría en Software, UPS).

## Cómo funciona

El agente es genérico: no está atado a ningún caso de negocio. Cada caso vive de
forma aislada bajo `discoveries/<nombre>/`, con dos carpetas:

- `interviews/` — entrevistas crudas en Markdown (español), con frontmatter
  (`rol_entrevistado`, `primera_persona`, `anonimizada`). Es la única fuente de
  verdad sobre ese negocio.
- `outputs/` — todo artefacto generado a partir de esa evidencia.

La skill `discovery` (`.claude/skills/discovery/`) define el formato exacto de
cada artefacto. Los comandos disponibles:

```
/discovery:analyze <discovery>       → personas.md, requisitos.md, evidence-map.json
/discovery:generate-mvp <discovery>  → user-stories.md, mvp-canvas.md
/discovery:experiments <discovery>   → hypotheses.md, experiment-board.json
/discovery:report <discovery>        → outputs/report.html (dashboard visual)
```

### Regla de oro: cero invención

Ninguna persona, dolor o requisito se afirma sin una entrevista real que lo
respalde. Una persona solo cuenta como respaldada si existe una entrevista *en
primera persona* de ese rol — que otros la mencionen no basta.

### Los gates (hooks)

Dos hooks en `.claude/hooks/`, registrados en `.claude/settings.json`, custodian
la calidad de la evidencia antes de generar artefactos clave:

- **`readiness-gate.py`** — bloquea `mvp-canvas.md` / `user-stories.md` si el
  `evidence-map.json` no existe, hay muy pocas entrevistas, alguna persona
  primaria no tiene respaldo de primera mano, o hay dolores sin fuente real.
- **`hypothesis-gate.py`** — bloquea `hypotheses.md` / `experiment-board.json`
  si alguna hipótesis no tiene señal medible, umbral concreto (con número), una
  regla de decisión que contemple el fallo, o si la métrica es de vanidad.

Ambos hooks se auto-ubican por la ruta del archivo que se escribe, así que
funcionan para cualquier discovery sin configuración adicional.

## Caso desarrollado: `sportcontrol`

Discovery completo de un sistema de gestión para un torneo deportivo
multi-disciplina (ediciones, equipos, disciplinas, reglas de puntuación, Tabla
General), hoy operado con validación manual.

- **Evidencia:** 3 entrevistas de primera mano en
  `discoveries/sportcontrol/interviews/` — Administrador, Staff operativo y
  Capitán de equipo.
- **Artefactos generados** en `discoveries/sportcontrol/outputs/`: `personas.md`,
  `requisitos.md` (36 requisitos), `evidence-map.json`, `user-stories.md` (15
  historias INVEST), `mvp-canvas.md`, `hypotheses.md` (3 hipótesis falsables
  priorizadas por riesgo), `experiment-board.json` y `report.html`.
- **Demo del gate:** el `readiness-gate` se probó bloqueando y resolviendo un
  caso real de evidencia incompleta. Evidencia en video:
  `discovery-agent-readiness-gate-evidence.mp4`.
- **Reflexión de la entrega:** `REFLEXION.md`.

Otros discoveries en el repo (`quiniela`, `stickertrack`) tienen evidencia
cargada pero están en distintas etapas del flujo, no completos.

## Estructura del repo

```
discoveries/
  _template/          discovery en blanco para copiar al empezar uno nuevo
  sportcontrol/        caso principal de esta entrega (completo)
  quiniela/            evidencia cargada, análisis pendiente
  stickertrack/         evidencia cargada, análisis pendiente
.claude/
  skills/discovery/    estándar de formato de los artefactos
  commands/            /discovery:analyze, generate-mvp, experiments, report
  hooks/                readiness-gate.py, hypothesis-gate.py
  scripts/build-report.py   generador determinista del report.html
CLAUDE.md               constitución del proyecto: reglas no negociables
REFLEXION.md            reflexión de la entrega (supuestos, dificultades, gobernanza ejecutable)
```

## Uso

```
/discovery:analyze discoveries/sportcontrol
/discovery:generate-mvp discoveries/sportcontrol
/discovery:experiments discoveries/sportcontrol
/discovery:report discoveries/sportcontrol
```

Para empezar un discovery nuevo, copia `discoveries/_template/` con el nombre
del caso y coloca ahí las entrevistas de primera mano antes de correr el flujo.
