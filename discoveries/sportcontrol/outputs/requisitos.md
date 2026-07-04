# Requisitos candidatos — sportcontrol

## Ediciones y configuración general

- **[R-01]** El sistema debe permitir gestionar varias ediciones del evento, con una única edición activa a la vez.
  - Tipo: funcional
  - Origen: administrador.md · Administrador

- **[R-02]** Las ediciones anteriores deben quedar como histórico, sin permitir cambios de Staff ni Capitanes sobre ellas.
  - Tipo: funcional
  - Origen: administrador.md · Administrador

- **[R-03]** Al crear una edición, el Administrador debe poder configurar nombre, fecha(s), estado, equipos participantes, disciplinas, reglas generales, puntos adicionales, sistemas de puntuación y reglas de desempate de la Tabla General.
  - Tipo: funcional
  - Origen: administrador.md · Administrador

## Equipos y participantes

- **[R-04]** Los equipos deben poder crearse manualmente o cargarse desde plantilla/archivo, con nombre, color, logo opcional y límite de integrantes configurable por edición (sin colores fijos predefinidos por el sistema).
  - Tipo: funcional
  - Origen: administrador.md · Administrador

- **[R-05]** Los participantes deben poder registrarse manualmente o por plantilla, con nombre completo, identificación o código interno, correo institucional opcional, equipo asignado, estado, tipo de participante y disciplinas en las que participa.
  - Tipo: funcional
  - Origen: administrador.md · Administrador

- **[R-06]** Cada participante debe pertenecer a un único equipo dentro de la edición activa.
  - Tipo: funcional (regla de negocio)
  - Origen: administrador.md · Administrador

- **[R-07]** Los participantes/jugadores no requieren cuenta de acceso a la app; solo los roles Administrador, Staff y Capitán tienen login, y sus cuentas las crea el Administrador.
  - Tipo: funcional
  - Origen: administrador.md · Administrador

- **[R-08]** Cada equipo debe tener un Capitán principal y, opcionalmente, un Capitán suplente, asignados por el Administrador dentro de la edición activa.
  - Tipo: funcional
  - Origen: administrador.md · Administrador

## Disciplinas y puntuación

- **[R-09]** Las disciplinas deben poder crearse manualmente o cargarse desde archivo, con nombre, tipo, reglas, equipos participantes, formato de competencia, sistema de puntuación y condiciones de cierre; toda disciplina registrada suma puntos a la Tabla General.
  - Tipo: funcional
  - Origen: administrador.md · Administrador

- **[R-10]** El sistema debe soportar dos sistemas de puntuación configurables: por posiciones (por defecto 1° 30 pts, 2° 15 pts, 3° 10 pts, 4° 5 pts) y semifinal + final (por defecto campeón 30 pts, subcampeón 15 pts, eliminados en semifinal 5 pts cada uno, sin partido por tercer lugar).
  - Tipo: funcional
  - Origen: administrador.md · Administrador; staff.md · Staff operativo

- **[R-11]** Los puntos de una disciplina se asignan únicamente cuando se cierra el partido decisivo o se registran las posiciones finales, no por cada partido normal jugado.
  - Tipo: funcional
  - Origen: administrador.md · Administrador

- **[R-12]** El Administrador debe poder crear puntos adicionales configurables por edición (nombre, descripción, puntaje y objetivo).
  - Tipo: funcional
  - Origen: administrador.md · Administrador

- **[R-13]** Tanto el Administrador como cualquier Staff pueden asignar puntos adicionales a un equipo; la asignación suma directamente a la Tabla General y el Administrador puede corregirla después.
  - Tipo: funcional
  - Origen: administrador.md · Administrador; staff.md · Staff operativo

- **[R-14]** El sistema no debe incluir penalizaciones en esta primera versión.
  - Tipo: funcional (alcance)
  - Origen: administrador.md · Administrador; staff.md · Staff operativo

## Fixture y partidos

- **[R-15]** El fixture puede generarse automáticamente según equipos, disciplinas y formato, y debe permitir ajustes manuales de Administrador y Staff (enfrentamientos, fecha, hora, cancha o ubicación).
  - Tipo: funcional
  - Origen: administrador.md · Administrador; staff.md · Staff operativo

- **[R-16]** Un partido solo maneja tres estados: pendiente, en curso y finalizado.
  - Tipo: funcional
  - Origen: administrador.md · Administrador; staff.md · Staff operativo

- **[R-17]** No debe existir empate final en partidos ni disciplinas; si el marcador queda igualado, el Staff o el Administrador deben registrar un valor de desempate por equipo para definir el ganador del encuentro.
  - Tipo: funcional (regla de negocio)
  - Origen: administrador.md · Administrador; staff.md · Staff operativo

- **[R-18]** Para la Tabla General, el Administrador configura por edición las reglas de desempate (p. ej. mayor número de primeros lugares); si persiste el empate, el Administrador registra manualmente un valor de desempate final. Solo el Administrador puede configurar estas reglas.
  - Tipo: funcional
  - Origen: administrador.md · Administrador

## Cierre y reportes

- **[R-19]** Al cerrar una edición, el Administrador puede hacer correcciones finales antes del cierre definitivo; luego la edición queda como histórico y se genera un reporte final.
  - Tipo: funcional
  - Origen: administrador.md · Administrador

- **[R-20]** El reporte final debe incluir edición, fecha del evento, equipos participantes, Tabla General final, ganador general, resultados por disciplina, puntos adicionales asignados, asistencia por equipo y resumen de partidos jugados, exportable en PDF y Excel.
  - Tipo: funcional
  - Origen: administrador.md · Administrador

- **[R-21]** El sistema debe permitir recuperación de contraseña por correo electrónico y restablecimiento manual por el Administrador para usuarios con rol Administrador, Staff o Capitán.
  - Tipo: no funcional (seguridad / usabilidad)
  - Origen: administrador.md · Administrador

## Operación del Staff

- **[R-22]** El Staff solo puede operar sobre la edición activa; no puede trabajar sobre ediciones pasadas ni cerradas.
  - Tipo: funcional
  - Origen: staff.md · Staff operativo

- **[R-23]** Al ingresar, el Staff debe ver la edición activa, la lista de partidos y actividades, filtros por disciplina o estado, accesos rápidos para registrar resultados, marcar asistencia, asignar puntos adicionales y consultar la Tabla General, además de un resumen de partidos pendientes, en curso y finalizados.
  - Tipo: funcional
  - Origen: staff.md · Staff operativo

- **[R-24]** El Staff puede definir enfrentamientos, ajustar fecha/hora/cancha/ubicación y cambiar el estado del partido, pero no puede modificar reglas generales del fixture ni configuraciones de la edición.
  - Tipo: funcional
  - Origen: staff.md · Staff operativo

- **[R-25]** Al guardar un resultado, el Staff registra Equipo A y su marcador, Equipo B y su marcador; el sistema registra automáticamente la fecha y hora del registro.
  - Tipo: funcional
  - Origen: staff.md · Staff operativo

- **[R-26]** Los resultados se publican directamente sin requerir aprobación del Administrador; cualquier Staff puede corregir cualquier resultado de la edición activa.
  - Tipo: funcional
  - Origen: staff.md · Staff operativo

- **[R-27]** La Tabla General no se edita manualmente: se calcula automáticamente a partir de resultados, posiciones, disciplinas cerradas y puntos adicionales asignados. El Staff solo puede consultarla.
  - Tipo: funcional
  - Origen: staff.md · Staff operativo

- **[R-28]** Cuando se cierra la final en el sistema semifinal + final, el sistema debe asignar automáticamente los puntos configurados (por defecto 30/15/5).
  - Tipo: funcional
  - Origen: staff.md · Staff operativo

- **[R-29]** En disciplinas configuradas por posiciones, el Staff o el Administrador registran las posiciones finales y el sistema asigna automáticamente los puntos configurados.
  - Tipo: funcional
  - Origen: staff.md · Staff operativo

- **[R-30]** La asistencia se marca por equipo (presente o ausente), no jugador por jugador; el sistema debe registrar automáticamente la fecha y hora del check-in.
  - Tipo: funcional
  - Origen: staff.md · Staff operativo

- **[R-31]** El Staff no puede crear ediciones ni equipos, gestionar usuarios, modificar reglas generales, configurar sistemas de puntuación, configurar reglas de desempate ni cerrar definitivamente una edición.
  - Tipo: funcional (restricción de permisos)
  - Origen: staff.md · Staff operativo

## Consulta del Capitán

- **[R-32]** El Capitán puede consultar la información general y la nómina de su propio equipo (nombre, disciplinas, tipo de participante, estado), sin ver datos sensibles como identificación, código interno o correo institucional.
  - Tipo: funcional
  - Origen: capitan.md · Capitán de equipo

- **[R-33]** El Capitán puede consultar en modo lectura las nóminas oficiales de otros equipos, viendo solo nombre del participante, equipo y disciplinas, sin datos administrativos.
  - Tipo: funcional
  - Origen: capitan.md · Capitán de equipo

- **[R-34]** El Capitán puede consultar el fixture (enfrentamientos, fecha, hora, cancha o ubicación, estado) y los resultados del evento, pero no puede registrar resultados ni editar nóminas.
  - Tipo: funcional
  - Origen: capitan.md · Capitán de equipo

- **[R-35]** El Capitán no tiene acceso a la Tabla General en esta primera versión.
  - Tipo: funcional (alcance)
  - Origen: capitan.md · Capitán de equipo

- **[R-36]** No se requieren notificaciones push para el Capitán en esta primera versión.
  - Tipo: funcional (alcance, descartado)
  - Origen: capitan.md · Capitán de equipo
