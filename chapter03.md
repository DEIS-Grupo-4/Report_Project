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

### Lista de Épicas

<table>
  <thead>
    <tr>
      <th>ID</th>
      <th>Título</th>
      <th>Descripción</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>EP01</td>
      <td>Acceso a la aplicación</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario de la aplicación, quiero acceder con mi información para hacer uso de las características disponibles.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>EP02</td>
      <td>Funcionalidades de la app</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario de la aplicación, quiero que las funcionalidades principales que me ofrece el servicio sean funcionales.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>EP03</td>
      <td>Gestión de pagos y suscripciones</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario, quiero gestionar mis métodos de pago y suscripciones para acceder a los servicios y planes de la aplicación.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>EP04</td>
      <td>Uso del mapa</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario de la aplicación, quiero acceder al mapa de la aplicación para realizar la reserva de vehículos y seguimiento de rutas.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>EP05</td>
      <td>Gestión de viajes</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario, quiero visualizar y gestionar mis trayectos en el mapa, incluyendo detalles del vehículo, ruta y estado del viaje.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>EP06</td>
      <td>Gestión de reservas</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario, quiero reservar vehículos y recibir notificaciones sobre el estado y fin de mi reserva para asegurar disponibilidad.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>EP07</td>
      <td>Desbloqueo y acceso rápido a vehículos</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario, quiero desbloquear y acceder a los vehículos de forma ágil mediante tecnologías como QR para mejorar la experiencia de inicio de viaje.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>EP08</td>
      <td>Landing page y soporte</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como visitante o usuario, quiero conocer WeRide y contactar a soporte para decidir usar el servicio y resolver mis dudas.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>EP09</td>
      <td>Administración de la plataforma</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como administrador o agente de soporte, quiero gestionar flota, planes y reportes para mantener el servicio disponible.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>EP10</td>
      <td>Calidad, pruebas y automatización</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como equipo de desarrollo, queremos pruebas automáticas e integración continua para entregar software confiable.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>EP11</td>
      <td>Gestión corporativa B2B</td>
      <td><ul style="margin:0; padding-left:18px;"><li>Como responsable de una empresa, quiero administrar colaboradores, planes corporativos y reportes de movilidad para controlar el uso y evaluar los beneficios del servicio.</li></ul></td>
    </tr>
  </tbody>
</table>



### Lista de Historias de Usuario


## 3.3. Product Backlog
El Product Backlog de WeRide está ordenado según valor para el usuario, dependencias funcionales y contribución a la propuesta de valor B2C y B2B. Los Story Points son estimaciones iniciales con escala Fibonacci y deben validarse mediante estimación conjunta del equipo. La prioridad representa el orden de implementación propuesto, no el estado de desarrollo.

| N° Orden | User Story ID | Título | Descripción | Story points | Nivel |
|----------|---------------|--------|-------------|--------------|-------|
| 1 | US-27 | Landing page informativa | Como visitante, quiero ver una landing page clara con beneficios, planes y pasos de uso para decidir si me registro en WeRide. | 3 | Alta |
| 2 | US-25 | Archivo db.json para pruebas locales | Como desarrollador, quiero un archivo db.json con usuarios, vehículos y reservas para probar el frontend sin depender del backend. | 2 | Alta |
| 3 | US-01 | Inicio de sesión y registro | Como usuario quiero poder iniciar sesión o registrarme en la app para usarla diariamente. | 5 | Alta |
| 4 | US-04 | Datos de usuario | Como usuario nuevo, quiero crear mi perfil con mis datos para que la app personalice mi experiencia. | 3 | Alta |
| 5 | US-05 | Página Principal | Como usuario, quiero ver una pantalla principal clara con accesos rápidos para llegar rápido a reservar un vehículo. | 3 | Alta |
| 6 | US-29 | Administrar flota de vehículos | Como administrador de flota, quiero registrar, editar y dar de baja vehículos para mantener actualizado el catálogo disponible. | 5 | Alta |
| 7 | US-07 | Gestión y visualización de vehículos en Garaje | Como usuario, quiero ver los vehículos del Garaje para elegir el que mejor se ajuste a mi viaje. | 5 | Alta |
| 8 | US-11 | Seleccionar ubicación para ver vehículos cercanos disponibles | Como usuario, quiero ver los vehículos cercanos a la ubicación que elijo en el mapa para reservar el más cercano. | 5 | Alta |
| 9 | US-08 | Filtrado de vehículos en Garaje | Como usuario, quiero filtrar los vehículos por tipo, precio, disponibilidad o marca para encontrar rápidamente el adecuado. | 3 | Alta |
| 10 | US-17 | Crear una reserva | Como usuario, quiero reservar un vehículo desde la app para asegurar su disponibilidad. | 5 | Alta |
| 11 | US-19 | Desbloqueo de vehículo con QR | Como usuario con reserva activa, quiero desbloquear el vehículo escaneando un QR para iniciar mi viaje sin pasos adicionales. | 3 | Alta |
| 12 | US-20 | Desbloqueo de vehículo desde la app | Como usuario con reserva activa, quiero desbloquear el vehículo desde la app para iniciar mi viaje cuando no puedo escanear el QR. | 3 | Alta |
| 13 | US-21 | Ver estado de desbloqueo | Como usuario, quiero ver el estado del desbloqueo en tiempo real para saber cuándo puedo empezar a conducir. | 2 | Alta |
| 14 | US-12 | Visualización de viaje en mapa | Como usuario en viaje, quiero ver mi trayecto y los datos del vehículo para controlar la batería y el tiempo restante. | 5 | Alta |
| 15 | US-23 | Finalizar viaje | Como usuario en viaje, quiero finalizar mi viaje desde la app para dejar el vehículo bloqueado y cerrar el cobro. | 3 | Alta |
| 16 | US-24 | Pago en línea (sandbox) | Como usuario, quiero pagar mi viaje o plan con Yape/Plin (modo sandbox) para completar el cobro sin usar efectivo. | 8 | Alta |
| 17 | US-09 | Selección y pago de planes | Como usuario, quiero comparar los planes disponibles para elegir el que más me conviene. | 5 | Alta |
| 18 | US-10 | Proceso de pago de planes | Como usuario quiero ingresar los datos de mi tarjeta para activar el plan seleccionado. | 5 | Alta |
| 19 | US-38 | Administrar planes de suscripción | Como administrador, quiero crear, actualizar y eliminar planes de suscripción para mantener actualizada la oferta de WeRide. | 5 | Alta |
| 20 | US-02 | Introducir Número de Celular | Como usuario, quiero introducir mi número de celular para validar mi identidad y recibir notificaciones importantes. | 2 | Alta |
| 21 | US-03 | Introducir código de verificación | Como usuario, quiero introducir un código de verificación para validar mi identidad en la aplicación. | 2 | Alta |
| 22 | US-37 | Cancelar reserva | Como usuario con una reserva activa, quiero cancelarla para liberar el vehículo si cambio de planes. | 3 | Alta |
| 23 | US-16 | Notificación de fin de reserva | Como usuario, quiero recibir una notificación antes de que finalice mi reserva. | 3 | Alta |
| 24 | US-18 | Notificación de inicio y vencimiento | Como usuario con reserva, quiero recibir notificaciones cuando mi reserva esté activa y por expirar para no perderla. | 3 | Alta |
| 25 | US-30 | Monitorear estado de vehículos | Como administrador de flota, quiero ver batería, ubicación y estado de cada vehículo para planificar recargas y mantenimiento. | 3 | Media |
| 26 | US-15 | Reportar problema con vehículo | Como usuario, quiero reportar un problema con el vehículo para alertar a soporte y obtener ayuda rápida. | 3 | Media |
| 27 | US-31 | Gestionar reportes de problemas | Como agente de soporte, quiero ver y atender los reportes de problemas de vehículos para resolver incidencias y retirar unidades dañadas. | 3 | Media |
| 28 | US-13 | Historial de viajes | Como usuario, quiero ver el historial de mis viajes para trackear gastos y rutas. | 3 | Media |
| 29 | US-36 | Recuperar contraseña | Como usuario registrado, quiero recuperar mi contraseña para volver a entrar si la olvido. | 3 | Media |
| 30 | US-28 | Contactar con soporte | Como usuario, quiero contactar a soporte desde la landing o la app para resolver mis dudas rápidamente. | 2 | Media |
| 31 | US-39 | Registrar colaboradores corporativos | Como administrador corporativo, quiero registrar y administrar colaboradores autorizados para que puedan acceder al servicio WeRide de mi empresa. | 5 | Media |
| 32 | US-41 | Gestionar suscripción corporativa | Como administrador corporativo, quiero consultar y gestionar el plan de suscripción de mi empresa para controlar los servicios contratados. | 5 | Media |
| 33 | US-40 | Consultar dashboard corporativo | Como administrador corporativo, quiero visualizar el uso de vehículos y viajes de mis colaboradores para supervisar la movilidad empresarial. | 5 | Media |
| 34 | US-42 | Generar reportes de movilidad corporativa | Como administrador corporativo, quiero consultar y exportar reportes de viajes, tiempo y costos para evaluar el servicio ante la gerencia. | 5 | Media |
| 35 | US-06 | Gestión y personalización de perfil | Como usuario, quiero administrar mi cuenta y mi perfil para mantener mis datos actualizados. | 5 | Media |
| 36 | US-14 | Calificación de viaje | Como usuario, quiero calificar mi experiencia después del viaje para feedback y mejora del servicio. | 2 | Media |
| 37 | US-22 | Desbloqueo programado | Como usuario, quiero programar el desbloqueo de un vehículo para una hora específica y asegurar su disponibilidad. | 5 | Baja |
| 38 | US-32 | Documentación Swagger de la API | Como desarrollador frontend, quiero documentación OpenAPI/Swagger de la API para integrar los endpoints sin ambigüedades. | 2 | Baja |
| 39 | US-33 | Pruebas unitarias de servicios | Como equipo de desarrollo, queremos pruebas unitarias de los servicios de aplicación para detectar errores en las reglas de negocio de forma temprana. | 3 | Baja |
| 40 | US-34 | Pruebas BDD de la API con Karate | Como equipo de QA, queremos escenarios BDD con Karate sobre la API para validar los criterios de aceptación de las historias de forma automática. | 5 | Baja |
| 41 | US-26 | Pruebas de integración del flujo completo | Como equipo de desarrollo, queremos verificar el flujo registro, login, reserva y viaje para detectar fallos de integración antes del despliegue. | 2 | Baja |
| 42 | US-35 | Pipeline de integración continua con Jenkins | Como equipo DevOps, queremos un pipeline de integración continua en Jenkins para compilar y probar el backend en cada cambio. | 5 | Baja |



## 3.4. Impact Mapping.

Un mapa de impacto es una técnica colaborativa y visual de planificación estratégica que alinea los objetivos de un proyecto con las acciones necesarias para alcanzarlos. En esta sección , el equipo presenta los mapas de impacto realizados.


![User Persona](assets/chapter03/Impact%20map%203.png)

![User Persona](assets/chapter03/Impact%20map%202%20(1).png)
