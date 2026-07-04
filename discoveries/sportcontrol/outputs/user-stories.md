# User stories — sportcontrol

Historias priorizadas por núcleo de valor: primero lo que más se repite y más
duele entre personas (automatizar reglamento y puntuación, operar resultados sin
fricción), luego la consulta de transparencia del Capitán. Fuera del MVP van
reportes exportables, recuperación de contraseña por correo y multi-edición
histórica — ver `mvp-canvas.md`.

## Configuración de edición (Administrador)

- **[US-01]** Como Administrador, quiero crear una edición del torneo con equipos, disciplinas y reglas de puntuación para tener el torneo listo antes de que empiece.
  - Criterios de aceptación:
    - Dado que no existe una edición activa, cuando el Administrador crea una nueva edición con nombre, fecha(s), equipos y disciplinas, entonces la edición queda registrada como activa.
    - Dado que existe una edición activa, cuando el Administrador intenta crear otra, entonces el sistema no permite dos ediciones activas simultáneas.
  - Fuente: administrador.md (R-01, R-03)

- **[US-02]** Como Administrador, quiero configurar el sistema de puntuación de cada disciplina (por posiciones o semifinal+final) para que los puntos se asignen según las reglas del torneo sin decidirlo yo a mano cada vez.
  - Criterios de aceptación:
    - Dado que configuro una disciplina por posiciones, cuando se registran las posiciones finales, entonces el sistema asigna automáticamente los puntos por defecto (30/15/10/5) o los que yo haya configurado.
    - Dado que configuro una disciplina semifinal+final, cuando se cierra la final, entonces el sistema asigna automáticamente los puntos de campeón, subcampeón y eliminados en semifinal, sin partido de tercer lugar.
  - Fuente: administrador.md (R-09, R-10, R-11, R-28, R-29)

- **[US-03]** Como Administrador, quiero crear equipos con color configurable por edición (sin colores fijos del sistema) para no arrastrar la rigidez de versiones anteriores.
  - Criterios de aceptación:
    - Dado que creo un equipo, cuando le asigno un color, entonces puedo elegir cualquier color y no una lista fija predefinida por el sistema.
  - Fuente: administrador.md (R-04)

- **[US-04]** Como Administrador, quiero registrar participantes asignados a un único equipo, sin que necesiten cuenta de acceso, para reflejar cómo se inscribe realmente a los jugadores.
  - Criterios de aceptación:
    - Dado que registro un participante, cuando lo asigno a un equipo, entonces queda vinculado a un único equipo dentro de la edición activa.
    - Dado un participante registrado, cuando reviso su cuenta, entonces no existe login asociado a él.
  - Fuente: administrador.md (R-05, R-06, R-07)

- **[US-05]** Como Administrador, quiero crear puntos adicionales configurables por edición para premiar comportamientos que el reglamento define fuera del resultado deportivo.
  - Criterios de aceptación:
    - Dado que creo un punto adicional con nombre, puntaje y objetivo, cuando el Staff o yo lo asignamos a un equipo, entonces suma directamente a la Tabla General.
  - Fuente: administrador.md (R-12, R-13)

## Operación de resultados (Staff)

- **[US-06]** Como Staff operativo, quiero registrar el resultado de un partido con el marcador de ambos equipos para dejar constancia inmediata sin esperar aprobación.
  - Criterios de aceptación:
    - Dado un partido pendiente o en curso, cuando guardo el marcador de Equipo A y Equipo B, entonces el sistema publica el resultado de inmediato y registra automáticamente fecha y hora del registro.
  - Fuente: staff.md (R-25, R-26)

- **[US-07]** Como Staff operativo, quiero poder corregir cualquier resultado de la edición activa, sin importar quién lo registró primero, para que la operación no dependa de una sola persona.
  - Criterios de aceptación:
    - Dado un resultado ya registrado por otro Staff, cuando yo lo edito, entonces el sistema acepta la corrección sin pedir aprobación adicional.
  - Fuente: staff.md (R-26)

- **[US-08]** Como Staff operativo, quiero registrar un valor de desempate cuando el marcador quede igualado, para que nunca quede un partido sin ganador.
  - Criterios de aceptación:
    - Dado un partido con marcador igualado al finalizar, cuando registro el valor de desempate por equipo, entonces el sistema define un ganador y no permite dejar el partido como empatado.
  - Fuente: staff.md, administrador.md (R-17)

- **[US-09]** Como Staff operativo, quiero marcar la asistencia por equipo para llevar control de presencia sin registrar jugador por jugador.
  - Criterios de aceptación:
    - Dado un equipo convocado a un partido, cuando marco su asistencia como presente o ausente, entonces el sistema registra automáticamente la fecha y hora del check-in.
  - Fuente: staff.md (R-30)

- **[US-10]** Como Staff operativo, quiero ver al ingresar la edición activa, el fixture y accesos directos para registrar resultados y asistencia, para operar rápido sin navegar de más.
  - Criterios de aceptación:
    - Dado que inicio sesión, cuando entro al sistema, entonces veo la edición activa, la lista de partidos con su estado y accesos rápidos a registrar resultado, marcar asistencia y asignar puntos adicionales.
  - Fuente: staff.md (R-23)

## Tabla General automática (Administrador, Staff)

- **[US-11]** Como Administrador o Staff, quiero consultar la Tabla General calculada automáticamente a partir de resultados, disciplinas cerradas y puntos adicionales, para no tener que sumar puntos manualmente.
  - Criterios de aceptación:
    - Dado que se registran resultados, se cierran disciplinas o se asignan puntos adicionales, cuando consulto la Tabla General, entonces los totales reflejan esos cambios sin que nadie los haya editado a mano.
    - Dado un intento de edición manual de la Tabla General, cuando el Staff lo intenta, entonces el sistema lo rechaza porque solo se calcula, no se edita.
  - Fuente: staff.md, administrador.md (R-27)

- **[US-12]** Como Administrador, quiero configurar las reglas de desempate de la Tabla General por edición para resolver empates entre equipos sin discutirlo caso por caso.
  - Criterios de aceptación:
    - Dado dos equipos empatados en la Tabla General, cuando aplico la regla de desempate configurada (p. ej. mayor número de primeros lugares), entonces el sistema define el orden; si persiste el empate, registro manualmente un valor de desempate final.
  - Fuente: administrador.md (R-18)

## Consulta de transparencia (Capitán)

- **[US-13]** Como Capitán de equipo, quiero consultar la nómina de mi equipo para verificar que mis jugadores estén correctamente registrados.
  - Criterios de aceptación:
    - Dado que soy Capitán de un equipo, cuando consulto su nómina, entonces veo nombre, disciplinas y estado de cada participante, sin datos sensibles como identificación, código interno o correo institucional.
  - Fuente: capitan.md (R-32)

- **[US-14]** Como Capitán de equipo, quiero consultar en modo lectura las nóminas oficiales de los equipos rivales para confirmar que los participantes estén registrados correctamente y dar transparencia al torneo.
  - Criterios de aceptación:
    - Dado un equipo rival en la edición activa, cuando consulto su nómina, entonces veo solo nombre del participante, equipo y disciplinas, sin datos administrativos.
  - Fuente: capitan.md (R-33)

- **[US-15]** Como Capitán de equipo, quiero consultar el fixture y los resultados del evento para organizar a mi equipo con información oficial y actualizada.
  - Criterios de aceptación:
    - Dado un partido programado, cuando lo consulto, entonces veo enfrentamiento, fecha, hora, cancha o ubicación y estado; y si ya finalizó, veo su resultado.
    - Dado que soy Capitán, cuando intento registrar un resultado o editar una nómina, entonces el sistema no me lo permite (solo lectura).
  - Fuente: capitan.md (R-34)
