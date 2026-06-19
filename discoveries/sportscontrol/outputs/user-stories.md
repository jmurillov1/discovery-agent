# User stories — sportscontrol

Historias priorizadas por el núcleo de valor: el control automático de nómina y
la visibilidad de plantilla, que es el dolor que más se repite entre las dos
personas primarias (Representante de Talento Humano y Capitán de equipo). Las
reglas de marcador en vivo y la Tabla General (dolor exclusivo de Talento
Humano, mucho más costoso de construir) quedan fuera de este primer MVP — ver
`mvp-canvas.md`.

- **[US-01]** Como Representante de Talento Humano, quiero que el sistema
  bloquee el registro de un nuevo integrante en un equipo que ya tiene 28
  personas, para terminar con el control manual en papel que genera el caos de
  nóminas.
  - Criterios de aceptación:
    - Dado un equipo con 28 integrantes registrados, cuando se intenta agregar
      un integrante 29, entonces el sistema rechaza el registro y muestra el
      motivo (tope alcanzado).
    - Dado un equipo con menos de 28 integrantes, cuando se agrega uno nuevo,
      entonces el registro se acepta normalmente.
  - Fuente: human-talent-manager.md, captain.md (R-01, `pesadilla-listas`).

- **[US-02]** Como Representante de Talento Humano, quiero atar cada jugador a
  un único color de equipo de forma permanente, para eliminar el "baile" de
  jugadores entre equipos.
  - Criterios de aceptación:
    - Dado un jugador ya asignado al color Cian, cuando alguien intenta
      registrarlo también en el equipo Verde, entonces el sistema rechaza la
      operación.
    - Dado un jugador sin equipo asignado, cuando se le asigna un color por
      primera vez, entonces queda fijo y no editable salvo por una excepción
      administrativa explícita.
  - Fuente: human-talent-manager.md, captain.md (R-02, `pesadilla-listas`).

- **[US-03]** Como Representante de Talento Humano, quiero recibir una alerta
  automática cuando un jugador quede inscrito en dos disciplinas con horarios
  que se cruzan, para detectar el conflicto antes de que ocurra en cancha.
  - Criterios de aceptación:
    - Dado un jugador inscrito en la lista principal de Fútbol 7 con partido a
      las 09:00, cuando se lo intenta inscribir en la lista principal de
      Baloncesto con partido también a las 09:00, entonces el sistema muestra
      una alerta de cruce de horario antes de confirmar.
  - Fuente: human-talent-manager.md (R-03, `pesadilla-listas`).

- **[US-04]** Como Capitán de equipo, quiero ver sombreados o bloqueados a los
  jugadores que ya disputaron un deporte de balón al armar mi dupla del
  Campeonato de 40, para no tener que memorizar la regla ni discutirla con la
  organización.
  - Criterios de aceptación:
    - Dado un jugador que ya jugó Fútbol 7, Baloncesto o Ecuavoley en el
      torneo, cuando el capitán abre la pantalla de armado de dupla del
      Campeonato de 40, entonces ese jugador aparece sombreado y no
      seleccionable.
    - Dado un jugador que no ha jugado ningún deporte de balón, cuando se
      arma la dupla, entonces aparece disponible para seleccionar.
  - Fuente: human-talent-manager.md, captain.md (R-04, `pesadilla-listas`).

- **[US-05]** Como Capitán de equipo, quiero ver el estado en tiempo real de
  cada jugador de mi plantilla (Libre, Jugando - <disciplina>, Lesionado),
  para coordinar apoyos sin depender de WhatsApp.
  - Criterios de aceptación:
    - Dado un jugador que está disputando un partido de Baloncesto, cuando el
      capitán abre el inventario de plantilla, entonces ve a ese jugador con
      estado "Jugando - Baloncesto".
    - Dado un jugador sin partido activo, cuando el capitán abre el
      inventario, entonces lo ve con estado "Libre".
  - Fuente: captain.md (R-11, `logistica-ciegas`).

- **[US-06]** Como Capitán de equipo, quiero solicitar un jugador de apoyo del
  mismo color sugiriendo únicamente a los que están libres en ese instante,
  para completar mi equipo en cancha sin perder tiempo llamando uno por uno.
  - Criterios de aceptación:
    - Dado que el capitán necesita un apoyo, cuando abre la pantalla de
      solicitud de apoyo, entonces el sistema solo le sugiere jugadores de su
      mismo color con estado "Libre" en ese momento.
    - Dado que no hay jugadores libres de ese color, cuando se abre la
      pantalla de solicitud, entonces el sistema informa que no hay apoyos
      disponibles en lugar de sugerir jugadores ocupados.
  - Fuente: captain.md (R-05, `logistica-ciegas`).

- **[US-07]** Como Capitán de equipo, quiero auditar la lista oficial validada
  de cualquier equipo rival por color, para verificar que cumple el tope de 28
  y no tiene refuerzos no autorizados.
  - Criterios de aceptación:
    - Dado un equipo rival con su lista validada por Talento Humano, cuando un
      capitán busca ese equipo por color, entonces ve la nómina completa y el
      conteo total de integrantes.
    - Dado que el capitán intenta editar la lista de un equipo rival, cuando
      hace la consulta, entonces el sistema solo permite ver, nunca modificar.
  - Fuente: captain.md (R-13, `falta-transparencia-rivales`).
