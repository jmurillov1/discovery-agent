---
fuente: entrevista
rol_entrevistado: administrador
primera_persona: true
anonimizada: true
fecha: 2026-07-04
---

# Entrevista — Administrador del sistema

> Notas crudas de la conversación. El nombre real fue reemplazado por "A." por anonimización.
> El entrevistado corresponde al administrador encargado de crear álbumes base, gestionar stickers, revisar usuarios y mantener la información general del sistema.

**Entrevistador:** ¿Cómo esperas crear los álbumes dentro del sistema?

**A. (administrador):** Quiero poder crear álbumes cargando una estructura YAML, ya sea pegando el texto en la app o subiendo un archivo `.yaml` o `.yml`. El sistema debería validar el contenido antes de guardarlo.

**Entrevistador:** ¿Qué información general debe tener un álbum dentro del YAML?

**A.:** El YAML debe incluir nombre del álbum, descripción, categoría, temporada, editorial, país o región, URL de portada, estado activo o inactivo y las secciones del álbum.

**Entrevistador:** ¿Cómo quieres que el YAML permita crear los stickers del álbum?

**A.:** Quiero que permita crear stickers por secciones usando rangos. Por ejemplo, una sección Ecuador con código `ECU` del 1 al 20, generando stickers como `ECU-01`, `ECU-02`, etc. También debe permitir marcar algunos números como especiales dorados, por ejemplo `especiales: [5, 9]`.

**Entrevistador:** ¿Qué validaciones debe hacer el sistema cuando se carga el YAML?

**A.:** El sistema debe validar que el YAML esté bien escrito, que tenga los datos obligatorios del álbum, que las secciones tengan nombre y código, que los rangos estén correctos, que no existan códigos repetidos, que los stickers especiales estén dentro del rango y que la URL de portada sea válida.

**Entrevistador:** ¿Qué esperas que pase después de cargar un YAML válido?

**A.:** Me gustaría que el sistema muestre una vista previa del álbum antes de guardarlo, indicando el nombre, portada, secciones, cantidad total de stickers, stickers especiales dorados y posibles advertencias. Luego el administrador debería poder confirmar o cancelar la creación del álbum.

**Entrevistador:** ¿Qué acciones necesitas hacer después de que un álbum ya fue creado?

**A.:** Necesito poder editar los datos del álbum, activarlo o desactivarlo, eliminarlo si fue creado por error, revisar qué usuarios lo están usando y corregir secciones, stickers o portada si encuentro algún problema.

**Entrevistador:** ¿Qué información te gustaría ver en el inicio o panel principal del administrador?

**A.:** Me gustaría ver un resumen con los álbumes creados, cuáles están activos o inactivos, total de usuarios registrados, álbumes más usados, reportes generales, errores recientes de carga YAML y acceso a la gestión de usuarios.

**Entrevistador:** ¿Qué acciones debería poder hacer sobre los usuarios registrados?

**A.:** Me gustaría poder ver la lista de usuarios, buscar usuarios por nombre o correo, revisar qué álbumes tiene cada uno, activar o desactivar cuentas si es necesario y ver su actividad general dentro de la app.

**Entrevistador:** ¿Qué problema quieres evitar al crear álbumes manualmente?

**A.:** Quiero evitar tener que crear sticker por sticker de forma manual, porque sería lento y propenso a errores. Por eso necesito que el YAML permita generar álbumes completos de manera rápida, usando secciones, códigos, rangos y stickers especiales.

**Entrevistador:** ¿Qué reportes o estadísticas necesitas ver como administrador?

**A.:** Me gustaría ver total de usuarios registrados, total de álbumes creados, álbumes activos e inactivos, álbumes más usados, cantidad de stickers por álbum, cantidad de intercambios realizados, usuarios más activos y errores detectados en archivos YAML cargados.
