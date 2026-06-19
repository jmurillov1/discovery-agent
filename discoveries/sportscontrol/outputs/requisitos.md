# Requisitos candidatos — sportscontrol

- **[R-01]** Bloquear el registro de un equipo si ya cuenta con 28 integrantes.
  - Tipo: funcional
  - Origen: human-talent-manager.md, captain.md · Representante de Talento Humano, Capitán de equipo

- **[R-02]** Atar cada usuario a su color de equipo (Cian, Verde, Púrpura, Azul)
  sin posibilidad de préstamo de jugadores entre equipos.
  - Tipo: funcional
  - Origen: human-talent-manager.md, captain.md · Representante de Talento Humano, Capitán de equipo

- **[R-03]** Emitir una alerta automática si se intenta inscribir a un mismo
  jugador en dos listas principales de disciplinas que se cruzan en horario.
  - Tipo: funcional
  - Origen: human-talent-manager.md · Representante de Talento Humano

- **[R-04]** Bloquear o sombrear visualmente, al armar la dupla del Campeonato
  de 40, a los jugadores que ya hayan participado en deportes de balón
  (Fútbol 7, Baloncesto, Ecuavoley).
  - Tipo: funcional
  - Origen: human-talent-manager.md, captain.md · Representante de Talento Humano, Capitán de equipo

- **[R-05]** Permitir solicitar apoyo interno (jugador de soporte del mismo
  color) cuando el equipo está incompleto en cancha, sugiriendo únicamente
  jugadores libres de horario en ese instante.
  - Tipo: funcional
  - Origen: captain.md · Capitán de equipo

- **[R-06]** Exigir el check-in de las sustituciones obligatorias (3 en Fútbol
  7, 4 en Baloncesto) y levantar una bandera de "Incumplimiento del Espíritu
  de Integración" si no se registran al terminar el partido.
  - Tipo: funcional
  - Origen: human-talent-manager.md · Representante de Talento Humano

- **[R-07]** Detener el partido y declarar ganador automáticamente por ventaja
  desproporcionada: diferencia de 4 goles en Fútbol 7, 15 puntos en
  Baloncesto, o parcial 7-0 en Ecuavoley (cierre automático del set).
  - Tipo: funcional
  - Origen: human-talent-manager.md · Representante de Talento Humano

- **[R-08]** En el Campeonato de 40, deshabilitar los tantos ordinarios al
  llegar a 38 puntos, forzando que el cierre de la partida se ejecute única y
  exclusivamente mediante el evento "Caída".
  - Tipo: funcional
  - Origen: human-talent-manager.md · Representante de Talento Humano

- **[R-09]** Consolidar en tiempo real la Tabla General sumando los puntajes
  directos (+30, +15, +5), la Gincana y el Bono de Inauguración (+20 puntos)
  por asistencia completa a las 08:00 AM con uniforme y barra.
  - Tipo: funcional
  - Origen: human-talent-manager.md · Representante de Talento Humano

- **[R-10]** Resolver los empates en la tabla acumulada aplicando, en orden
  descendente: (1) mayor número de campeonatos, (2) mayor número de
  subcampeonatos, (3) mayor puntaje en la Gincana.
  - Tipo: funcional
  - Origen: human-talent-manager.md · Representante de Talento Humano

- **[R-11]** Mostrar a cada capitán un inventario visual de su plantilla con
  estado dinámico por jugador ("Libre", "Jugando - <disciplina>", "Lesionado").
  - Tipo: funcional
  - Origen: captain.md · Capitán de equipo

- **[R-12]** Mostrar fixtures interactivos (Semifinales A/B, Gran Final) por
  disciplina, con notificaciones push cuando el árbitro actualiza un
  resultado.
  - Tipo: funcional
  - Origen: captain.md · Capitán de equipo

- **[R-13]** Permitir a cualquier capitán auditar la lista oficial validada de
  un equipo rival (por ejemplo, buscando por color de equipo) para verificar
  el límite de 28 personas y la ausencia de refuerzos no autorizados.
  - Tipo: funcional
  - Origen: captain.md · Capitán de equipo

- **[R-14]** El sistema debe reflejar los resultados reportados por los
  árbitros en la Tabla General sin demoras ni inconsistencias de formato, para
  evitar acusaciones de favoritismo institucional.
  - Tipo: no funcional
  - Origen: human-talent-manager.md · Representante de Talento Humano
