# Resumen de la entrega — Discovery Agent (caso: sportcontrol)

**Repositorio:** https://github.com/jmurillov1/discovery-agent

**Caso elegido:** gestión de un torneo deportivo multi-disciplina — ediciones,
equipos, disciplinas, reglas de puntuación y Tabla General, para un área
organizadora que hoy valida todo manualmente.

## Evidencia recopilada

3 entrevistas en primera persona, en `discoveries/sportcontrol/interviews/`:
- `administrador.md` — administrador del evento
- `staff.md` — staff operativo
- `capitan.md` — capitán de equipo

## Flujo de descubrimiento ejecutado

1. `/discovery:analyze` → `personas.md`, `requisitos.md` (36 requisitos), `evidence-map.json`
2. `/discovery:generate-mvp` → `user-stories.md` (15 historias INVEST), `mvp-canvas.md`
3. `/discovery:experiments` → `hypotheses.md`, `experiment-board.json` (3 hipótesis falsables, priorizadas por riesgo)
4. `/discovery:report` → `report.html` (dashboard visual autocontenido)

Todo en `discoveries/sportcontrol/outputs/`.

## Demostración del gate (obligatorio)

Se provocó un bloqueo real del `readiness-gate.py` retirando temporalmente las
entrevistas de Staff y Capitán antes de correr `generate-mvp`; el hook bloqueó
señalando exactamente qué personas quedaban sin respaldo de primera mano. Al
restaurar las entrevistas, el comando pasó sin problema. Evidencia en video:
`discovery-agent-readiness-gate-evidence.mp4`.

## Verificación de trazabilidad

Se contrastaron manualmente 3 afirmaciones de `personas.md` contra sus
entrevistas fuente (`administrador.md`, `staff.md`, `capitan.md`); todas
trazaron correctamente sin invención.

## Reflexión

`REFLEXION.md` — responde qué supuestos cambiaron con la evidencia real (p. ej.
que la corrección de resultados no requiere aprobación, y que el Jugador no es
una persona del sistema), qué fue lo más difícil de cumplir cero invención, y
cómo aplicaría la gobernanza ejecutable fuera del ejercicio.

## Corrección incidental

De paso se detectó y corrigió un bug real en `.claude/settings.json`: los
hooks estaban invocados con `python3 -m "<ruta>"` (flag inválido para una ruta
de archivo), lo que impedía que los gates se ejecutaran. Corregido en el commit
`0b37330`.
