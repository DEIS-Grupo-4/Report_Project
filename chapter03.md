# Capítulo III: Requirements Specification

## 3.1.User Stories.

### Lista de Épicas

<table>
  <thead>
    <tr>
      <th>ID</th>
      <th>Título</th>
      <th>Descripción</th>
      <th>Criterios de aceptación</th>
      <th>EpicID</th>
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
      <td>No corresponde</td>
      <td>No corresponde</td>
    </tr>
    <tr>
      <td>EP02</td>
      <td>Funcionalidades de la app</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario de la aplicación, quiero que las funcionalidades principales que me ofrece el servicio sean funcionales.</li>
        </ul>
      </td>
      <td>No corresponde</td>
      <td>No corresponde</td>
    </tr>
    <tr>
      <td>EP03</td>
      <td>Gestión de pagos y suscripciones</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario, quiero gestionar mis métodos de pago y suscripciones para acceder a los servicios y planes de la aplicación.</li>
        </ul>
      </td>
      <td>No corresponde</td>
      <td>No corresponde</td>
    </tr>
    <tr>
      <td>EP04</td>
      <td>Uso del mapa</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario de la aplicación, quiero acceder al mapa de la aplicación para realizar la reserva de vehículos y seguimiento de rutas.</li>
        </ul>
      </td>
      <td>No corresponde</td>
      <td>No corresponde</td>
    </tr>
    <tr>
      <td>EP05</td>
      <td>Gestión de viajes</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario, quiero visualizar y gestionar mis trayectos en el mapa, incluyendo detalles del vehículo, ruta y estado del viaje.</li>
        </ul>
      </td>
      <td>No corresponde</td>
      <td>No corresponde</td>
    </tr>
    <tr>
      <td>EP06</td>
      <td>Gestión de reservas</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario, quiero reservar vehículos y recibir notificaciones sobre el estado y fin de mi reserva para asegurar disponibilidad.</li>
        </ul>
      </td>
      <td>No corresponde</td>
      <td>No corresponde</td>
    </tr>
    <tr>
      <td>EP07</td>
      <td>Desbloqueo y acceso rápido a vehículos</td>
      <td>
        <ul style="margin:0; padding-left:18px;">
          <li>Como usuario, quiero desbloquear y acceder a los vehículos de forma ágil mediante tecnologías como QR para mejorar la experiencia de inicio de viaje.</li>
        </ul>
      </td>
      <td>No corresponde</td>
      <td>No corresponde</td>
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
          <li>Como usuario quiero poder crear un perfil para colocar mis datos.</li>
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
          <li>Como usuario quiero poder ver una pantalla principal estética que me atraiga a usar el servicio.</li>
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
          <li>Como usuario quiero acceder a mi perfil para administrar mi cuenta.</li>
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
          <li>Como usuario quiero acceder al Garaje para gestionar los vehículos disponibles.</li>
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
          <li>Como usuario quiero filtrar los vehículos disponibles en el Garaje por tipo.</li>
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
          <li>Como usuario quiero visualizar los diferentes planes disponibles.</li>
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
          <li>Como usuario, al seleccionar una ubicación del mapa quiero ver los vehículos cercanos disponibles.</li>
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
          <li>Como usuario quiero ver mi trayecto actual en el mapa, junto con información relevante del vehículo.</li>
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
          <li>Como usuario, quiero reservar un vehículo desde la app.</li>
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
          <li>Como usuario, quiero recibir notificaciones cuando mi reserva esté activa y cuando esté por expirar.</li>
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
          <li>Como usuario, quiero desbloquear el vehículo escaneando un QR.</li>
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
          <li>Como usuario, quiero desbloquear el vehículo directamente desde la aplicación.</li>
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
          <li>Como usuario, quiero ver el estado de desbloqueo del vehículo en tiempo real.</li>
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
      <td>EP07</td>
    </tr>
  </tbody>
</table>

## 3.2. Impact Mapping.

Un mapa de impacto es una técnica colaborativa y visual de planificación estratégica que alinea los objetivos de un proyecto con las acciones necesarias para alcanzarlos. En esta sección , el equipo presenta los mapas de impacto realizados.


![User Persona](assets/chapter03/Impact%20map%203.png)

![User Persona](assets/chapter03/Impact%20map%202%20(1).png)


## 3.3. Product Backlog

| N° Orden | User Story ID | Título                                   | Descripción                                                                                                    | Story points |
|----------|---------------|------------------------------------------|----------------------------------------------------------------------------------------------------------------|--------------|
| 1        | US-01         | Inicio de sesión y registro              | Como usuario quiero poder iniciar sesión o registrarme en la app para usarla diariamente.                      | 5            |
| 2        | US-02         | Introducir Número de Celular             | Como usuario, quiero introducir mi número de celular para validar mi identidad y recibir notificaciones importantes. | 2            |
| 3        | US-03         | Introducir código de verificación        | Como usuario, quiero introducir un código de verificación para validar mi identidad en la aplicación.          | 2            |
| 4        | US-04         | Datos de usuario                         | Como usuario quiero poder crear un perfil para colocar mis datos.                                              | 3            |
| 5        | US-05         | Página Principal                         | Como usuario quiero poder ver una pantalla principal estética que me atraiga a usar el servicio.               | 3            |
| 6        | US-06         | Gestión y personalización de perfil      | Como usuario quiero acceder a mi perfil para administrar mi cuenta.                                            | 5            |
| 7        | US-07         | Gestión y visualización de vehículos en Garaje | Como usuario quiero acceder al Garaje para gestionar los vehículos disponibles.                          | 5            |
| 8        | US-08         | Filtrado de vehículos en Garaje          | Como usuario quiero filtrar los vehículos disponibles en el Garaje por tipo.                                   | 3            |
| 9        | US-09         | Selección y pago de planes               | Como usuario quiero visualizar los diferentes planes disponibles.                                              | 5            |
| 10       | US-10         | Proceso de pago de planes                | Como usuario quiero ingresar los datos de mi tarjeta para activar el plan seleccionado.                        | 5            |
| 11       | US-11         | Seleccionar ubicación para ver vehículos cercanos disponibles | Como usuario, al seleccionar una ubicación del mapa quiero ver los vehículos cercanos disponibles. | 5            |
| 12       | US-12         | Visualización de viaje en mapa           | Como usuario quiero ver mi trayecto actual en el mapa, junto con información relevante del vehículo.           | 5            |
| 13       | US-13         | Historial de viajes                      | Como usuario, quiero ver el historial de mis viajes para trackear gastos y rutas.                              | 3            |
| 14       | US-14         | Calificación de viaje                    | Como usuario, quiero calificar mi experiencia después del viaje para feedback y mejora del servicio.           | 2            |
| 15       | US-15         | Reportar problema con vehículo           | Como usuario, quiero reportar un problema con el vehículo para alertar a soporte y obtener ayuda rápida.       | 3            |
| 16       | US-16         | Notificación de fin de reserva           | Como usuario, quiero recibir una notificación antes de que finalice mi reserva.                                | 3            |
| 17       | US-17         | Crear una reserva                        | Como usuario, quiero reservar un vehículo desde la app.                                                        | 5            |
| 18       | US-18         | Notificación de inicio y vencimiento     | Como usuario, quiero recibir notificaciones cuando mi reserva esté activa y cuando esté por expirar.           | 3            |
| 19       | US-19         | Desbloqueo de vehículo con QR            | Como usuario, quiero desbloquear el vehículo escaneando un QR.                                                 | 3            |
| 20       | US-20         | Desbloqueo de vehículo desde la app      | Como usuario, quiero desbloquear el vehículo directamente desde la aplicación.                                 | 3            |
| 21       | US-21         | Ver estado de desbloqueo                 | Como usuario, quiero ver el estado de desbloqueo del vehículo en tiempo real.                                  | 2            |
| 22       | US-22         | Desbloqueo programado                    | Como usuario, quiero programar el desbloqueo de un vehículo para una hora específica y asegurar su disponibilidad. | 5            |
