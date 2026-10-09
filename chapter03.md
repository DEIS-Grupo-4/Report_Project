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

    
  </tbody>
</table>


### Lista de Historias de Usuario

<table>
  <tbody>
    <tr>
      <th>ID (HU)</th>
      <th>Título</th>
      <th>Descripción</th>
      <th>Criterios de aceptación</th>
      <th>Epic-ID</th>
    </tr>
    <!-- US-01 -->
    <tr>
      <td>US-01</td>
      <td>Inicio de sesión y registro</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario quiero poder iniciar sesión o registrarme en la app para usarla diariamente.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Inicio de sesión exitoso<br><b>Given</b> que el usuario tiene una cuenta registrada<br><b>When</b> ingresa sus credenciales correctas<br><b>Then</b> el sistema permite el acceso a la app.</li>
          <li><b>Escenario 2:</b> Registro exitoso<br><b>Given</b> que el usuario no tiene una cuenta<br><b>When</b> completa el formulario de registro con sus datos válidos<br><b>Then</b> el sistema crea la cuenta y permite el acceso.</li>
          <li><b>Escenario 3:</b> Fallo de autenticación<br><b>Given</b> que el usuario ingresa credenciales incorrectas<br><b>When</b> intenta iniciar sesión<br><b>Then</b> el sistema muestra un mensaje de error.</li>
        </ul>
      </td>
      <td>EP-01</td>
    </tr>
    <!-- US-02 -->
    <tr>
      <td>US-02</td>
      <td>Introducir Número de Celular</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario, quiero introducir mi número de celular para validar mi identidad y recibir notificaciones importantes.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Introducción exitosa<br><b>Given</b> que el usuario accede al formulario de perfil<br><b>When</b> ingresa un número de celular válido y lo guarda<br><b>Then</b> el sistema valida el número y lo asocia al perfil del usuario.</li>
          <li><b>Escenario 2:</b> Número inválido<br><b>Given</b> que el usuario intenta guardar su número<br><b>When</b> el número ingresado no cumple con el formato requerido<br><b>Then</b> el sistema muestra un mensaje de error y solicita corregir el dato.</li>
          <li><b>Escenario 3:</b> Error de conexión<br><b>Given</b> que el usuario ingresa su número<br><b>When</b> hay problemas de conexión al guardar el dato<br><b>Then</b> el sistema informa el error y permite reintentar la acción.</li>
        </ul>
      </td>
      <td>EP-01</td>
    </tr>
    <!-- US-03 -->
    <tr>
      <td>US-03</td>
      <td>Introducir código de verificación</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario, quiero introducir un código de verificación para validar mi identidad en la aplicación.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Verificación exitosa<br><b>Given</b> que el usuario ha recibido un código de verificación en su celular<br><b>When</b> ingresa el código correctamente en el formulario de la app<br><b>Then</b> el sistema valida el código y confirma la verificación de identidad.</li>
          <li><b>Escenario 2:</b> Código incorrecto<br><b>Given</b> que el usuario intenta verificar su identidad<br><b>When</b> ingresa un código inválido o expirado<br><b>Then</b> el sistema muestra un mensaje de error y permite reintentar la verificación.</li>
          <li><b>Escenario 3:</b> Error de conexión<br><b>Given</b> que el usuario ingresa el código de verificación<br><b>When</b> ocurre un problema de conexión al validar el código<br><b>Then</b> el sistema informa el error y permite al usuario reintentar la acción cuando se restablezca la conexión.</li>
        </ul>
      </td>
      <td>EP-01</td>
    </tr>
    <!-- US-04 -->
    <tr>
      <td>US-04</td>
      <td>Datos de usuario</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario nuevo, quiero crear mi perfil con mis datos para que la app personalice mi experiencia.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Creación exitosa<br><b>Given</b> que el usuario accede a su cuenta<br><b>When</b> ingresa sus datos (nombre, correo, foto, etc.) y los guarda<br><b>Then</b> el sistema actualiza el perfil con éxito.</li>
          <li><b>Escenario 2:</b> Error en la creación<br><b>Given</b> que el usuario intenta guardar sus datos<br><b>When</b> alguno es inválido o falta completar un campo obligatorio<br><b>Then</b> el sistema muestra un mensaje indicando el error.</li>
        </ul>
      </td>
      <td>EP-01</td>
    </tr>
    <!-- US-05 -->
    <tr>
      <td>US-05</td>
      <td>Página Principal</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario, quiero ver una pantalla principal clara con accesos rápidos para llegar rápido a reservar un vehículo.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Visualización exitosa<br><b>Given</b> que el usuario ha iniciado sesión en la aplicación<br><b>When</b> accede a la pantalla principal<br><b>Then</b> el sistema muestra una interfaz atractiva, con acceso rápido a las funciones principales y elementos visuales bien organizados.</li>
          <li><b>Escenario 2:</b> Elementos no cargados<br><b>Given</b> que el usuario accede a la pantalla principal<br><b>When</b> algunos elementos visuales o funcionalidades no se cargan correctamente por problemas de conexión o error interno<br><b>Then</b> el sistema muestra un mensaje de error y permite reintentar la carga.</li>
          <li><b>Escenario 3:</b> Personalización<br><b>Given</b> que el usuario accede a la pantalla principal<br><b>When</b> personaliza la vista (por ejemplo, elige tema claro/oscuro o reordena accesos rápidos)<br><b>Then</b> el sistema guarda las preferencias y actualiza la interfaz según la selección del usuario.</li>
        </ul>
      </td>
      <td>EP-02</td>
    </tr>
    <!-- US-06 -->
    <tr>
      <td>US-06</td>
      <td>Gestión y personalización de perfil</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario, quiero administrar mi cuenta y mi perfil para mantener mis datos actualizados.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Acceso exitoso al perfil<br><b>Given</b> que el usuario ha iniciado sesión en la aplicación<br><b>When</b> accede a la sección "Tu" desde el menú lateral<br><b>Then</b> el sistema muestra las opciones de administrar cuenta, personalizar perfil, cartera, historial, centro de seguridad, ayuda y ajustes.</li>
          <li><b>Escenario 2:</b> Personalización de perfil<br><b>Given</b> que el usuario accede a la opción de personalizar perfil<br><b>When</b> modifica su información personal (nombre, foto, etc.)<br><b>Then</b> el sistema guarda los cambios y actualiza la información mostrada.</li>
          <li><b>Escenario 3:</b> Acceso a funcionalidades adicionales<br><b>Given</b> que el usuario accede a las opciones de cartera, historial, centro de seguridad, ayuda o ajustes<br><b>When</b> selecciona alguna de estas opciones<br><b>Then</b> el sistema muestra la información o funcionalidad correspondiente (por ejemplo, ver historial de trayectos, administrar métodos de pago, acceder a soporte, modificar ajustes de la cuenta, etc.).</li>
        </ul>
      </td>
      <td>EP-02</td>
    </tr>
    <!-- US-07 -->
    <tr>
      <td>US-07</td>
      <td>Gestión y visualización de vehículos en Garaje</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario, quiero ver los vehículos del Garaje para elegir el que mejor se ajuste a mi viaje.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Visualización exitosa de vehículos<br><b>Given</b> que el usuario accede a la sección Garaje desde el menú lateral<br><b>When</b> se muestran los vehículos disponibles con imagen, nombre, disponibilidad, marca y valoración<br><b>Then</b> el sistema permite ver todos los vehículos y sus detalles.</li>
          <li><b>Escenario 2:</b> Filtrado de vehículos<br><b>Given</b> que el usuario está en la sección Garaje<br><b>When</b> utiliza los filtros para mostrar solo e-scooters, motos o bicicletas<br><b>Then</b> el sistema actualiza la lista mostrando únicamente los vehículos del tipo seleccionado.</li>
          <li><b>Escenario 3:</b> Gestión de favoritos<br><b>Given</b> que el usuario visualiza los vehículos en el Garaje<br><b>When</b> marca un vehículo como favorito usando el ícono de corazón<br><b>Then</b> el sistema guarda la preferencia y permite acceder rápidamente a los vehículos favoritos.</li>
        </ul>
      </td>
      <td>EP-02</td>
    </tr>
    <!-- US-08 -->
    <tr>
      <td>US-08</td>
      <td>Filtrado de vehículos en Garaje</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario, quiero filtrar los vehículos por tipo, precio, disponibilidad o marca para encontrar rápidamente el adecuado.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Filtrado exitoso<br><b>Given</b> que el usuario accede a la sección Garaje<br><b>When</b> utiliza el menú de filtros para seleccionar tipo de vehículo, precio, disponibilidad, calificación o marca<br><b>Then</b> el sistema muestra únicamente los vehículos que cumplen con los criterios seleccionados.</li>
          <li><b>Escenario 2:</b> Sin resultados<br><b>Given</b> que el usuario aplica filtros en el Garaje<br><b>When</b> no existen vehículos que cumplan con los criterios seleccionados<br><b>Then</b> el sistema muestra un mensaje indicando que no hay vehículos disponibles según el filtro.</li>
          <li><b>Escenario 3:</b> Error de conexión<br><b>Given</b> que el usuario intenta filtrar vehículos<br><b>When</b> ocurre un problema de conexión<br><b>Then</b> el sistema muestra un mensaje de error y permite reintentar la acción.</li>
        </ul>
      </td>
      <td>EP-02</td>
    </tr>
    <!-- US-09 -->
    <tr>
      <td>US-09</td>
      <td>Selección y pago de planes</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario, quiero comparar los planes disponibles para elegir el que más me conviene.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Visualización de planes<br><b>Given</b> que el usuario accede a la sección "Planes" desde el menú lateral<br><b>When</b> se muestran los diferentes tipos de planes con sus nombres y detalles<br><b>Then</b> el sistema permite al usuario comparar y seleccionar el plan deseado.</li>
          <li><b>Escenario 2:</b> Pago exitoso de plan<br><b>Given</b> que el usuario ha seleccionado un plan<br><b>When</b> presiona el botón "Pagar" y realiza el proceso de pago<br><b>Then</b> el sistema activa el plan y lo asocia a la cuenta del usuario.</li>
          <li><b>Escenario 3:</b> Error en el pago<br><b>Given</b> que el usuario intenta pagar un plan<br><b>When</b> ocurre un problema con el método de pago o la conexión<br><b>Then</b> el sistema muestra un mensaje de error y permite reintentar la acción.</li>
        </ul>
      </td>
      <td>EP-03</td>
    </tr>
    <!-- US-10 -->
    <tr>
      <td>US-10</td>
      <td>Proceso de pago de planes</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario quiero ingresar los datos de mi tarjeta para activar el plan seleccionado.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Ingreso exitoso de datos de pago<br><b>Given</b> que el usuario ha seleccionado un plan<br><b>When</b> ingresa el número de tarjeta, fecha de vencimiento, CVV y dirección de facturación<br><b>Then</b> el sistema valida los datos y permite avanzar al resumen de pago.</li>
          <li><b>Escenario 2:</b> Confirmación y finalización de pago<br><b>Given</b> que el usuario ha ingresado correctamente todos los datos<br><b>When</b> presiona el botón "Finalizar Pago"<br><b>Then</b> el sistema procesa el pago, muestra el total y activa el plan en la cuenta del usuario.</li>
          <li><b>Escenario 3:</b> Error en el proceso de pago<br><b>Given</b> que el usuario intenta finalizar el pago<br><b>When</b> hay un error en los datos ingresados o problemas de conexión<br><b>Then</b> el sistema muestra un mensaje de error y permite corregir los datos o reintentar la acción.</li>
        </ul>
      </td>
      <td>EP-03</td>
    </tr>
    <!-- US-11 -->
    <tr>
      <td>US-11</td>
      <td>Seleccionar ubicación para ver vehículos cercanos disponibles</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario, quiero ver los vehículos cercanos a la ubicación que elijo en el mapa para reservar el más cercano.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Visualización exitosa<br><b>Given</b> que el usuario accede al mapa de la aplicación<br><b>When</b> selecciona una ubicación específica en el mapa<br><b>Then</b> el sistema muestra en tiempo real los vehículos disponibles cerca de esa ubicación.</li>
          <li><b>Escenario 2:</b> Ubicación sin vehículos<br><b>Given</b> que el usuario selecciona una ubicación en el mapa<br><b>When</b> no hay vehículos disponibles cerca de esa ubicación<br><b>Then</b> el sistema informa que no hay vehículos disponibles y sugiere ubicaciones alternativas.</li>
          <li><b>Escenario 3:</b> Error de conexión<br><b>Given</b> que el usuario selecciona una ubicación en el mapa<br><b>When</b> ocurre un problema de conexión al cargar los vehículos<br><b>Then</b> el sistema muestra un mensaje de error y permite reintentar la acción.</li>
        </ul>
      </td>
      <td>EP-04</td>
    </tr>
    <!-- US-12 -->
    <tr>
      <td>US-12</td>
      <td>Visualización de viaje en mapa</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario en viaje, quiero ver mi trayecto y los datos del vehículo para controlar la batería y el tiempo restante.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Visualización exitosa del viaje<br><b>Given</b> que el usuario accede a la sección "Viaje" desde el menú lateral<br><b>When</b> se muestra el mapa con la ruta actual, puntos de inicio y destino, y detalles del vehículo<br><b>Then</b> el sistema presenta la información de ubicación, batería, tiempo restante y estado del viaje en tiempo real.</li>
          <li><b>Escenario 2:</b> Actualización de información<br><b>Given</b> que el usuario está visualizando el viaje<br><b>When</b> cambia la ruta, el vehículo o el estado del trayecto<br><b>Then</b> el sistema actualiza la información mostrada en el mapa y en el panel de detalles.</li>
          <li><b>Escenario 3:</b> Error de conexión<br><b>Given</b> que el usuario intenta visualizar o actualizar el viaje<br><b>When</b> ocurre un problema de conexión<br><b>Then</b> el sistema muestra un mensaje de error y permite reintentar la acción.</li>
        </ul>
      </td>
      <td>EP-05</td>
    </tr>
    <!-- US-13 -->
    <tr>
      <td>US-13</td>
      <td>Historial de viajes</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario, quiero ver el historial de mis viajes para trackear gastos y rutas.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Visualización exitosa<br>Given que el usuario inicia sesión<br>When accede a la sección "Mis Viajes"<br>Then el sistema muestra una lista con fecha, costo y distancia de cada viaje.</li>
          <li><b>Escenario 2:</b> Error de carga<br>Given que el usuario accede al historial<br>When no hay conexión a internet<br>Then el sistema muestra un mensaje de error y opción para reintentar.</li>
        </ul>
      </td>
      <td>EP-05</td>
    </tr>
    <!-- US-14 -->
    <tr>
      <td>US-14</td>
      <td>Calificación de viaje</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario, quiero calificar mi experiencia después del viaje para feedback y mejora del servicio.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Calificación exitosa<br>Given que el usuario finaliza un viaje<br>When selecciona una puntuación (1-5 estrellas) y envía<br>Then el sistema guarda la calificación y muestra agradecimiento.</li>
          <li><b>Escenario 2:</b> Calificación fallida<br>Given que el usuario intenta calificar<br>When no hay conexión a internet<br>Then el sistema guarda la calificación localmente y la envía después.</li>
        </ul>
      </td>
      <td>EP-05</td>
    </tr>
    <!-- US-15 -->
    <tr>
      <td>US-15</td>
      <td>Reportar problema con vehículo</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario, quiero reportar un problema con el vehículo para alertar a soporte y obtener ayuda rápida.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Reporte exitoso<br>Given que el usuario está usando el vehículo<br>When selecciona "Reportar problema" y elige una categoría (ej.: falla mecánica)<br>Then el sistema envía el reporte a soporte y muestra confirmación.</li>
          <li><b>Escenario 2:</b> Reporte fallido<br>Given que el usuario intenta reportar un problema<br>When no hay conexión a internet<br>Then el sistema guarda el reporte localmente y lo envía al recuperar la conexión.</li>
        </ul>
      </td>
      <td>EP-05</td>
    </tr>
    <!-- US-16 -->
    <tr>
      <td>US-16</td>
      <td>Notificación de fin de reserva</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario, quiero recibir una notificación antes de que finalice mi reserva.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Notificación exitosa<br>Given que el usuario tiene una reserva activa<br>When faltan 5 minutos para el fin de la reserva<br>Then el sistema envía una notificación push con opción para extender el tiempo.</li>
          <li><b>Escenario 2:</b> Notificación fallida<br>Given que la reserva está por finalizar<br>When no hay conexión a internet<br>Then el sistema registra el intento y reintenta enviar la notificación al recuperar la conexión.</li>
        </ul>
      </td>
      <td>EP-06</td>
    </tr>
    <!-- US-17 -->
    <tr>
      <td>US-17</td>
      <td>Crear una reserva</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario, quiero reservar un vehículo desde la app para asegurar su disponibilidad.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Reserva exitosa<br><b>Given</b> que el usuario visualiza los vehículos disponibles<br><b>When</b> selecciona un vehículo y confirma la reserva<br><b>Then</b> el sistema bloquea el vehículo y muestra un temporizador de la reserva.</li>
          <li><b>Escenario 2:</b> Vehículo no disponible<br><b>Given</b> que el usuario intenta reservar un vehículo<br><b>When</b> otro usuario ya lo reservó antes<br><b>Then</b> el sistema muestra un mensaje de error indicando que debe seleccionar otro vehículo.</li>
          <li><b>Escenario 3:</b> Error de conexión<br><b>Given</b> que el usuario confirma una reserva<br><b>When</b> no hay conexión a internet<br><b>Then</b> el sistema informa que no se pudo completar la acción y permite reintentar cuando se restablezca la conexión.</li>
        </ul>
      </td>
      <td>EP-06</td>
    </tr>
    <!-- US-18 -->
    <tr>
      <td>US-18</td>
      <td>Notificación de inicio y vencimiento</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario con reserva, quiero recibir notificaciones cuando mi reserva esté activa y por expirar para no perderla.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Notificación de inicio<br><b>Given</b> que el usuario tiene una reserva activa<br><b>When</b> la reserva comienza<br><b>Then</b> el sistema envía una notificación push confirmando el inicio.</li>
          <li><b>Escenario 2:</b> Notificación de vencimiento<br><b>Given</b> que el usuario tiene una reserva próxima a expirar<br><b>When</b> faltan pocos minutos para que finalice<br><b>Then</b> el sistema envía una notificación recordatoria.</li>
          <li><b>Escenario 3:</b> Expiración de reserva<br><b>Given</b> que el usuario no inicia el viaje<br><b>When</b> la reserva llega a su fin<br><b>Then</b> el sistema libera automáticamente el vehículo y notifica al usuario.</li>
        </ul>
      </td>
      <td>EP-06</td>
    </tr>
    <!-- US-19 -->
    <tr>
      <td>US-19</td>
      <td>Desbloqueo de vehículo con QR</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario con reserva activa, quiero desbloquear el vehículo escaneando un QR para iniciar mi viaje sin pasos adicionales.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Desbloqueo exitoso<br>Given que el usuario reserva un vehículo<br>When escanea el QR del vehículo<br>Then el sistema desbloquea el vehículo y inicia el viaje.</li>
          <li><b>Escenario 2:</b> Desbloqueo fallido<br>Given que el usuario escanea el QR<br>When el QR no es válido o el vehículo ya está en uso<br>Then el sistema muestra un mensaje de error.</li>
        </ul>
      </td>
      <td>EP-07</td>
    </tr>
    <!-- US-20 -->
    <tr>
      <td>US-20</td>
      <td>Desbloqueo de vehículo desde la app</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario con reserva activa, quiero desbloquear el vehículo desde la app para iniciar mi viaje cuando no puedo escanear el QR.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Desbloqueo exitoso<br><b>Given</b> que el usuario tiene una reserva activa<br><b>When</b> presiona el botón "Desbloquear" en la app<br><b>Then</b> el sistema desbloquea el vehículo y muestra la información del viaje.</li>
          <li><b>Escenario 2:</b> Desbloqueo fallido<br><b>Given</b> que el usuario intenta desbloquear desde la app<br><b>When</b> hay problemas de conexión o el vehículo está ocupado<br><b>Then</b> el sistema muestra un mensaje de error y permite reintentar.</li>
        </ul>
      </td>
      <td>EP-07</td>
    </tr>
    <!-- US-21 -->
    <tr>
      <td>US-21</td>
      <td>Ver estado de desbloqueo</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario, quiero ver el estado del desbloqueo en tiempo real para saber cuándo puedo empezar a conducir.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Visualización exitosa<br><b>Given</b> que el usuario ha solicitado el desbloqueo<br><b>When</b> el sistema procesa la solicitud<br><b>Then</b> el sistema muestra el estado actualizado (desbloqueado, en proceso, error) en la app.</li>
          <li><b>Escenario 2:</b> Error de actualización<br><b>Given</b> que el usuario espera la confirmación de desbloqueo<br><b>When</b> hay problemas de conexión<br><b>Then</b> el sistema muestra un mensaje de error y permite reintentar la consulta.</li>
        </ul>
      </td>
      <td>EP-07</td>
    </tr>
    <!-- US-22 -->
    <tr>
      <td>US-22</td>
      <td>Desbloqueo programado</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario, quiero programar el desbloqueo de un vehículo para una hora específica y asegurar su disponibilidad.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Programación exitosa<br><b>Given</b> que el usuario selecciona un vehículo y una hora futura<br><b>When</b> confirma la programación de desbloqueo<br><b>Then</b> el sistema reserva el vehículo y lo desbloquea automáticamente en la hora indicada.</li>
          <li><b>Escenario 2:</b> Programación fallida<br><b>Given</b> que el usuario intenta programar el desbloqueo<br><b>When</b> el vehículo no está disponible en la hora seleccionada<br><b>Then</b> el sistema muestra un mensaje de error y sugiere otras opciones.</li>
        </ul>
      </td>
      <td>EP-07</td>
    </tr>
    <!-- US-23 -->
    <tr>
      <td>US-23</td>
      <td>Finalizar viaje</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario en viaje, quiero finalizar mi viaje desde la app para dejar el vehículo bloqueado y cerrar el cobro.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Finalización exitosa<br><b>Given</b> que el usuario tiene un viaje activo<br><b>When</b> presiona "Finalizar viaje" dentro de una estación virtual<br><b>Then</b> el sistema bloquea el vehículo, registra la hora de fin y muestra el resumen del viaje.</li>
          <li><b>Escenario 2:</b> Finalización fuera de zona<br><b>Given</b> que el usuario tiene un viaje activo<br><b>When</b> intenta finalizar fuera de una estación virtual<br><b>Then</b> el sistema muestra un aviso de posible penalización y le pide dirigirse a una estación.</li>
        </ul>
      </td>
      <td>EP-05</td>
    </tr>
    <!-- US-24 -->
    <tr>
      <td>US-24</td>
      <td>Pago en línea (sandbox)</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario, quiero pagar mi viaje o plan con Yape/Plin (modo sandbox) para completar el cobro sin usar efectivo.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Pago exitoso<br><b>Given</b> que el usuario tiene un pago pendiente<br><b>When</b> confirma el pago con un método válido de prueba<br><b>Then</b> el sistema registra la transacción como pagada y muestra el comprobante.</li>
          <li><b>Escenario 2:</b> Pago rechazado<br><b>Given</b> que el usuario intenta pagar<br><b>When</b> el método de pago es rechazado<br><b>Then</b> el sistema muestra el motivo y permite reintentar con otro método.</li>
          <li><b>Escenario 3:</b> Error de conexión<br><b>Given</b> que el usuario confirma el pago<br><b>When</b> se pierde la conexión durante el proceso<br><b>Then</b> el sistema informa que el pago no se completó y no genera un cobro duplicado.</li>
        </ul>
      </td>
      <td>EP-03</td>
    </tr>
    <!-- US-25-->
    <tr>
      <td>US-25</td>
      <td>Archivo db.json para pruebas locales</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como desarrollador, quiero un archivo db.json con usuarios, vehículos y reservas para probar el frontend sin depender del backend.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Lectura exitosa<br><b>Given</b> que el servidor simulado (json-server) está levantado<br><b>When</b> el frontend consulta /vehicles<br><b>Then</b> recibe la lista de vehículos simulados en formato JSON.</li>
          <li><b>Escenario 2:</b> Recurso inexistente<br><b>Given</b> que el servidor simulado está levantado<br><b>When</b> el frontend consulta un recurso inexistente<br><b>Then</b> el servidor responde 404.</li>
        </ul>
      </td>
      <td>EP-10</td>
    </tr>
    <!-- US-26-->
    <tr>
      <td>US-26</td>
      <td>Pruebas de integración del flujo completo</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como equipo de desarrollo, queremos verificar el flujo registro, login, reserva y viaje para detectar fallos de integración antes del despliegue.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Flujo completo exitoso<br><b>Given</b> que existe un usuario de prueba y un vehículo disponible<br><b>When</b> se ejecuta el flujo completo de registro, login, reserva y viaje<br><b>Then</b> cada paso responde con el código esperado y los datos quedan persistidos.</li>
          <li><b>Escenario 2:</b> Acceso sin token<br><b>Given</b> que el flujo se ejecuta sin token<br><b>When</b> se llama a un endpoint protegido<br><b>Then</b> la API responde 401.</li>
        </ul>
      </td>
      <td>EP-10</td>
    </tr>
    <!-- US-27-->
    <tr>
      <td>US-27</td>
      <td>Landing page informativa</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como visitante, quiero ver una landing page clara con beneficios, planes y pasos de uso para decidir si me registro en WeRide.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Visualización exitosa<br><b>Given</b> que el visitante entra a la landing page<br><b>When</b> la página termina de cargar<br><b>Then</b> ve las secciones de beneficios, pasos de uso y un botón para registrarse.</li>
          <li><b>Escenario 2:</b> Visualización en móvil<br><b>Given</b> que el visitante abre la landing desde un celular<br><b>When</b> la página carga<br><b>Then</b> el diseño se adapta al tamaño de pantalla sin perder contenido.</li>
        </ul>
      </td>
      <td>EP-08</td>
    </tr>
    <!-- US-28-->
    <tr>
      <td>US-28</td>
      <td>Contactar con soporte</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario, quiero contactar a soporte desde la landing o la app para resolver mis dudas rápidamente.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Envío exitoso<br><b>Given</b> que el usuario abre el formulario de contacto<br><b>When</b> envía nombre, correo y mensaje válidos<br><b>Then</b> el sistema confirma el envío del mensaje.</li>
          <li><b>Escenario 2:</b> Campos incompletos<br><b>Given</b> que el usuario abre el formulario de contacto<br><b>When</b> deja campos obligatorios vacíos<br><b>Then</b> el sistema marca los campos faltantes y no envía el mensaje.</li>
        </ul>
      </td>
      <td>EP-08</td>
    </tr>
    <!-- US-29-->
    <tr>
      <td>US-29</td>
      <td>Administrar flota de vehículos</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como administrador de flota, quiero registrar, editar y dar de baja vehículos para mantener actualizado el catálogo disponible.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Registro de vehículo exitoso<br><b>Given</b> que el administrador está autenticado<br><b>When</b> registra un vehículo con datos válidos<br><b>Then</b> el vehículo aparece en el catálogo con estado disponible.</li>
          <li><b>Escenario 2:</b> Placa duplicada<br><b>Given</b> que ya existe un vehículo con la misma placa<br><b>When</b> el administrador intenta registrar otro con esa placa<br><b>Then</b> el sistema rechaza el registro e indica que la placa está duplicada.</li>
          <li><b>Escenario 3:</b> Baja con reserva activa<br><b>Given</b> que un vehículo tiene una reserva activa<br><b>When</b> el administrador intenta darlo de baja<br><b>Then</b> el sistema impide la baja y explica el motivo.</li>
        </ul>
      </td>
      <td>EP-09</td>
    </tr>
    <!-- US-30-->
    <tr>
      <td>US-30</td>
      <td>Monitorear estado de vehículos</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como administrador de flota, quiero ver batería, ubicación y estado de cada vehículo para planificar recargas y mantenimiento.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Visualización del estado<br><b>Given</b> que el administrador abre el panel de flota<br><b>When</b> el panel carga<br><b>Then</b> ve cada vehículo con su batería, ubicación y estado.</li>
          <li><b>Escenario 2:</b> Alerta de batería baja<br><b>Given</b> que un vehículo tiene batería menor al 20%<br><b>When</b> el administrador visualiza el panel<br><b>Then</b> el sistema resalta ese vehículo con una alerta.</li>
        </ul>
      </td>
      <td>EP-09</td>
    </tr>
    <!-- US-31-->
    <tr>
      <td>US-31</td>
      <td>Gestionar reportes de problemas</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como agente de soporte, quiero ver y atender los reportes de problemas de vehículos para resolver incidencias y retirar unidades dañadas.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Listado de reportes<br><b>Given</b> que existen reportes enviados por usuarios<br><b>When</b> el agente abre la lista de reportes<br><b>Then</b> ve los reportes ordenados por fecha y filtrables por estado.</li>
          <li><b>Escenario 2:</b> Reporte resuelto<br><b>Given</b> que el agente atendió un reporte<br><b>When</b> lo marca como resuelto<br><b>Then</b> el sistema actualiza el estado y notifica al usuario que lo reportó.</li>
        </ul>
      </td>
      <td>EP-09</td>
    </tr>
    <!-- US-32-->
    <tr>
      <td>US-32</td>
      <td>Documentación Swagger de la API</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como desarrollador frontend, quiero documentación OpenAPI/Swagger de la API para integrar los endpoints sin ambigüedades.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Consulta de documentación<br><b>Given</b> que el backend está desplegado<br><b>When</b> el desarrollador abre /swagger-ui/index.html<br><b>Then</b> ve los endpoints agrupados con descripción y ejemplos de request y response.</li>
          <li><b>Escenario 2:</b> Prueba de endpoint<br><b>Given</b> que el desarrollador está en Swagger UI<br><b>When</b> ejecuta "Try it out" sobre el inicio de sesión<br><b>Then</b> recibe una respuesta real de la API.</li>
        </ul>
      </td>
      <td>EP-10</td>
    </tr>
    <!-- US-33-->
    <tr>
      <td>US-33</td>
      <td>Pruebas unitarias de servicios</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como equipo de desarrollo, queremos pruebas unitarias de los servicios de aplicación para detectar errores en las reglas de negocio de forma temprana.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Pruebas aprobadas<br><b>Given</b> que existen pruebas unitarias para los bounded contexts IAM y Plans<br><b>When</b> se ejecuta mvn test<br><b>Then</b> todas las pruebas pasan y se genera el reporte.</li>
          <li><b>Escenario 2:</b> Regla rota detectada<br><b>Given</b> que una regla de negocio cambia y rompe un caso<br><b>When</b> se ejecuta mvn test<br><b>Then</b> la prueba correspondiente falla e indica el caso afectado.</li>
        </ul>
      </td>
      <td>EP-10</td>
    </tr>    
    <!-- US-34-->
    <tr>
      <td>US-34</td>
      <td>Pruebas BDD de la API con Karate</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como equipo de QA, queremos escenarios BDD con Karate sobre la API para validar los criterios de aceptación de las historias de forma automática.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Ejecución exitosa<br><b>Given</b> que la API está levantada<br><b>When</b> se ejecuta el TestRunner de Karate<br><b>Then</b> se genera un reporte HTML con los escenarios aprobados y fallidos.</li>
          <li><b>Escenario 2:</b> Escenario negativo<br><b>Given</b> que existe un escenario con credenciales inválidas<br><b>When</b> se ejecuta el TestRunner de Karate<br><b>Then</b> el escenario verifica que la API rechaza el acceso y lo marca como aprobado.</li>
        </ul>
      </td>
      <td>EP-10</td>
    </tr>
    <!-- US-35-->
    <tr>
      <td>US-35</td>
      <td>Pipeline de integración continua con Jenkins</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como equipo DevOps, queremos un pipeline de integración continua en Jenkins para compilar y probar el backend en cada cambio.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Ejecución automática<br><b>Given</b> que se hace push a la rama develop<br><b>When</b> Jenkins recibe el aviso del repositorio<br><b>Then</b> ejecuta checkout, build y pruebas automáticamente.</li>
          <li><b>Escenario 2:</b> Falla de pruebas<br><b>Given</b> que una prueba falla<br><b>When</b> el pipeline se ejecuta<br><b>Then</b> el build se marca como FAILED y no continúa a las siguientes etapas.</li>
        </ul>
      </td>
      <td>EP-10</td>
    </tr>
    <!-- US-36-->
        <tr>
      <td>US-36</td>
      <td>Recuperar contraseña</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario registrado, quiero recuperar mi contraseña para volver a entrar si la olvido.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Recuperación exitosa<br><b>Given</b> que el usuario tiene una cuenta registrada<br><b>When</b> solicita recuperar su contraseña con su correo<br><b>Then</b> el sistema envía un enlace para restablecerla.</li>
          <li><b>Escenario 2:</b> Correo no registrado<br><b>Given</b> que el correo ingresado no está registrado<br><b>When</b> el usuario solicita recuperar su contraseña<br><b>Then</b> el sistema muestra un mensaje genérico sin revelar si la cuenta existe.</li>
        </ul>
      </td>
      <td>EP-01</td>
    </tr>
    <!-- US-37-->
    <tr>
      <td>US-37</td>
      <td>Cancelar reserva</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario con una reserva activa, quiero cancelarla para liberar el vehículo si cambio de planes.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Cancelación exitosa<br><b>Given</b> que el usuario tiene una reserva activa<br><b>When</b> presiona "Cancelar reserva" antes de que expire<br><b>Then</b> el sistema libera el vehículo y confirma la cancelación.</li>
          <li><b>Escenario 2:</b> Error de conexión<br><b>Given</b> que el usuario intenta cancelar<br><b>When</b> no hay conexión a internet<br><b>Then</b> el sistema informa el error y permite reintentar.</li>
        </ul>
      </td>
      <td>EP-06</td>
    </tr>
    <!-- US-38-->
    <tr>
      <td>US-38</td>
      <td>Administrar planes de suscripción</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como administrador, quiero crear, actualizar y eliminar planes de suscripción para mantener actualizada la oferta de WeRide.</li>
        </ul>
      </td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li><b>Escenario 1:</b> Creación exitosa<br><b>Given</b> que el administrador está autenticado con un token JWT válido<br><b>When</b> envía un nuevo plan con datos válidos<br><b>Then</b> el sistema responde 201 y el plan aparece en el catálogo de planes.</li>
          <li><b>Escenario 2:</b> Actualización de un plan existente<br><b>Given</b> que existe un plan registrado<br><b>When</b> el administrador envía los nuevos datos del plan<br><b>Then</b> el sistema actualiza el plan y devuelve el plan actualizado.</li>
          <li><b>Escenario 3:</b> Eliminación de un plan inexistente<br><b>Given</b> que no existe un plan con el identificador indicado<br><b>When</b> el administrador solicita eliminarlo<br><b>Then</b> el sistema informa que no se encontró el plan y no realiza ninguna eliminación.</li>
        </ul>
      </td>
      <td>EP-09</td>
    </tr>

    
  </tbody>
</table>

## 3.3. Product Backlog

| N° Orden | User Story ID | Título                                   | Descripción                                                                                                    | Story points | Nivel |
|----------|---------------|------------------------------------------|----------------------------------------------------------------------------------------------------------------|--------------|---------|
| 1 | US-01 | Inicio de sesión y registro | Como usuario quiero poder iniciar sesión o registrarme en la app para usarla diariamente. | 5 | Alta |
| 2 | US-02 | Introducir Número de Celular | Como usuario, quiero introducir mi número de celular para validar mi identidad y recibir notificaciones importantes. | 2 | Alta |
| 3 | US-03 | Introducir código de verificación | Como usuario, quiero introducir un código de verificación para validar mi identidad en la aplicación. | 2 | Alta |
| 4 | US-04 | Datos de usuario | Como usuario nuevo, quiero crear mi perfil con mis datos para que la app personalice mi experiencia. | 3 | Alta |
| 5 | US-27 | Landing page informativa | Como visitante, quiero ver una landing page clara con beneficios, planes y pasos de uso para decidir si me registro en WeRide. | 3 | Alta |
| 6 | US-11 | Seleccionar ubicación para ver vehículos cercanos disponibles | Como usuario, quiero ver los vehículos cercanos a la ubicación que elijo en el mapa para reservar el más cercano. | 5 | Alta |
| 7 | US-07 | Gestión y visualización de vehículos en Garaje | Como usuario, quiero ver los vehículos del Garaje para elegir el que mejor se ajuste a mi viaje. | 5 | Alta |
| 8 | US-08 | Filtrado de vehículos en Garaje | Como usuario, quiero filtrar los vehículos por tipo, precio, disponibilidad o marca para encontrar rápidamente el adecuado. | 3 | Alta |
| 9 | US-17 | Crear una reserva | Como usuario, quiero reservar un vehículo desde la app para asegurar su disponibilidad. | 5 | Alta |
| 10 | US-19 | Desbloqueo de vehículo con QR | Como usuario con reserva activa, quiero desbloquear el vehículo escaneando un QR para iniciar mi viaje sin pasos adicionales. | 3 | Alta |
| 11 | US-20 | Desbloqueo de vehículo desde la app | Como usuario con reserva activa, quiero desbloquear el vehículo desde la app para iniciar mi viaje cuando no puedo escanear el QR. | 3 | Alta |
| 12 | US-21 | Ver estado de desbloqueo | Como usuario, quiero ver el estado del desbloqueo en tiempo real para saber cuándo puedo empezar a conducir. | 2 | Alta |
| 13 | US-12 | Visualización de viaje en mapa | Como usuario en viaje, quiero ver mi trayecto y los datos del vehículo para controlar la batería y el tiempo restante. | 5 | Alta |
| 14 | US-23 | Finalizar viaje | Como usuario en viaje, quiero finalizar mi viaje desde la app para dejar el vehículo bloqueado y cerrar el cobro. | 3 | Alta |
| 15 | US-09 | Selección y pago de planes | Como usuario, quiero comparar los planes disponibles para elegir el que más me conviene. | 5 | Alta |
| 16 | US-10 | Proceso de pago de planes | Como usuario quiero ingresar los datos de mi tarjeta para activar el plan seleccionado. | 5 | Alta |
| 17 | US-24 | Pago en línea (sandbox) | Como usuario, quiero pagar mi viaje o plan con Yape/Plin (modo sandbox) para completar el cobro sin usar efectivo. | 8 | Alta |
| 18 | US-38 | Administrar planes de suscripción | Como administrador, quiero crear, actualizar y eliminar planes de suscripción para mantener actualizada la oferta de WeRide. | 5 | Alta |
| 19 | US-33 | Pruebas unitarias de servicios | Como equipo de desarrollo, queremos pruebas unitarias de los servicios de aplicación para detectar errores en las reglas de negocio de forma temprana. | 3 | Alta |
| 20 | US-34 | Pruebas BDD de la API con Karate | Como equipo de QA, queremos escenarios BDD con Karate sobre la API para validar los criterios de aceptación de las historias de forma automática. | 5 | Alta |
| 21 | US-35 | Pipeline de integración continua con Jenkins | Como equipo DevOps, queremos un pipeline de integración continua en Jenkins para compilar y probar el backend en cada cambio. | 5 | Alta |
| 22 | US-13 | Historial de viajes | Como usuario, quiero ver el historial de mis viajes para trackear gastos y rutas. | 3 | Media |
| 23 | US-05 | Página Principal | Como usuario, quiero ver una pantalla principal clara con accesos rápidos para llegar rápido a reservar un vehículo. | 3 | Media |
| 24 | US-06 | Gestión y personalización de perfil | Como usuario, quiero administrar mi cuenta y mi perfil para mantener mis datos actualizados. | 5 | Media |
| 25 | US-16 | Notificación de fin de reserva | Como usuario, quiero recibir una notificación antes de que finalice mi reserva. | 3 | Media |
| 26 | US-18 | Notificación de inicio y vencimiento | Como usuario con reserva, quiero recibir notificaciones cuando mi reserva esté activa y por expirar para no perderla. | 3 | Media |
| 27 | US-37 | Cancelar reserva | Como usuario con una reserva activa, quiero cancelarla para liberar el vehículo si cambio de planes. | 3 | Media |
| 28 | US-14 | Calificación de viaje | Como usuario, quiero calificar mi experiencia después del viaje para feedback y mejora del servicio. | 2 | Media |
| 29 | US-15 | Reportar problema con vehículo | Como usuario, quiero reportar un problema con el vehículo para alertar a soporte y obtener ayuda rápida. | 3 | Media |
| 30 | US-28 | Contactar con soporte | Como usuario, quiero contactar a soporte desde la landing o la app para resolver mis dudas rápidamente. | 2 | Media |
| 31 | US-36 | Recuperar contraseña | Como usuario registrado, quiero recuperar mi contraseña para volver a entrar si la olvido. | 3 | Media |
| 32 | US-22 | Desbloqueo programado | Como usuario, quiero programar el desbloqueo de un vehículo para una hora específica y asegurar su disponibilidad. | 5 | Media |
| 33 | US-29 | Administrar flota de vehículos | Como administrador de flota, quiero registrar, editar y dar de baja vehículos para mantener actualizado el catálogo disponible. | 5 | Baja |
| 34 | US-30 | Monitorear estado de vehículos | Como administrador de flota, quiero ver batería, ubicación y estado de cada vehículo para planificar recargas y mantenimiento. | 3 | Baja |
| 35 | US-31 | Gestionar reportes de problemas | Como agente de soporte, quiero ver y atender los reportes de problemas de vehículos para resolver incidencias y retirar unidades dañadas. | 3 | Baja |
| 36 | US-25 | Archivo db.json para pruebas locales | Como desarrollador, quiero un archivo db.json con usuarios, vehículos y reservas para probar el frontend sin depender del backend. | 2 | Baja |
| 37 | US-26 | Pruebas de integración del flujo completo | Como equipo de desarrollo, queremos verificar el flujo registro, login, reserva y viaje para detectar fallos de integración antes del despliegue. | 2 | Baja |
| 38 | US-32 | Documentación Swagger de la API | Como desarrollador frontend, quiero documentación OpenAPI/Swagger de la API para integrar los endpoints sin ambigüedades. | 2 | Baja |

## 3.4. Impact Mapping.

Un mapa de impacto es una técnica colaborativa y visual de planificación estratégica que alinea los objetivos de un proyecto con las acciones necesarias para alcanzarlos. En esta sección , el equipo presenta los mapas de impacto realizados.


![User Persona](assets/chapter03/Impact%20map%203.png)

![User Persona](assets/chapter03/Impact%20map%202%20(1).png)
