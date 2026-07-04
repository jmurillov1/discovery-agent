---
fuente: entrevista
rol_entrevistado: administrador
primera_persona: true
anonimizada: true
fecha: 2026-07-04
---

# Entrevista — Administrador de quiniela

> Notas crudas de la conversación. Entrevista cualitativa sobre la administración de una app para pollas mundialistas o quinielas, enfocada en configuración de torneos, pagos, premios, pronósticos, ranking, auditoría y transparencia.
> El nombre real fue reemplazado por "A." por anonimización.

**Entrevistador:** ¿Cuál será el rol principal del Administrador dentro de la app?

**A. (administrador):** El Administrador será quien cree y configure cada quiniela. Debe poder configurar el torneo, los partidos, las reglas de puntuación, la cuota de inscripción, la comisión, el pozo de premios y los participantes.

**Entrevistador:** ¿Qué roles tendrá el sistema?

**A.:** El sistema tendrá dos roles principales: Administrador y Usuario o Participante. El Administrador gestiona quinielas, torneos, pagos, resultados, premios y ranking. El Usuario participa, realiza pronósticos y consulta su avance. También se considera a futuro un sistema o API externa de resultados deportivos.

**Entrevistador:** ¿El Administrador puede crear varias quinielas?

**A.:** Sí. Un Administrador puede crear y administrar varias quinielas al mismo tiempo. Cada quiniela tendrá su propia configuración, participantes, partidos, reglas, pagos, premios, ranking y estado.

**Entrevistador:** ¿Qué estados tendrá una quiniela?

**A.:** La quiniela tendrá los estados borrador, abierta, en curso, finalizada y archivada. En borrador se configura; en abierta los usuarios pueden unirse; en curso ya hay partidos activos; finalizada bloquea cambios para usuarios; y archivada queda solo como histórico.

**Entrevistador:** ¿Qué pasa cuando una quiniela se finaliza?

**A.:** Cuando esté finalizada, los usuarios ya no podrán registrar pronósticos, hacer pagos ni modificar información de participación. El Administrador podrá hacer correcciones finales de resultados o recalcular el ranking antes de archivarla. Luego se genera el ranking final, la distribución de premios y el reporte final.

**Entrevistador:** ¿La quiniela será pública o privada?

**A.:** Debe ser configurable. Una quiniela pública puede ser vista por usuarios registrados para solicitar unirse. Una quiniela privada se accede mediante código o enlace de invitación.

**Entrevistador:** ¿Cómo se manejará la inscripción de participantes?

**A.:** El Usuario podrá solicitar unirse a una quiniela pública o ingresar mediante código/enlace si es privada. El Administrador también podrá agregar participantes manualmente. La participación oficial dependerá del estado de inscripción y pago, si la quiniela requiere pago.

**Entrevistador:** ¿Se podrán crear quinielas gratuitas?

**A.:** Sí, si la cuota de inscripción se configura en 0. En ese caso, el Administrador podrá decidir si los usuarios quedan activos automáticamente al unirse o si requieren aprobación manual.

**Entrevistador:** ¿Qué estados tendrá la inscripción de un Usuario?

**A.:** En quinielas pagadas se manejarán: pendiente de pago, comprobante enviado, pago aprobado, pago rechazado y participante activo. En quinielas gratuitas se manejarán: solicitud enviada, participante activo, rechazado e inactivo.

**Entrevistador:** ¿Cómo se manejarán los pagos?

**A.:** El Usuario puede subir un comprobante de pago y el Administrador lo valida. El Administrador también puede registrar pagos manualmente si el pago se hizo por otro medio, como efectivo o transferencia confirmada fuera de la plataforma.

**Entrevistador:** ¿Qué debe ver el Administrador en los comprobantes?

**A.:** Debe ver el Usuario, la quiniela asociada, estado de inscripción, archivo o imagen del comprobante, fecha de carga, monto reportado y botones para aprobar o rechazar.

**Entrevistador:** ¿Qué pasa cuando se rechaza un comprobante?

**A.:** El Administrador puede rechazarlo y agregar un motivo opcional. No quiero que sea obligatorio para no hacer pesado el proceso.

**Entrevistador:** ¿Qué pasa cuando se aprueba un comprobante?

**A.:** El Usuario puede pasar automáticamente a participante activo. Además, el Administrador debe tener un botón para activar manualmente al Usuario en cualquier caso, incluso si no paga, por cortesía, invitación, exoneración o registro interno.

**Entrevistador:** ¿Cómo se calculará el pozo de premios?

**A.:** El sistema debe calcular automáticamente el pozo según la cuota de inscripción y los participantes activos o con pago aprobado. La comisión del Administrador será configurable y puede ser 0% si no se desea cobrar comisión.

**Entrevistador:** ¿Cómo se distribuirán los premios?

**A.:** El Administrador podrá configurar premios por posición en el ranking general. La distribución puede ser por porcentajes del pozo o por montos fijos. La cantidad de posiciones ganadoras será configurable.

**Entrevistador:** ¿Habrá premios especiales?

**A.:** No por ahora. Solo premios por posición en el ranking general.

**Entrevistador:** ¿Cómo se cargarán los partidos?

**A.:** El Administrador podrá registrar partidos manualmente o cargarlos desde una plantilla o archivo. Además, podrá usar un torneo base para no repetir la carga de partidos en varias quinielas.

**Entrevistador:** ¿Qué es un torneo base?

**A.:** Es una estructura reutilizable con equipos, fases, partidos, fechas y horarios. El sistema puede traer torneos base preconfigurados, como Mundial 2026, pero el Administrador también puede crear torneos propios.

**Entrevistador:** ¿Una quiniela puede modificar un torneo base?

**A.:** Si necesita modificarlo, el Administrador debe copiar el torneo base y crear una versión editable para su quiniela. Así se protege el torneo base original y no se afecta a otras quinielas.

**Entrevistador:** ¿Qué datos mínimos tendrá un equipo del torneo base?

**A.:** Nombre del equipo, código corto como ECU, ARG o BRA, bandera o escudo opcional, grupo o fase inicial y estado activo o eliminado.

**Entrevistador:** ¿Qué formato se usará para cargar torneos base?

**A.:** YAML. El YAML debe permitir definir equipos, códigos, grupos o fases, partidos, fechas, horarios, estados y datos generales del torneo.

**Entrevistador:** ¿Qué debe validar el sistema al cargar un YAML?

**A.:** Debe validar equipos sin nombre o código, códigos repetidos, partidos con equipos inexistentes, fechas u horas inválidas, fases no definidas, partidos duplicados, YAML mal escrito y estados inválidos.

**Entrevistador:** ¿Qué debe pasar si el YAML es válido?

**A.:** El sistema debe mostrar una vista previa antes de guardar, con datos generales, equipos, fases, partidos, fechas, horarios, estados iniciales y advertencias si existen. Luego el Administrador confirma o cancela.

**Entrevistador:** ¿Qué datos mínimos tendrá cada partido?

**A.:** Equipo local, equipo visitante, fecha, hora, fase, estado, marcador del tiempo regular, tiempo extra si aplica, penales si aplica y resultado final definitivo.

**Entrevistador:** ¿Las fases del torneo serán fijas?

**A.:** No totalmente. El sistema puede traer fases por defecto como grupos, octavos, cuartos, semifinal y final, pero el Administrador podrá editarlas o crear fases personalizadas.

**Entrevistador:** ¿Qué pronostican los usuarios?

**A.:** Los usuarios pronostican únicamente el marcador del tiempo regular, es decir, los 90 minutos más el tiempo adicional agregado por el árbitro. No pronostican tiempo extra, penales ni ganador final por penales.

**Entrevistador:** ¿Cómo se calculan los puntos?

**A.:** El sistema compara el pronóstico del Usuario contra el marcador real del tiempo regular. Por defecto, un marcador exacto vale 3 puntos y acertar el resultado —gana local, empate o gana visitante— vale 1 punto. El Administrador puede cambiar esos valores.

**Entrevistador:** ¿Hasta cuándo se puede editar un pronóstico?

**A.:** El Usuario puede registrar o editar su pronóstico libremente hasta antes de la hora de inicio del partido. Cuando llega la hora de cierre, el pronóstico se bloquea.

**Entrevistador:** ¿Qué pasa si cambia la hora del partido?

**A.:** El cierre de pronósticos se mantiene con la primera hora registrada del partido. La hora visible puede actualizarse si el Administrador cambia el horario, pero el cierre queda ligado a la hora original para evitar ventajas o confusiones. El cambio queda en auditoría.

**Entrevistador:** ¿Se debe guardar la hora de cierre de pronóstico?

**A.:** Sí. Cada partido debe guardar una hora exacta de cierre de pronósticos. Esa hora se usa para bloquear predicciones, auditar cambios y demostrar que nadie pronosticó fuera de tiempo.

**Entrevistador:** ¿Qué pasa cuando llega la hora de cierre?

**A.:** El sistema bloquea automáticamente los pronósticos de ese partido y los hace públicos para los participantes de la quiniela.

**Entrevistador:** ¿Qué pasa si un Usuario no pronostica a tiempo?

**A.:** Pierde la oportunidad de pronosticar ese partido y recibe 0 puntos. El sistema no debe registrar marcadores automáticos ni permitir pronósticos después del cierre.

**Entrevistador:** ¿Cómo se registran los resultados reales?

**A.:** En la primera versión, el Administrador puede registrar resultados manualmente. La app debe quedar preparada para una futura integración con una API deportiva, pero no debe depender de ella al inicio.

**Entrevistador:** ¿Qué datos debe registrar el Administrador en el resultado real?

**A.:** Marcador del tiempo regular, si hubo tiempo extra, marcador después de tiempo extra, si hubo penales, marcador de penales, ganador final y confirmación del resultado para calcular puntos.

**Entrevistador:** ¿Los puntos se calculan con el resultado final o con el tiempo regular?

**A.:** Solo con el marcador del tiempo regular. Aunque el partido tenga tiempo extra o penales, el cálculo de puntos de la quiniela se hace contra los 90 minutos más tiempo adicional.

**Entrevistador:** ¿Cómo se actualiza el ranking?

**A.:** Cuando se registra o sincroniza un resultado real, el ranking se actualiza automáticamente. El Administrador también puede forzar un recálculo manual si detecta errores o corrige un resultado.

**Entrevistador:** ¿Cómo se resuelven empates en el ranking final?

**A.:** El Administrador podrá configurar las reglas de desempate. Por defecto pueden ser: mayor cantidad de marcadores exactos, mayor cantidad de aciertos de resultado y pronósticos registrados con mayor anticipación. Si el empate persiste, el Administrador define manualmente el orden final.

**Entrevistador:** ¿Ese desempate manual debe quedar auditado?

**A.:** Sí. Debe quedar registrado con fecha, hora, usuario administrador, participantes afectados, orden anterior y nuevo.

**Entrevistador:** ¿Qué acciones deben quedar en auditoría?

**A.:** Creación o edición de partidos, cambios de resultados reales, cambios en reglas de puntuación, validación o rechazo de pagos, cambios en inscripción, modificaciones de pronósticos antes del cierre, recálculos manuales del ranking y cambios manuales de desempate.

**Entrevistador:** ¿Qué debe mostrar el panel del Administrador?

**A.:** Debe mostrar quinielas creadas, participantes inscritos, pagos, pozo de premios calculado, partidos pendientes, en vivo y finalizados, resultados, ranking general y accesos a configuración de reglas, premios y partidos. No se necesita un módulo de alertas automáticas por ahora.

**Entrevistador:** ¿Cómo se gestionarán los pagos desde el panel?

**A.:** Debe existir una pantalla general de pagos con filtros por estado, quiniela y fecha de carga del comprobante. También se podrá revisar el pago desde el detalle de cada participante.

**Entrevistador:** ¿Qué filtros tendrá la pantalla de pagos?

**A.:** Todos, pendiente de pago, comprobante enviado, pago aprobado, pago rechazado, participante activo, por quiniela y por fecha de carga del comprobante.

**Entrevistador:** ¿Qué puede hacer el Administrador con los participantes?

**A.:** Puede ver participantes por quiniela, buscar por nombre, alias o correo, revisar estado de inscripción, activar manualmente, desactivar, ver comprobante, ver pronósticos, puntaje y posición en ranking.

**Entrevistador:** ¿Qué pasa si se desactiva un participante?

**A.:** Ya no puede pronosticar en esa quiniela, pero no se borra ningún dato. Se conservan sus pronósticos, puntaje, historial, comprobantes y estado. El Administrador decide si se mantiene visible o se oculta del ranking.

**Entrevistador:** ¿Se puede eliminar un participante?

**A.:** No. Solo se puede desactivar para conservar trazabilidad.

**Entrevistador:** ¿Se puede eliminar una quiniela?

**A.:** Solo si está en estado borrador y no tiene participantes. Si ya tiene participantes o avanzó a otros estados, no se elimina; solo se puede archivar.

**Entrevistador:** ¿Se puede eliminar un torneo base?

**A.:** Solo si no está asociado a ninguna quiniela. Si está en uso, no se elimina; se puede desactivar o archivar.

**Entrevistador:** ¿Habrá notificaciones?

**A.:** No por ahora. El Usuario debe ingresar a la plataforma para revisar partidos, ranking, pronósticos, pagos y resultados.

**Entrevistador:** ¿La app tendrá soporte móvil?

**A.:** Sí. Será una web responsive con soporte PWA instalable. El Administrador podrá usarla desde móvil y escritorio, pero la experiencia principal de administración debe optimizarse para escritorio.

**Entrevistador:** ¿La PWA funcionará sin internet?

**A.:** Sí, pero solo para consulta de información cargada previamente. No se podrá registrar ni editar pronósticos sin internet, porque el cierre de pronósticos debe ser exacto.
