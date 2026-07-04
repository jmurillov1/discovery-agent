---
fuente: entrevista
rol_entrevistado: administrador
primera_persona: true
anonimizada: true
fecha: 2026-07-04
---

# Entrevista — Administrador del evento

> Notas crudas de la conversación. Entrevista cualitativa sobre la administración general del evento, configuración de ediciones, equipos, disciplinas, puntajes, usuarios y cierre del torneo.
> El nombre real fue reemplazado por "A." por anonimización.

**Entrevistador:** ¿Cuál es el objetivo principal de la plataforma para la administración del evento?

**A. (administrador):** La app debe automatizar la aplicación del reglamento del torneo, reduciendo decisiones manuales y evitando interpretaciones subjetivas. También debe reducir la carga operativa del área organizadora, evitando que el personal tenga que validar manualmente cada regla, nómina o resultado del torneo.

**Entrevistador:** ¿Qué roles tendrá el sistema?

**A.:** Los roles principales serán Administrador, Staff y Capitán. El Administrador tendrá el control general del sistema. El Staff operará la edición activa del evento, registrando resultados, asistencia y puntos adicionales. El Capitán tendrá acceso principalmente de consulta para revisar su equipo, nóminas, fixture y resultados.

**Entrevistador:** ¿Cómo se manejarán las ediciones del evento?

**A.:** El sistema debe permitir gestionar varias ediciones del evento, pero solo una edición podrá estar activa a la vez. Las ediciones anteriores deben quedar como histórico. El Staff y los Capitanes trabajarán únicamente sobre la edición activa.

**Entrevistador:** ¿Qué datos debe configurar el Administrador al crear una edición?

**A.:** Debe configurar el nombre de la edición, fecha o fechas del evento, estado de la edición, equipos participantes, disciplinas, reglas generales, puntos adicionales, sistemas de puntuación y reglas de desempate para la Tabla General.

**Entrevistador:** ¿Cómo se crearán los equipos?

**A.:** Los equipos deben poder crearse manualmente o cargarse desde una plantilla o archivo. Cada equipo tendrá nombre, color, logo opcional y límite de integrantes configurable. No quiero que el sistema quede amarrado a colores fijos como Cian, Verde, Púrpura o Azul; eso debe configurarse por edición.

**Entrevistador:** ¿Cómo se registrarán los jugadores o participantes?

**A.:** Los participantes también deben poder registrarse manualmente o cargarse desde una plantilla. Cada participante debe tener nombre completo, identificación o código interno, correo institucional opcional, equipo asignado, estado, tipo de participante y disciplinas en las que participa. Cada participante debe pertenecer a un único equipo dentro de la edición activa.

**Entrevistador:** ¿Todos los participantes tendrán cuenta en la app?

**A.:** No necesariamente. El Administrador será quien cree las cuentas de acceso para los roles Administrador, Staff y Capitán. Los participantes o jugadores pueden estar registrados solo como integrantes de un equipo, sin necesidad de iniciar sesión.

**Entrevistador:** ¿Cómo se asignarán los Capitanes?

**A.:** Cada equipo tendrá un Capitán principal y opcionalmente un Capitán suplente. Ambos serán usuarios creados por el Administrador y asociados a un equipo dentro de la edición activa.

**Entrevistador:** ¿Cómo se configurarán las disciplinas?

**A.:** Las disciplinas podrán crearse manualmente o cargarse desde archivo. Cada disciplina debe tener nombre, tipo, reglas, equipos participantes, formato de competencia, sistema de puntuación y condiciones de cierre. Toda disciplina registrada debe sumar puntos a la Tabla General.

**Entrevistador:** ¿Qué sistemas de puntuación debe permitir la plataforma?

**A.:** Para esta primera versión se manejarán dos sistemas principales: Por posiciones y Semifinal + Final. También existirán puntos adicionales configurados por el Administrador. No se incluirán por ahora penalizaciones, puntos manuales, resultado directo ni actividades especiales como sistema de puntuación separado.

**Entrevistador:** ¿Cómo funciona el sistema de puntuación por posiciones?

**A.:** El sistema por posiciones asignará puntos según la ubicación final de los equipos. Por defecto será: primer lugar 30 puntos, segundo lugar 15 puntos, tercer lugar 10 puntos y cuarto lugar 5 puntos. Estos valores pueden personalizarse por disciplina si el reglamento lo requiere.

**Entrevistador:** ¿Cómo funciona el sistema Semifinal + Final?

**A.:** En ese sistema no habrá partido por tercer lugar. Cuando el Staff cierre la final, el sistema asignará automáticamente 30 puntos al campeón, 15 puntos al subcampeón y 5 puntos a cada equipo eliminado en semifinales. Estos valores también podrán personalizarse por disciplina.

**Entrevistador:** ¿Cuándo se asignan los puntos?

**A.:** Los puntos se asignan cuando el partido decisivo se cierra o cuando se registran posiciones finales, según el sistema de puntuación configurado. No se suman puntos por cada partido normal, sino cuando ese partido o cierre define una posición o resultado final de la disciplina.

**Entrevistador:** ¿Qué son los puntos adicionales?

**A.:** Los puntos adicionales son conceptos configurables por edición. El Administrador puede crear varios, colocando nombre, descripción, puntaje y objetivo. Por ejemplo, “Asistencia a inauguración” con 20 puntos o “Mejor barra” con 10 puntos. Luego el Administrador o el Staff pueden asignarlos al equipo que cumpla el objetivo.

**Entrevistador:** ¿El Staff puede asignar puntos adicionales?

**A.:** Sí. El Administrador los configura en la edición del torneo y cualquier Staff puede asignarlos a un equipo. No se pedirá observación ni evidencia en esta primera versión. La asignación suma directamente a la Tabla General, pero el Administrador puede corregirla después si detecta un error.

**Entrevistador:** ¿La plataforma manejará penalizaciones?

**A.:** No. Para esta primera versión no se incluirán penalizaciones. La Tabla General se calculará únicamente con puntos por posiciones, puntos por semifinal y final, y puntos adicionales asignados.

**Entrevistador:** ¿Cómo se manejará el fixture o calendario de partidos?

**A.:** El sistema puede generar automáticamente el fixture según equipos, disciplinas y formato, pero también debe permitir ajustes manuales. El Administrador y el Staff podrán definir quién juega contra quién. El Staff también podrá ajustar fecha, hora, cancha o ubicación, y estado del partido dentro de la edición activa.

**Entrevistador:** ¿Qué estados tendrá un partido?

**A.:** Solo tres estados: pendiente, en curso y finalizado. No quiero complicarlo con más estados por ahora.

**Entrevistador:** ¿Cómo se manejarán los empates en partidos o disciplinas?

**A.:** En los partidos o disciplinas no debe existir empate. Si un marcador queda igualado, el Staff o Administrador deberá registrar un valor de desempate por equipo para definir el ganador del encuentro.

**Entrevistador:** ¿Y los empates en la Tabla General?

**A.:** Eso es diferente. Para la Tabla General, el Administrador podrá configurar reglas de desempate por edición. Por ejemplo, mayor número de primeros lugares, mayor número de segundos lugares o mayor puntaje en una disciplina específica. Si las reglas automáticas no resuelven el empate, el Administrador podrá registrar un valor de desempate final por equipo.

**Entrevistador:** ¿Quién puede configurar las reglas de desempate?

**A.:** Solo el Administrador. El Staff podrá ver la Tabla General, pero no podrá modificar las reglas que determinan el orden final.

**Entrevistador:** ¿Cómo se cerrará una edición del evento?

**A.:** Al finalizar una edición, el Administrador podrá hacer correcciones finales antes del cierre definitivo. Luego la edición quedará como histórico y se generará un reporte final.

**Entrevistador:** ¿Qué debe incluir el reporte final?

**A.:** Debe incluir nombre de la edición, fecha del evento, equipos participantes, Tabla General final, ganador general, resultados por disciplina, puntos adicionales asignados, asistencia por equipo y resumen de partidos jugados. No debe incluir penalizaciones porque no estarán en esta versión.

**Entrevistador:** ¿En qué formatos debe exportarse el reporte final?

**A.:** Debe poder verse dentro de la plataforma y exportarse en PDF y Excel.

**Entrevistador:** ¿Cómo se manejará la recuperación de contraseña?

**A.:** El sistema debe permitir recuperación por correo electrónico y también restablecimiento manual por parte del Administrador para usuarios con rol Administrador, Staff o Capitán.
