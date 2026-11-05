# Capítulo III: Requirements Specification

## 3.1. To-Be Scenario Mapping

### Introducción

A partir del As-Is Scenario Mapping elaborado en el Capítulo II, el equipo construye la versión To-Be para cada User Persona, representando cómo cambiará su experiencia una vez implementada la solución WeRide. El proceso siguió las etapas de preparación, lluvia de ideas individual, revisión grupal, identificación de fases como columnas, y comparación directa con el mapa As-Is para identificar los cambios que ofrece la nueva experiencia.

### To-Be Scenario Map — Camila Torres (Joven Universitaria)

<table style="width:100%; border-collapse:collapse; text-align:left; font-size:13px;">
  <thead>
    <tr style="background:#f2f2f2;">
      <th style="border:1px solid #999; padding:8px;">Fase</th>
      <th style="border:1px solid #999; padding:8px;">Descubrimiento</th>
      <th style="border:1px solid #999; padding:8px;">Búsqueda y reserva</th>
      <th style="border:1px solid #999; padding:8px;">Uso del vehículo</th>
      <th style="border:1px solid #999; padding:8px;">Pago y cierre</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="border:1px solid #999; padding:8px; font-weight:bold;">Thinking</td>
      <td style="border:1px solid #999; padding:8px;">"¿Hay una forma más rápida y económica de llegar a la universidad?"</td>
      <td style="border:1px solid #999; padding:8px;">"Puedo ver en el mapa qué vehículos están disponibles cerca de mí."</td>
      <td style="border:1px solid #999; padding:8px;">"Me siento segura porque sé el estado de la batería y la ruta."</td>
      <td style="border:1px solid #999; padding:8px;">"Pagué con Yape/Plin sin necesitar efectivo."</td>
    </tr>
    <tr>
      <td style="border:1px solid #999; padding:8px; font-weight:bold;">Doing</td>
      <td style="border:1px solid #999; padding:8px;">Descarga la app WeRide y revisa el mapa en tiempo real.</td>
      <td style="border:1px solid #999; padding:8px;">Reserva un scooter/bicicleta cercano y lo desbloquea desde la app.</td>
      <td style="border:1px solid #999; padding:8px;">Viaja usando el vehículo, con monitoreo IoT activo.</td>
      <td style="border:1px solid #999; padding:8px;">Finaliza el viaje y paga automáticamente por la app.</td>
    </tr>
    <tr>
      <td style="border:1px solid #999; padding:8px; font-weight:bold;">Feeling</td>
      <td style="border:1px solid #999; padding:8px;">Curiosidad / Interés</td>
      <td style="border:1px solid #999; padding:8px;">Confianza</td>
      <td style="border:1px solid #999; padding:8px;">Tranquilidad</td>
      <td style="border:1px solid #999; padding:8px;">Satisfacción</td>
    </tr>
  </tbody>
</table>

Principales cambios respecto al As-Is: tiempos de búsqueda de vehículo reducidos gracias a geolocalización en tiempo real; proceso de desbloqueo simplificado; mayor sensación de seguridad por visibilidad del estado de batería/vehículo; eliminación de incertidumbre sobre disponibilidad y de la dependencia de efectivo.

### To-Be Scenario Map — Luis Salazar (Empresas / B2B)

<table style="width:100%; border-collapse:collapse; text-align:left; font-size:13px;">
  <thead>
    <tr style="background:#f2f2f2;">
      <th style="border:1px solid #999; padding:8px;">Fase</th>
      <th style="border:1px solid #999; padding:8px;">Evaluación</th>
      <th style="border:1px solid #999; padding:8px;">Implementación</th>
      <th style="border:1px solid #999; padding:8px;">Operación diaria</th>
      <th style="border:1px solid #999; padding:8px;">Seguimiento</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="border:1px solid #999; padding:8px; font-weight:bold;">Thinking</td>
      <td style="border:1px solid #999; padding:8px;">"WeRide puede reducir nuestros costos de transporte interno."</td>
      <td style="border:1px solid #999; padding:8px;">"El plan corporativo es flexible y escalable para todos los colaboradores."</td>
      <td style="border:1px solid #999; padding:8px;">"Puedo ver en el dashboard cuánto se está usando el servicio."</td>
      <td style="border:1px solid #999; padding:8px;">"Los reportes de uso justifican la inversión ante gerencia."</td>
    </tr>
    <tr>
      <td style="border:1px solid #999; padding:8px; font-weight:bold;">Doing</td>
      <td style="border:1px solid #999; padding:8px;">Contacta a WeTech y revisa el plan de suscripción corporativa.</td>
      <td style="border:1px solid #999; padding:8px;">Registra a los colaboradores en la plataforma empresarial.</td>
      <td style="border:1px solid #999; padding:8px;">Monitorea el uso de la flota desde el dashboard administrativo.</td>
      <td style="border:1px solid #999; padding:8px;">Analiza métricas de ahorro de tiempo y costos con el equipo directivo.</td>
    </tr>
    <tr>
      <td style="border:1px solid #999; padding:8px; font-weight:bold;">Feeling</td>
      <td style="border:1px solid #999; padding:8px;">Expectativa</td>
      <td style="border:1px solid #999; padding:8px;">Confianza</td>
      <td style="border:1px solid #999; padding:8px;">Control</td>
      <td style="border:1px solid #999; padding:8px;">Satisfacción</td>
    </tr>
  </tbody>
</table>

Principales cambios respecto al As-Is: visibilidad centralizada de uso de flota mediante dashboard administrativo; reducción de tiempos muertos de gestión y de costos por taxis/estacionamiento; trazabilidad completa de vehículos asignados a colaboradores; reemplazo de la frustración inicial por control y confianza en la solución.

---

## 3.2. User Stories.
En esta sección se presentan las épicas e historias de usuario identificadas para WeRide, incluyendo sus roles, prioridades, descripciones y criterios de aceptación. Los escenarios de aceptación se expresan mediante la estructura Dado–Cuando–Entonces.
### EP01 — Acceso a la aplicación

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-01 | Usuario | Alta | EP01 |
| **Title** | Inicio de sesión y registro | | |
| **Description** | Como usuario quiero poder iniciar sesión o registrarme en la app para usarla diariamente. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que una persona no tiene cuenta, cuando proporciona datos válidos de registro, entonces el sistema crea su cuenta y permite su autenticación. | | |
| | **Escenario 2:** Dado que las credenciales son incorrectas, cuando se intenta completar la operación correspondiente, entonces el sistema rechaza el acceso sin iniciar sesión. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-02 | Usuario | Alta | EP01 |
| **Title** | Introducir Número de Celular | | |
| **Description** | Como usuario, quiero introducir mi número de celular para validar mi identidad y recibir notificaciones importantes. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que un usuario debe verificar su identidad, cuando registra un número telefónico válido, entonces el sistema acepta el número para iniciar la verificación. | | |
| | **Escenario 2:** Dado que el número no cumple el formato esperado, cuando se intenta completar la operación correspondiente, entonces el sistema informa que no puede utilizarse. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-03 | Usuario | Alta | EP01 |
| **Title** | Introducir código de verificación | | |
| **Description** | Como usuario, quiero introducir un código de verificación para validar mi identidad en la aplicación. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que existe un código de verificación vigente, cuando el usuario proporciona el código correcto, entonces el sistema confirma la verificación. | | |
| | **Escenario 2:** Dado que el código es inválido o venció, cuando se intenta completar la operación correspondiente, entonces el sistema no valida la identidad. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-04 | Usuario nuevo | Alta | EP01 |
| **Title** | Datos de usuario | | |
| **Description** | Como usuario nuevo, quiero crear mi perfil con mis datos para que la app personalice mi experiencia. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que un usuario acaba de registrarse, cuando completa los datos obligatorios de su perfil, entonces el sistema guarda la información asociada a su cuenta. | | |
| | **Escenario 2:** Dado que faltan datos obligatorios, cuando se intenta completar la operación correspondiente, entonces el sistema impide completar el registro. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-06 | Usuario | Media | EP01 |
| **Title** | Gestión y personalización de perfil | | |
| **Description** | Como usuario, quiero administrar mi cuenta y mi perfil para mantener mis datos actualizados. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que un usuario autenticado tiene un perfil, cuando modifica datos permitidos, entonces el sistema conserva los cambios. | | |
| | **Escenario 2:** Dado que los datos nuevos no son válidos, cuando se intenta completar la operación correspondiente, entonces el sistema rechaza la actualización. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-36 | Usuario registrado | Media | EP01 |
| **Title** | Recuperar contraseña | | |
| **Description** | Como usuario registrado, quiero recuperar mi contraseña para volver a entrar si la olvido. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que un usuario registrado olvidó su contraseña, cuando solicita recuperar el acceso y verifica su identidad, entonces el sistema permite establecer nuevas credenciales. | | |
| | **Escenario 2:** Dado que la verificación no es válida, cuando se intenta completar la operación correspondiente, entonces el sistema impide modificar la contraseña. | | |

### EP02 — Funcionalidades de la app

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-05 | Usuario | Alta | EP02 |
| **Title** | Página Principal | | |
| **Description** | Como usuario, quiero ver una pantalla principal clara con accesos rápidos para llegar rápido a reservar un vehículo. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que un usuario ha iniciado sesión, cuando consulta las funciones principales, entonces el sistema ofrece acceso a búsqueda, reservas y viajes. | | |
| | **Escenario 2:** Dado que no hay reservas activas, cuando se intenta completar la operación correspondiente, entonces el sistema presenta el estado sin inventar viajes. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-07 | Usuario | Alta | EP02 |
| **Title** | Gestión y visualización de vehículos en Garaje | | |
| **Description** | Como usuario, quiero ver los vehículos del Garaje para elegir el que mejor se ajuste a mi viaje. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que existen vehículos registrados, cuando el usuario consulta el catálogo de vehículos, entonces el sistema devuelve sus características y disponibilidad. | | |
| | **Escenario 2:** Dado que no existen vehículos disponibles, cuando se intenta completar la operación correspondiente, entonces el sistema devuelve un resultado vacío. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-08 | Usuario | Alta | EP02 |
| **Title** | Filtrado de vehículos en Garaje | | |
| **Description** | Como usuario, quiero filtrar los vehículos por tipo, precio, disponibilidad o marca para encontrar rápidamente el adecuado. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que hay vehículos con diferentes características, cuando el usuario aplica filtros de tipo, precio o disponibilidad, entonces el sistema devuelve solo los vehículos que cumplen las condiciones. | | |
| | **Escenario 2:** Dado que ningún vehículo cumple los filtros, cuando se intenta completar la operación correspondiente, entonces el sistema devuelve un resultado vacío. | | |

### EP03 — Gestión de pagos y suscripciones

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-09 | Usuario | Alta | EP03 |
| **Title** | Selección y pago de planes | | |
| **Description** | Como usuario, quiero comparar los planes disponibles para elegir el que más me conviene. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que existen planes activos, cuando el usuario consulta y selecciona un plan, entonces el sistema informa las condiciones y el precio del plan. | | |
| | **Escenario 2:** Dado que el plan deja de estar disponible, cuando se intenta completar la operación correspondiente, entonces el sistema impide seleccionarlo. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-10 | Usuario | Alta | EP03 |
| **Title** | Proceso de pago de planes | | |
| **Description** | Como usuario quiero ingresar los datos de mi tarjeta para activar el plan seleccionado. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que un usuario seleccionó un plan vigente, cuando envía datos de pago válidos en el entorno habilitado, entonces el sistema procesa la solicitud y registra el resultado. | | |
| | **Escenario 2:** Dado que la operación de pago es rechazada, cuando se intenta completar la operación correspondiente, entonces el sistema no activa el plan. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-24 | Usuario | Alta | EP03 |
| **Title** | Pago en línea (sandbox) | | |
| **Description** | Como usuario, quiero pagar mi viaje o plan con Yape/Plin (modo sandbox) para completar el cobro sin usar efectivo. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que existe un importe pendiente en el entorno sandbox, cuando el usuario confirma el pago con el medio simulado, entonces el sistema registra el resultado de la transacción. | | |
| | **Escenario 2:** Dado que el proveedor simulado rechaza la operación, cuando se intenta completar la operación correspondiente, entonces el sistema mantiene el pago pendiente. | | |

### EP04 — Uso del mapa

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-11 | Usuario | Alta | EP04 |
| **Title** | Seleccionar ubicación para ver vehículos cercanos disponibles | | |
| **Description** | Como usuario, quiero ver los vehículos cercanos a la ubicación que elijo en el mapa para reservar el más cercano. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que el usuario indica una ubicación válida, cuando solicita vehículos próximos, entonces el sistema devuelve vehículos disponibles cercanos a esa ubicación. | | |
| | **Escenario 2:** Dado que no hay unidades cercanas, cuando se intenta completar la operación correspondiente, entonces el sistema informa que no hay disponibilidad. | | |

### EP05 — Gestión de viajes

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-12 | Usuario en viaje | Alta | EP05 |
| **Title** | Visualización de viaje en mapa | | |
| **Description** | Como usuario en viaje, quiero ver mi trayecto y los datos del vehículo para controlar la batería y el tiempo restante. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que hay un viaje en curso, cuando el usuario consulta su trayecto, entonces el sistema entrega la ruta y el estado actualizado del vehículo. | | |
| | **Escenario 2:** Dado que no existe un viaje activo, cuando se intenta completar la operación correspondiente, entonces el sistema no devuelve datos de un viaje ajeno. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-13 | Usuario | Media | EP05 |
| **Title** | Historial de viajes | | |
| **Description** | Como usuario, quiero ver el historial de mis viajes para trackear gastos y rutas. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que un usuario tiene viajes finalizados, cuando consulta su historial, entonces el sistema devuelve fechas, trayectos y costos asociados. | | |
| | **Escenario 2:** Dado que no existen viajes anteriores, cuando se intenta completar la operación correspondiente, entonces el sistema devuelve un historial vacío. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-14 | Usuario | Media | EP05 |
| **Title** | Calificación de viaje | | |
| **Description** | Como usuario, quiero calificar mi experiencia después del viaje para feedback y mejora del servicio. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que un usuario finalizó un viaje, cuando envía una calificación válida, entonces el sistema registra la valoración vinculada al viaje. | | |
| | **Escenario 2:** Dado que intenta calificar un viaje ajeno, cuando se intenta completar la operación correspondiente, entonces el sistema rechaza la calificación. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-15 | Usuario | Media | EP05 |
| **Title** | Reportar problema con vehículo | | |
| **Description** | Como usuario, quiero reportar un problema con el vehículo para alertar a soporte y obtener ayuda rápida. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que un usuario identifica una incidencia en un vehículo, cuando registra un reporte con los datos necesarios, entonces el sistema crea la incidencia para soporte. | | |
| | **Escenario 2:** Dado que faltan datos esenciales, cuando se intenta completar la operación correspondiente, entonces el sistema solicita completar el reporte. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-23 | Usuario en viaje | Alta | EP05 |
| **Title** | Finalizar viaje | | |
| **Description** | Como usuario en viaje, quiero finalizar mi viaje desde la app para dejar el vehículo bloqueado y cerrar el cobro. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que un usuario tiene un viaje activo, cuando solicita finalizarlo en condiciones permitidas, entonces el sistema cierra el viaje y calcula el importe. | | |
| | **Escenario 2:** Dado que no se confirma el bloqueo del vehículo, cuando se intenta completar la operación correspondiente, entonces el sistema informa que el cierre está pendiente. | | |

### EP06 — Gestión de reservas

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-16 | Usuario | Alta | EP06 |
| **Title** | Notificación de fin de reserva | | |
| **Description** | Como usuario, quiero recibir una notificación antes de que finalice mi reserva. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que una reserva está próxima a finalizar, cuando se alcanza el momento configurado de aviso, entonces el sistema genera la notificación de finalización próxima. | | |
| | **Escenario 2:** Dado que la reserva fue cancelada, cuando se intenta completar la operación correspondiente, entonces el sistema no envía un aviso de fin para esa reserva. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-17 | Usuario | Alta | EP06 |
| **Title** | Crear una reserva | | |
| **Description** | Como usuario, quiero reservar un vehículo desde la app para asegurar su disponibilidad. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que un vehículo se encuentra disponible, cuando el usuario solicita reservarlo, entonces el sistema registra la reserva y actualiza la disponibilidad. | | |
| | **Escenario 2:** Dado que el vehículo ya está reservado, cuando se intenta completar la operación correspondiente, entonces el sistema rechaza la reserva duplicada. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-18 | Usuario con reserva | Alta | EP06 |
| **Title** | Notificación de inicio y vencimiento | | |
| **Description** | Como usuario con reserva, quiero recibir notificaciones cuando mi reserva esté activa y por expirar para no perderla. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que una reserva cambia a activa o se aproxima a su vencimiento, cuando ocurre el evento correspondiente, entonces el sistema genera el aviso asociado al estado. | | |
| | **Escenario 2:** Dado que la reserva ya no está vigente, cuando se intenta completar la operación correspondiente, entonces el sistema evita generar avisos de vigencia incorrectos. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-37 | Usuario con una reserva activa | Alta | EP06 |
| **Title** | Cancelar reserva | | |
| **Description** | Como usuario con una reserva activa, quiero cancelarla para liberar el vehículo si cambio de planes. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que un usuario tiene una reserva cancelable, cuando solicita cancelarla, entonces el sistema actualiza su estado y libera el vehículo. | | |
| | **Escenario 2:** Dado que la reserva ya inició su viaje, cuando se intenta completar la operación correspondiente, entonces el sistema aplica las restricciones de cancelación. | | |

### EP07 — Desbloqueo y acceso rápido a vehículos

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-19 | Usuario con reserva activa | Alta | EP07 |
| **Title** | Desbloqueo de vehículo con QR | | |
| **Description** | Como usuario con reserva activa, quiero desbloquear el vehículo escaneando un QR para iniciar mi viaje sin pasos adicionales. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que el usuario tiene una reserva válida, cuando se valida el código QR del vehículo reservado, entonces el sistema autoriza el desbloqueo del vehículo correcto. | | |
| | **Escenario 2:** Dado que el código pertenece a otro vehículo, cuando se intenta completar la operación correspondiente, entonces el sistema deniega el desbloqueo. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-20 | Usuario con reserva activa | Alta | EP07 |
| **Title** | Desbloqueo de vehículo desde la app | | |
| **Description** | Como usuario con reserva activa, quiero desbloquear el vehículo desde la app para iniciar mi viaje cuando no puedo escanear el QR. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que el usuario tiene una reserva activa, cuando solicita desbloquear el vehículo reservado, entonces el sistema envía la orden de desbloqueo autorizada. | | |
| | **Escenario 2:** Dado que la reserva no corresponde al usuario, cuando se intenta completar la operación correspondiente, entonces el sistema rechaza la solicitud. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-21 | Usuario | Alta | EP07 |
| **Title** | Ver estado de desbloqueo | | |
| **Description** | Como usuario, quiero ver el estado del desbloqueo en tiempo real para saber cuándo puedo empezar a conducir. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que se solicitó un desbloqueo, cuando cambia el estado del dispositivo, entonces el sistema comunica el estado confirmado. | | |
| | **Escenario 2:** Dado que el dispositivo no confirma la operación, cuando se intenta completar la operación correspondiente, entonces el sistema informa que el desbloqueo no se completó. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-22 | Usuario | Baja | EP07 |
| **Title** | Desbloqueo programado | | |
| **Description** | Como usuario, quiero programar el desbloqueo de un vehículo para una hora específica y asegurar su disponibilidad. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que un vehículo admite programación y está disponible, cuando el usuario solicita un horario futuro válido, entonces el sistema registra la programación. | | |
| | **Escenario 2:** Dado que existe conflicto con otra reserva, cuando se intenta completar la operación correspondiente, entonces el sistema rechaza el horario. | | |

### EP08 — Landing page y soporte

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-27 | Visitante | Alta | EP08 |
| **Title** | Landing page informativa | | |
| **Description** | Como visitante, quiero conocer la propuesta de valor de WeRide desde la página de inicio para comprender qué servicio ofrece. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que un visitante abre la página de inicio, cuando termina de cargar, entonces visualiza el nombre de WeRide, un mensaje introductorio y una acción principal. | | |
| | **Escenario 2:** Dado que el contenido principal no está disponible, cuando se abre la página, entonces se presenta un mensaje comprensible sin mostrar contenido incompleto. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-28 | Usuario | Media | EP08 |
| **Title** | Contactar con soporte | | |
| **Description** | Como usuario, quiero acceder a un canal de soporte desde la landing page o la aplicación para resolver mis dudas. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que un usuario necesita asistencia, cuando selecciona la opción de contacto, entonces encuentra un canal de soporte identificable. | | |
| | **Escenario 2:** Dado que el canal de contacto no está disponible, cuando intenta utilizarlo, entonces recibe una indicación alternativa o un mensaje informativo. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-43 | Visitante | Alta | EP08 |
| **Title** | Navegación entre secciones | | |
| **Description** | Como visitante, quiero desplazarme a las secciones de la landing page desde el menú para encontrar rápidamente la información que busco. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que el visitante está en la landing page, cuando selecciona una sección del menú, entonces la página lo dirige a la sección correspondiente. | | |
| | **Escenario 2:** Dado que el visitante navega por distintas secciones, cuando utiliza el menú, entonces los enlaces conservan su destino correcto. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-44 | Visitante | Alta | EP08 |
| **Title** | Visualización del catálogo de vehículos | | |
| **Description** | Como visitante, quiero conocer los tipos de vehículos eléctricos ofrecidos para identificar alternativas adecuadas a mis necesidades. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que existen categorías de vehículos publicadas, cuando el visitante abre la sección Vehicles, entonces visualiza sus imágenes y nombres. | | |
| | **Escenario 2:** Dado que no se puede cargar una imagen del catálogo, cuando se muestra su tarjeta, entonces el nombre del vehículo continúa siendo legible. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-45 | Visitante | Alta | EP08 |
| **Title** | Comparación de vehículos eléctricos | | |
| **Description** | Como visitante, quiero consultar las especificaciones de cada tipo de vehículo para comparar sus características antes de elegir. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que el visitante abre Compare Vehicles, cuando selecciona una categoría, entonces visualiza la velocidad máxima, autonomía, peso y tiempo de carga correspondientes. | | |
| | **Escenario 2:** Dado que el visitante cambia de categoría, cuando selecciona otro vehículo, entonces las especificaciones mostradas se actualizan de forma coherente. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-46 | Visitante | Alta | EP08 |
| **Title** | Visualización de ubicaciones del servicio | | |
| **Description** | Como visitante, quiero consultar las zonas y puntos de referencia donde opera WeRide para evaluar si el servicio me resulta accesible. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que existen ubicaciones publicadas, cuando el visitante abre Locations, entonces visualiza el nombre y la dirección de cada punto. | | |
| | **Escenario 2:** Dado que una ubicación no tiene imagen disponible, cuando se muestra su información, entonces su nombre y dirección permanecen visibles. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-47 | Visitante | Alta | EP08 |
| **Title** | Información sobre el funcionamiento del servicio | | |
| **Description** | Como visitante, quiero conocer los pasos para registrarme, utilizar y devolver un vehículo para comprender el proceso de uso de WeRide. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que el visitante abre How it works, cuando revisa la sección, entonces encuentra los pasos del servicio en un orden comprensible. | | |
| | **Escenario 2:** Dado que el visitante consulta un paso, cuando lee su descripción, entonces identifica la acción que debe realizar. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-48 | Visitante | Alta | EP08 |
| **Title** | Visualización de planes y tarifas | | |
| **Description** | Como visitante, quiero comparar los planes, precios y beneficios disponibles para evaluar cuál se adapta a mis necesidades. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que existen planes publicados, cuando el visitante abre Choose Your Plan, entonces visualiza el nombre, precio y beneficios de cada plan. | | |
| | **Escenario 2:** Dado que el visitante revisa un plan, cuando consulta sus condiciones, entonces puede distinguir duración, tarifa por minuto y beneficios indicados. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-49 | Visitante | Alta | EP08 |
| **Title** | Acceso a la aplicación desde la landing page | | |
| **Description** | Como visitante, quiero abrir la aplicación mediante Go to App para comenzar a utilizar el servicio. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que el visitante está en la landing page, cuando selecciona Go to App, entonces se abre la ruta configurada de la aplicación. | | |
| | **Escenario 2:** Dado que el botón aparece en el encabezado o la portada, cuando el visitante lo utiliza, entonces ambos accesos conducen al mismo destino válido. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-50 | Visitante | Media | EP08 |
| **Title** | Información sobre beneficios del servicio | | |
| **Description** | Como visitante, quiero conocer las ventajas de la movilidad eléctrica que propone WeRide para evaluar su utilidad. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que el visitante consulta los beneficios del servicio, cuando abre la sección informativa correspondiente, entonces encuentra ventajas explicadas en lenguaje claro. | | |
| | **Escenario 2:** Dado que se presentan afirmaciones sobre beneficios, cuando el visitante las lee, entonces se distinguen de las cifras de desempeño verificadas. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-51 | Visitante | Media | EP08 |
| **Title** | Visualización de indicadores de impacto | | |
| **Description** | Como visitante, quiero consultar indicadores de alcance de WeRide para conocer la dimensión del servicio. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que existen indicadores respaldados por datos, cuando el visitante abre Our Impact, entonces visualiza sus cifras y unidades o etiquetas correspondientes. | | |
| | **Escenario 2:** Dado que los indicadores son demostrativos, cuando se presentan en la página, entonces se identifican claramente como datos de ejemplo. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-52 | Visitante | Media | EP08 |
| **Title** | Visualización de testimonios | | |
| **Description** | Como visitante, quiero leer experiencias de usuarios para conocer opiniones sobre el servicio antes de utilizarlo. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que existen testimonios autorizados, cuando el visitante abre Testimonials, entonces visualiza el contenido y la atribución permitida de cada testimonio. | | |
| | **Escenario 2:** Dado que se utilizan testimonios ficticios para una demostración, cuando se muestran, entonces se identifican como ejemplos. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-53 | Visitante | Media | EP08 |
| **Title** | Acceso a información de contacto | | |
| **Description** | Como visitante, quiero encontrar los datos de contacto de WeRide para realizar consultas generales sobre el servicio. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que el visitante selecciona Contact Us, cuando accede a esa sección, entonces encuentra los medios de contacto publicados. | | |
| | **Escenario 2:** Dado que existe un enlace de contacto, cuando el visitante lo selecciona, entonces se abre el destino configurado correctamente. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-54 | Visitante | Alta | EP08 |
| **Title** | Acceso a descarga de la aplicación | | |
| **Description** | Como visitante, quiero encontrar opciones para descargar WeRide para instalar la aplicación en un dispositivo compatible. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que existe una versión descargable publicada, cuando el visitante selecciona Download App, entonces accede al enlace de descarga correspondiente. | | |
| | **Escenario 2:** Dado que todavía no existe una descarga pública, cuando el visitante abre esa sección, entonces encuentra un aviso de disponibilidad sin enlaces engañosos. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-55 | Visitante corporativo | Alta | EP08 |
| **Title** | Visualización del plan corporativo B2B | | |
| **Description** | Como representante de una empresa, quiero consultar las condiciones del Business Plan para evaluar su utilidad para mis colaboradores. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que el visitante consulta Choose Your Plan, cuando revisa Business Plan, entonces visualiza su precio, condiciones y beneficios corporativos publicados. | | |
| | **Escenario 2:** Dado que el visitante necesita más información empresarial, cuando selecciona un canal de consulta disponible, entonces puede acceder a los datos de contacto correspondientes. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-56 | Visitante | Alta | EP08 |
| **Title** | Adaptación de la landing page a dispositivos móviles | | |
| **Description** | Como visitante, quiero navegar por la landing page desde mi celular para consultar sus secciones sin dificultades. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que el visitante utiliza una pantalla móvil, cuando abre la landing page, entonces el contenido se adapta al ancho disponible sin desplazamiento horizontal innecesario. | | |
| | **Escenario 2:** Dado que el visitante utiliza una pantalla móvil, cuando interactúa con el menú, las tarjetas y los botones, entonces puede leerlos y seleccionarlos correctamente. | | |

### EP09 — Administración de la plataforma

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-29 | Administrador de flota | Alta | EP09 |
| **Title** | Administrar flota de vehículos | | |
| **Description** | Como administrador de flota, quiero registrar, editar y dar de baja vehículos para mantener actualizado el catálogo disponible. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que un administrador está autorizado, cuando registra o modifica datos válidos de un vehículo, entonces el catálogo refleja la actualización. | | |
| | **Escenario 2:** Dado que intenta registrar datos inconsistentes, cuando se intenta completar la operación correspondiente, entonces el sistema rechaza el cambio. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-30 | Administrador de flota | Media | EP09 |
| **Title** | Monitorear estado de vehículos | | |
| **Description** | Como administrador de flota, quiero ver batería, ubicación y estado de cada vehículo para planificar recargas y mantenimiento. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que hay vehículos vinculados a la flota, cuando el administrador consulta su estado, entonces el sistema devuelve ubicación, batería y disponibilidad registradas. | | |
| | **Escenario 2:** Dado que un vehículo deja de reportar datos, cuando se intenta completar la operación correspondiente, entonces el sistema distingue el último estado conocido de uno actualizado. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-31 | Agente de soporte | Media | EP09 |
| **Title** | Gestionar reportes de problemas | | |
| **Description** | Como agente de soporte, quiero ver y atender los reportes de problemas de vehículos para resolver incidencias y retirar unidades dañadas. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que existen incidencias registradas, cuando el agente de soporte actualiza su atención, entonces el sistema registra el nuevo estado y responsable. | | |
| | **Escenario 2:** Dado que el reporte no existe, cuando se intenta completar la operación correspondiente, entonces el sistema rechaza la actualización. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-38 | Administrador | Alta | EP09 |
| **Title** | Administrar planes de suscripción | | |
| **Description** | Como administrador, quiero crear, actualizar y eliminar planes de suscripción para mantener actualizada la oferta de WeRide. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que un administrador autorizado gestiona planes, cuando registra o actualiza condiciones válidas, entonces el sistema refleja el plan vigente. | | |
| | **Escenario 2:** Dado que los datos del plan son inválidos, cuando se intenta completar la operación correspondiente, entonces el sistema rechaza su publicación. | | |

### EP10 — Calidad, pruebas y automatización

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-25 | Desarrollador | Alta | EP10 |
| **Title** | Archivo db.json para pruebas locales | | |
| **Description** | Como desarrollador, quiero un archivo db.json con usuarios, vehículos y reservas para probar el frontend sin depender del backend. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que el frontend requiere datos de prueba, cuando el desarrollador inicia el entorno local con db.json, entonces se dispone de datos coherentes de usuarios, vehículos y reservas. | | |
| | **Escenario 2:** Dado que se solicita un identificador inexistente, cuando se intenta completar la operación correspondiente, entonces el entorno de prueba devuelve una respuesta de recurso no encontrado. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-26 | Developer | Baja | EP10 |
| **Title** | Pruebas de integración del flujo completo | | |
| **Description** | Como equipo de desarrollo, queremos verificar el flujo registro, login, reserva y viaje para detectar fallos de integración antes del despliegue. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que están disponibles los componentes de registro, acceso y reserva, cuando el desarrollador ejecuta el flujo de integración, entonces se verifica el intercambio de datos entre componentes. | | |
| | **Escenario 2:** Dado que una integración falla, cuando se intenta completar la operación correspondiente, entonces la prueba identifica el punto de fallo. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-32 | Desarrollador frontend | Baja | EP10 |
| **Title** | Documentación Swagger de la API | | |
| **Description** | Como desarrollador frontend, quiero documentación OpenAPI/Swagger de la API para integrar los endpoints sin ambigüedades. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que la API tiene operaciones definidas, cuando el desarrollador consulta la especificación OpenAPI, entonces encuentra rutas, parámetros y respuestas documentadas. | | |
| | **Escenario 2:** Dado que se define una respuesta de error, cuando se intenta completar la operación correspondiente, entonces la especificación describe su código y estructura. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-33 | Developer | Baja | EP10 |
| **Title** | Pruebas unitarias de servicios | | |
| **Description** | Como equipo de desarrollo, queremos pruebas unitarias de los servicios de aplicación para detectar errores en las reglas de negocio de forma temprana. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que existen reglas de negocio implementadas, cuando el desarrollador ejecuta pruebas unitarias, entonces se comprueban resultados esperados en casos válidos. | | |
| | **Escenario 2:** Dado que se prueba una entrada inválida, cuando se intenta completar la operación correspondiente, entonces la prueba verifica el manejo previsto del error. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-34 | Developer | Baja | EP10 |
| **Title** | Pruebas BDD de la API con Karate | | |
| **Description** | Como equipo de QA, queremos escenarios BDD con Karate sobre la API para validar los criterios de aceptación de las historias de forma automática. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que existen escenarios BDD para la API, cuando el equipo ejecuta las pruebas Karate, entonces se validan solicitudes y respuestas contra criterios definidos. | | |
| | **Escenario 2:** Dado que una respuesta no coincide con el escenario, cuando se intenta completar la operación correspondiente, entonces la ejecución reporta el escenario fallido. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-35 | Developer | Baja | EP10 |
| **Title** | Pipeline de integración continua con Jenkins | | |
| **Description** | Como equipo DevOps, queremos un pipeline de integración continua en Jenkins para compilar y probar el backend en cada cambio. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que se integra un cambio al repositorio, cuando el pipeline Jenkins ejecuta la compilación y las pruebas, entonces el pipeline informa el resultado de la verificación. | | |
| | **Escenario 2:** Dado que una prueba falla, cuando se intenta completar la operación correspondiente, entonces el pipeline registra el fallo y no marca la ejecución como satisfactoria. | | |

### EP11 — Gestión corporativa B2B

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-39 | Administrador corporativo | Media | EP11 |
| **Title** | Registrar colaboradores corporativos | | |
| **Description** | Como administrador corporativo, quiero registrar y administrar colaboradores autorizados para que puedan acceder al servicio WeRide de mi empresa. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que una empresa tiene un plan corporativo habilitado, cuando el administrador corporativo registra un colaborador autorizado, entonces el sistema lo vincula a la organización. | | |
| | **Escenario 2:** Dado que el colaborador ya está vinculado, cuando se intenta completar la operación correspondiente, entonces el sistema evita duplicar el registro. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-40 | Administrador corporativo | Media | EP11 |
| **Title** | Consultar dashboard corporativo | | |
| **Description** | Como administrador corporativo, quiero visualizar el uso de vehículos y viajes de mis colaboradores para supervisar la movilidad empresarial. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que una empresa tiene viajes registrados, cuando el administrador corporativo consulta indicadores, entonces el sistema presenta métricas correspondientes a su organización. | | |
| | **Escenario 2:** Dado que no hay actividad en el periodo, cuando se intenta completar la operación correspondiente, entonces el sistema presenta indicadores sin actividad. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-41 | Administrador corporativo | Media | EP11 |
| **Title** | Gestionar suscripción corporativa | | |
| **Description** | Como administrador corporativo, quiero consultar y gestionar el plan de suscripción de mi empresa para controlar los servicios contratados. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que una empresa cuenta con una suscripción, cuando el administrador corporativo consulta sus condiciones, entonces el sistema informa estado y vigencia del plan. | | |
| | **Escenario 2:** Dado que el plan está vencido, cuando se intenta completar la operación correspondiente, entonces el sistema identifica la suscripción como no vigente. | | |

| Story ID | User | Priority | Epic |
|---|---|---|---|
| US-42 | Administrador corporativo | Media | EP11 |
| **Title** | Generar reportes de movilidad corporativa | | |
| **Description** | Como administrador corporativo, quiero consultar y exportar reportes de viajes, tiempo y costos para evaluar el servicio ante la gerencia. | | |
| **Acceptance Criteria** | **Escenario 1:** Dado que una empresa tiene registros de movilidad, cuando el administrador corporativo solicita un reporte de un periodo, entonces el sistema genera los datos de viajes, tiempo y costos de su organización. | | |
| | **Escenario 2:** Dado que el periodo no tiene registros, cuando se intenta completar la operación correspondiente, entonces el sistema entrega un reporte sin movimientos. | | |


### Spike Stories — Investigación técnica

#### SP-01

| Story ID | User | Priority | Epic |
|---|---|---|---|
| SP-01                   | Developer                                                                                                                                                                                        | Media    | EP07 |
| **Title**               | Investigar viabilidad del desbloqueo de vehículos mediante QR                                                                                                                                    |          |      |
| **Description**         | Como desarrollador, quiero investigar mecanismos de validación de códigos QR y comunicación con vehículos para determinar una alternativa viable y segura de desbloqueo en WeRide.               |          |      |
| **Acceptance Criteria** | **Escenario 1:** Dado que se investigan las alternativas de desbloqueo, cuando se comparan requisitos técnicos, seguridad y compatibilidad, entonces se documenta una recomendación justificada. |          |      |
|                         | **Escenario 2:** Dado que se selecciona una alternativa, cuando se realiza una prueba de concepto, entonces se documentan resultados, limitaciones y conclusiones de viabilidad.                 |          |      |

#### SP-02

| Story ID | User | Priority | Epic |
|---|---|---|---|
| SP-02                   | Developer                                                                                                                                                                                                                    | Media    | EP03 |
| **Title**               | Investigar integración de pagos de prueba con Yape y Plin                                                                                                                                                                    |          |      |
| **Description**         | Como desarrollador, quiero investigar las opciones disponibles para simular pagos asociados a Yape y Plin para definir un flujo de prueba viable sin efectuar cobros reales.                                                 |          |      |
| **Acceptance Criteria** | **Escenario 1:** Dado que se analizan las opciones de integración, cuando se evalúan documentación, restricciones y disponibilidad de entornos de prueba, entonces se presenta una matriz comparativa con una recomendación. |          |      |
|                         | **Escenario 2:** Dado que se define una alternativa de simulación, cuando se prueba un pago aprobado y uno rechazado, entonces se documentan los resultados y las limitaciones de la prueba de concepto.                     |          |      |

## 3.3. Product Backlog

El Product Backlog de WeRide reúne las 56 User Stories definidas en la sección 3.2. Su orden se establece según el valor que aportan a la propuesta de movilidad B2C y B2B. Se prioriza inicialmente la landing page como canal de presentación, captación y consulta del servicio; luego, el acceso a la aplicación y el flujo principal de disponibilidad, reserva, desbloqueo, viaje y pago. Después se consideran las funcionalidades corporativas, el soporte y las mejoras complementarias.

| # Orden | User Story Id | Título | Descripción | Story Points |
|---:|---|---|---|---:|
| 1 | US-27 | Landing page informativa | Como visitante, quiero conocer la propuesta de valor de WeRide desde la página de inicio para comprender qué servicio ofrece. | 3 |
| 2 | US-43 | Navegación entre secciones | Como visitante, quiero desplazarme a las secciones de la landing page desde el menú para encontrar rápidamente la información que busco. | 2 |
| 3 | US-56 | Adaptación de la landing page a dispositivos móviles | Como visitante, quiero navegar por la landing page desde mi celular para consultar sus secciones sin dificultades. | 5 |
| 4 | US-44 | Visualización del catálogo de vehículos | Como visitante, quiero conocer los tipos de vehículos eléctricos ofrecidos para identificar alternativas adecuadas a mis necesidades. | 3 |
| 5 | US-45 | Comparación de vehículos eléctricos | Como visitante, quiero consultar las especificaciones de cada tipo de vehículo para comparar sus características antes de elegir. | 5 |
| 6 | US-46 | Visualización de ubicaciones del servicio | Como visitante, quiero consultar las zonas y puntos de referencia donde opera WeRide para evaluar si el servicio me resulta accesible. | 3 |
| 7 | US-47 | Información sobre el funcionamiento del servicio | Como visitante, quiero conocer los pasos para registrarme, utilizar y devolver un vehículo para comprender el proceso de uso de WeRide. | 3 |
| 8 | US-48 | Visualización de planes y tarifas | Como visitante, quiero comparar los planes, precios y beneficios disponibles para evaluar cuál se adapta a mis necesidades. | 3 |
| 9 | US-55 | Visualización del plan corporativo B2B | Como representante de una empresa, quiero consultar las condiciones del Business Plan para evaluar su utilidad para mis colaboradores. | 3 |
| 10 | US-49 | Acceso a la aplicación desde la landing page | Como visitante, quiero abrir la aplicación mediante Go to App para comenzar a utilizar el servicio. | 2 |
| 11 | US-54 | Acceso a descarga de la aplicación | Como visitante, quiero encontrar opciones para descargar WeRide para instalar la aplicación en un dispositivo compatible. | 2 |
| 12 | US-53 | Acceso a información de contacto | Como visitante, quiero encontrar los datos de contacto de WeRide para realizar consultas generales sobre el servicio. | 2 |
| 13 | US-50 | Información sobre beneficios del servicio | Como visitante, quiero conocer las ventajas de la movilidad eléctrica que propone WeRide para evaluar su utilidad. | 2 |
| 14 | US-51 | Visualización de indicadores de impacto | Como visitante, quiero consultar indicadores de alcance de WeRide para conocer la dimensión del servicio. | 2 |
| 15 | US-52 | Visualización de testimonios | Como visitante, quiero leer experiencias de usuarios para conocer opiniones sobre el servicio antes de utilizarlo. | 2 |
| 16 | US-28 | Contactar con soporte | Como usuario, quiero acceder a un canal de soporte desde la landing page o la aplicación para resolver mis dudas. | 2 |
| 17 | US-25 | Archivo db.json para pruebas locales | Como desarrollador, quiero un archivo db.json con usuarios, vehículos y reservas para probar el frontend sin depender del backend. | 2 |
| 18 | US-01 | Inicio de sesión y registro | Como usuario quiero poder iniciar sesión o registrarme en la app para usarla diariamente. | 5 |
| 19 | US-02 | Introducir Número de Celular | Como usuario, quiero introducir mi número de celular para validar mi identidad y recibir notificaciones importantes. | 2 |
| 20 | US-03 | Introducir código de verificación | Como usuario, quiero introducir un código de verificación para validar mi identidad en la aplicación. | 2 |
| 21 | US-04 | Datos de usuario | Como usuario nuevo, quiero crear mi perfil con mis datos para que la app personalice mi experiencia. | 3 |
| 22 | US-05 | Página Principal | Como usuario, quiero ver una pantalla principal clara con accesos rápidos para llegar rápido a reservar un vehículo. | 3 |
| 23 | US-29 | Administrar flota de vehículos | Como administrador de flota, quiero registrar, editar y dar de baja vehículos para mantener actualizado el catálogo disponible. | 5 |
| 24 | US-07 | Gestión y visualización de vehículos en Garaje | Como usuario, quiero ver los vehículos del Garaje para elegir el que mejor se ajuste a mi viaje. | 5 |
| 25 | US-11 | Seleccionar ubicación para ver vehículos cercanos disponibles | Como usuario, quiero ver los vehículos cercanos a la ubicación que elijo en el mapa para reservar el más cercano. | 5 |
| 26 | US-08 | Filtrado de vehículos en Garaje | Como usuario, quiero filtrar los vehículos por tipo, precio, disponibilidad o marca para encontrar rápidamente el adecuado. | 3 |
| 27 | US-17 | Crear una reserva | Como usuario, quiero reservar un vehículo desde la app para asegurar su disponibilidad. | 5 |
| 28 | US-19 | Desbloqueo de vehículo con QR | Como usuario con reserva activa, quiero desbloquear el vehículo escaneando un QR para iniciar mi viaje sin pasos adicionales. | 3 |
| 29 | US-21 | Ver estado de desbloqueo | Como usuario, quiero ver el estado del desbloqueo en tiempo real para saber cuándo puedo empezar a conducir. | 2 |
| 30 | US-20 | Desbloqueo de vehículo desde la app | Como usuario con reserva activa, quiero desbloquear el vehículo desde la app para iniciar mi viaje cuando no puedo escanear el QR. | 3 |
| 31 | US-12 | Visualización de viaje en mapa | Como usuario en viaje, quiero ver mi trayecto y los datos del vehículo para controlar la batería y el tiempo restante. | 5 |
| 32 | US-23 | Finalizar viaje | Como usuario en viaje, quiero finalizar mi viaje desde la app para dejar el vehículo bloqueado y cerrar el cobro. | 3 |
| 33 | US-24 | Pago en línea (sandbox) | Como usuario, quiero pagar mi viaje o plan con Yape/Plin (modo sandbox) para completar el cobro sin usar efectivo. | 8 |
| 34 | US-09 | Selección y pago de planes | Como usuario, quiero comparar los planes disponibles para elegir el que más me conviene. | 5 |
| 35 | US-10 | Proceso de pago de planes | Como usuario quiero ingresar los datos de mi tarjeta para activar el plan seleccionado. | 5 |
| 36 | US-38 | Administrar planes de suscripción | Como administrador, quiero crear, actualizar y eliminar planes de suscripción para mantener actualizada la oferta de WeRide. | 5 |
| 37 | US-37 | Cancelar reserva | Como usuario con una reserva activa, quiero cancelarla para liberar el vehículo si cambio de planes. | 3 |
| 38 | US-18 | Notificación de inicio y vencimiento | Como usuario con reserva, quiero recibir notificaciones cuando mi reserva esté activa y por expirar para no perderla. | 3 |
| 39 | US-16 | Notificación de fin de reserva | Como usuario, quiero recibir una notificación antes de que finalice mi reserva. | 3 |
| 40 | US-39 | Registrar colaboradores corporativos | Como administrador corporativo, quiero registrar y administrar colaboradores autorizados para que puedan acceder al servicio WeRide de mi empresa. | 5 |
| 41 | US-41 | Gestionar suscripción corporativa | Como administrador corporativo, quiero consultar y gestionar el plan de suscripción de mi empresa para controlar los servicios contratados. | 5 |
| 42 | US-40 | Consultar dashboard corporativo | Como administrador corporativo, quiero visualizar el uso de vehículos y viajes de mis colaboradores para supervisar la movilidad empresarial. | 5 |
| 43 | US-42 | Generar reportes de movilidad corporativa | Como administrador corporativo, quiero consultar y exportar reportes de viajes, tiempo y costos para evaluar el servicio ante la gerencia. | 5 |
| 44 | US-30 | Monitorear estado de vehículos | Como administrador de flota, quiero ver batería, ubicación y estado de cada vehículo para planificar recargas y mantenimiento. | 3 |
| 45 | US-15 | Reportar problema con vehículo | Como usuario, quiero reportar un problema con el vehículo para alertar a soporte y obtener ayuda rápida. | 3 |
| 46 | US-31 | Gestionar reportes de problemas | Como agente de soporte, quiero ver y atender los reportes de problemas de vehículos para resolver incidencias y retirar unidades dañadas. | 3 |
| 47 | US-13 | Historial de viajes | Como usuario, quiero ver el historial de mis viajes para trackear gastos y rutas. | 3 |
| 48 | US-36 | Recuperar contraseña | Como usuario registrado, quiero recuperar mi contraseña para volver a entrar si la olvido. | 3 |
| 49 | US-06 | Gestión y personalización de perfil | Como usuario, quiero administrar mi cuenta y mi perfil para mantener mis datos actualizados. | 5 |
| 50 | US-14 | Calificación de viaje | Como usuario, quiero calificar mi experiencia después del viaje para feedback y mejora del servicio. | 2 |
| 51 | US-22 | Desbloqueo programado | Como usuario, quiero programar el desbloqueo de un vehículo para una hora específica y asegurar su disponibilidad. | 5 |
| 52 | US-32 | Documentación Swagger de la API | Como desarrollador frontend, quiero documentación OpenAPI/Swagger de la API para integrar los endpoints sin ambigüedades. | 2 |
| 53 | US-33 | Pruebas unitarias de servicios | Como equipo de desarrollo, queremos pruebas unitarias de los servicios de aplicación para detectar errores en las reglas de negocio de forma temprana. | 3 |
| 54 | US-26 | Pruebas de integración del flujo completo | Como equipo de desarrollo, queremos verificar el flujo registro, login, reserva y viaje para detectar fallos de integración antes del despliegue. | 2 |
| 55 | US-34 | Pruebas BDD de la API con Karate | Como equipo de QA, queremos escenarios BDD con Karate sobre la API para validar los criterios de aceptación de las historias de forma automática. | 5 |
| 56 | US-35 | Pipeline de integración continua con Jenkins | Como equipo DevOps, queremos un pipeline de integración continua en Jenkins para compilar y probar el backend en cada cambio. | 5 |


## 3.4. Impact Mapping.

Un mapa de impacto es una técnica colaborativa y visual de planificación estratégica que alinea los objetivos de un proyecto con las acciones necesarias para alcanzarlos. En esta sección , el equipo presenta los mapas de impacto realizados.


![User Persona](assets/chapter03/Impact%20map%203.png)

![User Persona](assets/chapter03/Impact%20map%202%20(1).png)
