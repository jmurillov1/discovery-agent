# Reflexión — Discovery Agent (caso: sportcontrol)

**Caso:** gestión de un torneo deportivo multi-disciplina (ediciones, equipos,
disciplinas, puntuación, tabla general) para un área organizadora que hoy valida
todo manualmente.

## ¿Qué supuesto tuyo cambió al revisar la evidencia real?

Previo a leer las entrevistas asumía que la corrección de un resultado ya registrado
sería una actividad crítica que necesitaría aprobación de un administrador, como
en la mayoría de sistemas administrativos. `staff.md` no estaba de acuerdo con esto: 
pide explícitamente que "cualquier Staff pueda modificar cualquier resultado... 
para que la operación no esté atada a quién registró primero el resultado". 
El objetivo real de los organizadores del evento no es el control jerárquico, sino la
velocidad operativa durante el evento, recalcando también la transparencia del proceso
— un torneo en vivo no puede esperar una aprobación para corregir un marcador mal asignado.

Lo segundo dado por hecho que cambió fue sobre quién es reconocida como "persona" del
sistema. Asumí que el Participante/Jugador sería al menos una persona
secundaria, porque es el actor más visible de este tipo de torneos. La evidencia
(`administrador.md`) afirma lo siguiente: "los participantes o
jugadores pueden estar registrados solo como integrantes de un equipo, sin
necesidad de iniciar sesión". No debe formar parte del sistema como tal — es
una entidad de datos gestionada por otros roles, no un usuario.

## ¿Qué fue lo más difícil de cumplir la regla de "cero invención"?

En base al desarrollo del agente, en el proceso de análisis este me dio una pista 
sobre el papel de esta persona (Participante/Jugador): la idea de modelarlo 
como persona secundaria "porque en teoría, un jugador obviamente usa un sistema de torneos" 
era muy determinante, a pesar de que no existía una entrevista que lo respaldaba
como actor con acceso al sistema o interacciones en la plataforma. 
La regla de cero invención obligó a dejar constancia explícita del por qué se descartó, 
en vez de dejarlo fuera sin una justificación clara. Luego se repite algo similar con Tabla General: fue
tentador dar por sentado reglas de desempate "algo normal" de otros torneos que no estaban
en `administrador.md`, y hubo que seguir los lineamientos tal cual la entrevista
los configuraba.

El gate de readiness endureció esta práctica de forma muy concreta: en un
momento del proceso, `staff.md` y `capitan.md` no estaban disponibles en
`interviews/` y el `readiness-gate.py` bloqueó la generación del MVP,
indicando las personas que no tenían respaldo de primera mano y qué
dolores citaban archivos inexistentes. No dejó continuar solo con lo ya
conversado — exigió la evidencia en disco antes de seguir.

## ¿Para qué te serviría la idea de "gobernanza ejecutable" en tu trabajo?

La gobernanza ejecutable —las directrices de calidad que un script valida en vez
de esperar que alguien "se acuerde" o de un proceso manual— es
ampliamente fácil de aplicar a cualquier proceso que tenga evidencia insuficiente,
relacionado a la presión de tiempo. En la realidad, esto determina que no se pasen 
a las siguientes fases de un proyecto como los son el diseño o desarrollo de software
sin validar los principales riesgos, o que se acepten métricas de éxito vagas ("engagement", "usuarios
felices") en vez de umbrales concretos y refutables. El equivalente al
`hypothesis-gate` en mi trabajo sería, por ejemplo, la checklist automatizada que
rechace un documento de requerimientos si no cita su fuente, o que bloquee un
plan de lanzamiento si su métrica de éxito no pasa la prueba ácida (si sube,
¿alguien puede decir qué decisión cambia?). La ventaja frente a una checklist
manual es que el gate no se puede "saltar" bajo presión: bloquea antes de que
el problema llegue más lejos en las fases siguientes del proceso.

## Cierre

Si ejecutara el ejercicio de nuevo, tomaría una nueva entrevista extra por
persona desde el inicio (esto por el Capitán, que hoy solo tiene
una fuente) para mitigar el riesgo de que un solo relato determine toda una
persona del sistema.
