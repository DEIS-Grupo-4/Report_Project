# Capítulo V: Product Implementation, Validation & Deployment.
## 5.1. Software Configuration Management.
 
Esta sección define las decisiones y acuerdos fundamentales para el desarrollo, mantenimiento y despliegue de **WeRide**, plataforma de alquiler de bicicletas y scooters eléctricos. Su objetivo es asegurar coherencia, trazabilidad y calidad a lo largo del ciclo de vida del producto.
 
### 5.1.1. Software Development Environment Configuration.
 
| Actividad | Producto | Propósito en el proyecto | Referencia |
|---|---|---|---|
| Project Management | GitHub | Almacenar el código fuente y el informe en repositorios, con control de versiones, Pull Requests e insights de colaboración. | https://github.com |
| | Trello | Organizar y asignar las tareas de cada Sprint. | https://trello.com |
| | WhatsApp | Coordinar acuerdos y recordatorios de reuniones. | https://www.whatsapp.com |
| | Discord y Google Meet | Realizar las reuniones virtuales de planificación, seguimiento y retrospectiva. | https://discord.com · https://meet.google.com |
| Requirements Management | Miro | Organizar visualmente requisitos, mapas y lluvia de ideas del equipo. | https://miro.com |
| Product UX/UI Design | Figma | Diseñar wireframes, mock-ups y prototipos interactivos. | https://www.figma.com |
| Software Development | Git | Control de versiones distribuido. | https://git-scm.com |
| | Node.js | Entorno de ejecución para construir y servir la Web Application. | https://nodejs.org |
| | HTML5, CSS3 y JavaScript | Estructura, estilo e interactividad de la Landing Page. | https://developer.mozilla.org |
| | TypeScript y Angular | Desarrollo de la Web Application como Single Page Application. | https://angular.dev |
| | Java 17 y Spring Boot | Desarrollo del backend con RESTful API. | https://spring.io/projects/spring-boot |
| | Maven | Gestión de dependencias y construcción del backend. | https://maven.apache.org |
| | MySQL y MySQL Workbench | Base de datos relacional y su administración visual. | https://www.mysql.com/products/workbench |
| | json-server | Simular una API con `db.json` durante el desarrollo inicial de la Web Application. | https://github.com/typicode/json-server |
| | Visual Studio Code y WebStorm | Entornos de desarrollo para la Landing Page y la Web Application. | https://code.visualstudio.com · https://www.jetbrains.com/webstorm |
| | IntelliJ IDEA | Entorno de desarrollo para el backend en Java. | https://www.jetbrains.com/idea |
| | Docker | Entorno reproducible: el backend incluye `Dockerfile` y `docker-compose.yml`. | https://www.docker.com |
| Software Documentation | Swagger (OpenAPI) | Documentar y probar los endpoints de la RESTful API. | https://swagger.io |
| | Markdown y Mermaid | Redacción del informe y diagramas de clases en el repositorio. | https://www.markdownguide.org · https://mermaid.js.org |
| | dbdiagram.io | Diagrama de la base de datos. | https://dbdiagram.io |
| | Structurizr | Diagramas de arquitectura con el modelo C4 (Structurizr DSL). | https://structurizr.com |
| Software Deployment | GitHub Pages | Publicar la Landing Page. | https://pages.github.com |
| | Vercel | Publicar la Web Application. | https://vercel.com |
| | Microsoft Azure (máquina virtual con Ubuntu 22.04) | Alojar el backend en un entorno real. | https://azure.microsoft.com |
| | nginx y systemd | Reverse proxy y ejecución del backend como servicio en la máquina virtual. | https://nginx.org |
| Software Testing | JUnit | Pruebas unitarias del backend. | https://junit.org |
| | Karate | Pruebas de aceptación de la API REST. | https://github.com/karatelabs/karate |
| | Selenium | Pruebas end-to-end de la Web Application. | https://www.selenium.dev |
| Continuous Integration | Jenkins | Automatizar compilación, pruebas y despliegue. | https://www.jenkins.io |
| | SonarQube | Análisis estático de calidad y seguridad del código. | https://www.sonarsource.com/products/sonarqube |

 
### 5.1.2. Source Code Management.
 
Se utiliza **GitHub** como plataforma de control de versiones, con un repositorio por producto:
 
| Producto | Repositorio |
|---|---|
| Informe del proyecto (Report) | https://github.com/DEIS-Grupo-4/Report_Project |
| Landing Page | https://github.com/DEIS-Grupo-4/Landing-Page.git |
| Web Application (Frontend) | https://github.com/DEIS-Grupo-4/Fronted-Weride-DEIS.git |
| Web Services (Backend) | https://github.com/DEIS-Grupo-4/Backend-Weride-DEIS |
 
#### Flujo de trabajo: GitFlow
 
El equipo aplica GitFlow como flujo de trabajo de ramas y colaboración:
 
| Rama | Origen | Destino | Propósito |
|---|---|---|---|
| `main` (`master` en el backend) | - | - | Código estable y desplegado. Solo recibe fusiones desde `release/*` y `hotfix/*`. |
| `develop` | `main` | - | Rama de integración donde se unen las funcionalidades terminadas. |
| `feature/<contexto>-<descripcion>` | `develop` | `develop` | Una rama por funcionalidad o historia de usuario. Ejemplo: `feature/booking-draft`. |
| `release/<x.y.z>` | `develop` | `main` y `develop` | Estabilización de una entrega antes de publicarla. |
| `hotfix/<x.y.z>` | `main` | `main` y `develop` | Corrección urgente de un error en producción. |
| `docs/<descripcion>` y `refactor/<descripcion>` | `develop` | `develop` | Ramas de trabajo para documentación y refactorización, con el mismo ciclo que una `feature`. |
 
Los nombres de rama usan inglés, minúsculas y guiones. Los cambios se integran a `develop` mediante **Pull Request** revisado por al menos un compañero del equipo.
 
#### Semantic Versioning
 
Las versiones se nombran con el formato `MAJOR.MINOR.PATCH` (Semantic Versioning 2.0.0): `MAJOR` para cambios incompatibles, `MINOR` para nuevas funcionalidades compatibles y `PATCH` para correcciones. Cada release se marca con un tag, por ejemplo `v1.0.0`.
 
#### Conventional Commits
 
Los mensajes de commit siguen la especificación Conventional Commits: `<tipo>(<contexto opcional>): <descripción>`. Los tipos usados son `feat`, `fix`, `docs`, `refactor`, `style`, `test` y `chore`. Ejemplos:
 
- `feat(booking): implement aggregate and command and query services`
- `refactor: use Long for userId in notifications and trips`
- `docs: add class diagram in three parts`
### 5.1.3. Source Code Style Guide & Conventions
 
El código y los artefactos se redactan con nomenclatura en inglés. Para cada lenguaje se adopta una guía de estilo de referencia:
 
| Lenguaje | Uso en el proyecto | Guía adoptada |
|---|---|---|
| HTML y CSS | Landing Page | Google HTML/CSS Style Guide (https://google.github.io/styleguide/htmlcssguide.html) |
| JavaScript | Landing Page | Google JavaScript Style Guide (https://google.github.io/styleguide/jsguide.html) |
| TypeScript | Web Application en Angular | Google TypeScript Style Guide (https://google.github.io/styleguide/tsguide.html) y Angular Coding Style Guide (https://angular.io/guide/styleguide) |
| Java | Backend con Spring Boot | Google Java Style Guide (https://google.github.io/styleguide/javaguide.html) |
| Gherkin | Archivos `.feature` | Gherkin Conventions for Readable Specifications (https://specflow.org/gherkin/gherkin-conventions-for-readable-specifications/) |
 
Convenciones propias del proyecto:
 
- **Backend:** clases en `PascalCase`, métodos y atributos en `camelCase`, y tablas en `snake_case` y plural (por ejemplo `trip_photos`). Cada bounded context se organiza en las capas `interfaces`, `application`, `domain` e `infrastructure`.
- **Web Application:** los componentes se organizan por bounded context (`auth`, `booking`, `garage`, `plans` y `trip`), cada uno con su archivo HTML, CSS y TypeScript.
### 5.1.4. Software Deployment Configuration.
 
#### Landing Page
 
Se publica con GitHub Pages: los archivos HTML, CSS y JavaScript del repositorio se sirven desde la rama configurada para Pages, y la página queda disponible en https://deis-grupo-4.github.io/Landing-Page/
 
#### Web Application
 
Se publica en Vercel: el proyecto se conecta al repositorio de GitHub y Vercel construye y despliega la aplicación automáticamente con cada push a la rama principal.
 
#### Web Services (Backend)
 
El backend se aloja en una máquina virtual de Microsoft Azure con Ubuntu 22.04. El despliegue se realiza manualmente mediante acceso SSH:
 
1. Instalar JDK 17, Maven, Git, MySQL y nginx en la máquina virtual.
2. Clonar el repositorio y construir la aplicación con `mvn clean package`.
3. Registrar la aplicación como servicio de systemd, para que se ejecute en segundo plano y se reinicie ante fallos.
4. Configurar nginx como reverse proxy, que expone la API en los puertos 80 y 443 y reenvía las solicitudes a la aplicación en el puerto 8080.
5. Verificar el servicio con los logs de systemd y con solicitudes a los endpoints.
El detalle de los comandos y las evidencias se documenta en la sección 5.2.4.7. **[CONFIRMAR: si existe un flujo de despliegue automático con GitHub Actions, describirlo aquí; si no, eliminar esa mención en 5.2.4.8]**
 
**Nota de decisión técnica:** el enunciado del curso sugiere ASP.NET Core y C# para el backend. El equipo decidió continuar con Java 17, Spring Boot y MySQL, porque corresponde a la arquitectura DDD y CQRS implementada y validada en el ciclo anterior. Migrar a ASP.NET Core implicaría reescribir los bounded contexts, los controladores REST y la capa de persistencia ya desplegada, lo cual representa un riesgo alto para los plazos del curso sin un beneficio funcional adicional.

## 5.2. Landing Page, Services & Applications Implementation.

Los Sprints 1 a 4 documentan el desarrollo inicial de WeRide realizado por el equipo WeTech en el ciclo anterior. El equipo actual continúa el producto a partir de ese trabajo y documenta sus propias contribuciones desde el Sprint 4 para adelante.

### 5.2.1. Sprint 1

#### 5.2.1.1. Sprint Planning 1.

<table>
  <tr>
    <th>Elemento</th>
    <th>Detalle</th>
  </tr>

  <tr>
    <td><strong>Sprint</strong></td>
    <td>Sprint 1 — Implementación inicial de la landing page de WeRide</td>
  </tr>
  <tr>
    <td><strong>Sprint Planning Background</strong></td>
    <td>Durante este primer sprint, el equipo WeTech se enfocará en desarrollar la landing page de WeRide como primer punto de contacto con los usuarios. Se priorizará presentar la propuesta de valor, facilitar la navegación entre secciones, adaptar la interfaz a dispositivos móviles, mostrar el catálogo y las características de los vehículos eléctricos, y habilitar el acceso a la aplicación.</td>
  </tr>

  <tr>
    <td><strong>Fecha</strong></td>
    <td>2025-09-19</td>
  </tr>
  <tr>
    <td><strong>Hora</strong></td>
    <td>22:00 (GMT-5)</td>
  </tr>
  <tr>
    <td><strong>Lugar</strong></td>
    <td>Reunión virtual — Discord</td>
  </tr>
  <tr>
    <td><strong>Preparado por</strong></td>
    <td>WeTech</td>
  </tr>
  <tr>
    <td><strong>Asistentes</strong></td>
    <td>Samuel Bonifacio, Jefferson Castro, Diego Seminario, Jhimy Romero, Arnold Morales</td>
  </tr>
  <tr>
    <td><strong>Sprint n-1 Review</strong></td>
    <td>Se creó la organización WeTech en GitHub, se definieron ramas, convenciones de commits y se asignaron tareas iniciales en investigación de usuarios, wireframes y mockups.</td>
  </tr>
  <tr>
    <td><strong>Sprint n-1 Retrospective</strong></td>
    <td>Se completó la estructura base de la landing page (HTML/CSS/JS). Lecciones aprendidas: mejorar granularidad en tareas y definir criterios de aceptación más claros.</td>
  </tr>

<tr>
  <td><strong>Sprint Goal (Statement)</strong></td>
  <td>
    <strong>Our focus is on</strong> implementar una landing page funcional, intuitiva y adaptable a dispositivos móviles, que permita a los visitantes conocer WeRide, explorar los vehículos eléctricos y acceder a la aplicación.<br>
    <strong>We believe it delivers</strong> una experiencia inicial clara y accesible, facilitando que los usuarios comprendan la propuesta de valor de WeRide y conozcan las alternativas de movilidad disponibles.<br>
    <strong>This will be confirmed when</strong> las seis User Stories seleccionadas cumplan sus criterios de aceptación y se verifique el funcionamiento de la navegación, la visualización del catálogo, la comparación de vehículos, el diseño responsive y el acceso a la aplicación.
  </td>
</tr>

<tr>
  <td><strong>User Stories (SP)</strong></td>
  <td>
    - <strong>US-27 (3 SP)</strong><br>
    - <strong>US-43 (2 SP)</strong><br>
    - <strong>US-56 (5 SP)</strong><br>
    - <strong>US-44 (3 SP)</strong><br>
    - <strong>US-45 (5 SP)</strong><br>
    - <strong>US-49 (2 SP)</strong><br>
  </td>
</tr>
<tr>
  <td><strong>Sprint 1 Velocity (forecast)</strong></td>
  <td>20 puntos</td>
</tr>
<tr>
  <td><strong>Sum of Story Points (commit)</strong></td>
  <td>20 puntos</td>
</tr>

</table>




#### User Stories seleccionadas para el Sprint 1

| ID | User Story | Puntos |
|---|---|---:|
| US-27 | Como visitante, quiero conocer la propuesta de valor de WeRide desde la página de inicio para comprender qué servicio ofrece. | 3 |
| US-43 | Como visitante, quiero desplazarme a las secciones de la landing page desde el menú para encontrar rápidamente la información que busco. | 2 |
| US-56 | Como visitante, quiero navegar por la landing page desde mi celular para consultar sus secciones sin dificultades. | 5 |
| US-44 | Como visitante, quiero conocer los tipos de vehículos eléctricos ofrecidos para identificar alternativas adecuadas a mis necesidades. | 3 |
| US-45 | Como visitante, quiero consultar las especificaciones de cada tipo de vehículo para comparar sus características antes de elegir. | 5 |
| US-49 | Como visitante, quiero abrir la aplicación mediante Go to App para comenzar a utilizar el servicio. | 2 |

**Total de puntos:** 20

---


---

#### 5.2.1.2. Aspect Leaders and Collaborators

En esta sección se presenta la matriz de liderazgo y colaboración (Leadership-and-Collaboration Matrix, LACX) para el Sprint 1 de WeRide. Esta matriz identifica, para cada aspecto clave del Sprint, quién es el líder responsable y quiénes son los colaboradores, facilitando así la comunicación y la asignación de tareas dentro del equipo. 

Los aspectos considerados en este Sprint incluyen: diseño de la landing page, desarrollo de funcionalidades de registro e inicio de sesión, implementación de la barra de navegación, y configuración del footer con enlaces de contacto y redes sociales.


| Team Member (Apellido, Nombre) | GitHub Username | Landing Page Design | Navegación | Catálogo y Comparación de Vehículos | Diseño Responsive | Acceso a la App |
|---|---|---|---|---|---|---|
| Bonifacio, Samuel | samuelbonifacio015 | L | L | C | L | C |
| Castro, Jefferson | JeffersonCastroPariona | C | C | L | C | L |
| Seminario, Diego | DiegoSeminario | C | L | C | C | C |
| Romero, Jhimy | jhimyromeromeza | L | L | C | C | C |
| Morales, Arnold | Arnold-TI | C | C | L | L | C |


**L:** Leader (Líder)  
**C:** Collaborator (Colaborador)

Esta organización permite una asignación clara de responsabilidades y fomenta la colaboración efectiva durante el desarrollo del Sprint.

---

#### 5.2.1.3. Sprint Backlog 1.

| ID | Title/Section | Description | Estimation (Hours) | Assigned To | Status |
|---|---|---|---:|---|---|
| US-27 | Landing Page Informativa | Diseñar e implementar la estructura principal de la landing page, incluyendo el encabezado, presentación de WeRide y propuesta de valor. | 4 | Bonifacio Jaramillo, Samuel Jesus | Done |
| US-27 | Estilos Generales | Aplicar colores, tipografías, espaciados y componentes visuales para mantener una identidad gráfica consistente. | 3 | Romero Meza, Jhimy Pool | Done |
| US-43 | Barra de Navegación | Implementar el menú de navegación con enlaces funcionales a las secciones de la landing page. | 3 | Seminario Castillo, Diego Vicente | Done |
| US-43 | Navegación entre Secciones | Configurar el desplazamiento y verificar que los enlaces conduzcan correctamente a cada sección. | 2 | Bonifacio Jaramillo, Samuel Jesus | Done |
| US-56 | Diseño Responsive | Adaptar la estructura, imágenes y componentes de la landing page a dispositivos móviles y tablets. | 5 | Morales Sosa, Arnold Gabriel | Done |
| US-56 | Validación Responsive | Comprobar la visualización y funcionamiento del menú, tarjetas y botones en diferentes resoluciones. | 3 | Romero Meza, Jhimy Pool | Done |
| US-44 | Catálogo de Vehículos | Implementar una sección que muestre los tipos de vehículos eléctricos disponibles, incluyendo imágenes y nombres. | 4 | Castro Pariona, Jefferson Ernesto | Done |
| US-45 | Comparación de Vehículos | Desarrollar la sección de comparación de vehículos con información sobre velocidad, autonomía, peso y tiempo de carga. | 5 | Castro Pariona, Jefferson Ernesto | Done |
| US-45 | Selección de Categorías | Implementar la interacción que permita seleccionar diferentes tipos de vehículos y actualizar sus especificaciones. | 3 | Seminario Castillo, Diego Vicente | Done |
| US-49 | Acceso a la Aplicación | Implementar el botón Go to App y configurar su redirección hacia la aplicación WeRide. | 3 | Castro Pariona, Jefferson Ernesto | Done |
| US-49 | Verificación de Redirección | Comprobar que los accesos a la aplicación desde el encabezado y la portada dirijan a la ruta configurada. | 2 | Morales Sosa, Arnold Gabriel | Done |

**Total de horas estimadas:** 37 horas.

**Total de Story Points comprometidos:** 20 SP.

---


#### 5.2.1.4. Development Evidence for Sprint Review

Durante el Sprint 1, el equipo de **WeTech** realizó múltiples commits en el repositorio de GitHub, evidenciando el avance y cumplimiento de las tareas planificadas. A continuación, se presenta una tabla con los principales commits realizados, siguiendo el formato requerido:

| Repository                                         | Branch | Commit Id | Commit Message                                 | Commit Message Body                                   | Committed on (Date)     |
|----------------------------------------------------|--------|-----------|------------------------------------------------|-------------------------------------------------------|------------------------|
| OpenSource-Grupo-4/Landing-Page                    | develop   | 9c5de9c   | Add footer styles to styles.css                | Se agregaron estilos para el footer en styles.css.    | 13/09/2025             |
| OpenSource-Grupo-4/Landing-Page                    | develop   | d0d0f0c   | Add footer section with contact and social links| Se añadió la sección de footer con enlaces de contacto y redes sociales. | 13/09/2025             |
| OpenSource-Grupo-4/Landing-Page                    | develop   | 098b740   | Merge pull request #2 from OpenSource-Grupo-4/develop | Se fusionaron cambios de la rama develop.             | 12/09/2025             |
| OpenSource-Grupo-4/Landing-Page                    | feature/responsive-navbar   | eddad5b   | feat: added navbar & hero section              | Se agregó la barra de navegación y la sección principal. | 12/09/2025             |
| OpenSource-Grupo-4/Landing-Page                    | develop   | 2a59cfe   | chore: index file refactor                     | Refactorización del archivo index.                    | 12/09/2025             |
| OpenSource-Grupo-4/Landing-Page                    | main   | 69695c3   | Merge pull request #1 from OpenSource-Grupo-4/develop | Se fusionaron cambios iniciales de la rama develop.   | 11/09/2025             |
| OpenSource-Grupo-4/Landing-Page                    | hero-ui-fix   | 90dd977   | /changes v.2 Jefferson Castro - Landing        | Cambios en la landing page por Jefferson Castro.      | 11/09/2025             |
| OpenSource-Grupo-4/Landing-Page                    | main   | 59a25be   | feat: added steps section                      | Se agregó la sección de pasos.                        | 18/09/2025             |
| OpenSource-Grupo-4/Landing-Page                    | feature/responsive   | 4317f4c   | styles: updated responsive for steps cards     | Se mejoró la responsividad de las tarjetas de pasos.  | 18/09/2025             |
| OpenSource-Grupo-4/Landing-Page                    | main   | 9deb5a8   | feat: added steps section                      | Se agregó la sección de pasos.                        | 18/09/2025             |
| OpenSource-Grupo-4/Landing-Page                    | develop   | 6802c55   | chore: added imgs & syntax updates             | Se añadieron imágenes y se actualizaron detalles de sintaxis. | 18/09/2025             |

Cada commit refleja el trabajo colaborativo y el cumplimiento de los objetivos del Sprint, asegurando la trazabilidad y transparencia en el desarrollo de **WeRide**.

**Reporte de commits:**

![Commits](assets/chapter05/landing-commits.png)

---

#### 5.2.1.5. Execution Evidence for Sprint Review.

En esta entrega, nos centramos en el desarrollo completo de la Landing Page para nuestra plataforma de alquiler en línea. Nuestro objetivo es desplegar una página web atractiva y efectiva que actúe como el punto de entrada para nuestros usuarios. 

Es por ello que se comparte las evidencias de ambos repositorios para corroborar el trabajo hecho por cada uno de los participantes.

![NetworkGraph](assets/chapter05/networkgraph.png)

#### 5.2.1.6. Services Documentation Evidence for Sprint Review.

Para esta primera entrega no hubo implementación de APIs, pues solo se realizó la Landing Page.

#### 5.2.1.7. Software Deployment Evidence for Sprint Review.

El objetivo del primer Sprint fue el desarrollo e implementación de la Landing Page. Para eso, utilizamos GitHub y GitHub Pages. El proceso del desarrollo fue el siguiente:

1. Se creó una organización en GitHub y, dentro de ella, se crearon dos repositorios. Uno para el informe del trabajo y otro para la Landing Page ![GithubOrg](assets/chapter05/organization-os.png)
2. Luego, a través de los commits, el equipo fue editando los archivos index.html y styles.css, además de ir añadiendo imágenes a utilizar en el directorio images. ![Commits-example](assets/chapter05/commits.png)
3. Finalmente, se implementó GitHub Pages en el repositorio de GitHub y se desplegó la Landing Page, la que se puede visitar en el siguiente link: https://deis-grupo-4.github.io/Landing-Page/

#### 5.2.1.8. Team Collaboration Insights during Sprint.

A continuación, se adjuntan las capturas de evidencia de los insights de los repositorios del informe y Landing Page para evidenciar la participación de todos los miembros:

- Insight Landing Page:
![InsightLP](assets/chapter05/insightLP.png)

- Insight Report
![InsightR](assets/chapter05/insightR.png)

## 5.2.2. Sprint 2


### 5.2.2.1. Sprint Planning 2

<table>
  <tr>
    <th>Elemento</th>
    <th>Detalle</th>
  </tr>
  <tr>
    <td><strong>Sprint</strong></td>
    <td>Sprint 2 — Implementación de secciones informativas, comerciales y de contacto de la landing page de WeRide</td>
  </tr>
  <tr>
    <td><strong>Sprint Planning Background</strong></td>
    <td>Después de desarrollar la estructura inicial de la landing page durante el Sprint 1, el equipo WeTech continuará incorporando información relevante sobre el servicio. Se priorizará mostrar las ubicaciones disponibles, explicar el funcionamiento de WeRide, presentar los planes y tarifas, incluir la oferta corporativa B2B y facilitar los canales de contacto. También se incorporarán contenidos sobre beneficios, impacto y testimonios.</td>
  </tr>
  <tr>
    <td><strong>Fecha</strong></td>
    <td>2025-10-08</td>
  </tr>
  <tr>
    <td><strong>Hora</strong></td>
    <td>21:00 (GMT-5)</td>
  </tr>
  <tr>
    <td><strong>Lugar</strong></td>
    <td>Reunión virtual — Google Meet</td>
  </tr>
  <tr>
    <td><strong>Preparado por</strong></td>
    <td>WeTech</td>
  </tr>
  <tr>
    <td><strong>Asistentes</strong></td>
    <td>Samuel Bonifacio, Jefferson Castro, Diego Seminario, Jhimy Romero, Arnold Morales</td>
  </tr>
  <tr>
    <td><strong>Sprint n-1 Review</strong></td>
    <td>Se revisaron los entregables del Sprint 1 relacionados con la estructura principal de la landing page, navegación, diseño responsive, catálogo y comparación de vehículos, así como el acceso a la aplicación. Los resultados y criterios de aceptación deben contrastarse con las evidencias del repositorio.</td>
  </tr>
  <tr>
    <td><strong>Sprint n-1 Retrospective</strong></td>
    <td>Se identificó la necesidad de mantener una distribución clara de responsabilidades, mejorar la organización de los componentes y verificar los criterios de aceptación de cada funcionalidad antes de cerrar las tareas.</td>
  </tr>
  <tr>
    <td><strong>Sprint Goal (Statement)</strong></td>
    <td>
      <strong>Our focus is on</strong> completar las secciones informativas y comerciales de la landing page de WeRide, permitiendo consultar ubicaciones, funcionamiento del servicio, planes, beneficios y medios de contacto.<br>
      <strong>We believe it delivers</strong> información más completa para que los visitantes comprendan cómo funciona WeRide, comparen alternativas y evalúen el servicio antes de utilizar la aplicación.<br>
      <strong>This will be confirmed when</strong> las ocho User Stories seleccionadas cumplan sus criterios de aceptación y se compruebe que las secciones muestran información clara, mantienen una navegación funcional y permiten acceder a los canales de contacto correspondientes.
    </td>
  </tr>
  <tr>
    <td><strong>User Stories (SP)</strong></td>
    <td>
      - <strong>US-46 (3 SP)</strong><br>
      - <strong>US-47 (3 SP)</strong><br>
      - <strong>US-48 (3 SP)</strong><br>
      - <strong>US-55 (3 SP)</strong><br>
      - <strong>US-53 (2 SP)</strong><br>
      - <strong>US-50 (2 SP)</strong><br>
      - <strong>US-51 (2 SP)</strong><br>
      - <strong>US-52 (2 SP)</strong>
    </td>
  </tr>
  <tr>
    <td><strong>Sprint 2 Velocity (forecast)</strong></td>
    <td>20 puntos</td>
  </tr>
  <tr>
    <td><strong>Sum of Story Points (commit)</strong></td>
    <td>20 puntos</td>
  </tr>
</table>


<hr>


<h2>Objetivo del Sprint (versión SMART)</h2>

<p><strong>Objetivo:</strong> Completar durante el Sprint 2 ocho funcionalidades informativas y comerciales de la landing page de WeRide, con un compromiso total de 20 Story Points, para que los visitantes puedan conocer las ubicaciones, el funcionamiento del servicio, los planes y los medios de contacto.</p>

<ul>
  <li><strong>Específico:</strong> Implementar las secciones de ubicaciones, funcionamiento del servicio, planes y tarifas, plan corporativo B2B, contacto, beneficios, indicadores de impacto y testimonios.</li>
  <li><strong>Medible:</strong> Verificar el cumplimiento de los criterios de aceptación de las ocho User Stories seleccionadas.</li>
  <li><strong>Alcanzable:</strong> Se establece un compromiso de 20 Story Points, sujeto a la capacidad estimada del equipo.</li>
  <li><strong>Relevante:</strong> Permite comunicar la propuesta de valor de WeRide y facilitar la evaluación del servicio por usuarios particulares y empresas.</li>
  <li><strong>Tiempo-bound:</strong> Las funcionalidades deberán completarse al cierre del Sprint 2.</li>
</ul>




#### User Stories seleccionadas para el Sprint 2

| ID | User Story | Puntos |
|---|---|---:|
| US-46 | Como visitante, quiero consultar las zonas y puntos de referencia donde opera WeRide para evaluar si el servicio me resulta accesible. | 3 |
| US-47 | Como visitante, quiero conocer los pasos para registrarme, utilizar y devolver un vehículo para comprender el proceso de uso de WeRide. | 3 |
| US-48 | Como visitante, quiero comparar los planes, precios y beneficios disponibles para evaluar cuál se adapta a mis necesidades. | 3 |
| US-55 | Como representante de una empresa, quiero consultar las condiciones del Business Plan para evaluar su utilidad para mis colaboradores. | 3 |
| US-53 | Como visitante, quiero encontrar los datos de contacto de WeRide para realizar consultas generales sobre el servicio. | 2 |
| US-50 | Como visitante, quiero conocer las ventajas de la movilidad eléctrica que propone WeRide para evaluar su utilidad. | 2 |
| US-51 | Como visitante, quiero consultar indicadores de alcance de WeRide para conocer la dimensión del servicio. | 2 |
| US-52 | Como visitante, quiero leer experiencias de usuarios para conocer opiniones sobre el servicio antes de utilizarlo. | 2 |

**Total de puntos:** 20

---


---


### 5.2.2.2. Aspect Leaders and Collaborators

En esta sección se presenta la matriz de liderazgo y colaboración (Leadership-and-Collaboration Matrix, LACX) correspondiente al Sprint 2 de WeRide. Su propósito es identificar a los integrantes responsables de las funcionalidades seleccionadas y facilitar la coordinación del trabajo.

Los aspectos considerados incluyen la visualización de ubicaciones (US-46), información sobre el funcionamiento del servicio (US-47), planes y tarifas (US-48), plan corporativo B2B (US-55), contacto (US-53), beneficios (US-50), indicadores de impacto (US-51) y testimonios (US-52).

| Team Member (Apellido, Nombre) | GitHub Username | Ubicaciones | Funcionamiento del Servicio | Planes y Tarifas / B2B | Contacto y Beneficios | Impacto y Testimonios |
|---|---|---|---|---|---|---|
| Bonifacio, Samuel | samuelbonifacio015 | L | C | C | C | C |
| Castro, Jefferson | JeffersonCastroPariona | C | C | L | C | C |
| Seminario, Diego | DiegoSeminario | C | L | C | C | C |
| Romero, Jhimy | jhimyromeromeza | C | C | C | C | L |
| Morales, Arnold | Arnold-TI | C | C | C | L | C |

**L:** Leader (Líder)  
**C:** Collaborator (Colaborador)

Esta distribución permite identificar un líder principal por aspecto y mantener la participación del equipo durante el desarrollo del Sprint 2.

---


### 5.2.2.3. Sprint Backlog 2

| ID | Title/Section | Description | Estimation (Hours) | Assigned To | Status |
|---|---|---|---:|---|---|
| US-46 | Sección de Ubicaciones | Implementar la sección Locations con los nombres, direcciones y puntos de referencia donde opera WeRide. | 4 | Bonifacio Jaramillo, Samuel Jesus | To Do |
| US-46 | Tarjetas de Ubicaciones | Diseñar las tarjetas de ubicación y verificar que la información permanezca visible cuando una imagen no esté disponible. | 2 | Bonifacio Jaramillo, Samuel Jesus | To Do |
| US-47 | Sección How It Works | Implementar una sección que explique los pasos para registrarse, utilizar y devolver un vehículo. | 4 | Seminario Castillo, Diego Vicente | To Do |
| US-48 | Sección de Planes y Tarifas | Implementar la visualización de los planes disponibles, incluyendo precios, duración, beneficios y condiciones. | 4 | Castro Pariona, Jefferson Ernesto | To Do |
| US-55 | Plan Corporativo B2B | Incorporar el Business Plan con sus condiciones, beneficios y un medio de contacto para consultas empresariales. | 4 | Castro Pariona, Jefferson Ernesto | To Do |
| US-53 | Información de Contacto | Implementar la sección Contact Us con los medios de contacto y enlaces correspondientes. | 3 | Morales Sosa, Arnold Gabriel | To Do |
| US-50 | Beneficios del Servicio | Desarrollar una sección informativa sobre las ventajas de la movilidad eléctrica y la propuesta de WeRide. | 3 | Morales Sosa, Arnold Gabriel | To Do |
| US-51 | Indicadores de Impacto | Implementar la sección Our Impact con indicadores y etiquetas que distingan los datos reales de los demostrativos. | 3 | Romero Meza, Jhimy Pool | To Do |
| US-52 | Testimonios | Implementar la sección Testimonials, mostrando las experiencias de usuarios y señalando los testimonios demostrativos cuando corresponda. | 3 | Romero Meza, Jhimy Pool | To Do |
| US-48 | Verificación de Planes | Comprobar que los planes publicados muestren correctamente precios, duración y beneficios. | 2 | Castro Pariona, Jefferson Ernesto | To Do |
| US-47 | Verificación de Contenido | Comprobar que los pasos de funcionamiento del servicio se presenten en el orden correcto y sean comprensibles. | 2 | Seminario Castillo, Diego Vicente | To Do |

**Total de horas estimadas:** 34 horas.

**Total de Story Points comprometidos:** 20 SP.

---


### 5.2.2.4. Development Evidence for Sprint Review

Durante el Sprint 2 se implementaron los principales módulos de la aplicación web, incluyendo el componente de **garaje, mapa de viajes, historial de viajes, gestión de planes, integración de pagos y el archivo db.json.** Cada funcionalidad fue desarrollada y registrada en los siguientes commits y ramas, evidenciando la colaboración del equipo:

| Repository | Branch | Commit Id | Commit Message | Autor | Committed on (Date) |
|-------------|-----------------------------|-----------|-----------------------------------------------|--------------------------|----------------------|
| OpenSource-Grupo-4/Landing-Page | samuel-1 | caa30aa | feat: added garage component (pending features) | samuelbonifacio015 | 07/10/2025 |
| OpenSource-Grupo-4/Landing-Page | samuel-1 | 33a6fef | feat: added trip-map | samuelbonifacio015 | 07/10/2025 |
| OpenSource-Grupo-4/Landing-Page | samuel-1 | c885f8f | feat: added db.json | samuelbonifacio015 | 07/10/2025 |
| OpenSource-Grupo-4/Landing-Page | samuel-1 | 64615a8 | feat: plan component added | samuelbonifacio015 | 07/10/2025 |
| OpenSource-Grupo-4/Landing-Page | samuel-1 | f078e3d | feat: added trip-history component | samuelbonifacio015 | 07/10/2025 |
| OpenSource-Grupo-4/Landing-Page | jefferson | fbe7e9c | Implementation bounded-context booking | JeffersonCastroPariona | 06/10/2025 |
| OpenSource-Grupo-4/Landing-Page | diego | 38ba86c | us7,8 | DiegoSeminario | 07/10/2025 |
| OpenSource-Grupo-4/Landing-Page | feature/US-05-Map | 3d5995a | feat(Map): add map component whit marker and location user | jhimyromeromeza | 07/10/2025 |

Cada commit refleja el trabajo colaborativo y el cumplimiento de los objetivos del Sprint, asegurando la trazabilidad y transparencia en el desarrollo de **WeRide.**

**Reporte de commits:**

![CommitsSprint2](assets/chapter05/commits-2.png)

---

### 5.2.2.5. Execution Evidence for Sprint Review

En esta entrega, nos centramos en el desarrollo completo del desarrollo de la **Web Application** de WeRide.

Es por ello que se comparte las evidencias de ambos repositorios para corroborar el trabajo hecho por cada uno de los participantes.

![ExecutionEvidence](assets/chapter05/networkgraph-2.png)

---

### 5.2.2.6. Services Documentation Evidence for Sprint Review

El db.json fue creado para simular una base de datos local y facilitar el desarrollo y pruebas de la aplicación web. Este archivo contiene datos estructurados en formato JSON, representando las entidades principales del sistema: **usuarios, vehículos, reservas y planes.**

***json server:***

![db.json](assets/chapter05/json-server.png)
---

### 5.2.2.7. Software Deployment Evidence for Sprint Review

El objetivo del segundo Sprint fue el desarrollo e implementación de la Web Application. Para eso, utilizamos GitHub y GitHub Pages. El proceso del desarrollo fue el siguiente:

1. Se creó un repositorio para el desarrollo de la Web Application en GitHub. ![GithubRepoWebApp](assets/chapter05/frontend-repo.png)
2. Se creó el entorno de desarrollo con Node.js y Angular usando WebStorm como IDE. ![NodeAngular](assets/chapter05/webstorm-setup.png)
3. Se desplegó el db.json con json-server para simular una base de datos local. ![JsonServer](assets/chapter05/json-server.png)
4. Se desarrollaron los componentes usando el patrón de DDD (Domain-Driven Design) para estructurar el código. ![DDD](assets/chapter05/bounded-context.png)
5. Se desplegó el frontend en github pages para pruebas y visualización.

---

### 5.2.2.8. Team Collaboration Insights during Sprint

A continuación, se adjuntan las capturas de evidencia de los insights del repositorio del desarrollo de la Web Application para evidenciar la participación de todos los miembros:

* Insight Web Application:
  ![InsightWebApp](assets/chapter05/commits-2.png)

* Insight Report
  ![InsightR](assets/chapter05/insightR.png)

## 5.2.3. Sprint 3

<h3>5.2.3.1. Sprint Planning 3</h3>

<table>
  <tr>
    <th>Elemento</th>
    <th>Detalle</th>
  </tr>

  <tr>
    <td><strong>Sprint</strong></td>
    <td>Sprint 3 — Primera versión del backend con Java (Spring Boot) y conexión a MySQL (WeRide)</td>
  </tr>

  <tr>
    <td><strong>Sprint Planning Background</strong></td>
    <td>Sprint orientado a entregar la capa mínima de backend que soporte autenticación, gestión de vehículos y reservas; establecer conexión estable con MySQL Workbench; y preparar los bounded contexts para futuras integraciones (auth, vehicle, booking). Se prioriza robustez, pruebas básicas y scripts de inicialización de esquema.</td>
  </tr>

  <tr>
    <td><strong>Fecha</strong></td>
    <td>2025-10-27</td>
  </tr>

  <tr>
    <td><strong>Hora</strong></td>
    <td>20:00 (GMT-5)</td>
  </tr>

  <tr>
    <td><strong>Lugar</strong></td>
    <td>Reunión virtual — Google Meet</td>
  </tr>

  <tr>
    <td><strong>Preparado por</strong></td>
    <td>WeTech</td>
  </tr>

  <tr>
    <td><strong>Asistentes</strong></td>
    <td>Samuel Bonifacio, Jefferson Castro, Diego Seminario, Arnold Morales</td>
  </tr>

  <tr>
    <td><strong>Sprint n-2 Review</strong></td>
    <td>Se asignaron los bounded contexts para el backend y se iniciaron las primeras contribuciones en el repositorio; frontend consumiendo <code>db.json</code> para pruebas.</td>
  </tr>

  <tr>
    <td><strong>Sprint n-2 Retrospective</strong></td>
    <td>Buena coordinación y claridad en las tareas; pendiente mejorar cobertura de pruebas unitarias y definir pipelines CI/CD para despliegues automáticos.</td>
  </tr>

  <tr>
    <td><strong>Sprint Goal (Statement)</strong></td>
    <td>
      <strong>Our focus is on</strong> entregar la primera versión operativa del backend (servicios REST) que permita autenticación, gestión de vehículos y reservas, conectada a MySQL Workbench.<br>
      <strong>We believe it delivers</strong> la capacidad de realizar pruebas end-to-end entre frontend y backend, garantizando persistencia y consistencia básica de datos.<br>
      <strong>This will be confirmed when</strong> los endpoints de autenticación, consulta de vehículos y creación de reservas responden correctamente en el entorno de pruebas y las operaciones CRUD se verifican contra la base de datos MySQL mediante consultas y pruebas automatizadas.
    </td>
  </tr>

  <tr>
    <td><strong>User Stories (seleccionadas)</strong></td>
    <td>Ver tabla abajo (IDs, descripción y puntos).</td>
  </tr>

  <tr>
    <td><strong>Sprint 3 Velocity (forecast)</strong></td>
    <td>20 puntos</td>
  </tr>

  <tr>
    <td><strong>Sum of Story Points (commit)</strong></td>
    <td>20 puntos</td>
  </tr>
</table>

<br>

<h4>Objetivo del Sprint (versión SMART)</h4>
<p><strong>Objetivo:</strong> Entregar la primera iteración del backend en Spring Boot con conexión a MySQL que permita registro/inicio de sesión, creación y consulta de perfiles, y persistencia de reservas/vehículos para pruebas end-to-end.</p>

<ul>
  <li><strong>Específico:</strong> Endpoints de auth (registro/login), persistencia de usuario/perfil, endpoints para vehículos y reservas; scripts de inicialización de esquema en MySQL.</li>
  <li><strong>Medible:</strong> Todos los endpoints listados en las user stories pasan sus criterios de aceptación y las operaciones CRUD quedan verificadas contra MySQL.</li>
  <li><strong>Alcanzable:</strong> Basado en la capacidad del equipo y velocity estimada (20 SP).</li>
  <li><strong>Relevante:</strong> Habilita integración real con frontend y pruebas de integración para pilotos.</li>
  <li><strong>Time-bound:</strong> Entrega al cierre de Sprint 3 (1 iteración).</li>
</ul>

<hr>

<h4>User Stories seleccionadas para el Sprint 3</h4>

<table>
  <tr>
    <th>ID</th>
    <th>User Story</th>
    <th>Puntos</th>
  </tr>
  <tr>
    <td>01</td>
    <td>Como usuario quiero poder iniciar sesión o registrarme en la app para usarla diariamente.</td>
    <td>5</td>
  </tr>
  <tr>
    <td>02</td>
    <td>Como usuario, quiero introducir mi número de celular para validar mi identidad y recibir notificaciones.</td>
    <td>4</td>
  </tr>
  <tr>
    <td>03</td>
    <td>Como usuario, quiero introducir un código de verificación para validar mi identidad en la aplicación.</td>
    <td>4</td>
  </tr>
  <tr>
    <td>04</td>
    <td>Como usuario quiero poder crear un perfil para colocar mis datos.</td>
    <td>5</td>
  </tr>
  <tr>
    <td>05</td>
    <td>Como usuario quiero poder ver una pantalla principal estética que me atraiga a usar el servicio.</td>
    <td>2</td>
  </tr>
  <tr>
    <td></td>
    <td><strong>Total de puntos comprometidos:</strong></td>
    <td><strong>20</strong></td>
  </tr>
</table>

<hr>

<h4>Criterios de aceptación (ejemplos rápidos)</h4>
<ul>
  <li><strong>US-01:</strong> Registro almacena usuario en MySQL, responde 201 Created y devuelve token JWT; login valida credenciales y retorna token.</li>
  <li><strong>US-02 / US-03:</strong> Número celular guardado y proceso de verificación simulado (código) implementado; endpoints de verificación devuelven estado validado.</li>
  <li><strong>US-04:</strong> Perfil editable con campos básicos (nombre, documento, foto URL) y persistencia verificada.</li>
  <li><strong>US-05:</strong> Endpoint que provee datos para la pantalla principal (promociones/estadísticas) y respuesta &lt; 500ms en entorno de pruebas.</li>
</ul>

<h4>Riesgos identificados y mitigaciones</h4>
<ul>
  <li><strong>Riesgo:</strong> Problemas de conexión o configuración con MySQL Workbench. <strong>Mitigación:</strong> scripts de bootstrap de DB y contenedores locales (Docker Compose) para entorno reproducible.</li>
  <li><strong>Riesgo:</strong> Falta de pruebas automatizadas. <strong>Mitigación:</strong> incluir pruebas unitarias básicas y pruebas de integración que validen CRUD contra una DB de prueba.</li>
  <li><strong>Riesgo:</strong> Dependencias inseguras en librerías. <strong>Mitigación:</strong> revisar versiones y políticas de seguridad (dependabot/scan).</li>
</ul>


### 5.2.3.2. Aspect Leaders and Collaborators

| Team Member (Apellido, Nombre) | GitHub Username | Deploy de Base de Datos | Historial de Viajes | Gestión de Perfiles | Reservas | Garage |
|--------------------------------|------------------|-------------------------|---------------------|---------------------|-------|----------------------|
| Bonifacio, Samuel | samuelbonifacio015 | L | L | L | L | L |
| Castro, Jefferson | JeffersonCastroPariona | L | C | L | L | C |
| Seminario, Diego | DiegoSeminario | L | C | L | C | L |
| Romero, Jhimy | jhimyromeromeza | L | C | C | C | C |
| Morales, Arnold | Arnold-TI | L | L| L | L | C |

**L:** Leader (Líder)  
**C:** Collaborator (Colaborador)

---

### 5.2.3.3. Sprint Backlog 3

| ID | Title/Section | Description | Estimation (Hours) | Assigned To | Status |
|----|----------------|--------------|--------------------|--------------|--------|
| US21 | Registro de Usuario | Como usuario, quiero registrar una cuenta desde la aplicación para acceder a los servicios de WeRide. | 3 | Castro Pariona, Jefferson Ernesto | Done |
| US22 | Visualización de Vehículos | Como usuario, quiero visualizar los vehículos disponibles para elegir uno según mis necesidades. | 4 | Seminario Castillo, Diego Vicente | Done |
| US23 | Reserva de Vehículo | Como usuario, quiero poder reservar un vehículo seleccionando fecha y hora de uso. | 4 | Romero Meza, Jhimy Pool | Done |
| US24 | Pago en Línea | Como usuario, quiero realizar el pago de mi reserva de manera segura mediante una interfaz simple y funcional. | 5 | Morales Sosa, Arnold Gabriel | Done |
| US25 | Archivo db.json | Como desarrollador, quiero crear un archivo db.json con los datos de usuarios, vehículos y reservas para pruebas locales. | 2 | Bonifacio Jaramillo, Samuel Jesús | Done |
| US26 | Pruebas e Integración | Como equipo, queremos realizar pruebas de funcionamiento e integración del flujo completo del sistema. | 2 | Todos | Done |

---

### 5.2.3.4. Development Evidence for Sprint Review

Durante el Sprint 3 se implementaron los principales módulos del backend, incluyendo el componente de **gestión de perfiles, reservas, historial de viajes y garage de autos.** A continuación se listan los commits más relevantes registrados en el repositorio del backend durante este Sprint (captura en el panel de commits):

| Repository | Branch | Commit Id | Commit Message | Autor | Committed on (Date) |
|------------|--------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------|-----------------------|----------------------|
| OpenSource-Grupo-4/Backend-WeRide | feat/travelHistory | f7222d1 | feat(travelHistory): Add news endpoints for create TravelHistory and find TravelHistory by userId | jhimyromeromeza | 09/11/2025 |
| OpenSource-Grupo-4/Backend-WeRide | feature/profile | 6e8bd4f | feat: Implement Profile Bounded Context | Arnold-TI | 08/11/2025 |
| OpenSource-Grupo-4/Backend-WeRide | main | 69c362f | feat: implement JWT auth | samuelbonifacio015 | 29/10/2025 |
| OpenSource-Grupo-4/Backend-WeRide | main | e733cf1 | feat: added rest interfaces for iam | samuelbonifacio015 | 29/10/2025 |
| OpenSource-Grupo-4/Backend-WeRide | main | 7c22d3e | feat: added iam infrastructure | samuelbonifacio015 | 29/10/2025 |
| OpenSource-Grupo-4/Backend-WeRide | feat/booking | e3c8283 | feat(booking): update classes logic validation | JeffersonCastroPariona | 29/10/2025 |
| OpenSource-Grupo-4/Backend-WeRide | feat/booking | a60ea90 | feat(booking): implement aggregate and commands queries services | JeffersonCastroPariona | 28/10/2025 |
| OpenSource-Grupo-4/Backend-WeRide | bc/garage | 5875d27 | bc/garage | DiegoSeminario | 11/11/2025 |

Cada commit refleja el trabajo colaborativo y el cumplimiento de los objetivos del Sprint, asegurando la trazabilidad y transparencia en el desarrollo de **WeRide.**

**Reporte de commits (captura):**

![CommitsSprint3](assets/chapter05/commits-3.png)

---

### 5.2.3.5. Execution Evidence for Sprint Review

En esta entrega, nos centramos en el desarrollo completo del desarrollo de los **Web Services** de WeRide.

Es por ello que se comparte las evidencias de ambos repositorios para corroborar el trabajo hecho por cada uno de los participantes.

![ExecutionEvidence](assets/chapter05/networkgraph-backend.png)

---

### 5.2.3.6. Services Documentation Evidence for Sprint Review

Para el backend, hemos desarrollado nuestro API utilizando Java con el framework Spring Boot. Este backend se conecta a una base de datos MySQL Workbench para gestionar el inicio de sesión, gestión de perfiles, reservas, historial de viajes y garage de autos.

Para verificar que la optención de datos se realice correctamente, utilizamos Swagger UI, una herramienta que nos permite interactuar con nuestra API de manera visual y probar los diferentes endpoints que hemos creado.

*Schemas:*

![updateprofileresource](assets/chapter05/backend/updateprofileresource.png)

![profileresource](assets/chapter05/backend/profileresource.png)

![createbookingresource](assets/chapter05/backend/createbookingresource.png)

![localtime](assets/chapter05/backend/localtime.png)

![bookingresource](assets/chapter05/backend/bookingresource.png)

![signupresource](assets/chapter05/backend/signupresource.png)

![signinresource](assets/chapter05/backend/signinresource.png)

![accountResource](assets/chapter05/backend/accountresource.png)

![authenticatedaccountresource](assets/chapter05/backend/authenticatedaccountresource.png)

![createtravelhistoryresource](assets/chapter05/backend/createtravelhistoryresource.png)

![user](assets/chapter05/backend/user.png)

![registerusercomand](assets/chapter05/backend/registerusercommand.png)

![pagebookingresource](assets/chapter05/backend/pagebookingresource.png)

![pageableobject](assets/chapter05/backend/pageableobject.png)

![sortobject](assets/chapter05/backend/sortobject.png)

![travelhistoryresource](assets/chapter05/backend/travelhistoryresource.png)

![reservation](assets/chapter05/backend/reservation.png)

*Swagger:*

##### Accounts

![accounts](assets/chapter05/backend/accounts-endpoint.png)  

![accountsGet](assets/chapter05/backend/accountsGet.png)

##### Authentication

![auth](assets/chapter05/backend/auth-endpoint.png)

##### SignUp:

![authenticationPost](assets/chapter05/backend/authenticationPost.png)

##### SignIn:

![authenticationPostSignIn](assets/chapter05/backend/authenticationPostSignIn.png)

##### Auth:

![authLogin](assets/chapter05/backend/authPost.png)

![authRegister](assets/chapter05/backend/authRegister.png)

##### Reservations:

![reservations](assets/chapter05/backend/reservationsGet.png)

![reservationsPost](assets/chapter05/backend/reservationsPost.png)

![reservationsPost2](assets/chapter05/backend/reservationsPost2.png)

##### Profiles:

![profiles](assets/chapter05/backend/profiles-endpoint.png)

![profilesPut](assets/chapter05/backend/profilesPut.png)

![profilesGet](assets/chapter05/backend/profilesGet.png)

##### Bookings:

![booking](assets/chapter05/backend/bookincontroller-endpoint.png)

![bookingGet](assets/chapter05/backend/boookingGet.png)

![bookingsPost](assets/chapter05/backend/bookingsPost.png)

![bookingsDraftPost](assets/chapter05/backend/bookingsDraftPost.png)

![bookingsIdGet](assets/chapter05/backend/bookingsIdGet.png)

![bookingsDraftGet](assets/chapter05/backend/bookingsDraftGet.png)

##### Vehicles:

![vehiclesGet](assets/chapter05/backend/vehiclesGet.png)

![vehiclesPost](assets/chapter05/backend/vehiclesPost.png)

##### Travel History:

![travelhistory](assets/chapter05/backend/travelhistorycontroller-endpoint.png)

![travelhistoryGet](assets/chapter05/backend/travelhistoryGet.png)

![travelhistoryPost](assets/chapter05/backend/travelhistoryPost.png)

##### Users:

![usersGet](assets/chapter05/backend/usersGet.png)

--- 

### 5.2.3.7. Software Deployment Evidence for Sprint Review

El objetivo del tercer Sprint fue el desarrollo e implementación del Backend de la Web Application. Para eso, utilizamos GitHub. El proceso del desarrollo fue el siguiente:

1. Se creó un repositorio para el desarrollo del Backend en GitHub. ![GithubRepoBackend](assets/chapter05/backend-repo.png)
2. Se creó el entorno de desarrollo con Java(Springboot) y MySQL Workbench usando IntelliJ IDEA como IDE. ![JavaMySQL](assets/chapter05/intelliJIdea-setup.png)
3. Se desarrollaron los bounded context usando el patrón de DDD (Domain-Driven Design) para estructurar el código. ![DDDBackend](assets/chapter05/bounded-context-backend.png)
4. Se utilizó Swagger UI para documentar y probar los endpoints del API desarrollado.
5. Se desplegó el backend en un servidor local para pruebas y visualización.
   
---
   
### 5.2.3.8. Team Collaboration Insights during Sprint

A continuación, se adjuntan las capturas de evidencia de los insights del repositorio del desarrollo de los Web Services para evidenciar la participación de todos los miembros:

* Insight Web Service:
  ![InsightWebServices](assets/chapter05/commits-3.png)

* Insight Report
  ![InsightR](assets/chapter05/insightR.png)

## 5.2.4. Sprint 4
### 5.2.4.1.Sprint Planning 4.
Para el sprint 4, el equipo realizó el sprint planning meeting para la distribución de tareas y revisión de errores a corregir. El resumen se mostrará a continuación:

<table>
  <tr>
    <th>Elemento</th>
    <th>Detalle</th>
  </tr>

  <tr>
    <td><strong>Sprint</strong></td>
    <td>Sprint 4 — Integración final Frontend ↔ Backend, despliegue y mejora del informe / landing page (WeRide)</td>
  </tr>

  <tr>
    <td><strong>Sprint Planning Background</strong></td>
    <td>Sprint orientado a integrar los componentes desarrollados (frontend y backend), corregir errores críticos identificados en pruebas, completar secciones faltantes del informe y pulir la landing page para el despliegue final del piloto. Prioriza estabilidad, experiencias end-to-end y evidencia documental para entrega.</td>
  </tr>

  <tr>
    <td><strong>Fecha</strong></td>
    <td>2025-12-01</td>
  </tr>

  <tr>
    <td><strong>Hora</strong></td>
    <td>21:00 (GMT-5)</td>
  </tr>

  <tr>
    <td><strong>Lugar</strong></td>
    <td>Reunión virtual — Google Meet</td>
  </tr>

  <tr>
    <td><strong>Preparado por</strong></td>
    <td>Seminario Castillo, Diego Vicente (WeTech)</td>
  </tr>

  <tr>
    <td><strong>Asistentes (Planning Meeting)</strong></td>
    <td>Castro Pariona, Jefferson Ernesto · Bonifacio Jaramillo, Samuel Jesus · Seminario Castillo, Diego Vicente · Romero Meza, Jhimy Pool · Morales Sosa, Arnold Gabriel</td>
  </tr>

  <tr>
    <td><strong>Sprint n-3 Review (Resumen)</strong></td>
    <td>Se completó la primera versión del backend, se integró con frontend simulando <code>db.json</code> y se corrigieron la mayoría de errores reportados del frontend. Se desplegó la versión inicial en entorno de staging y se avanzó en el diseño final de la landing page.</td>
  </tr>

  <tr>
    <td><strong>Sprint n-3 Retrospective (Resumen)</strong></td>
    <td>Buena coordinación del equipo; mejora en procesos de revisión. Acciones de mejora: reforzar pruebas e2e, documentar criterios de aceptación y automatizar despliegues.</td>
  </tr>

  <tr>
    <td><strong>Sprint Goal (Statement)</strong></td>
    <td>
      <strong>Our focus is on</strong> entregar la versión integrada y estable de frontend y backend, corrigiendo errores críticos, completando las secciones faltantes del informe y refinando la landing page para el despliegue piloto.<br>
      <strong>We believe it delivers</strong> mayor confianza operativa y evidencia para presentación académica y pilotos corporativos, aumentando la probabilidad de adopción inicial.<br>
      <strong>This will be confirmed when</strong> la aplicación integrada realiza viajes simulados end-to-end, las APIs responden en staging, el informe está actualizado y validado por el equipo, y la landing page está publicada con métricas iniciales (visitas y conversiones de registro).
    </td>
  </tr>

  <tr>
    <td><strong>Sprint 4 Velocity</strong></td>
    <td>61 puntos</td>
  </tr>

  <tr>
    <td><strong>Sum of Story Points (commit)</strong></td>
    <td>61 puntos</td>
  </tr>

</table>


### 5.2.4.2. Aspect Leaders and Collaborators.

Durante este Sprint, el equipo se enfocó en el **diseño visual, maquetación y despliegue de la Landing Page** de **WeRide**, junto con la implementación inicial del soporte multilenguaje y la adaptación responsiva del sitio web.  
Para optimizar el trabajo colaborativo, se elaboró la **Matriz de Liderazgo y Colaboración (LACX)**, donde se asignan los roles de **Líder (L)** y **Colaborador (C)** en los principales aspectos del Sprint.

| **Team Member (Last Name, First Name)** | **GitHub Username**                                      | **Diseño visual y maquetación web (Frontend funcional)** | **Implementación técnica del cambio de idioma (Multilenguaje funcional)** | **Responsividad y pruebas en distintos dispositivos** | **Despliegue de la aplicación web** |
|-----------------------------------------|----------------------------------------------------------|----------------------------------------------------------|---------------------------------------------------------------------------|-------------------------------------------------------|-------------------------------------|
| **Bonifacio Jaramillo, Samuel Jesus**   | [@samuelbonifacio015](https://github.com/samuelbonifacio015) | L                                                        | C                                                                         | C                                                     | C                                   |
| **Romero Meza, Jhimy Pool**             | [@jhimyromeromeza](https://github.com/jhimyromeromeza)       | C                                                        | L                                                                         | C                                                     | C                                   |
| **Seminario Castillo ,Diego Vicente**   | [@DiegoSeminario](https://github.com/DiegoSeminario)     | C                                                        | C                                                                         | C                                                     | L                                   |
| **Morales Sosa, Arnold Gabriel**        | [@Arnold-TI](https://github.com/Arnold-TI)           | C                                                        | C                                                                         | C                                                     | L                                   |
| **Castro Pariona, Jefferson Ernesto**   | [@JeffersonCastroPariona](https://github.com/JeffersonCastroPariona)                              | C                                                        | L                                                                         | L                                                     |                                     |
### 5.2.4.3.Sprint Backlog 4.

### 5.2.4.3 Sprint Backlog — Sprint 4 (WeRide)

| ID   | Título (HU)                                | Descripción (resumen)                                                                 | Story Points | Est. (hrs) | Assigned To                                        | Status      |
|------|--------------------------------------------|----------------------------------------------------------------------------------------|:------------:|:----------:|----------------------------------------------------|-------------|
| US-01| Inicio de sesión y registro                 | Registro/login, persistencia en backend, token JWT                                    |      8       |    12      | Jefferson Castro (Frontend) / Backend support       | In Progress |
| US-02| Introducir número de celular + verificación | Guardar número, solicitar código y validar (flow SMS/sandbox)                         |      5       |     8      | Samuel Bonifacio (Backend/DevOps)                   | In Progress |
| US-04| Datos de usuario / Perfil                   | Crear/editar perfil (nombre, foto, correo) y persistencia                             |      3       |     6      | Jhimy Romero (Frontend) / Backend support           | To Do       |
| US-05| Página principal / Landing (pulido)         | Pulir UI/UX de la pantalla principal y landing (performance, CTA, tracking)           |      3       |     6      | Diego Seminario (Frontend)                          | In Progress |
| US-11| Seleccionar ubicación y ver vehículos       | Al seleccionar ubicación en mapa mostrar vehículos cercanos y detalles (realtime)     |      8       |    10      | Diego Seminario (Frontend) / Backend support        | In Progress |
| US-07| Gestión/Visualización en Garaje             | Vista Garaje con listados, detalles y filtros (tipo, batería, valoración)             |      5       |     8      | Jhimy Romero (Frontend) / Backend support          | To Do       |
| US-17| Crear una reserva                            | Reserva de vehículo: seleccionar, confirmar, bloquear vehículo y temporizador         |      8       |    10      | Jhimy Romero (Frontend) / Arnold Morales (Backend)  | To Do       |
| US-24| Pago en línea (sandbox)                      | Integración mock/sandbox Yape/Plin; registro de transacción en backend                |      8       |    12      | Arnold Morales (Backend) / Frontend support         | To Do       |
| US-19| Desbloqueo con QR / US-20 Desbloqueo app     | Flujo de desbloqueo (QR y botón app) + estado de desbloqueo en tiempo real            |      5       |     8      | Arnold Morales (Backend) / Jhimy (Frontend)        | To Do       |
| US-12| Visualización de viaje en mapa               | Mostrar trayecto en tiempo real con datos de vehículo (batería, tiempo restante)      |      3       |     6      | Jhimy Romero (Frontend) / Backend support          | To Do       |
| CI-1 | CI/CD pipeline & Deploy a staging            | Pipeline (build/test/deploy) automático a staging                                     |      3       |     8      | Samuel Bonifacio (DevOps)                           | To Do       |
| TST1 | Pruebas E2E (smoke)                          | Suite e2e mínima para flujo crítico: registro→login→reserva→pago                      |      2       |     6      | Equipo (coordinado)                                 | To Do       |
| US-25| Archivo db.json (verificar)                  | db.json ya creado; verificar migración / uso en staging                              |      0       |     3      | Samuel Bonifacio (DevOps)                           | Done        |

**Sum Story Points comprometidos (Sprint 4):** 61 SP  
**Nota:** US-25 aparece como *Done* (verificado) y no suma SP al comprometido arriba.



### 5.2.4.4.Development Evidence for Sprint Review.
| **Repository**  | **Branch**            | **Commit ID**                            | **Author**        | **Time ago** |
|-----------------|-----------------------|------------------------------------------|-------------------|--------------|
| Backend-WeRide | master                | d92fe801832a83b5b698f5b24639effd021daaf7 | samuelbonifacio015 | 1 days ago   |
| Backend-WeRide  | Arnold                | 6e8bd4fc9fa6ef5ad2faf2109d06f411ba538402 | Arnold-TI         | 1 days ago   |
| Backend-WeRide  | feature/garage        | 5875d271c3a5cbbdeb171e9f6cabbe8d3c95f24c | DiegoSeminario    | 1 days ago   |
| Backend-WeRide  | feature/travelhistory | f7222d1cf6576893ce94db44932de35a96058eae | jhimyromeromeza| 14 days ago  |
| Backend-WeRide | jefferson             | e3c8283af91b64fd807e18d1bfd90f27fa7fd04b | JeffersonCastroPariona   | 1 days ago   |
| Backend-WeRide  | samuel                | bfd7ddf55775bc30cdd1eb003c869e8ec897045b | samuelbonifacio   | 6 days ago   |
| Backend-WeRide  | develop               | 538a2e9a51d6fe0d2a8c95d429a24bbeb598237f | samuelbonifacio015| 1 days ago   |


<!-- ========================= -->
<!-- 5.2.4.5 Execution Evidence -->
<!-- ========================= -->
<h3 id="5-2-4-5">5.2.4.5. Execution Evidence for Sprint Review</h3>

En el Sprint 4 se completó la integración final entre Frontend y Backend, se corrigieron errores críticos identificados en pruebas de staging, se pulió la landing page y se realizó el despliegue del backend en Render con base de datos MySQL en Aiven. Las funcionalidades validadas end-to-end incluyen: registro/login con JWT, visualización de vehículos, flujo de reserva y ejecución de viajes simulados. Se generaron evidencias visuales (capturas) y un video de demostración que muestra la navegación y los flujos principales.</p>

<h4>Principales logros</h4>
<ul>
  <li>Integración Frontend ↔ Backend funcionando en entorno de staging y ambiente desplegado en Render.</li>
  <li>Corrección de errores críticos y mejoras de rendimiento en endpoints clave.</li>
  <li>Landing page actualizada y publicada con métricas iniciales de navegación.</li>
  <li>Validación de flujos: onboarding (registro/login), reserva, inicio/fin de viaje, historial de trips.</li>
</ul>

<h4>Capturas (incluir en informe)</h4>
<ul>
  <li><strong>Screenshot 1:</strong> Página de login/registro — <img src="./assets/1.png"/></li>
  <li><strong>Screenshot 2:</strong> Vista de mapa con vehículos simulados — <img src="./assets/2.png"/></li>
  <li><strong>Screenshot 3:</strong> Flujo de reserva (confirmación) — <img src="./assets/4.png"/></li>
  <li><strong>Screenshot 4:</strong> Historial de viajes (trip history) —<img src="./assets/3.png"/></li>
</ul>

<hr>

<!-- =================================== -->
<!-- 5.2.4.6 Services Documentation -->
<!-- =================================== -->
### 5.2.4.6. Services Documentation Evidence for Sprint Review

La documentación del RESTful API de WeRide se genera automáticamente con **OpenAPI (springdoc-openapi)** a partir de los controllers del backend y se publica mediante **Swagger UI**.

- **Swagger UI:** `https://backend-weride-2wpb.onrender.com/swagger-ui/index.html`
- **Especificación OpenAPI (JSON):** `https://backend-weride-2wpb.onrender.com/v3/api-docs`
- **Repositorio:** https://github.com/OpenSource-Grupo-4/Backend-WeRide

**Seguridad:** los endpoints de `/api/v1/authentication/**`, `/health` y Swagger son públicos. El resto requiere el header `Authorization: Bearer <token>` (JWT obtenido en `sign-in`).

#### Resumen de endpoints (base: `/api/v1`)

| Grupo | Endpoint | Método | Acción |
|---|---|---|---|
| Authentication | `/authentication/sign-up` | POST | Registrar una cuenta |
| Authentication | `/authentication/sign-in` | POST | Iniciar sesión y obtener JWT |
| Accounts | `/accounts/{accountId}` | GET | Consultar una cuenta |
| Profiles | `/profiles` | POST | Crear perfil |
| Profiles | `/profiles/me` | GET, PUT | Consultar / actualizar el perfil propio |
| Profiles | `/profiles/{id}` | GET | Consultar un perfil |
| Vehicles | `/vehicles` | POST, GET | Crear / listar vehículos |
| Vehicles | `/vehicles/{id}` | GET, PUT, DELETE | Consultar / actualizar / eliminar |
| Plans | `/plans` | POST, GET | Crear / listar planes |
| Plans | `/plans/{id}` | GET, PUT, DELETE | Consultar / actualizar / eliminar |
| Bookings | `/bookings` | POST, GET | Crear / listar reservas |
| Bookings | `/bookings/draft` | POST | Crear borrador de reserva |
| Bookings | `/bookings/drafts` | GET | Listar borradores |
| Bookings | `/bookings/draft/{draftId}` | DELETE | Eliminar borrador |
| Bookings | `/bookings/{id}` | GET, PATCH, PUT, DELETE | Consultar / actualizar / eliminar |
| Bookings | `/bookings/vehicle/{vehicleId}` | GET | Reservas por vehículo |
| Bookings | `/bookings/status/{status}` | GET | Reservas por estado |
| Bookings | `/bookings/user/{userId}` | GET | Reservas por usuario |
| Bookings | `/bookings/user/{userId}/pending` | GET | Reservas pendientes del usuario |
| Bookings | `/bookings/user/{userId}/completed` | GET | Reservas completadas del usuario |
| Trips | `/trips` | POST, GET | Crear / listar viajes |
| Trips | `/trips/{id}` | GET, PATCH, DELETE | Consultar / actualizar / eliminar |
| Travel History | `/travel-history` | POST, GET | Registrar / listar historial |
| Travel History | `/travel-history/me` | GET | Historial del usuario autenticado |
| Travel History | `/travel-history/{userId}` | GET | Historial por usuario |
| Travel History | `/travel-history/{id}` | PUT | Actualizar un registro |
| Notifications | `/notifications` | POST, GET | Crear / listar notificaciones |
| Notifications | `/notifications/{notificationId}` | GET, PATCH, DELETE | Consultar / actualizar / eliminar |
| Notifications | `/notifications/{notificationId}/read` | PATCH | Marcar como leída |
| Location | `/location` | POST, GET | Crear / listar ubicaciones |
| Location | `/location/{id}` | GET, PUT, PATCH, DELETE | Consultar / actualizar / eliminar |
| Unlock Requests | `/unlockRequests` | POST, GET | Crear / listar solicitudes de desbloqueo |
| Unlock Requests | `/unlockRequests/{id}` | GET, PATCH, DELETE | Consultar / actualizar / eliminar |
| Health | `/health` (sin prefijo `/api/v1`) | GET | Estado del servicio |

#### Ejemplos de request / response

**POST `/api/v1/authentication/sign-up`** (público)

```json
// Request
{ "username": "usuario1", "password": "Weride2026!" }
// Response 201 Created
{ "id": 1, "username": "usuario1" }
```
Respuesta `400 Bad Request` si el username/password están vacíos o la cuenta no puede crearse.

**POST `/api/v1/authentication/sign-in`** (público)

```json
// Request
{ "username": "usuario1", "password": "Weride2026!" }
// Response 200 OK
{ "id": 1, "token": "<JWT>", "profileId": 1 }
```
Respuesta `404 Not Found` si las credenciales no corresponden a una cuenta.

**POST `/api/v1/vehicles`** (requiere Bearer token)

```json
// Request
{ "brand": "Tesla", "model": "Model 3", "year": 2023, "type": "car",
  "pricePerMinute": 0.5, "status": "available" }
// Response 201 Created
{ "id": "1", "brand": "Tesla", "model": "Model 3", "year": 2023, "type": "car",
  "status": "available", "pricePerMinute": 0.5, "...": "demás campos del VehicleResource" }
```

**GET `/api/v1/vehicles`** → `200 OK` con un arreglo de `VehicleResource`.
**GET `/api/v1/vehicles/{id}`** → `200 OK` o `404 Not Found`.
**PUT `/api/v1/vehicles/{id}`** → `200 OK` con el vehículo actualizado, o `404`.
**DELETE `/api/v1/vehicles/{id}`** → `204 No Content`, o `404`.

> Para el resto de grupos (Plans, Bookings, Trips, etc.) los esquemas completos de request/response están disponibles en Swagger UI.

#### Despliegue del servicio

El backend (Spring Boot, empaquetado con el `Dockerfile` del repositorio) se despliega como **Web Service en Render** (plan Free, runtime Docker) y utiliza una base de datos **MySQL 8 administrada en Aiven**. La configuración sensible (URL, usuario y contraseña de la base de datos, `JWT_SECRET`) se inyecta mediante variables de entorno de Render y no se almacena en el repositorio. Al iniciar, Hibernate crea el esquema (`ddl-auto=update`) y se cargan datos demo (vehículos y planes).

- **URL pública del API:** https://backend-weride-2wpb.onrender.com
- **Swagger UI:** https://backend-weride-2wpb.onrender.com/swagger-ui/index.html

> Nota: al usar el plan gratuito de Render, el servicio entra en reposo tras un periodo de inactividad; la primera petición puede tardar cerca de un minuto en responder.

#### Evidencia

**Figura 5.X.** Swagger UI del API de WeRide desplegado en Render, con los grupos de endpoints documentados.

![Swagger UI desplegado](assets/chapter05/swagger-overview.png)

**Figura 5.X+1.** Ejecución de `POST /api/v1/authentication/sign-up` en el servicio desplegado (respuesta 201 Created).

![Sign-up 201](assets/chapter05/sign-up-201.png)

**Figura 5.X+2.** Ejecución de `POST /api/v1/authentication/sign-in` (respuesta 200 OK con JWT).

![Sign-in 200](assets/chapter05/sign-in-200.png)

**Figura 5.X+3.** Servicio `backend-weride` en estado *Live* en el dashboard de Render.

![Render Live](assets/chapter05/render-live.png)


<!-- ============================== -->
<!-- 5.2.4.7 Software Deployment Evidence -->
<!-- ============================== -->
<h3 id="5-2-4-7">5.2.4.7. Software Deployment Evidence for Sprint Review</h3>

<p>El backend de WeRide (Spring Boot, empaquetado con el <code>Dockerfile</code> del repositorio) se desplegó como <strong>Web Service en Render</strong> (plan Free, runtime Docker), conectado a una base de datos <strong>MySQL 8 administrada en Aiven</strong>. El despliegue se realiza directamente desde el repositorio de código en GitHub (rama <code>master</code>), por lo que cada cambio puede volver a desplegarse desde el sistema de control de versiones.</p>

<h4>Resumen del proceso de despliegue</h4>
<ol>
  <li>Creación de la base de datos MySQL 8 en Aiven y obtención de sus datos de conexión (host, puerto, usuario, contraseña, base <code>defaultdb</code>, SSL requerido).</li>
  <li>Creación de un Web Service en Render conectado al repositorio de GitHub, con runtime Docker y plan Free.</li>
  <li>Configuración de variables de entorno en Render: <code>SPRING_DATASOURCE_URL</code>, <code>SPRING_DATASOURCE_USERNAME</code>, <code>SPRING_DATASOURCE_PASSWORD</code>, <code>JWT_SECRET</code>, <code>PORT</code> y <code>JAVA_TOOL_OPTIONS</code> (límite de memoria de la JVM). Ningún secreto se almacena en el repositorio.</li>
  <li>Build de la imagen con el Dockerfile (Maven + JDK) y arranque del servicio. Hibernate crea el esquema en MySQL (<code>ddl-auto=update</code>) y se cargan datos demo (vehículos y planes).</li>
  <li>Verificación: el servicio queda en estado <em>Live</em>, Swagger UI responde y los endpoints de autenticación (<code>sign-up</code> / <code>sign-in</code>) devuelven 201 y 200 respectivamente.</li>
</ol>

<h4>Configuración utilizada</h4>
<table border="1" cellpadding="6" cellspacing="0">
  <thead><tr><th>Componente</th><th>Servicio</th><th>Detalle</th></tr></thead>
  <tbody>
    <tr><td>Backend</td><td>Render (Web Service, Docker, Free)</td><td>https://backend-weride-2wpb.onrender.com</td></tr>
    <tr><td>Base de datos</td><td>Aiven for MySQL 8</td><td>Conexión con SSL requerido, base <code>defaultdb</code></td></tr>
    <tr><td>Documentación</td><td>Swagger UI (springdoc-openapi)</td><td>https://backend-weride-2wpb.onrender.com/swagger-ui/index.html</td></tr>
  </tbody>
</table>

<p><em>Nota:</em> al usar el plan gratuito de Render, el servicio entra en reposo tras un periodo de inactividad y la primera petición puede tardar cerca de un minuto.</p>

<p>Las evidencias (Swagger UI, ejecución de sign-up/sign-in y estado Live del servicio) se encuentran en la sección 5.2.4.6.</p>

<!-- ================================== -->
<!-- 5.2.4.8 Team Collaboration Insights -->
<!-- ================================== -->
<h3 id="5-2-4-8">5.2.4.8. Team Collaboration Insights during Sprint</h3>

El equipo ejecutó actividades coordinadas para entregar la integración y despliegue final. Se trabajó con GitHub (issues, PRs, branches), reuniones diarias de seguimiento (standups), revisión de código y pruebas colaborativas en staging y producción. A continuación se presentan los principales insights y métricas a documentar en el informe.</p>

<h4>Prácticas y procesos aplicados</h4>
<ul>
  <li><strong>Branching:</strong> flujo git feature/ → PR → review → main → deploy (Jenkins).</li>
  <li><strong>Code Review:</strong> todas las PRs requerían al menos 1 revisor y checklist de QA (tests, lint, documentación de endpoints).</li>
  <li><strong>Gestión de tareas:</strong> backlog y tablero Kanban (GitHub Projects / Trello) con estados: To Do / In Progress / Code Review / QA / Done.</li>
  <li><strong>Comunicación:</strong> reuniones de planificación y retro en Google Meet; coordinación diaria en canal de Discord/Slack.</li>
  <li><strong>Testing colaborativo:</strong> sesiones de QA donde distintos miembros ejecutaron pruebas end-to-end y reportaron issues en GitHub Issues.</li>
</ul>


<h4>Evidencias</h4>
<ul>
  <li>Captura: gráfico de contributions por miembro (GitHub Insights / Contributors).</li>
  <img src="./assets//chapter05/commits.png">
  <img src="./assets//chapter05/commits-2.png">
  
</ul>

## 5.2.5. Acuerdo de Servicio - SaaS (Terms and Conditions)

El siguiente acuerdo de servicio rige el uso de la plataforma **WeRide** por parte de los usuarios registrados (conductores/arrendatarios de vehículos de micromovilidad eléctrica).

**1. Aceptación de los Términos.** Al registrarse y utilizar la plataforma WeRide (landing page, aplicación web y servicios backend asociados), el usuario acepta íntegramente los presentes Términos y Condiciones. El uso continuado del servicio implica la aceptación de cualquier actualización posterior de este acuerdo.

**2. Descripción del Servicio.** WeRide es una plataforma SaaS que conecta a usuarios con vehículos de micromovilidad eléctrica (bicicletas y scooters) disponibles para alquiler de corto plazo, permitiendo la búsqueda, reserva, desbloqueo y pago del servicio a través de la aplicación web.

**3. Registro de Usuario.** El usuario debe proporcionar información veraz y actualizada durante el proceso de registro (nombre, correo electrónico, método de pago). El usuario es responsable de mantener la confidencialidad de sus credenciales de acceso.

**4. Uso del Servicio.** El usuario se compromete a utilizar los vehículos de forma responsable, respetando las normas de tránsito vigentes y las condiciones de uso indicadas en la aplicación. Queda prohibido el uso del vehículo para fines distintos al traslado personal o su cesión a terceros no registrados.

**5. Tarifas y Pagos.** Las tarifas aplicables (por tiempo de uso, plan o membresía) se muestran en la aplicación antes de confirmar cada reserva. Los cobros se procesan a través del método de pago registrado por el usuario al momento de finalizar cada viaje.

**6. Responsabilidad y Seguridad.** WeRide no se hace responsable por daños derivados del uso indebido del vehículo o el incumplimiento de las normas de tránsito por parte del usuario. El usuario es responsable de reportar cualquier desperfecto del vehículo antes de iniciar su uso.

**7. Privacidad de Datos.** El tratamiento de los datos personales del usuario se rige conforme a la Ley N° 29733 - Ley de Protección de Datos Personales del Perú. WeRide no comparte la información personal de sus usuarios con terceros sin su consentimiento, salvo requerimiento legal.

**8. Cancelaciones y Reembolsos.** [Pendiente: política de cancelación a definir por el equipo]

**9. Modificaciones del Servicio.** WeRide se reserva el derecho de modificar, suspender o descontinuar funcionalidades del servicio, notificando a los usuarios con antelación razonable cuando el cambio afecte sus condiciones de uso.

**10. Legislación Aplicable.** Este acuerdo se rige por las leyes de la República del Perú. Cualquier controversia derivada de su interpretación o cumplimiento será resuelta conforme a la legislación peruana vigente.

## 5.3 Validation Interviews

### 5.3.1 Diseño de Entrevistas

**Segmento 1: Universitarios y Jóvenes Profesionales (B2C)**

**Preguntas principales (Landing Page):**

- "¿Qué entiendes que ofrece WeRide al ver la landing page?"
  
- "¿Cuál es el elemento que más te llama la atención o te genera confianza? (ej. precios, testimonios, método de pago)"
  
- "¿Qué información te falta para sentirte seguro al registrarte?"
  
- "¿Qué cambiarías en el diseño o en el copy para que la propuesta sea más clara?"

- "¿El llamado a la acción (CTA) es claro y te invita a registrarte o saber más?"
  
- "¿Las imágenes y gráficos reflejan la experiencia real del servicio?"

- "¿Confías en las formas de pago mostradas en la landing? ¿Por qué sí/no?"
  
- "¿La landing carga rápido y se ve bien en tu dispositivo móvil?"
  
**Preguntas principales (Frontend Web Application):**

- "Si elegiste 'Continuar como invitado', ¿te quedó claro qué funcionalidades tendrías disponibles sin registrarte?"

- "Al llegar a WeRide por primera vez, ¿qué impresión te causó la página de inicio? ¿Te resultó clara la propuesta de valor?"

- "Después de acceder, ¿te resultó intuitivo entender cómo navegar por la aplicación? ¿Qué fue lo primero que intentaste hacer?"

- "Si tuvieras que buscar el historial de tus viajes anteriores, ¿dónde buscarías primero? ¿Te parece lógica esa ubicación?"
  
- "Al buscar un vehículo, ¿la información mostrada (imagen, batería, marca, disponibilidad, precio) fue suficiente para decidir?"

- "Si todos los vehículos cercanos estuvieran ocupados, ¿qué esperarías que la app te ofreciera? (notificaciones, reserva anticipada, alternativas)"
  
- "Describe el proceso de crear una reserva: ¿hubo pasos poco claros o que te generaron dudas?"
  
- "¿Qué te pareció el proceso de pago y los formularios asociados (tarjeta, selección de plan)?"
  
- "¿Hubo algún momento en que te sentiste perdido/a o no supiste qué hacer a continuación?"

**Segmento 2: Empresas y Planes Corporativos (B2B)**

**Preguntas principales (Landing Page):**
- “Al ver la landing de WeRide, ¿qué entendiste que ofrece la plataforma específicamente para empresas?”

- “¿La propuesta de valor empresarial te pareció clara o orientada más al usuario final?”

- “¿Qué elemento visual o textual te transmitió mayor confianza para un uso corporativo?”

- “¿Qué información clave te faltó para evaluar si esto es viable para tu empresa? (precios, soporte, infraestructura, contratos, SLA, mantenimiento…)”

- “¿El CTA te orientó a una solución empresarial (‘solicitar demo’, ‘agendar llamada’, etc.) o lo sentiste más de consumo público?”

- “¿Consideras que la landing diferencia bien entre los servicios B2C y B2B?”

- “¿El diseño te transmite profesionalismo suficiente para un proveedor corporativo?”

**Preguntas principales (Frontend Web Application):**
- “¿Los empleados deberían poder reservar vehículos? ¿O prefieres uso inmediato sin reserva?”

- “En una operación real, ¿cuánto antes se planifican los desplazamientos?”

- “¿Se necesitarían restricciones personalizadas (por sede, por tipo de vehículo, por horas)?”

- “Si todos los vehículos estuvieran ocupados, ¿qué solución esperas? (lista de espera, reserva prioritaria por cargo/área, flota adicional, alertas)”

- “¿Qué tipo de procesos necesitan aprobación previa?”

- “¿Qué modelo se adapta mejor a tu empresa: pago por uso, suscripción mensual, leasing de flota, tarifa fija por empleado?”

- “¿La interfaz te transmite suficiente profesionalismo para un uso corporativo?”
  
---
### 5.3.2 Registro de Entrevistas

### 5.3.2 Registro de Entrevistas

**Segmento 1: Universitarios y Jóvenes Profesionales (B2C)**

#### Entrevista 1

<div style="text-align: center; margin-bottom: 40px;">
<img src="assets/chapter05/willy.png" alt="Williams Avendaño" style="width: 500px; height: auto;" />
</div>

| Campo | Valor |
|-------|-------|
| **Nombre** | Williams Avendaño |
| **Edad** | 20 años |
| **Distrito** | Surco |
| **Institución** | Estudiante ESAN |
| **Video** | [https://www.youtube.com/watch?v=vxBR4mxMcmQ](https://www.youtube.com/watch?v=vxBR4mxMcmQ) |
| **Timing** | 00:00:00 – 00:10:44 |
| **Duración** | 10:44 |
| **Resumen** | Williams comenta que usa apps como Beat y scooters públicos para moverse. Le interesa WeRide porque ahorra tiempo y es más económico. Sugiere más información sobre cobertura. Valora que la app sea fácil de usar y que permita reservar vehículos. |
| **Características Objetivas** | iPhone 12, laptop ASUS; apps: Google Maps, Beat, Yape, WhatsApp. |
| **Características Subjetivas** | Organizado, práctico; prefiere marcas confiables (Apple, Nike); influenciado por amigos y TikTok. |

---

#### Entrevista 2

<div style="text-align: center; margin-bottom: 40px;">
<img src="assets/chapter05/cardenas.png" alt="Patrick Cárdenas" style="width: 500px; height: auto;" />
</div>

| Campo | Valor |
|-------|-------|
| **Nombre** | Patrick Cárdenas |
| **Edad** | 19 años |
| **Distrito** | Ate |
| **Institución** | Estudiante PUCP |
| **Video** | [https://www.youtube.com/watch?v=vxBR4mxMcmQ](https://www.youtube.com/watch?v=vxBR4mxMcmQ) |
| **Timing** | 00:10:45 – 00:19:15 |
| **Duración** | 8:30 |
| **Resumen** | Patrick se mueve entre casa, universidad y prácticas. Usa buses y motos por apps. Sugiere agregar un mapa de disponibilidad en tiempo real. La landing y la app le parecen claras y profesionales. |
| **Características Objetivas** | Samsung A52, laptop Lenovo; apps: Moovit, Google Maps, Uber Moto, Plin. |
| **Características Subjetivas** | Extrovertido, sociable; busca rapidez. Prefiere Samsung/Xiaomi; influido por YouTube. |

---

#### Entrevista 3

<div style="text-align: center; margin-bottom: 40px;">
<img src="assets/chapter05/correa.png" alt="Patrick Correa" style="width: 500px; height: auto;" />
</div>

| Campo | Valor |
|-------|-------|
| **Nombre** | Patrick Correa |
| **Edad** | 20 años |
| **Distrito** | San Miguel |
| **Institución** | Estudiante Universidad de Lima |
| **Video** | [https://www.youtube.com/watch?v=vxBR4mxMcmQ](https://www.youtube.com/watch?v=vxBR4mxMcmQ) |
| **Timing** | 00:19:16 – 00:47:42 |
| **Duración** | 28:22 |
| **Resumen** | Correa usa transporte público y bicicleta. Percibe WeRide como útil si opera cerca de su universidad. Entendió bien la landing, pero pide más información sobre seguridad. La app le parece intuitiva e incluso sugiere incluir tutoriales para nuevos usuarios. |
| **Características Objetivas** | iPhone XR, iPad 8th gen; apps: Google Maps, Cabify, Duolingo, Instagram. |
| **Características Subjetivas** | Tranquilo, analítico; prefiere diseños minimalistas; influido por TikTokers y creadores estudiantiles. |


**Segmento 2: Empresas y Planes Corporativos (B2B)**

#### Entrevista 1

<div style="text-align: center; margin-bottom: 40px;">
<img src="assets/chapter05/ricardo.png" alt="Ricardo Del Aguila" style="width: 500px; height: auto;" />
</div>

| Campo | Valor |
|-------|-------|
| **Nombre** | Ricardo Del Aguila |
| **Edad** | 27 años |
| **Distrito** | San Miguel |
| **Cargo** | Jefe de inmobiliaria Grupo Horc |
| **Video** | [https://www.youtube.com/watch?v=0qsQ9NOwHMc](https://www.youtube.com/watch?v=0qsQ9NOwHMc) |
| **Timing** | 00:00:00 – 00:13:14 |
| **Duración** | 13:14 |
| **Resumen** | Ricardo entiende que WeRide ofrece movilidad interna eficiente y controlable para empresas. La landing le pareció más dirigida al usuario final, pero identifica potencial corporativo. Señala que necesita información sobre SLA, costos y soporte técnico. Destaca que la interfaz del panel corporativo inspira confianza. Sugiere agregar casos de éxito y comparativas de ahorro. |
| **Características Objetivas** | Laptop Dell Latitude corporativa, iPhone 14 Pro; usa Slack, Microsoft Teams, Trello, Google Workspace; maneja dashboards a diario. |
| **Características Subjetivas** | Perfil analítico, orientado a procesos. Prefiere soluciones confiables y con respaldo técnico. Le influyen benchmarks y referencias de otras empresas del sector. |

---

#### Entrevista 2

<div style="text-align: center; margin-bottom: 40px;">
<img src="assets/chapter05/matias.png" alt="Matias Flores" style="width: 500px; height: auto;" />
</div>

| Campo | Valor |
|-------|-------|
| **Nombre** | Matias Flores Flores |
| **Edad** | 26 años |
| **Distrito** | San Isidro |
| **Cargo** | Jefe de Recursos Humanos – empresa de servicios |
| **Video** | [https://www.youtube.com/watch?v=vxBR4mxMcmQ](https://www.youtube.com/watch?v=vxBR4mxMcmQ) |
| **Timing** | 00:13:15 – 00:22:35 |
| **Duración** | 9:20 |
| **Resumen** | Matias percibe que WeRide ofrece una alternativa sostenible de movilidad para colaboradores, reduciendo tiempos muertos. Considera que la landing transmite profesionalismo, pero falta segmentación clara B2B/B2C. Requiere información sobre modelos de pago por empleado y contratos mensuales. En el frontend destaca la necesidad de restricciones por sede y roles. También menciona que valoraría flujos de aprobación por jefatura. |
| **Características Objetivas** | iPhone 13, laptop MacBook Air M1; apps: Teams, Outlook, BambooHR, Zoom; gestión constante de personal. |
| **Características Subjetivas** | Empático, orientado a bienestar laboral. Prefiere marcas con enfoque moderno y sostenible (Apple, Notion). Influenciado por tendencias de HR Tech y recomendaciones en LinkedIn. |

---

#### Entrevista 3

<div style="text-align: center; margin-bottom: 40px;">
<img src="assets/chapter05/angie.png" alt="Angie Santos" style="width: 500px; height: auto;" />
</div>

| Campo | Valor |
|-------|-------|
| **Nombre** | Angie Santos |
| **Edad** | 46 años |
| **Distrito** | Santiago de Surco |
| **Cargo** | Jefa de TI – empresa corporativa multisede |
| **Video** | [https://www.youtube.com/watch?v=vxBR4mxMcmQ](https://www.youtube.com/watch?v=vxBR4mxMcmQ) |
| **Timing** | 00:22:36 – 00:29:05 |
| **Duración** | 7:31 |
| **Resumen** | Angie entendió que WeRide puede integrarse como una solución tecnológica para movilidad interna, con trazabilidad y control. La landing le pareció visualmente sólida, pero requiere información técnica: API, integraciones, seguridad, infraestructura y tiempos de mantenimiento. En la app considera importante la disponibilidad en tiempo real y alertas automáticas. Prefiere modelos de suscripción con leasing de flota. |
| **Características Objetivas** | Laptop ThinkPad serie T, Pixel 7 Pro; apps: Azure AD, Jira, Confluence, Power BI, Google Admin; revisa métricas y KPIs a diario. |
| **Características Subjetivas** | Perfil estratégico y exigente en temas de ciberseguridad. Prefiere soluciones escalables y con soporte 24/7. Influenciada por estándares internacionales y casos de integración tecnológica. |



### 5.3.3 Evaluaciones según heuristicas

### Auditoria del Grupo 4:

**UX Heuristics & Principles Evaluation**

**Usability – Inclusive Design – Information Architecture**

**CARRERA:** Ingeniería de Software

**CURSO:** Desarrollo de Aplicaciones Open Source

**SECCIÓN:** 7380  

**PROFESORES:** Todos

**AUDITOR:** Apaza Bocanegra, Elizabeth Noelia

**CLIENTE(S):**
- Bonifacio Jaramillo, Samuel Jesus
- Castro Pariona, Jefferson Ernesto
- Morales Sosa, Arnold Gabriel
- Romero Meza, Jhimy Pool
- Seminario Castillo, Diego Vicente

**SITE o APP A EVALUAR:** WeRide

## TAREAS A EVALUAR:

El alcance de esta evaluación incluye la revisión de la usabilidad de las siguientes tareas:

1. Falta de Login en la Landing Page.
2. Funciones Inaccesibles en el login.
3. Interfaz demasiado limpia y sin distribucion clara, imagenes demasiado grandes.
4. Cards demasiado amplias, no funciona el boton de filtrado ni el de favoritos.
5. No hay datos para Bicicletas electricas.
6. No permite Cancelar Reservas.
7. No permite Guardar nuevas reservas desde Booking.
8. La seccion de viaje en ver detalles esta inactiva.
9. El boton Pagar de la seccion planes esta inactivo.
10. Botones de la barra principal como setings, user y demas estan inactivos.
11. No hay opciones de traduccion dificultan comprension de recibos.
12. Reservar vehiculo inactivo.
13. Boton de reservar en cards tambien Inactivo.
14. No permite usar el boton edit booking.

## ESCALA DE SEVERIDAD:

Los errores serán puntuados tomando en cuenta la siguiente escala de severidad

| Nivel | Descripción                                                                                                                                                                                    |
| :---: | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1     | Problema superficial: puede ser fácilmente superador por el usuario ó ocurre con muy poco frecuencia. No necesita ser arreglado a no ser que exista disponibilidad de tiempo.                  |
| 2     | Problema menor: puede ocurrir un poco más frecuentemente o es un poco más difícil de superar para el usuario. Se le debería asignar una prioridad baja resolverlo de cara al siguiente reléase |
| 3     | Problema mayor: ocurre frecuentemente o los usuarios no son capaces de resolverlos. Es importante que sean corregidos y se les debe asignar una prioridad alta.                                |
| 4     | Problema muy grave: un error de gran impacto que impide al usuario continuar con el uso de la herramienta. Es imperativo que sea corregido antes del lanzamiento.                              |

## TABLA RESUMEN:

| \#    | Problema                                                    | Escala de severidad | Heurística/Principio violada(o)                 |
| :---: | :---------------------------------------------------------- | :-----------------: | :---------------------------------------------- |
| 1	    | Falta de Login en la Landing Page	                          | 2	                  | Usability: Libertad y control del usuario       |
| 2	    | Funciones inaccesibles en el Login	                        | 3	                  | Usability: Visibilidad del estado del sistema   | 
| 3	    | Interfaz sin distribución clara; imágenes demasiado grandes	| 1	                  | Usability: Diseño estético y minimalista        |
| 4	    | Cards muy amplias; filtrado y favoritos inactivos	          | 3	                  | Usability: Libertad y control del usuario       |
| 5	    | No hay datos para Bicicletas Eléctricas	                    | 2	                  | Usability: Consistencia y estándares            |
| 6	    | No permite cancelar reservas	                              | 4	                  | Usability: Libertad y control del usuario       |
| 7	    | No se guardan nuevas reservas desde Booking	                | 4	                  | Usability: Prevención y recuperación de errores |
| 8	    | Sección “Viaje” en Ver Detalles inactiva	                  | 2	                  | Usability: Visibilidad del estado del sistema   |
| 9	    | Botón “Pagar” inactivo en la sección Planes	                | 3	                  | Usability: Libertad y control del usuario       |
| 10	  | Botones del menú superior (Settings, User, etc.) inactivos	| 2	                  | Usability: Visibilidad del estado del sistema   |
| 11	  | No hay traducción; dificulta comprensión de recibos	        | 1	                  | Usability: Consistencia y estándares            |
| 12	  | Función “Reservar vehículo” inactiva	                      | 4	                  | Usability: Prevención de errores                |
| 13	  | Botón reservar en las cards inactivo	                      | 3	                  | Usability: Libertad y control del usuario       |
| 14	  | Botón “Edit Booking” no funciona	                          | 3	                  | Usability: Flexibilidad y eficiencia de uso     |

## DESCRIPCIÓN DE PROBLEMAS:

## OBSERVACIÓN 1: Falta de Login en la Landing Page

- **Severidad:** 2. Heurística violada: Usabilidad – Libertad y control del usuario
- **Problema:** La Landing Page no ofrece un acceso visible hacia la pantalla de Login. El usuario no tiene una ruta clara para ingresar al sistema, generando confusión y aumentando la tasa de abandono.
- **Recomendación:** Agregar un botón visible (“Iniciar Sesión”, “Ir al Panel”), ubicado en el header o hero principal.

<p align="center">
    <img src="assets/chapter05/auditoria/heuristicas_1.jpeg" alt="heuristicas_1"/>    
</p>

## OBSERVACIÓN 2: Funciones inaccesibles en el Login

- **Severidad:** 3. Heurística violada: Usabilidad – Visibilidad del estado del sistema
- **Problema:** Algunas funciones de la pantalla de Login no responden o no muestran retroalimentación, como recuperación de contraseña o creación de cuenta. El usuario queda sin información sobre fallas.
- **Recomendación:** Habilitar todos los botones y agregar mensajes de feedback claros (error, éxito, pasos a seguir).

<p align="center">
    <img src="assets/chapter05/auditoria/heuristicas_2.jpeg" alt="heuristicas_2"/>    
</p>


## OBSERVACIÓN 3: Interfaz demasiado limpia, sin distribución clara e imágenes muy grandes

- **Severidad:** 1. Heurística violada: Usabilidad – Diseño estético y minimalista
- **Problema:** La interfaz presenta espacios vacíos extensos y elementos demasiado grandes, lo que dificulta encontrar las funciones principales.
- **Recomendación:** Redistribuir el layout usando jerarquía visual, reducir el tamaño de imágenes y reforzar la navegación.

<p align="center">
    <img src="assets/chapter05/auditoria/heuristicas_3.jpeg" alt="heuristicas_3"/>    
</p>

## OBSERVACIÓN 4: Cards demasiado amplias; botones de filtrado y favoritos no funcionan

- **Severidad:** 3. Heurística violada: Usabilidad – Libertad y control del usuario
- **Problema:** Las cards ocupan demasiado espacio y los botones clave no funcionan, afectando directamente el flujo de selección de vehículos.
- **Recomendación:** Optimizar dimensiones, activar funcionalidad de filtros, favoritos y feedback visual.

<p align="center">
    <img src="assets/chapter05/auditoria/heuristicas_4.jpeg" alt="heuristicas_4"/>    
</p>

## OBSERVACIÓN 5: No hay datos para Bicicletas eléctricas

- **Severidad:** 2. Heurística violada: Usabilidad – Consistencia y estándares
- **Problema:** La sección aparece vacía, lo que genera una experiencia inconsistente frente a otras categorías que sí muestran información.
- **Recomendación:** Cargar datos por defecto, mostrar placeholders o indicar que “Pronto habrá disponibilidad”.

<p align="center">
    <img src="assets/chapter05/auditoria/heuristicas_5.jpeg" alt="heuristicas_5"/>    
</p>

## OBSERVACIÓN 6: No permite Cancelar Reservas

- **Severidad:** 4. Heurística violada: Usabilidad – Libertad y control del usuario
- **Problema:** Los usuarios no pueden cancelar sus reservas, bloqueando su flujo y generando frustración.
- **Recomendación:** Incorporar botón “Cancelar reserva” con confirmación de acción.

<p align="center">
    <img src="assets/chapter05/auditoria/heuristicas_6.jpeg" alt="heuristicas_6"/>    
</p>

## OBSERVACIÓN 7: No permite guardar nuevas reservas desde Booking

- **Severidad: 4**. Heurística violada: Usabilidad – Prevención y recuperación de errores
- **Problema:** El flujo de Booking falla al guardar una nueva reserva, interrumpiendo una función crítica.
- **Recomendación:** Corregir el flujo técnico y añadir mensajes que indiquen causa del error y pasos sugeridos.

<p align="center">
    <img src="assets/chapter05/auditoria/heuristicas_7.jpeg" alt="heuristicas_7"/>    
</p>

## OBSERVACIÓN 8: La sección “Viaje” en Ver Detalles está inactiva

- **Severidad:** 2. Heurística violada: Usabilidad – Visibilidad del estado del sistema
- **Problema:** El panel “Viaje” no despliega información ni responde a la interacción. El usuario no entiende si es temporal, un error o falta de permisos.
- **Recomendación:** Activar el componente o mostrar un mensaje informativo (“Función en desarrollo”, “No hay información disponible”).

<p align="center">
    <img src="assets/chapter05/auditoria/heuristicas_8.jpeg" alt="heuristicas_8"/>    
</p>

## OBSERVACIÓN 9: El botón “Pagar” de la sección Planes está inactivo

- **Severidad:** 3. Heurística violada: Usabilidad – Libertad y control del usuario
- **Problema:** El usuario no puede completar el pago de un plan, bloqueando una acción central del modelo de negocio.
- **Recomendación:** Activar el botón, conectar el flujo a la pasarela de pago y agregar validaciones previas.

<p align="center">
    <img src="assets/chapter05/auditoria/heuristicas_9.jpeg" alt="heuristicas_9"/>    
</p>

## OBSERVACIÓN 10: Botones como Settings y User en la barra principal están inactivos

- **Severidad:** 2. Heurística violada: Usabilidad – Visibilidad del estado del sistema
- **Problema:** Los accesos principales no ejecutan acción alguna, lo que genera percepción de sistema incompleto o fallido.
- **Recomendación:** Implementar navegación interna o, al menos, mensajes temporales de “módulo en construcción”.

<p align="center">
    <img src="assets/chapter05/auditoria/heuristicas_10.jpeg" alt="heuristicas_10"/>    
</p>

## OBSERVACIÓN 11: No hay opciones de traducción y dificulta la comprensión de recibos

- **Severidad:** 1. Heurística violada: Usabilidad – Consistencia y estándares
- **Problema:** El contenido de recibos y pantallas clave está solo en un idioma, dificultando la comprensión para usuarios que no lo manejan.
- **Recomendación:** Integrar sistema de internacionalización (i18n) y traducciones completas.

<p align="center">
    <img src="assets/chapter05/auditoria/heuristicas_11.jpeg" alt="heuristicas_11"/>    
</p>

## OBSERVACIÓN 12: Reservar vehículo está inactivo

- **Severidad:** 4. Heurística violada: Usabilidad – Prevención de errores
- **Problema:** Al intentar reservar un vehículo, el botón o acción no funciona. Esto afecta directamente la funcionalidad principal del sistema.
- **Recomendación:** Habilitar el botón, validar datos y mostrar confirmación de reserva exitosa.

<p align="center">
    <img src="assets/chapter05/auditoria/heuristicas_12.jpeg" alt="heuristicas_12"/>    
</p>

## OBSERVACIÓN 13: Botón de reservar dentro de las cards también está inactivo

- **Severidad:** 3. Heurística violada: Usabilidad – Libertad y control del usuario
- **Problema:** El usuario no puede reservar desde la vista de cards, obligándolo a pasos adicionales o impidiendo continuar.
- **Recomendación:** Activar interacción, añadir feedback visual y redirigir al flujo de Booking.

<p align="center">
    <img src="assets/chapter05/auditoria/heuristicas_13.jpeg" alt="heuristicas_13"/>    
</p>

## OBSERVACIÓN 14: No permite usar el botón “Edit Booking”

- **Severidad:** 3. Heurística violada: Usabilidad – Flexibilidad y eficiencia de uso
- **Problema:** El botón para editar una reserva no responde, y el usuario no puede modificar fechas, horarios o vehículo seleccionado.
- **Recomendación:** Implementar formulario editable, mensajes de validación y confirmación de cambios.

<p align="center">
    <img src="assets/chapter05/auditoria/heuristicas_14.jpeg" alt="heuristicas_14"/>    
</p>

---

## 5.4. Video About The Product
<img src="assets/chapter05/about-the-product.png" alt="Imagen Entrevistado" width="90%" style="text-align: center;"/>

<a href="https://www.youtube.com/watch?v=UVP-NVpaT6Y" target="_blank" rel="noopener">Ver Video del Producto</a>

# Capítulo VI: Product Verification & Validation  

La verificación y validación del producto **WeRide** tiene como finalidad comprobar que los componentes implementados cumplen con los requisitos funcionales definidos para la gestión de cuentas de usuario y la administración de planes. Para ello, se establece una estrategia de pruebas organizada en cuatro niveles: pruebas unitarias, pruebas de integración, pruebas basadas en comportamiento (BDD) y pruebas de sistema.

En esta etapa, el alcance de las pruebas comprende dos *bounded contexts* del backend: **IAM (Identity and Access Management)** y **Plans**. El *bounded context* IAM gestiona el registro de cuentas y la autenticación de usuarios mediante credenciales, mientras que Plans permite crear, actualizar y eliminar planes disponibles en la plataforma.

Las pruebas unitarias se implementan utilizando **JUnit 5** y **Mockito**, lo que permite verificar la lógica de los servicios de aplicación de manera aislada. Para las pruebas de integración y de sistema, se considera la interacción entre los componentes de la aplicación, los endpoints REST y la persistencia de datos en la base de datos. Los escenarios BDD permiten especificar el comportamiento esperado de las funcionalidades mediante criterios comprensibles para los desarrolladores y los responsables del producto. La ejecución y los resultados de cada prueba se registran para demostrar el cumplimiento de los criterios de aceptación correspondientes.  

## 6.1. Testing Suites & Validation  

La verificación y validación del producto **WeRide** tiene como finalidad comprobar que los componentes implementados cumplen con los requisitos funcionales definidos para la gestión de cuentas de usuario y la administración de planes. Para ello, se establece una estrategia de pruebas organizada en cuatro niveles: pruebas unitarias, pruebas de integración, pruebas basadas en comportamiento (BDD) y pruebas de sistema.

En esta etapa, el alcance de las pruebas comprende dos *bounded contexts* del backend: **IAM (Identity and Access Management)** y **Plans*. El *bounded context* IAM gestiona el registro de cuentas y la autenticación de usuarios mediante credenciales, mientras que Plans permite crear, actualizar y eliminar planes disponibles en la plataforma.

Las pruebas unitarias se implementan utilizando **JUnit 5** y **Mockito**, lo que permite verificar la lógica de los servicios de aplicación de manera aislada. Para las pruebas de integración y de sistema, se considera la interacción entre los componentes de la aplicación, los endpoints REST y la persistencia de datos en la base de datos. Los escenarios BDD permiten especificar el comportamiento esperado de las funcionalidades mediante criterios comprensibles para los desarrolladores y los responsables del producto. La ejecución y los resultados de cada prueba se registran para demostrar el cumplimiento de los criterios de aceptación correspondientes.



### 6.1.1. Core Entities Unit Tests.

Las pruebas unitarias tienen como objetivo verificar el comportamiento de los servicios de aplicación de los *bounded contexts* IAM y Plans de manera independiente de la base de datos y de otros componentes externos. Para ello, se emplean objetos simulados (*mocks*) que permiten controlar las respuestas de las dependencias y comprobar los resultados de cada operación.

Se utiliza el patrón **Arrange–Act–Assert (AAA)**, que organiza cada prueba en tres etapas: preparación de los datos y dependencias, ejecución del método evaluado y validación del resultado obtenido.

#### **A. Pruebas unitarias del bounded context IAM**

El servicio `AccountCommandServiceImpl` concentra las operaciones de registro e inicio de sesión. Para el registro, verifica la existencia previa del nombre de usuario, aplica el servicio de *hashing* a la contraseña y coordina la creación de la cuenta y su perfil asociado. Para el inicio de sesión, verifica las credenciales y solicita la generación del token de autenticación cuando estas son válidas.

Las dependencias `AccountRepository`, `HashingService`, `TokenService` y `ProfileContextFacade` se simulan mediante **Mockito** para evaluar la lógica del servicio sin requerir una conexión real a la base de datos.

**Tabla 6.1\. Casos de prueba unitarios del bounded context IAM**

| ID Caso de prueba  | Escenario                                       | Resultado esperado                                                                                                                                                        |
| ------------------ | ----------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **IAM-UT-01** | Inicio de sesión con usuario inexistente   | Se envían credenciales de un usuario que no está registrado. El servicio lanza una excepción con el mensaje `User not found`.                                        |
| **IAM-UT-02** | Inicio de sesión con contraseña incorrecta | El usuario existe, pero la contraseña no coincide con el hash almacenado. El servicio lanza una excepción con el mensaje `Invalid credentials` y no genera un token. |
| **IAM-UT-03** | Inicio de sesión exitoso                   | El usuario existe y la contraseña es válida. El servicio devuelve la cuenta y el token JWT generado[9].                                                                 |
| **IAM-UT-04** | Registro con nombre de usuario existente   | Se intenta registrar una cuenta cuyo nombre de usuario ya está registrado. El servicio lanza una excepción con el mensaje `User already exists`.                     |
| **IAM-UT-05** | Registro exitoso                           | Se registra una cuenta nueva y se crea el perfil asociado. El servicio devuelve la cuenta creada y actualizada con su identificador de perfil.                       |

*Fuente: Elaboración propia.*

Los casos `IAM-UT-01`, `IAM-UT-02` e `IAM-UT-03` permiten verificar los principales escenarios del inicio de sesión. Los casos `IAM-UT-04` e `IAM-UT-05` evalúan el comportamiento del registro, incluyendo la prevención de usuarios duplicados y la coordinación con el *bounded context* Profile.


![localtime](assets/chapter05/unitTest/unit-test-iam.png)


#### **B. Pruebas unitarias del bounded context Plans**

El servicio `PlanCommandServiceImpl` administra las operaciones principales de los planes mediante el repositorio `PlanRepository`. Sus métodos permiten crear un plan, eliminarlo a partir de su identificador y actualizar sus datos cuando el registro existe. Para las pruebas unitarias, se simula el repositorio y se verifica tanto el resultado de cada operación como las llamadas realizadas por el servicio.

**Tabla 6.2\. Casos de prueba unitarios del bounded context Plans**

| ID Caso de prueba   | Escenario                                  | Resultado esperado                                                                                                                                          |
| ------------------- | ------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **PLN-UT-01** | Creación de un plan                  | Se envía un comando válido para crear un plan. El servicio guarda el plan y devuelve el objeto persistido.                                            |
| **PLN-UT-02** | Eliminación de un plan existente     | Se solicita eliminar un plan cuyo identificador existe. El servicio elimina el plan y devuelve `true`.                                                |
| **PLN-UT-03** | Eliminación de un plan inexistente   | Se solicita eliminar un plan cuyo identificador no existe. El servicio devuelve `false` y no ejecuta la eliminación.                                  |
| **PLN-UT-04** | Actualización de un plan existente   | Se envía un comando de actualización para un plan registrado. El servicio actualiza sus atributos, guarda los cambios y devuelve el plan actualizado. |
| **PLN-UT-05** | Actualización de un plan inexistente | Se intenta actualizar un plan que no se encuentra en el repositorio. El servicio devuelve `Optional.empty()` y no guarda ningún cambio.               |

*Fuente: Elaboración propia.*

Estos casos permiten comprobar las rutas principales de ejecución de `PlanCommandServiceImpl`, incluyendo el tratamiento de identificadores inexistentes[13]. En conjunto con las pruebas de IAM, constituyen la base para verificar el comportamiento de los servicios de aplicación de los dos *bounded contexts* considerados[13].

![localtime](assets/chapter05/unitTest/unit-test-plans.png)
### 6.1.2. Core Integration Tests.

Las pruebas de integración verifican que los controladores REST API, los servicios de aplicación y la capa de persistencia interactúen correctamente entre sí dentro del entorno de la aplicación. A diferencia de las pruebas unitarias, estas pruebas evalúan la integración con la base de datos relacional y el procesamiento de peticiones HTTP en los endpoints expuestos.

Para llevar a cabo estas pruebas, se utiliza el entorno de prueba web de **Spring Boot (** **@SpringBootTest** **con** **MockMvc** **)** junto con una base de datos en memoria (H2) para simular las operaciones de lectura y escritura sin alterar datos de producción.

**Tabla 6.3\. Casos de prueba de integración para la API RESTful**

| ID Caso de prueba | Endpoint y Método HTTP                | Escenario de Integración                                                                   | Resultado esperado                                                                                               |
| ----------------- | ------------------------------------- | ------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------- |
| **IAM-IT-01**     | `POST /api/v1/authentication/sign-up` | Envío de solicitud HTTP con payload JSON conteniendo datos de un usuario nuevo.            | HTTP `201 Created`. La cuenta y el perfil son correctamente creados y persistidos en la base de datos.           |
| **IAM-IT-02**     | `POST /api/v1/authentication/sign-in` | Autenticación vía petición HTTP con credenciales válidas almacenadas en la base de datos.  | HTTP `200 OK`. Se retorna la estructura JSON conteniendo el token de acceso JWT válido y los datos del usuario.  |
| **PLN-IT-01**     | `POST /api/v1/plans`                  | Creación de un plan enviando un token JWT de administrador en la cabecera `Authorization`. | HTTP `201 Created`. El registro se guarda en la base de datos y se retorna la entidad creada con su ID generado. |
| **PLN-IT-02**     | `GET /api/v1/plans`                   | Consulta pública de planes de suscripción disponibles en el sistema.                       | HTTP `200 OK`. Se obtiene una lista JSON con la totalidad de los planes activos persistidos.                     |

*Fuente: Elaboración propia.*


### 6.1.3. Core Behavior-Driven Development

Las pruebas basadas en comportamiento (BDD) validan la API de WeRide desde la perspectiva del usuario y de las reglas de negocio. Los escenarios se escriben en lenguaje **Gherkin** con la sintaxis `Given-When-Then` (Dado - Cuando - Entonces) y se ejecutan con **Karate 1.5.2** (`karate-junit5`), un framework que permite probar APIs REST directamente desde los archivos `.feature`, sin necesidad de escribir *step definitions* en Java.

Las pruebas se ejecutan contra una instancia real del backend levantada con **Docker Compose** (contenedores `backend-weride` y `mysql-db`), por lo que validan el flujo completo: controlador REST, seguridad con JWT, lógica de aplicación y persistencia en MySQL. La URL base se define en `karate-config.js` (por defecto `http://localhost:8080`) y puede cambiarse para apuntar al despliegue en Render.

**Estructura de archivos (repositorio Backend-WeRide):**

| Archivo | Ubicación | Función |
| --- | --- | --- |
| `KarateTestRunner.java` | `src/test/java/karate/` | Punto de entrada JUnit 5. Ejecuta los features `auth` y `vehicles`. |
| `auth.feature` | `src/test/java/karate/` | Escenarios de registro e inicio de sesión (bounded context IAM). |
| `vehicles.feature` | `src/test/java/karate/` | Escenarios de gestión de vehículos (flota). |
| `karate-config.js` | `src/test/resources/` | Define `baseUrl` para todos los escenarios. |

**Ejecutor de pruebas:**

```java
package karate;

import com.intuit.karate.junit5.Karate;

class KarateTestRunner {

    @Karate.Test
    Karate testAuth() {
        return Karate.run("auth").relativeTo(getClass());
    }

    @Karate.Test
    Karate testVehicles() {
        return Karate.run("vehicles").relativeTo(getClass());
    }
}
```

#### **A. Archivo de especificación (`auth.feature`) — IAM**

Cada escenario genera un nombre de usuario único en el `Background`, de modo que las pruebas pueden ejecutarse repetidamente sin colisiones con datos previos.

```gherkin
Feature: Authentication - Sign Up & Sign In
  As a WeRide user
  I want to create an account and sign in
  So that I can access the booking and vehicle features of the platform

  Background:
    * url baseUrl
    * def randomUsername = 'ku' + java.util.UUID.randomUUID().toString().substring(0, 8)

  Scenario: Sign up with valid credentials creates a new account
    Given path '/api/v1/authentication/sign-up'
    And request { username: '#(randomUsername)', password: 'Weride2026!' }
    When method post
    Then status 201
    And match response.username == randomUsername
    And match response.id == '#number'

  Scenario: Sign up with a blank username is rejected
    Given path '/api/v1/authentication/sign-up'
    And request { username: '', password: 'Weride2026!' }
    When method post
    Then status 400

  Scenario: Sign in with valid credentials returns a JWT token
    Given path '/api/v1/authentication/sign-up'
    And request { username: '#(randomUsername)', password: 'Weride2026!' }
    When method post
    Then status 201

    Given path '/api/v1/authentication/sign-in'
    And request { username: '#(randomUsername)', password: 'Weride2026!' }
    When method post
    Then status 200
    And match response.token == '#string'
    And match response.id == '#number'

  Scenario: Sign in with a wrong password is rejected
    Given path '/api/v1/authentication/sign-up'
    And request { username: '#(randomUsername)', password: 'Weride2026!' }
    When method post
    Then status 201

    Given path '/api/v1/authentication/sign-in'
    And request { username: '#(randomUsername)', password: 'WrongPassword!' }
    When method post
    Then status 401
```

#### **B. Archivo de especificación (`vehicles.feature`) — Gestión de vehículos**

Los endpoints de vehículos requieren autenticación. Por ello, el `Background` registra un usuario nuevo, inicia sesión y configura el encabezado `Authorization: Bearer <token>` para todas las peticiones del escenario.

```gherkin
Feature: Vehicle Fleet Management (Garage)
  As an authenticated WeRide user
  I want to manage vehicles in the fleet
  So that users can browse and book available vehicles

  Background:
    * url baseUrl
    * def randomUser = 'ku' + java.util.UUID.randomUUID().toString().substring(0, 8)
    Given path '/api/v1/authentication/sign-up'
    And request { username: '#(randomUser)', password: 'Weride2026!' }
    When method post
    Then status 201

    Given path '/api/v1/authentication/sign-in'
    And request { username: '#(randomUser)', password: 'Weride2026!' }
    When method post
    Then status 200
    * def authHeader = 'Bearer ' + response.token
    * configure headers = { Authorization: '#(authHeader)' }

  Scenario: Create a vehicle and then retrieve it by id
    # POST /api/v1/vehicles -> 201, luego GET /api/v1/vehicles/{id} -> 200
    ...

  Scenario: List all vehicles returns an array
    Given path '/api/v1/vehicles'
    When method get
    Then status 200
    And match response == '#array'

  Scenario: Requesting a non-existent vehicle returns 404
    Given path '/api/v1/vehicles', '999999999'
    When method get
    Then status 404

  Scenario: Create and delete a vehicle (lifecycle)
    # POST -> 201, GET -> 200, DELETE -> 204, GET -> 404
    ...
```

*(En el repositorio los escenarios incluyen el cuerpo JSON completo del vehículo; aquí se resumen por extensión.)*

**Tabla 6.5. Casos de prueba BDD ejecutados con Karate**

| ID | Feature | Escenario | Resultado esperado | Resultado obtenido |
| --- | --- | --- | --- | --- |
| BDD-01 | auth | Registro con credenciales válidas | `201 Created` con `id` numérico y `username` igual al enviado | Aprobado |
| BDD-02 | auth | Registro con nombre de usuario vacío | `400 Bad Request` | Aprobado |
| BDD-03 | auth | Inicio de sesión con credenciales válidas | `200 OK` con `token` (JWT) e `id` | Aprobado |
| BDD-04 | auth | Inicio de sesión con contraseña incorrecta | `401 Unauthorized` | Aprobado |
| BDD-05 | vehicles | Crear un vehículo y consultarlo por id | `201 Created`; luego `200 OK` con la misma placa | Aprobado |
| BDD-06 | vehicles | Listar vehículos | `200 OK` con un arreglo JSON | Aprobado |
| BDD-07 | vehicles | Consultar un vehículo inexistente | `404 Not Found` | Aprobado |
| BDD-08 | vehicles | Crear y eliminar un vehículo | `201`, `200`, `204` y luego `404` | Aprobado |

*Fuente: Elaboración propia.*

**Resultado de la ejecución:** 8 escenarios ejecutados, 8 aprobados, 0 fallidos (4 de `auth.feature` y 4 de `vehicles.feature`). Karate genera además un reporte HTML en `target/karate-reports/karate-summary.html`.

![Ejecución de KarateTestRunner en IntelliJ IDEA: 8 tests passed](assets/karate-8-tests-passed.png)

*Figura 6.1. Ejecución de las pruebas Karate en IntelliJ IDEA (8 de 8 aprobadas).*

![Reporte HTML de Karate](assets/karate-report-summary.png)

*Figura 6.2. Reporte HTML generado por Karate.*

### 6.1.4. Core System Tests.
Las pruebas de sistema (*End-to-End* / E2E) evalúan la aplicación completa de manera integral, simulando la interacción real de los usuarios en la interfaz Web (Vue.js) y en la aplicación Móvil. Estas pruebas verifican la comunicación entre el frontend, las APIs RESTful del backend y la base de datos en escenarios de uso reales.

Se utiliza **Playwright** para la automatización web y **Appium** para la automatización de la interfaz móvil.

**Tabla 6.4\. Matriz de Pruebas de Sistema (End-to-End)**

| ID Caso de prueba | Plataforma               | Flujo de Usuario Evaluado (Happy/Unhappy Path)                                                | Resultado esperado                                                                                              |
| ----------------- | ------------------------ | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| **SYS-E2E-01**    | Web Browser (Vue.js)     | Flujo completo de registro de usuario, inicio de sesión y redirección al Dashboard principal. | El usuario completa el formulario, recibe la confirmación de cuenta y visualiza correctamente su panel privado. |
| **SYS-E2E-02**    | Web Browser (Vue.js)     | Selección de un plan de suscripción y procesamiento de la suscripción.                        | La interfaz actualiza el estado del plan del usuario y muestra el comprobante digital correspondiente.          |
| **SYS-E2E-03**    | Mobile App (Android/iOS) | Autenticación desde la aplicación móvil con credenciales inválidas.                           | La app muestra un mensaje de error accesible indicando "Invalid credentials" sin cerrar la aplicación.          |

*Fuente: Elaboración propia.*

![localtime](assets/chapter05/unitTest/test-karate-dash.png)

---

## 6.2. Static Code Analysis

### 6.2.1. Static Code Analysis Tools

Para el análisis estático del backend de WeRide se evaluaron tres alternativas y se eligió SonarQube, porque cubre en una sola herramienta las convenciones de código, la calidad y la seguridad del backend en Java, y porque se integra con Maven y con la tubería de integración continua descrita en el Capítulo VII.

**Tabla 6.3. Comparación de herramientas de análisis estático**

| Criterio | SonarQube Community Build | ESLint | Checkmarx |
| --- | --- | --- | --- |
| Lenguajes | Java, Kotlin, JavaScript/TypeScript, entre otros | JavaScript / TypeScript (y Angular con el plugin `angular-eslint`) | Múltiples lenguajes |
| Enfoque principal | Calidad (bugs, code smells), seguridad (vulnerabilidades y hotspots), duplicación | Estilo y errores de código JavaScript | Seguridad (SAST) |
| Cubre el backend Java | Sí | No | Sí |
| Cubre el frontend Angular/TypeScript | Sí (parcial) | Sí (especializado) | Sí |
| Costo | Gratuito (edición Community) | Gratuito (código abierto) | Licencia comercial |
| Integración con Maven / CI | Plugin `sonar-maven-plugin` y servidor propio | Se ejecuta con npm | Servicio o agente propio |
| Uso en este proyecto | **Sí (backend)** | Recomendado para el frontend | No (costo y licencia) |

*Fuente: elaboración propia a partir de la documentación oficial de cada herramienta.*

#### 6.2.1.1. Coding standard & Code conventions

El equipo adoptó las siguientes convenciones para el código del backend:

- **Estructura por bounded context y capas.** Cada contexto (por ejemplo `iam`, `plans`, `vehicles`) se organiza en capas `domain`, `application`, `infrastructure` e `interfaces`, siguiendo el diseño guiado por el dominio del Capítulo IV.
- **Nombres.** Clases e interfaces en `PascalCase`; métodos y atributos en `camelCase`; constantes en `UPPER_SNAKE_CASE`; paquetes en minúsculas.
- **Endpoints REST.** Rutas bajo `/api/v1/` y nombres en plural y `camelCase` (por ejemplo `/api/v1/vehicles`, `/api/v1/unlockRequests`).
- **Separación de modelos.** Los controladores reciben y devuelven recursos (`Resource`) y no exponen directamente las entidades del dominio.
- **Validaciones.** Las restricciones de entrada se declaran con anotaciones de Bean Validation (por ejemplo `@Size(max = 20)` en el nombre de usuario).
- **Flujo de trabajo en Git.** Ramas por funcionalidad (por ejemplo `feature/karate-bdd-tests`) y cambios integrados mediante Pull Request.

Como regla de verificación automática se usó el perfil de calidad por defecto de SonarQube para Java (*Sonar way*), que revisa en cada análisis el cumplimiento de buenas prácticas y convenciones del lenguaje.

#### 6.2.1.2. Code Quality & Code Security

Se ejecutó SonarQube Community Build v26.11 (instancia local con Docker) sobre el repositorio `Backend-WeRide`, mediante el plugin `sonar-maven-plugin` desde un contenedor Maven. El comando empleado fue:

```bash
mvn -B clean verify org.sonarsource.scanner.maven:sonar-maven-plugin:sonar -DskipTests \
  -Dsonar.projectKey=backend-weride \
  -Dsonar.host.url=http://host.docker.internal:9000 \
  -Dsonar.token=<token>
```

El token de acceso no se incluye en el repositorio ni en este informe.

**Tabla 6.4. Resultados del análisis estático de `Backend-WeRide` (11/11/2026)**

| Métrica | Resultado | Calificación |
| --- | --- | --- |
| Líneas de código | 5.8 k | — |
| Issues aceptados | 1 | — |
| Seguridad (issues abiertos) | 0 (1 aceptado, ver abajo) | A |
| Fiabilidad (bugs) | 0 | A |
| Mantenibilidad (code smells) | 0 | A |
| Security Hotspots | 0 | A |
| Duplicación | 1.4 % (sobre 7.7 k líneas) | — |
| Cobertura de pruebas unitarias | 0.0 % (sobre 1.8 k líneas) | — |
| Quality Gate | Passed | — |

*Fuente: SonarQube Community Build v26.11, proyecto `backend-weride`.*

![Resumen del análisis en SonarQube](assets/sonarqube-summary.png)

*Figura 6.3. Resumen del análisis estático del backend en SonarQube.*

**Issue de seguridad detectado.** En el primer análisis, SonarQube reportó un issue de severidad alta en `WebSecurityConfig.java` (línea 94): *"Make sure disabling Spring Security's CSRF protection is safe here"* (CWE, categoría Spring).

![Issue de seguridad en SonarQube](assets/sonarqube-issues.png)

*Figura 6.4. Issue de seguridad aceptado en SonarQube, con el comentario de justificación.*

**Análisis y decisión.** La protección CSRF protege a las aplicaciones que autentican con cookies de sesión, porque el navegador las envía de forma automática. El backend de WeRide es una API REST sin estado que autentica cada petición con un token JWT enviado en la cabecera `Authorization: Bearer`, sin cookies de sesión. Como el navegador no adjunta esa cabecera por sí solo, el ataque CSRF no aplica a este diseño, y deshabilitar la protección es la configuración recomendada para APIs de este tipo. Por ello el equipo evaluó el issue como un **riesgo aceptado** y lo marcó como *Accepted* en SonarQube con ese comentario. Tras ello, el resumen muestra 0 issues de seguridad abiertos (calificación A) y 1 issue aceptado.

**Cobertura.** El 0.0 % refleja que el análisis se ejecutó con `-DskipTests` y sin el agente JaCoCo, por lo que no se generó reporte de cobertura. Las pruebas del backend se verifican de forma externa con la suite BDD de Karate (sección 6.1.3), cuyos 8 escenarios pasan. Instrumentar la cobertura con JaCoCo queda como mejora para el siguiente avance.

**Conclusiones del análisis.**
- No se detectaron bugs ni code smells, y la duplicación es baja (1.4 %).
- El único hallazgo de seguridad corresponde a una decisión de diseño justificada (API sin estado con JWT).
- La principal oportunidad de mejora es medir la cobertura de pruebas unitarias.


# Capítulo VII: DevOps Practices

## 7.1. Continuous Integration

La integración continua es fundamental para asegurar la calidad y coherencia del código a lo largo del ciclo de vida del proyecto, ya que el proyecto está dividido en repositorios diferentes, el implementar integración continua nos permite automatizar las validaciones de cada cambio realizado, antes de ser fusionado con las ramas principales.
El objetivo principal de nuestra estrategia de integración continua es el detectar errores con anticipación, evitar conflictos al momento de integrar y validar que las modificaciones realizadas no alteren la lógica de aplicación existente.

### 7.1.1. Tools and Practices

Para implementar este entorno, se utilizaron herramientas y prácticas especializadas que permiten también un flujo de trabajo colaborativo.

**Tools:**

  - Sistema de Control de Versiones:

    Git y GitHub: Utilizamos Git como sistema de control de versiones y GitHub como plataforma para el alojamiento de nuestros repositorios (Landing Page, Frontend-WeRide, Backend-WeRide). GitHub facilita la revisión de código mediante pull requests y      gestión de incidencias.

  - Automatización de Pipelines:

    Jenkins: Es el servidor de automatización que usamos para los pipelines de CI/CD, como se trabaja en el curso. El pipeline se define como código en un `Jenkinsfile` en la raíz del repositorio (ver sección 7.1).

  - IDE y Linters:

    WebStorm: Utilizado para el desarrollo frontend (Angular 20, TypeScript, HTML, CSS con Angular Material). La calidad del código frontend se refuerza con las pruebas unitarias de Karma y Jasmine configuradas en el proyecto.

  - Frameworks de Pruebas Automatizadas:

    JUnit 5 y Mockito: Utilizados para la ejecución automática de pruebas unitarias y de integración en el backend, como Bounded Contexts de IAM y Plans durante el pipeline de CI.

**Practices:**

  - GitFlow Workflow: La estructura de ramas del proyecto está de acuerdo con el modelo GitFlow. El código principal está en la rama main, mientras que el código en desarrollo se centra en la rama develop, y para cada nueva tarea, creamos ramas con el      prefijo feature/nombre.
    
  - Conventional Commits: Todos los mensajes de los commits siguen la especificación de Conventional Commits. Utilizando prefijos como feat, fix, chore y test dependiendo de la modificación. Esto crea un historial de cambios legible para cualquiera.

  - Code Review y Pull Requests: Como se especifica en el curso, ningún código se integra directamente a develop o main. Todo código nuevo debe enviarse a través de un Pull Request. Y como práctica obligatoria, se requiere la revisión y aprobación de       un encargado miembro del equipo antes de realizar el merge.

  - Ejecución de Pruebas en cada Pull Request: Como parte del pipeline de CI en Jenkins, cada vez que se abre o actualiza un Pull Request, se dispara el pipeline que construye el proyecto y ejecuta todo el paquete de pruebas unitarias y de             integración. Si alguna prueba falla, el pipeline se marca en rojo y el merge queda bloqueado hasta que el encargado corrija el error.
    

### 7.1.2. Build & Test Suite Pipeline Components

El pipeline del repositorio **Backend-WeRide** se compone de las siguientes etapas:
 
| Etapa | Descripción | Herramienta | Resultado |
| --- | --- | --- | --- |
| **Checkout** | Descarga el código de la rama que disparó el pipeline. | Jenkins + Git | Código fuente en el workspace |
| **Build** | Compila el proyecto y empaqueta la aplicación sin ejecutar pruebas. | Maven | Archivo `.jar` |
| **Unit & Integration Tests** | Ejecuta las pruebas unitarias y de integración (capítulo VI, secciones 6.1.1 y 6.1.2). | JUnit 5, Mockito, Spring Boot Test | Reportes JUnit publicados en Jenkins |
| **Start API (test)** | Levanta la aplicación con el perfil de pruebas para que Karate pueda consumirla. | Java | API disponible en `localhost:8080` |
| **Karate (BDD / Acceptance)** | Ejecuta los escenarios Given-When-Then sobre la API (sección 6.1.3). | Karate | Reporte HTML `karate-summary.html` archivado |
| **Reports & Cleanup** | Publica los resultados y detiene la aplicación de pruebas. | Jenkins | Resultado visible en el panel del build |
 
**Jenkinsfile** (en la raíz del repositorio Backend-WeRide):
 
```groovy
pipeline {
  agent any
 
  tools {
    maven 'Maven3'
    jdk 'JDK17'
  }
 
  stages {
    stage('Checkout') {
      steps { checkout scm }
    }
 
    stage('Build') {
      steps { sh 'mvn -B clean package -DskipTests' }
    }
 
    stage('Unit & Integration Tests') {
      steps { sh 'mvn -B test' }
      post {
        always { junit 'target/surefire-reports/*.xml' }
      }
    }
 
    stage('Start API (test)') {
      steps {
        sh '''
          nohup java -jar target/*.jar --spring.profiles.active=test > api.log 2>&1 &
          echo $! > api.pid
          for i in $(seq 1 30); do
            curl -s -o /dev/null http://localhost:8080/swagger-ui/index.html && break
            sleep 2
          done
        '''
      }
    }
 
    stage('Karate (BDD / Acceptance)') {
      steps { sh 'mvn -B -f karate-tests/pom.xml test' }
      post {
        always {
          archiveArtifacts artifacts: 'karate-tests/target/karate-reports/**', allowEmptyArchive: true
        }
      }
    }
  }
 
  post {
    always {
      sh 'if [ -f api.pid ]; then kill $(cat api.pid) || true; fi'
    }
    failure {
      echo 'El pipeline falló: revisar los reportes de pruebas y el log api.log.'
    }
  }
}
```
 
**Configuración de Jenkins utilizada:**
 
1. Se levantó Jenkins con Docker en el puerto 8081, para no chocar con el backend que usa el 8080: `docker run -d -p 8081:8080 -p 50000:50000 -v jenkins_home:/var/jenkins_home jenkins/jenkins:lts-jdk17`.
2. Se instalaron los plugins **Pipeline**, **Git**, **GitHub** y **JUnit**.
3. En *Manage Jenkins → Tools* se configuraron **JDK17** y **Maven3** (instalación automática), con los mismos nombres usados en el `Jenkinsfile`.
4. Se creó un proyecto **Multibranch Pipeline** apuntando al repositorio Backend-WeRide.
5. Se configuró el disparo automático con un webhook de GitHub o, si Jenkins no es accesible desde internet, con sondeo del repositorio (*Poll SCM*, `H/5 * * * *`).
6. Se hizo push del `Jenkinsfile` a `develop` y se verificó la primera ejecución.

## 7.3. Continuous Deployment

El despliegue continuo automatiza la publicación del backend de WeRide en un entorno accesible desde internet, de manera que cada versión aprobada pueda ser consumida por el frontend y verificada por el equipo y los evaluadores sin intervención manual.

### 7.3.1. Tools and Practices

**Tools:**

| Herramienta | Uso en el proyecto |
| --- | --- |
| **Docker** | Empaqueta el backend en una imagen mediante un `Dockerfile` multi-etapa: una etapa de compilación con Maven y JDK 24, y una etapa de ejecución con `eclipse-temurin:24-jdk-alpine`. |
| **Render (Web Service)** | Plataforma de despliegue del backend. Construye la imagen Docker desde el repositorio de GitHub y la ejecuta como servicio web con URL pública HTTPS. |
| **Aiven for MySQL** | Base de datos MySQL 8.4 administrada en la nube, usada por el backend desplegado. |
| **GitHub** | Repositorio de código fuente que Render observa para construir y desplegar. |
| **springdoc-openapi (Swagger UI)** | Documentación interactiva de la API, publicada junto con el servicio. |

**Practices:**

- **Despliegue desde el repositorio:** Render está conectado al repositorio de GitHub del backend; cada cambio en la rama configurada puede disparar una nueva construcción y despliegue.
- **Configuración por variables de entorno:** las credenciales y parámetros sensibles no se escriben en el código. La conexión a la base de datos (`SPRING_DATASOURCE_URL`, `SPRING_DATASOURCE_USERNAME`, `SPRING_DATASOURCE_PASSWORD`) y el secreto de firma de tokens (`JWT_SECRET`) se definen como variables de entorno en Render y sustituyen a los valores de `application.properties`.
- **Ajuste de memoria para el plan gratuito:** el servicio corre con 512 MB de RAM, por lo que se configura `JAVA_TOOL_OPTIONS=-Xmx350m -XX:+UseSerialGC` para limitar el consumo de la JVM.
- **Verificación posterior al despliegue:** tras cada despliegue se comprueba la disponibilidad del servicio con el endpoint público `/health` y se valida la documentación en Swagger UI.
- **Entorno local equivalente:** el mismo `Dockerfile` y un `docker-compose.yml` (backend + MySQL) permiten reproducir localmente el entorno de ejecución, de modo que las pruebas de la sección 6.1.3 se ejecutan contra el mismo tipo de contenedor que se despliega.

### 7.3.2. Production Deployment Pipeline Components

| Etapa | Descripción | Herramienta | Resultado |
| --- | --- | --- | --- |
| **Trigger** | Un cambio llega a la rama del repositorio conectada a Render. | GitHub | Render detecta el cambio. |
| **Build de imagen** | Render ejecuta el `Dockerfile`: compila el proyecto con Maven y genera el `.jar`. | Docker + Maven | Imagen del backend lista. |
| **Inyección de configuración** | Se aplican las variables de entorno del servicio (base de datos, `JWT_SECRET`, `PORT=8080`, opciones de JVM). | Render | Contenedor configurado para producción. |
| **Despliegue** | Render inicia el contenedor y lo expone con una URL pública HTTPS. | Render | Servicio en línea. |
| **Conexión a la base de datos** | El backend se conecta a MySQL en Aiven y Hibernate actualiza el esquema (`ddl-auto=update`). | Aiven for MySQL | Tablas disponibles en la base de datos de producción. |
| **Verificación** | Se consulta `/health` y la documentación Swagger UI del servicio. | Navegador / Swagger UI | Servicio verificado. |

**Entorno de producción:**

| Elemento | Valor |
| --- | --- |
| API desplegada | https://backend-weride-2wpb.onrender.com |
| Documentación (Swagger UI) | https://backend-weride-2wpb.onrender.com/swagger-ui/index.html |
| Proveedor de la aplicación | Render, Web Service con runtime Docker, plan gratuito (512 MB RAM) |
| Base de datos | Aiven for MySQL 8.4 |

*Nota:* en el plan gratuito de Render el servicio entra en reposo tras un periodo de inactividad, por lo que la primera petición posterior puede tardar alrededor de un minuto mientras el contenedor vuelve a iniciar.

![Servicio desplegado en Render](assets/chapter05/render-live.png)

*Figura 7.1. Servicio del backend en ejecución en Render.*

![Swagger UI del backend desplegado](assets/chapter05/swagger-overview.png)

*Figura 7.2. Documentación Swagger UI del servicio desplegado.*




# Capítulo VIII: Experiment-Driven Development

El desarrollo guiado por experimentos busca que las decisiones sobre WeRide se tomen con evidencia y no con opiniones. En este capítulo se planifican y diseñan los experimentos que permitirán validar las hipótesis de negocio, usuario, valor y funcionalidad definidas en el capítulo I, se establecen las métricas y los planes de medición, y se traduce lo que se necesita construir para ejecutarlos en historias de usuario y un Product Backlog To-Be.

Este capítulo parte de insumos ya existentes en el informe: las entrevistas y el needfinding del capítulo II, el Lean UX Canvas y las hipótesis del capítulo I, las historias de usuario y el Product Backlog del capítulo III, y las observaciones de la evaluación de la plataforma del capítulo V.

## 8.1. Experiment Planning

### 8.1.1. As-Is Summary

**Situación del usuario (sin WeRide).** El needfinding del capítulo II muestra dos segmentos con problemas distintos:

| Segmento | Perfil | Frustraciones principales (As-Is) |
| --- | --- | --- |
| B2C — Universitarios y jóvenes profesionales | Camila Torres, joven universitaria | Tráfico que la retrasa, transporte incómodo e inseguro, falta de efectivo para pagar y poca disponibilidad de opciones rápidas cerca de su ubicación. |
| B2B — Empresas y planes corporativos | Luis Salazar, gerente de operaciones | Congestión vehicular que afecta la puntualidad y la productividad, costos elevados por taxis y estacionamientos, y dificultad para implementar una solución escalable para todos los empleados. |

**Contexto de mercado (capítulo I).** El transporte genera más del 30 % de las emisiones urbanas, los usuarios pagan entre 30 % y 40 % más por trayectos cortos al no haber alternativas, y la falta de monitoreo IoT incrementa los costos operativos entre 25 % y 50 %. Los hallazgos de las entrevistas indican preferencia por pagos locales (Yape/Plin) y sensibilidad al precio; para que el modelo sea rentable, el informe fija como objetivo una utilización mínima de 4 a 5 viajes por vehículo al día.

**Situación del producto (hoy).** WeRide cuenta con un backend desplegado (API REST documentada con Swagger), una landing page y una aplicación web con garaje de vehículos, reservas, planes y perfil. La evaluación del capítulo V registró 14 observaciones sobre la plataforma, entre ellas botones inactivos (reservar, pagar, editar reserva), ausencia de datos para bicicletas eléctricas y falta de opciones de traducción. La telemetría IoT se simula, tal como se planteó en el plan de MVP, por lo que los experimentos de campo se diseñan con datos de simulación y pilotos acotados.

**Lo que aún no se sabe.** No se ha medido el comportamiento real de uso: no hay datos de conversión, abandono, tiempos de desbloqueo ni disposición de pago observada, solo declarada en entrevistas.

### 8.1.2. Raw Material: Assumptions, Knowledge Gaps, Ideas, Claims

**Tabla 8.1. Material base para la experimentación**

| ID | Tipo | Enunciado | Origen |
| --- | --- | --- | --- |
| A-01 | Assumption (usuario) | Los usuarios urbanos adoptarán WeRide si es más rápido y económico que sus opciones actuales. | Cap. I, Lean UX |
| A-02 | Assumption (usuario) | Los usuarios valoran ver en tiempo real la ubicación y el estado de los vehículos y un desbloqueo sencillo. | Cap. I, Lean UX |
| A-03 | Assumption (negocio) | Un modelo mixto (tarifa por uso, suscripción y planes B2B) es viable en Lima. | Cap. I, Lean UX |
| A-04 | Assumption (valor) | Mostrar batería y estado del vehículo aumenta la confianza y reduce cancelaciones. | Cap. I, Lean UX |
| A-05 | Assumption (negocio) | Las empresas valoran un plan corporativo con panel de uso y reportes. | Cap. II (segmento B2B), US-40 a US-42 |
| KG-01 | Knowledge gap | ¿Qué porcentaje de visitantes de la landing llega a abrir la aplicación? | Sin datos de tráfico |
| KG-02 | Knowledge gap | ¿Cuánto tarda un usuario nuevo en encontrar, reservar y desbloquear un vehículo, y dónde se atasca? | Sin pruebas con usuarios |
| KG-03 | Knowledge gap | ¿Qué tan rápido responde el desbloqueo en condiciones reales? | Sin medición |
| KG-04 | Knowledge gap | ¿Qué plan (por uso, diario, mensual, corporativo) prefieren los usuarios al ver precios concretos? | Solo disposición declarada |
| KG-05 | Knowledge gap | ¿Cuántas empresas aceptarían un piloto y qué indicadores querrían ver? | Sin contacto comercial |
| I-01 | Idea | Indicador visible de batería y estado en cada tarjeta del garaje. | Cap. III, US-07 y US-30 |
| I-02 | Idea | Desbloqueo con QR como método principal y desde la app como alternativa. | Cap. III, US-19 y US-20 |
| I-03 | Idea | Panel corporativo con uso de vehículos y reportes de movilidad. | Cap. III, US-40 y US-42 |
| C-01 | Claim | "WeRide reduce el tiempo de traslado de trayectos cortos." | Propuesta de valor |
| C-02 | Claim | "WeRide ofrece una alternativa económica y sostenible frente a taxis y transporte público." | Propuesta de valor |

*Fuente: Elaboración propia a partir de los capítulos I, II y III.*

### 8.1.3. Experiment-Ready Questions

Cada pregunta transforma un vacío de conocimiento en algo que puede responderse con datos.

**Tabla 8.2. Preguntas listas para experimentar**

| ID | Pregunta | Relacionada con |
| --- | --- | --- |
| Q-01 | ¿Qué porcentaje de visitantes únicos de la landing hace clic en "Go to App" o en la descarga? | KG-01, A-01 |
| Q-02 | ¿Cuánto tiempo y cuántos pasos necesita un usuario nuevo para encontrar, reservar y desbloquear un vehículo? | KG-02, A-02 |
| Q-03 | ¿Qué tasa de tareas completadas sin ayuda logra un usuario nuevo en ese flujo? | KG-02 |
| Q-04 | ¿Cuál es el tiempo de respuesta del desbloqueo (solicitud a estado "desbloqueado") y qué porcentaje cumple 5 segundos o menos? | KG-03 |
| Q-05 | ¿Mostrar la batería y el estado en las tarjetas del garaje reduce el abandono de reservas respecto a no mostrarlo? | A-04, I-01 |
| Q-06 | ¿Qué plan eligen los visitantes cuando ven precios reales de cada opción? | KG-04, A-03 |
| Q-07 | ¿Cuántas empresas solicitan información o aceptan un piloto del plan corporativo? | KG-05, A-05 |
| Q-08 | ¿Los colaboradores de una empresa piloto usan el servicio de forma recurrente durante cuatro semanas? | A-05, A-01 |
| Q-09 | ¿Qué nivel de satisfacción (NPS) reportan los usuarios tras sus primeros viajes? | A-01, C-02 |
| Q-10 | ¿La disponibilidad de la flota piloto alcanza o supera el 85 %? | A-03 |

*Fuente: Elaboración propia.*

### 8.1.4. Question Backlog

Las preguntas se priorizan por **impacto** en la decisión de producto y por **incertidumbre** (qué tan poco se sabe). El orden refleja qué conviene aprender primero.

**Tabla 8.3. Question Backlog priorizado**

| Prioridad | Pregunta | Impacto | Incertidumbre | Esfuerzo | Experimento |
| ---: | --- | --- | --- | --- | --- |
| 1 | Q-02, Q-03 (flujo de reserva y desbloqueo) | Alto | Alta | Bajo | EXP-01 |
| 2 | Q-04 (tiempo de desbloqueo) | Alto | Media | Bajo | EXP-04 |
| 3 | Q-05 (indicador de batería) | Alto | Alta | Medio | EXP-03 |
| 4 | Q-01, Q-06 (landing y planes) | Medio | Alta | Bajo | EXP-02 |
| 5 | Q-07 (interés corporativo) | Alto | Alta | Medio | EXP-02 y EXP-05 |
| 6 | Q-08, Q-09, Q-10 (uso recurrente, NPS, disponibilidad) | Alto | Alta | Alto | EXP-05 |

*Fuente: Elaboración propia.*

### 8.1.5. Experiment Cards

**Tabla 8.4. Experiment Card EXP-01 — Test de usabilidad del flujo de reserva**

| Campo | Contenido |
| --- | --- |
| Nombre | Usabilidad del flujo encontrar, reservar y desbloquear |
| Pregunta | Q-02, Q-03 |
| Hipótesis | H-02 |
| Método | Test de usabilidad moderado con tareas y "think aloud", más cuestionario SUS |
| Qué se hará | 5 participantes del segmento B2C realizan 3 tareas en la aplicación web: ubicar un vehículo cercano, reservarlo y desbloquearlo. Se registra tiempo, errores y comentarios. |
| Métrica de éxito | Tiempo medio de la tarea completa menor a 60 s, tasa de tareas completadas sin ayuda de 80 % o más, SUS de 68 o más |
| Decisión si se cumple | Mantener el flujo y pasar a optimizar detalles |
| Decisión si no se cumple | Rediseñar los pasos con mayor fricción antes del piloto |

**Tabla 8.5. Experiment Card EXP-02 — Landing page y puerta falsa del plan corporativo**

| Campo | Contenido |
| --- | --- |
| Nombre | Interés en la landing: acceso a la app, planes y plan corporativo |
| Pregunta | Q-01, Q-06, Q-07 |
| Hipótesis | H-03, H-04 |
| Método | Medición de clics y experimento de puerta falsa (*fake door*): botón "Solicitar demo corporativa" que registra el interés sin construir aún el servicio completo |
| Qué se hará | Instrumentar los llamados a la acción de la landing (Go to App, descarga, planes, plan corporativo) y publicar un formulario de interés corporativo. Se difunde en canales de la universidad y contactos de empresas. |
| Métrica de éxito | 10 % o más de visitantes únicos hace clic en "Go to App", y al menos 3 empresas dejan una solicitud de demo |
| Decisión si se cumple | Priorizar el desarrollo del plan corporativo (US-39 a US-42) |
| Decisión si no se cumple | Revisar el mensaje de la landing y el segmento B2B antes de invertir en el panel corporativo |

**Tabla 8.6. Experiment Card EXP-03 — Indicador de batería y estado (A/B)**

| Campo | Contenido |
| --- | --- |
| Nombre | Efecto del indicador de batería y estado en el abandono de reservas |
| Pregunta | Q-05 |
| Hipótesis | H-05 |
| Método | Prueba A/B: variante A (control) sin indicador y variante B con batería y estado visibles en la tarjeta del vehículo |
| Qué se hará | Asignar a cada sesión una variante de forma aleatoria y medir cuántas reservas iniciadas se completan |
| Métrica de éxito | La tasa de abandono baja de 30 % (valor supuesto, a calibrar con los primeros datos) a 15 % o menos |
| Tamaño de muestra | 121 sesiones por variante (ver 8.2.5) |
| Decisión si se cumple | Mantener el indicador como funcionalidad estándar |
| Decisión si no se cumple | Retirar el indicador de las tarjetas y mostrarlo solo en el detalle |

**Tabla 8.7. Experiment Card EXP-04 — Tiempo de desbloqueo**

| Campo | Contenido |
| --- | --- |
| Nombre | Medición del tiempo de respuesta del desbloqueo |
| Pregunta | Q-04 |
| Hipótesis | H-06 |
| Método | Experimento técnico: medir el tiempo del flujo de desbloqueo contra la API desplegada, con el vehículo simulado |
| Qué se hará | Ejecutar 35 desbloqueos contra el backend desplegado, midiendo desde el cliente de prueba el tiempo total del flujo: creación de la solicitud de desbloqueo y actualización a estado desbloqueado. El vehículo se simula, por lo que se mide la latencia del software y no la del hardware IoT. |
| Métrica de éxito | 95 % de los desbloqueos responden en 5 s o menos |
| Decisión si se cumple | Dar por válida la arquitectura de desbloqueo para el piloto |
| Decisión si no se cumple | Optimizar la ruta de solicitud (consultas, notificación) y repetir |

**Tabla 8.8. Experiment Card EXP-05 — Piloto B2B con panel corporativo**

| Campo | Contenido |
| --- | --- |
| Nombre | Piloto cerrado con una empresa |
| Pregunta | Q-07, Q-08, Q-09, Q-10 |
| Hipótesis | H-01, H-04, H-07 |
| Método | Piloto cerrado de cuatro semanas con acompañamiento manual (concierge): el equipo prepara los reportes del panel y recoge retroalimentación |
| Qué se hará | Una empresa o grupo de 5 a 10 colaboradores usa el servicio; se mide uso semanal, utilización por vehículo, disponibilidad de la flota y NPS; al final se entrevista al administrador sobre disposición a pagar |
| Métrica de éxito | NPS de 40 o más, uso recurrente de al menos 3 de cada 5 colaboradores cada semana, disponibilidad de flota de 85 % o más, y la empresa acepta continuar con un plan de pago |
| Decisión si se cumple | Convertir el piloto en caso de éxito y escalar a más empresas |
| Decisión si no se cumple | Analizar causas (uso, precio, flota) y ajustar el plan corporativo |

*Fuente: Elaboración propia.*

## 8.2. Experiment Design

### 8.2.1. Hypotheses

Las hipótesis retoman las del capítulo I con el formato "Creemos que… Sabremos que es verdad cuando…".

**Tabla 8.9. Hipótesis de los experimentos**

| ID | Tipo | Creemos que… | Sabremos que es verdad cuando… | Experimento |
| --- | --- | --- | --- | --- |
| H-01 | Negocio | WeRide logrará una operación sostenible si la telemetría reduce el tiempo de inactividad y los costos de mantenimiento. | Al menos una empresa acepta el piloto y la disponibilidad de flota es de 85 % o más. | EXP-05 |
| H-02 | Usuario | Los usuarios nuevos pueden encontrar y desbloquear un vehículo en menos de 60 segundos viendo su estado en tiempo real. | Tiempo medio menor a 60 s y 80 % o más de tareas completadas sin ayuda. | EXP-01 |
| H-03 | Usuario | Los visitantes de la landing se interesan en la propuesta si entienden el servicio y los planes. | 10 % o más de visitantes únicos hace clic en "Go to App". | EXP-02 |
| H-04 | Negocio | Las empresas valoran un plan corporativo con panel de uso y reportes. | Al menos 3 solicitudes de demo y una empresa dispuesta a pagar el plan tras el piloto. | EXP-02, EXP-05 |
| H-05 | Funcionalidad | Mostrar batería y estado del vehículo reduce el abandono de reservas. | La tasa de abandono baja de 30 % a 15 % o menos entre variantes. | EXP-03 |
| H-06 | Funcionalidad | El desbloqueo digital responde con rapidez suficiente para no generar fricción. | 95 % de los desbloqueos responde en 5 s o menos. | EXP-04 |
| H-07 | Valor | Un uso simple y confiable genera satisfacción y uso recurrente. | NPS de 40 o más y uso semanal recurrente de los colaboradores. | EXP-05 |

*Fuente: Elaboración propia a partir del capítulo I.*

### 8.2.2. Domain Business Metrics

Las métricas de negocio se organizan con el marco AARRR (adquisición, activación, retención, ingresos, recomendación) y se complementan con métricas operativas propias de una flota compartida.

**Tabla 8.10. Métricas de negocio del dominio**

| Categoría | Métrica | Definición | Objetivo |
| --- | --- | --- | --- |
| Adquisición | Tasa de clic a la app | Visitantes únicos que hacen clic en "Go to App" entre visitantes únicos de la landing | 10 % o más |
| Activación | Tasa de reserva completada | Usuarios nuevos que completan su primera reserva entre usuarios registrados | 10 % o más (vista a reserva, cap. I) |
| Activación | Tiempo a primer desbloqueo | Tiempo desde la apertura de la app hasta el primer desbloqueo | Menos de 60 s |
| Retención | Uso semanal recurrente | Usuarios con al menos un viaje cada semana entre usuarios activos | Positivo tras 4 semanas |
| Ingresos | Utilización por vehículo | Viajes por vehículo por día | 4 a 5 viajes al día; mejora de 20 % en las semanas iniciales |
| Recomendación | NPS | Porcentaje de promotores menos porcentaje de detractores | 40 o más en el piloto |
| Operación | Disponibilidad de flota | Vehículos disponibles entre vehículos totales de la zona | 85 % o más |
| Operación | Incidentes por vehículo | Fallas o reportes de problema por vehículo | Reducción de 30 % o más |

*Fuente: Elaboración propia a partir de las métricas de éxito del capítulo I.*

### 8.2.3. Measures

Una medida es la forma concreta y repetible de calcular cada métrica.

**Tabla 8.11. Medidas operativas**

| Medida | Cómo se calcula | Fuente de datos | Frecuencia |
| --- | --- | --- | --- |
| Visitantes únicos de la landing | Conteo de sesiones únicas | Analítica web | Diaria |
| Clics en llamados a la acción | Conteo del evento `cta_click` por botón | Analítica web | Diaria |
| Reservas iniciadas y completadas | Registros de reservas y su estado (borrador, pendiente, completada) | Base de datos del backend (recurso de reservas) | Diaria |
| Tiempo de la tarea de reserva | Marca de tiempo final menos inicial por participante | Registro del test de usabilidad | Por sesión |
| Tiempo de desbloqueo | Tiempo total, medido con cronómetro en el cliente de prueba, de crear la solicitud de desbloqueo y actualizar su estado | Script de medición contra la API (recurso de solicitudes de desbloqueo) | Por evento |
| Viajes por vehículo | Conteo de viajes por vehículo y por día | Recurso de viajes y del historial | Diaria |
| Disponibilidad de flota | Vehículos con estado disponible entre total, medido cada hora | Recurso de vehículos | Horaria |
| NPS | Encuesta de una pregunta (0 a 10) al finalizar el viaje | Formulario dentro de la app | Por viaje |
| Solicitudes de demo corporativa | Conteo de envíos del formulario de interés | Formulario de la landing | Diaria |

*Fuente: Elaboración propia.*

### 8.2.4. Conditions

Las condiciones fijan en qué contexto se ejecuta cada experimento para que los resultados sean comparables.

**Tabla 8.12. Condiciones de los experimentos**

| Experimento | Participantes | Entorno | Duración | Control / variante | Criterio de parada |
| --- | --- | --- | --- | --- | --- |
| EXP-01 | 5 usuarios del segmento B2C (jóvenes universitarios) | Aplicación web desplegada, vehículos de prueba cargados | 1 semana | Sin grupo de control (estudio cualitativo) | 5 participantes completos |
| EXP-02 | Visitantes de la landing por difusión en la universidad y contactos de empresas | Landing pública con analítica | 2 semanas | Sin control; se compara contra el umbral | Fin del periodo o 100 visitantes únicos |
| EXP-03 | Usuarios de la aplicación web | Garaje de vehículos con asignación aleatoria de variante | Hasta alcanzar la muestra o 4 semanas | A: sin indicador; B: con batería y estado | 121 sesiones por variante |
| EXP-04 | Sistema (sin participantes) | Backend desplegado en Render y vehículo simulado | 1 día | Sin control; se compara contra el umbral de 5 s | 35 desbloqueos medidos |
| EXP-05 | 5 a 10 colaboradores de una empresa | Aplicación web, flota simulada o piloto acotado | 4 semanas | Sin control; se compara con las metas | Fin de la cuarta semana |

*Fuente: Elaboración propia.*

### 8.2.5. Scale Calculations and Decisions

Siguiendo los lineamientos del curso, el tamaño de muestra se calcula con un nivel de significancia de α = 5 % (95 % de confianza), una potencia estadística de 80 % (probabilidad de error tipo II de 20 %) y un **efecto mínimo detectable (MDE)** definido para cada experimento. Los participantes y las sesiones se toman de los segmentos objetivo (universitarios y jóvenes profesionales en B2C, y empresas en B2B) para que los hallazgos sean representativos del grupo de interés.

**Tabla 8.12-A. Parámetros estadísticos por experimento**

| Experimento | α | Potencia | MDE | Tamaño de muestra |
| --- | --- | --- | --- | --- |
| EXP-01 (usabilidad) | 5 % | No aplica (estudio cualitativo) | Detectar problemas que afecten al menos al 31 % de los usuarios | 5 participantes |
| EXP-02 (landing) | 5 % | No aplica (estimación) | Margen de error de ±5 puntos porcentuales | 139 visitantes únicos |
| EXP-03 (A/B) | 5 % | 80 % | 15 puntos porcentuales (de 30 % a 15 %) | 121 sesiones por variante |
| EXP-04 (desbloqueo) | 5 % | No aplica (estimación) | Margen de error de ±1 s en el tiempo medio | 35 mediciones |
| EXP-05 (piloto) | 5 % | No aplica (piloto cerrado) | NPS de 40 o más | 5 a 10 colaboradores |

**Estimación de una proporción (EXP-02, conversión).** Para estimar una conversión esperada de 10 % con un margen de error de ±5 puntos:

n = Z² · p · (1 − p) / e² = 1,96² · 0,10 · 0,90 / 0,05² ≈ **139 visitantes únicos**

**Comparación de dos proporciones (EXP-03, A/B).** Con una tasa de abandono supuesta de 30 % en el control y una meta de 15 % en la variante B, con 95 % de confianza y 80 % de potencia:

n por variante = (Zα/2 · √(2 · p̄ · q̄) + Zβ · √(p₁q₁ + p₂q₂))² / (p₁ − p₂)² ≈ **121 sesiones por variante** (MDE de 15 puntos porcentuales)

El 30 % es un supuesto que se calibrará con los primeros datos reales. Si la meta fuera una reducción menor (de 20 % a 14 %), la muestra necesaria subiría a unas 615 sesiones por variante, lo que excede el tráfico esperado del piloto.

**Usabilidad (EXP-01).** La probabilidad de encontrar un problema de usabilidad con n participantes es 1 − (1 − 0,31)ⁿ. Con 5 participantes se detecta cerca del 84 % de los problemas; con 8, cerca del 95 %.

**Tiempo medio de desbloqueo (EXP-04).** Para estimar el tiempo medio con un margen de ±1 s, suponiendo una desviación estándar de 3 s: n = (1,96 · 3 / 1)² ≈ **35 mediciones**.

**Tabla 8.13. Decisiones de escala**

| Situación | Decisión |
| --- | --- |
| El tráfico no alcanza la muestra calculada en EXP-02 o EXP-03 | Extender la duración hasta 4 semanas; si aun así no se alcanza, tratar el resultado como **indicativo** y confirmarlo en el piloto de EXP-05 |
| EXP-01 muestra problemas graves con los primeros 3 participantes | Corregir antes de continuar con los 2 restantes (se detecta cerca del 67 % de los problemas con 3 participantes) |
| Los resultados cumplen las metas de forma clara | Pasar a la siguiente fase del backlog y ampliar el alcance del piloto |

*Fuente: Elaboración propia.*

### 8.2.6. Methods Selection

**Tabla 8.14. Selección de métodos**

| Pregunta | Tipo de dato | Método elegido | Por qué |
| --- | --- | --- | --- |
| Q-02, Q-03 | Cualitativo y cuantitativo | Test de usabilidad moderado y SUS | Permite ver dónde se atasca el usuario con pocos participantes |
| Q-01, Q-06 | Cuantitativo | Analítica de clics en la landing | Es barato y mide comportamiento real |
| Q-07 | Cuantitativo | Puerta falsa (*fake door*) | Mide interés antes de construir el servicio completo |
| Q-05 | Cuantitativo | Prueba A/B | Aísla el efecto de una sola funcionalidad |
| Q-04 | Cuantitativo | Medición técnica contra la API | El tiempo de respuesta es objetivo y se mide automáticamente |
| Q-08, Q-09, Q-10 | Mixto | Piloto cerrado con acompañamiento y encuesta NPS | Reproduce el uso real en un grupo acotado |

*Fuente: Elaboración propia.*

### 8.2.7. Data Analytics: Goals, KPIs and Metrics Selection

Se aplica el enfoque Goal–Question–Metric: de cada objetivo se derivan preguntas y de estas, los indicadores.

**Tabla 8.15. Objetivos, KPIs y métricas**

| Objetivo | KPI | Métricas que lo componen | Meta | Experimento |
| --- | --- | --- | --- | --- |
| Atraer usuarios a la plataforma | Tasa de clic a la app | Visitantes únicos, clics en "Go to App" | 10 % o más | EXP-02 |
| Lograr que el primer uso sea fácil | Éxito del primer uso | Tiempo a primer desbloqueo, tareas completadas sin ayuda, SUS | Menos de 60 s, 80 % o más, SUS de 68 o más | EXP-01 |
| Reducir la fricción en la reserva | Tasa de abandono de reserva | Reservas iniciadas, reservas completadas | 15 % o menos | EXP-03 |
| Garantizar un desbloqueo confiable | Desbloqueos rápidos | Tiempo de desbloqueo (percentil 95) | 5 s o menos | EXP-04 |
| Validar el modelo B2B | Interés y retención corporativa | Solicitudes de demo, uso semanal recurrente, aceptación del plan | 3 solicitudes, 3 de 5 colaboradores activos, 1 empresa dispuesta a pagar | EXP-02, EXP-05 |
| Asegurar calidad del servicio | Satisfacción y disponibilidad | NPS, disponibilidad de flota, incidentes por vehículo | NPS de 40 o más, disponibilidad de 85 % o más | EXP-05 |

*Fuente: Elaboración propia.*

### 8.2.8. Web and Mobile Tracking Plan

El plan de seguimiento define qué eventos se registran en la landing, la aplicación web y la aplicación móvil. Los eventos usan nombres en minúsculas con guion bajo y propiedades comunes (`user_id` anónimo, `platform`, `variant`, `timestamp`). Las métricas de reservas, viajes, desbloqueos y vehículos se obtienen además directamente de la base de datos del backend, lo que evita depender solo de la analítica del cliente.

**Herramientas propuestas:** una herramienta de analítica web para la landing y la aplicación web (por ejemplo Google Analytics 4), una herramienta de analítica móvil para la aplicación (por ejemplo Firebase Analytics) y consultas sobre la base de datos del backend para las métricas operativas.

**Tabla 8.16. Plan de seguimiento de eventos**

| Evento | Cuándo se dispara | Propiedades | Plataforma | Métrica que alimenta |
| --- | --- | --- | --- | --- |
| `landing_view` | Se carga la landing | `source`, `device` | Web | Visitantes únicos |
| `cta_click` | Clic en Go to App, descarga, planes o plan corporativo | `cta_id`, `section` | Web | Tasa de clic a la app |
| `demo_request_submit` | Se envía el formulario de interés corporativo | `company_size` | Web | Solicitudes de demo |
| `signup_complete` | Registro exitoso | `method` | Web y móvil | Activación |
| `vehicle_list_view` | Se abre el garaje o el mapa | `variant`, `filters_used` | Web y móvil | Embudo de reserva |
| `vehicle_card_view` | Se visualiza una tarjeta de vehículo | `vehicle_id`, `variant`, `battery_shown` | Web y móvil | Efecto del indicador (EXP-03) |
| `booking_start` | Se inicia una reserva | `vehicle_id`, `variant` | Web y móvil | Reservas iniciadas |
| `booking_complete` | Se confirma la reserva | `vehicle_id`, `variant` | Web y móvil | Tasa de abandono |
| `booking_cancel` | Se cancela una reserva | `vehicle_id`, `reason` | Web y móvil | Cancelaciones |
| `unlock_request` | El usuario solicita desbloquear | `vehicle_id`, `method` (QR o app) | Web y móvil | Tiempo de desbloqueo |
| `unlock_result` | Llega el estado del desbloqueo | `vehicle_id`, `status`, `duration_ms` | Backend | Tiempo de desbloqueo (percentil 95) |
| `trip_end` | Finaliza un viaje | `trip_id`, `duration`, `distance` | Web y móvil | Viajes por vehículo |
| `nps_submit` | El usuario responde la encuesta | `score` | Web y móvil | NPS |
| `plan_select` | Se elige un plan | `plan_id` | Web y móvil | Preferencia de planes |

**Reglas de privacidad:** los identificadores de usuario se anonimizan, no se registran datos de pago y la analítica se activa solo con el consentimiento del usuario.

*Fuente: Elaboración propia.*

## 8.3. Experimentation

### 8.3.1. To-Be User Stories

Para poder ejecutar los experimentos se necesitan capacidades que hoy no existen en el producto: instrumentación, variantes, encuestas y formularios. Estas historias complementan las 56 definidas en el capítulo III (se numeran a partir de US-57).

**Tabla 8.17. Historias de usuario To-Be**

| ID | Título | Historia | Criterios de aceptación | Experimento |
| --- | --- | --- | --- | --- |
| US-57 | Analítica de la landing | Como equipo de producto, quiero registrar visitas y clics en los llamados a la acción de la landing para medir el interés de los visitantes. | Dado que un visitante abre la landing, cuando hace clic en un botón de acción, entonces se registra el evento `cta_click` con el identificador del botón. | EXP-02 |
| US-58 | Formulario de interés corporativo | Como representante de una empresa, quiero solicitar una demo del plan corporativo para conocer su funcionamiento. | Dado que el visitante completa el formulario con datos válidos, cuando lo envía, entonces se registra la solicitud y se muestra una confirmación. | EXP-02 |
| US-59 | Analítica del flujo de reserva | Como equipo de producto, quiero registrar los eventos del flujo de reserva y desbloqueo para medir tiempos y abandono. | Dado que un usuario inicia una reserva, cuando avanza o abandona, entonces se registran `booking_start`, `booking_complete` o `booking_cancel` con el vehículo y la variante. | EXP-01, EXP-03 |
| US-60 | Variantes de experimento | Como equipo de producto, quiero asignar variantes de forma aleatoria a cada sesión para ejecutar pruebas A/B. | Dado que una sesión nueva entra al garaje, cuando se carga la pantalla, entonces se le asigna la variante A o B de forma estable durante toda la sesión. | EXP-03 |
| US-61 | Indicador de batería y estado | Como usuario, quiero ver la batería y el estado del vehículo en la tarjeta para decidir si lo reservo. | Dado que la sesión está en la variante B, cuando se muestra una tarjeta, entonces aparecen la batería y el estado del vehículo. | EXP-03 |
| US-62 | Medición del tiempo de desbloqueo | Como equipo técnico, quiero registrar el tiempo entre la solicitud y el resultado del desbloqueo para verificar el objetivo de 5 segundos. | Dado que un usuario solicita un desbloqueo, cuando el sistema responde, entonces se guarda la duración en milisegundos y el estado. | EXP-04 |
| US-63 | Encuesta NPS tras el viaje | Como usuario, quiero responder una pregunta breve de satisfacción al terminar mi viaje para dar mi opinión. | Dado que el viaje finalizó, cuando se muestra la encuesta, entonces el usuario puede puntuar de 0 a 10 y el resultado se guarda. | EXP-05 |
| US-64 | Panel de métricas del experimento | Como equipo de producto, quiero consultar en un solo lugar los KPIs de cada experimento para tomar decisiones. | Dado que existen datos registrados, cuando se abre el panel, entonces se muestran los KPIs de la Tabla 8.15 con su meta y su valor actual. | Todos |

*Fuente: Elaboración propia.*

### 8.3.2. To-Be Product Backlog

**Tabla 8.18. Product Backlog To-Be**

| Orden | ID | Título | Experimento | Story Points |
| ---: | --- | --- | --- | ---: |
| 1 | US-59 | Analítica del flujo de reserva | EXP-01, EXP-03 | 5 |
| 2 | US-62 | Medición del tiempo de desbloqueo | EXP-04 | 3 |
| 3 | US-57 | Analítica de la landing | EXP-02 | 3 |
| 4 | US-58 | Formulario de interés corporativo | EXP-02 | 3 |
| 5 | US-60 | Variantes de experimento | EXP-03 | 5 |
| 6 | US-61 | Indicador de batería y estado | EXP-03 | 3 |
| 7 | US-63 | Encuesta NPS tras el viaje | EXP-05 | 3 |
| 8 | US-64 | Panel de métricas del experimento | Todos | 5 |

El orden sigue la prioridad del Question Backlog (Tabla 8.3): primero lo necesario para EXP-01 y EXP-04, luego la landing y el A/B, y al final el piloto y el panel. Los puntos de historia son una estimación inicial del equipo y se ajustarán en la planificación del sprint.

*Fuente: Elaboración propia.*

## 8.4. Experiment Aftermath & Analysis

### 8.4.1. Analysis and Interpretation of Results

**Estado de los experimentos.** Se ejecutó el experimento EXP-04. Los demás experimentos están diseñados (sección 8.1.5) y se ejecutarán cuando se construyan las capacidades de medición de las historias US-57 a US-64; los resultados que no se han obtenido no se reportan.

**Tabla 8.20. Estado de ejecución de los experimentos**

| Experimento | Estado | Resultado |
| --- | --- | --- |
| EXP-01 Usabilidad del flujo de reserva | Planificado | Pendiente |
| EXP-02 Landing y puerta falsa | Planificado | Pendiente (requiere US-57 y US-58) |
| EXP-03 Indicador de batería (A/B) | Planificado | Pendiente (requiere US-60 y US-61) |
| EXP-04 Tiempo de desbloqueo | **Ejecutado** | Hipótesis H-06 confirmada para la parte de software |
| EXP-05 Piloto B2B | Planificado | Pendiente |

**Resultados de EXP-04.** Se ejecutó un script de medición contra el backend desplegado en Render (https://backend-weride-2wpb.onrender.com). Después de despertar el servicio y de tres pasadas de calentamiento que no se cuentan, se midieron 35 flujos de desbloqueo. Cada flujo consiste en crear una solicitud de desbloqueo (`POST /api/v1/unlockRequests`) y actualizar su estado a desbloqueado (`PATCH /api/v1/unlockRequests/{id}`), y el tiempo se mide desde el cliente de prueba.

**Tabla 8.21. Resultados de EXP-04 (n = 35)**

| Estadístico | Valor |
| --- | --- |
| Media | 1 675,3 ms |
| Desviación estándar | 293,2 ms |
| Mínimo | 1 431,6 ms |
| Máximo | 2 623,3 ms |
| Percentil 95 | 2 354,1 ms |
| Intervalo de confianza del 95 % para la media | 1 578 ms a 1 773 ms |
| Mediciones dentro de 5 s | 35 de 35 (100 %) |

![Resultados de la ejecución de EXP-04](assets/exp04-resultados.png)

*Figura 8.1. Salida del script de medición de EXP-04.*

**Interpretación.** La hipótesis H-06 planteaba que al menos el 95 % de los desbloqueos respondería en 5 segundos o menos. Se obtuvo el 100 %, con un tiempo medio de 1,68 s y un percentil 95 de 2,35 s, es decir, menos de la mitad del límite. Como la desviación estándar observada (0,29 s) fue mucho menor que la supuesta para el cálculo de la muestra (3 s), las 35 mediciones resultan más que suficientes para el margen de error planteado. La variación entre mediciones es baja; el valor máximo (2,62 s) es un caso aislado.

**Limitaciones.** Los vehículos están simulados, por lo que el resultado mide la latencia del software (red desde el cliente, API y base de datos) y no el tiempo de respuesta del hardware IoT real. Además, la medición incluye el tiempo de red entre el cliente de prueba y el servicio en la nube, y se hizo con el plan gratuito de Render, de modo que en otro plan o ubicación los tiempos podrían variar.

**Conclusión.** La hipótesis H-06 se confirma para la parte de software: el servicio no es un obstáculo para cumplir el objetivo de 5 segundos. Queda por validar la latencia con hardware real.

### 8.4.2. Re-scored and Re-prioritized Question Backlog

A partir de lo aprendido en EXP-04 se actualiza el Question Backlog de la Tabla 8.3: la pregunta Q-04 se responde para el software y se agrega una nueva pregunta sobre el hardware. Las demás conservan su prioridad, y el orden se ajusta para empezar por las que más impacto tienen y no tienen respuesta aún.

**Tabla 8.22. Question Backlog repuntuado y repriorizado**

| Prioridad | Pregunta | Estado | Cambio respecto a la versión anterior |
| ---: | --- | --- | --- |
| 1 | Q-02, Q-03 (flujo de reserva y desbloqueo) | Abierta | Sube a primera prioridad: ahora se sabe que el servicio responde rápido, así que el riesgo restante está en la usabilidad |
| 2 | Q-05 (indicador de batería) | Abierta | Sin cambio de contenido; pasa de la posición 3 a la 2 |
| 3 | Q-01, Q-06 (landing y planes) | Abierta | Sube de la posición 4 a la 3 |
| 4 | Q-07 (interés corporativo) | Abierta | Sube de la posición 5 a la 4 |
| 5 | Q-08, Q-09, Q-10 (uso recurrente, NPS, disponibilidad) | Abierta | Sube de la posición 6 a la 5 |
| 6 | **Q-11 (nueva):** ¿Cuál es la latencia del desbloqueo con hardware IoT real? | Nueva | Surge de la limitación de EXP-04 |
| — | Q-04 (tiempo de desbloqueo del software) | **Respondida** | Hipótesis H-06 confirmada con 35 de 35 mediciones dentro de 5 s |

*Fuente: Elaboración propia.*

## 8.5. Continuous Learning

### 8.5.1. Shareback Session Artifacts: Learning Workflow

El aprendizaje de cada experimento se comparte con el equipo en una sesión breve de revisión (*shareback session*) al cerrar cada experimento, con el siguiente flujo:

1. **Planificar:** se confirma la pregunta, la hipótesis, la métrica y la muestra de la Experiment Card.
2. **Ejecutar:** se corre el experimento en las condiciones definidas y se registran los datos con el plan de seguimiento.
3. **Analizar:** se comparan los resultados con la meta de la hipótesis.
4. **Compartir:** en la sesión de revisión se presenta una **Learning Card** con el resultado y la decisión.
5. **Decidir:** se elige entre persistir (mantener), pivotar (cambiar el enfoque) o detener, y se actualizan el Product Backlog y el Question Backlog.

**Tabla 8.19. Plantilla de Learning Card**

| Campo | Contenido |
| --- | --- |
| Experimento | ID y nombre |
| Hipótesis | Enunciado de la hipótesis probada |
| Resultado | Valor obtenido de la métrica frente a la meta |
| ¿Se confirmó la hipótesis? | Sí, no o parcialmente |
| Aprendizaje clave | Qué se descubrió |
| Decisión | Persistir, pivotar o detener |
| Acciones | Historias o tareas que se agregan o se cambian en el backlog |

**Tabla 8.23. Learning Card de EXP-04**

| Campo | Contenido |
| --- | --- |
| Experimento | EXP-04 — Tiempo de respuesta del flujo de desbloqueo |
| Hipótesis | H-06: el desbloqueo digital responde con rapidez suficiente para no generar fricción (95 % de los desbloqueos en 5 s o menos) |
| Resultado | 35 de 35 mediciones dentro de 5 s; media de 1,68 s; percentil 95 de 2,35 s |
| ¿Se confirmó la hipótesis? | Sí, para la parte de software |
| Aprendizaje clave | La API y la base de datos no limitan el tiempo de desbloqueo. El riesgo restante está en la latencia del hardware IoT, que aún está simulado. |
| Decisión | Persistir con la arquitectura actual del flujo de desbloqueo |
| Acciones | Agregar la pregunta Q-11 al Question Backlog; incorporar la medición de la latencia (US-62) en el sistema para repetir el experimento con hardware real |

Los resultados de cada experimento se registran en una Learning Card una vez ejecutado, y no se reportan resultados de experimentos que aún no se hayan realizado.

## Conclusiones
- El proyecto de micromovilidad eléctrica compartida responde a necesidades reales de movilidad en áreas urbanas peruanas: congestión, tiempos de traslado elevados, y demanda por alternativas más económicas y sostenibles. La combinación de scooters, bicicletas y motos eléctricas gestionadas desde una única plataforma web representa una propuesta con alto potencial de adopción, especialmente en segmentos juveniles y corporativos.
- La identificación de dos segmentos prioritarios —jóvenes universitarios y empresas con planes de suscripción— es coherente con los hallazgos cualitativos. Los primeros buscan conveniencia, bajo costo y métodos de pago locales (Yape/Plin); las empresas buscan soluciones de movilidad para colaboradores y valoran la previsibilidad de costos y la imagen de sostenibilidad. Esta segmentación favorece estrategias de adquisición y retención diferenciadas.
- La propuesta de combinar pago por uso (desbloqueo + tarifa por minuto) con pases diarios, mensuales y corporativos ofrece una mezcla adecuada para equilibrar ingresos inmediatos y recurrentes. Los precios sugeridos y el descuento universitario crean incentivos para adopción temprana y fidelización. No obstante, la rentabilidad dependerá de la tasa de utilización por vehículo (objetivo mínimo: 4–5 viajes/día) y de una gestión eficiente de costos operativos (mantenimiento, recarga, logística).
- Las funciones críticas —búsqueda en tiempo real (GPS/IoT), mapa interactivo, reservas con temporizador y desbloqueo digital (QR/PIN/IoT)— están correctamente priorizadas. Estas funcionalidades garantizan una experiencia simple y confiable desde la web, mientras que el desbloqueo digital y la gestión remota son componentes esenciales para control y seguridad de la flota.

  

<ul>
  <li>Alexander, I., & Beus-Dukic, L. (2009). <em>Discovering Requirements: How to Specify Products and Services</em>. Wiley.</li>
  <li>Cohn, M. (2004). <em>User Stories Applied: For Agile Software Development</em>. Addison-Wesley.</li>
  <li>Gamma, E., Helm, R., Johnson, R., & Vlissides, J. (1994). <em>Design Patterns: Elements of Reusable Object-Oriented Software</em>. Addison-Wesley.</li>
  <li>Kruchten, P. (2003). <em>The Rational Unified Process: An Introduction</em>. Addison-Wesley.</li>
  <li>Newman, S. (2015). <em>Building Microservices: Designing Fine-Grained Systems</em>. O’Reilly Media.</li>
  <li>Sommerville, I. (2016). <em>Software Engineering</em> (10th ed.). Pearson.</li>
  <li>W3C. (2024). <em>HTML &amp; CSS Standards</em>. Recuperado de: <a href="https://www.w3.org/" target="_blank" rel="noopener">https://www.w3.org/</a></li>
  <li>Mozilla Developer Network (MDN). (2024). <em>JavaScript Guide</em>. Recuperado de: <a href="https://developer.mozilla.org/es/docs/Web/JavaScript/Guide" target="_blank" rel="noopener">https://developer.mozilla.org/es/docs/Web/JavaScript/Guide</a></li>
  <li>GitHub Docs. (2024). <em>GitHub Pages Documentation</em>. Recuperado de: <a href="https://docs.github.com/en/pages" target="_blank" rel="noopener">https://docs.github.com/en/pages</a></li>
  <li>Stripe Docs. (2024). <em>Stripe Payments Integration Guide</em>. Recuperado de: <a href="https://stripe.com/docs" target="_blank" rel="noopener">https://stripe.com/docs</a></li>
  <li>Figma. (2024). <em>Figma Design Documentation</em>. Recuperado de: <a href="https://help.figma.com/" target="_blank" rel="noopener">https://help.figma.com/</a></li>
  <li>Google Maps Platform. (2024). <em>Maps JavaScript API Documentation</em>. Recuperado de: <a href="https://developers.google.com/maps/documentation/javascript" target="_blank" rel="noopener">https://developers.google.com/maps/documentation/javascript</a></li>
  <li>Node.js Foundation. (2024). <em>Node.js Documentation</em>. Recuperado de: <a href="https://nodejs.org/en/docs/" target="_blank" rel="noopener">https://nodejs.org/en/docs/</a></li>
  <li>Vue.js. (2024). <em>Vue.js Guide</em>. Recuperado de: <a href="https://vuejs.org/guide/introduction.html" target="_blank" rel="noopener">https://vuejs.org/guide/introduction.html</a></li>
</ul>

## Anexos.

<a href="https://www.youtube.com/watch?v=UVP-NVpaT6Y" target="_blank" rel="noopener">About The Product</a>

<a href="https://github.com/OpenSource-Grupo-4" target="_blank" rel="noopener">Organización</a>

<a href="https://github.com/OpenSource-Grupo-4/ReportTB1" target="_blank" rel="noopener">Reporte del Proyecto</a>

<a href="https://github.com/OpenSource-Grupo-4/Frontend-WeRide" target="_blank" rel="noopener">Repositorio de Frontend Web Application</a>

<a href="https://frontend-we-ride-lake.vercel.app" target="_blank" rel="noopener">Deploy de Frontend Web Application</a>

<a href="https://github.com/OpenSource-Grupo-4/Backend-WeRide" target="_blank" rel="noopener">Repositorio de Backend Web Services</a>

<a href="https://backend-weride-2wpb.onrender.com/swagger-ui/index.html" target="_blank" rel="noopener">Deploy de Backend Web Services</a>

<a href="https://github.com/OpenSource-Grupo-4/Landing-Page" target="_blank" rel="noopener">Repositorio de Landing Page</a>

<a href="https://opensource-grupo-4.github.io/Landing-Page" target="_blank" rel="noopener">Deploy de Landing Page</a>

<a href="https://www.canva.com/design/DAGzltc5qz0/jV9yXK8Nme4XSOk6AUhFgg/edit" target="_blank" rel="noopener">Presentación de Canvas</a>

<a href="https://www.figma.com/design/6R0aWHPQEpwX8DyWLrCHmd/Open-Source-2025-2?t=moMeoEwSHQRhgL2O-0" target="_blank" rel="noopener">Figma</a>
