# Capítulo VI: Product Implementation, Validation & Deployment

## 6.1. Software Configuration Management

Esta sección detalla el marco normativo y técnico para la Gestión de Configuración de Software de **SATECHO**, estableciendo las directrices fundamentales que aseguran la consistencia operativa durante todo el ciclo de vida del desarrollo. Al abarcar la administración estructurada del código fuente, la configuración estandarizada de los entornos de trabajo y la orquestación de los procesos de despliegue, este marco metodológico busca salvaguardar la integridad, la seguridad y la trazabilidad de nuestra solución tecnológica; es por ello que, con la implementación de estas convenciones estratégicas, garantizamos una colaboración altamente eficiente y sincronizada entre todos los miembros del equipo, consolidando así un ecosistema de desarrollo robusto que minimiza los riesgos, facilita la resolución de conflictos y potencia la entrega continua de valor bajo los más exigentes estándares de calidad

### 6.1.1. Software Development Environment Configuration

Se especifican y describen las herramientas y productos de software que los miembros del equipo deben utilizar durante el ciclo de vida del desarrollo de **Agrosafe**, para garantizar la colaboración eficiente y la consistencia en el proyecto. Estas herramientas cubren todas las áreas clave, incluyendo la gestión del proyecto, el diseño UX/UI, el desarrollo, las pruebas y el despliegue.

| Actividad               | Herramienta / Guía                                     | Propósito                                                                          | Tipo de acceso / Ruta                                                                                                            |
| ----------------------- | ------------------------------------------------------ | ---------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| Project Management      | Jira                                                   | Seguimiento de backlog, tareas, sprints y desempeño del equipo.  | [https://www.atlassian.com/es/software/jira](https://www.atlassian.com/es/software/jira)                                                                                               |
| Requirements Management | Gherkin Conventions                                    | Escritura de historias de usuario y criterios de aceptación en formato Given/When/Then.                       | [https://cucumber.io/docs/gherkin/](https://cucumber.io/docs/gherkin/)                                                                   |
| Product Design          | Structurizr C4                                         | Modelado de la arquitectura del sistema mediante diagramas de contexto, contenedores y componentes.                 | [https://playground.structurizr.com/](https://playground.structurizr.com/)                                                           |
| Product Design          | PlantUML                                               | Creación de diagramas de secuencia y de clases mediante código.             | [https://plantuml.com/](https://plantuml.com/)                                                           |
| Product Design          | Figma                                                  | Diseño de interfaces (UI) y prototipado de experiencia de usuario (UX) para web y móvil.                 | [https://figma.com](https://figma.com)                                                                                            |
| Product Design          | Cirkit Designer                                                  | Simulación y diseño de circuitos para los dispositivos IoT (ESP32).                                           | [https://app.cirkitdesigner.com](https://app.cirkitdesigner.com)                                                                                            |
| Software Development    | HTML5, CSS y JavaScript / Visual Studio Code                     | Desarrollo y maquetación del sitio web estático de la organización.                                              | [https://code.visualstudio.com](https://code.visualstudio.com)                        |
| Software Development    | Flutter y Dart / Android Studio                        | Desarrollo de la aplicación móvil multiplataforma.                                               | [https://developer.android.com/studio?hl=es-419](https://developer.android.com/studio?hl=es-419)                                                               |
| Software Development    | VueJS / Visual Studio Code                        | Desarrollo de la interfaz de la aplicación web principal.                                                  | [https://code.visualstudio.com](https://code.visualstudio.com)                                                         |
| Software Development    | Java y Spring Boot / IntelliJ IDEA                     | Desarrollo de la lógica de negocio y servicios del REST API.                                      | [https://www.jetbrains.com/idea/](https://www.jetbrains.com/idea/)                                                         |
| Software Development    | Python y Flask / Visual Studio Code                               | Desarrollo de la capa Edge para el procesamiento de datos IoT.                                    | [https://code.visualstudio.com](https://code.visualstudio.com/)                                    
| Software Development    | C++ / Arduino IDE                                      | Programación de firmware y lógica embebida para sensores y actuadores.                       | [https://www.arduino.cc/en/software](https://www.arduino.cc/en/software)                                                         ||
| Software Development    | Git + GitHub                                           | Control de versiones distribuido y gestión colaborativa del código.                                           | [https://github.com](https://github.com)                                                                                          |
| Software Testing        | JUnit5 & Mockito                                         | Pruebas unitarias, de integración y creación de dobles de prueba para el backend.                             | [https://junit.org/](https://junit.org/) / [https://site.mockito.org/](https://site.mockito.org/)           |
| Software Testing        | pytest                                                 | Automatización de pruebas unitarias para los servicios en Python (Edge).                                                | [https://docs.pytest.org/](https://docs.pytest.org/)   |
| Software Deployment     | Github Pages                                                | Hosting y despliegue del sitio web estático informativo.                                       | [https://docs.github.com/es/pages](https://docs.github.com/es/pages)                                                |
| Software Deployment     | Vercel                                                 | Plataforma de despliegue continuo para la aplicación web (Vue.js).                                          | [https://vercel.com/](https://vercel.com/)                                                |
| Software Deployment     | Firebase App Distribution                              | Distribución de versiones beta de la aplicación móvil para testing.                                        | [https://firebase.google.com/docs/app-distribution](https://firebase.google.com/docs/app-distribution)                                                |
| Software Deployment     | Azure App Service                                                | Alojamiento y escalado del REST API en la nube.                                          | [https://azure.microsoft.com/es-es/products/app-service/web](https://azure.microsoft.com/es-es/products/app-service/web)                                                | 
| Software Documentation  | Swagger                                                | Documentación interactiva de los endpoints y contratos del API.                      | [https://swagger.io/](https://swagger.io/)                                               |  

### 6.1.2. Source Code Management

En esta sección se define el marco de gobernanza para la gestión del código fuente de SATECHO, utilizando GitHub como plataforma centralizada de control de versiones. El equipo implementa una estrategia de ramificación estructurada y estándares de comunicación que garantizan la trazabilidad, la integridad y la calidad del software en cada etapa del ciclo de vida.

**Ecosistema de Repositorios**

La solución SATECHO se descompone en repositorios modulares para facilitar el mantenimiento y el despliegue independiente de sus componentes.

#### Repositorios de productos de software

| Producto de software | URL del repositorio                         | 
| -------------------- | --------------------------------------------| 
| Landing Page         | [https://github.com/S-A-T-E-C-H-O/Landing-Page-SATECHO](https://github.com/S-A-T-E-C-H-O/Landing-Page-SATECHO)                                            | 
| Web Application      | [https://github.com/S-A-T-E-C-H-O/Web-Application-SATECHO](https://github.com/S-A-T-E-C-H-O/Web-Application-SATECHO)                                            |
| Mobile Application   | [https://github.com/S-A-T-E-C-H-O/Mobile-Application-SATECHO](https://github.com/S-A-T-E-C-H-O/Mobile-Application-SATECHO)                                            |
| REST Services API    | [https://github.com/S-A-T-E-C-H-O/Web-API-Service-SATECHO](https://github.com/S-A-T-E-C-H-O/Web-API-Service-SATECHO)                                            |
| Edge Services API    | [https://github.com/S-A-T-E-C-H-O/Edge-API-Service-SATECHO](https://github.com/S-A-T-E-C-H-O/Edge-API-Service-SATECHO)                                            |
| Embedded Application | [https://github.com/S-A-T-E-C-H-O/Embedded-Application-Satecho](https://github.com/S-A-T-E-C-H-O/Embedded-Application-Satecho)                                            |

**GitFlow Workflow**

Se adopta el modelo GitFlow para gestionar el flujo de trabajo colaborativo, permitiendo un desarrollo paralelo organizado y lanzamientos controlados.

- main: Rama productiva que contiene exclusivamente código estable y verificado.

- develop: Rama de integración principal donde convergen las nuevas funcionalidades.

- deployment: Rama dedicada a la orquestación de despliegues en entornos de staging y pre-producción.

**Ramas de Apoyo:**

- Feature Branches (feature/): Utilizadas para el desarrollo de nuevas funcionalidades. Se originan y finalizan en develop.
  - Ejemplo: `feature/sensor-humidity-integration`

- Release Branches (release/): Ramas de estabilización para preparar un nuevo lanzamiento oficial
  - Ejemplo: `release/v1.0.0`

- Hotfix Branches (hotfix/): Ramas de emergencia para corregir errores críticos en main. Se sincronizan con main y develop.
  - Ejemplo: `hotfix/api-connection-timeout`

**Semantic Versioning**

Para el control de versiones del software, se aplica el estándar Semantic Versioning (SemVer) bajo el formato `vX.Y.Z`:

- X (Major): Cambios estructurales o de ruptura (breaking changes).

- Y (Minor): Incorporación de nuevas funcionalidades compatibles con versiones anteriores.

- Z (Patch): Correcciones menores, parches de seguridad y optimizaciones.

**Conventional Commits**

En SATECHO, el historial de Git no es simplemente un registro de cambios, sino la narrativa técnica de la evolución de nuestro producto; por lo tanto, para garantizar que cada contribución sea legible, rastreable y automatizable, adoptamos el estándar de *Conventional Commits*. Este marco transforma cada "commit" en una unidad de información con significado semántico inmediato.

```bash
<type>[optional scope]: <description>
```

**I. Taxonomía de Cambios (Types)**

Definimos las siguientes categorías para clasificar la intención de cada intervención en el ecosistema:

- feat: Introducción de una nueva capacidad o funcionalidad (asociada a ramas feature/).

- fix: Resolución de bugs, errores de lógica o fallos técnicos detectados.

- docs: Modificaciones en la documentación técnica del producto (archivos README, guías de arquitectura o comentarios de código).

- refactor: Mejoras en la estructura del código que no alteran el comportamiento externo (limpieza, legibilidad o deuda técnica).

- chore: Tareas de mantenimiento, actualización de dependencias o configuraciones de entorno (ej. initial commit).

- test: Creación, actualización o reparación de pruebas unitarias, de integración o de carga.

**II. El Componente de Contexto (Scope)**

El scope es fundamental para identificar qué módulo está siendo intervenido. Debe escribirse entre paréntesis y referenciar de forma precisa el componente afectado (ej. iot, api, ui-web, auth).

**III. Semántica de la Descripción**

La descripción es el núcleo del mensaje y debe cumplir rigurosamente con los siguientes estándares de calidad:

- Idioma: Debe redactarse exclusivamente en inglés, como lengua estándar de la industria.

- Modo Imperativo: El mensaje debe leerse como una orden al código (ej. "add", no "added" o "adds").

- Formato: Escritura en minúsculas y finalización obligatoria con un punto final (.).

- Concisión: Debe ser un resumen directo del impacto del cambio, evitando detalles extensos que pertenecen a la sección opcional del body.

**IV. Anatomía de un Commit de Excelencia**

Un mensaje que cumple con nuestro estándar de ingeniería se visualiza de la siguiente manera:

```bash
feat(iot): implement soil moisture sensor calibration logic
```

**Proceso de Code Review**

Todo cambio propuesto debe someterse a un proceso de revisión riguroso mediante Pull Requests (PRs) antes de ser integrado en las ramas de jerarquía superior (develop o main).

- **Requisito de Aprobación:** Al menos un revisor debe validar el código para asegurar el cumplimiento de los estándares de arquitectura, seguridad y mantenibilidad.

- **Validación:** El proceso busca mitigar la introducción de bugs y garantizar que la nueva contribución se alinee con el diseño sistémico de SATECHO.

### 6.1.3. Source Code Style Guide & Conventions

En **SATECHO**, el código no solo debe ser funcional, sino también legible, mantenible y estéticamente profesional. Esta guía establece el "lenguaje común" para nuestro equipo multidisciplinario, asegurando que cualquier desarrollador pueda navegar por el ecosistema del proyecto con total claridad.

**Fundamentos Globales de Nomenclatura**

Independientemente del lenguaje de programación, aplicamos tres reglas inquebrantables:

1. **Código en Inglés:** Todo el léxico técnico (variables, métodos, clases, comentarios técnicos y nombres de archivos) se redactará exclusivamente en inglés para mantener la compatibilidad con estándares globales de la industria.

2. **Significado sobre Brevedad:** Preferimos nombres descriptivos como sensorReadingInterval sobre abreviaturas ambiguas como sri.

3. **Consistencia de Casos:**

- camelCase: Utilizado para variables, funciones y métodos. (Ej: getSoilMoisture()).

- PascalCase: Reservado para clases, interfaces, tipos y componentes. (Ej: AuthService).

- snake_case: Exclusivo para nombres de archivos y recursos físicos. (Ej: main_navigation.dart).

- kebab-case: Utilizado en clases CSS y selectores HTML. (Ej: btn-primary).

**Estándares por Tecnología**

#### Capa Web (HTML5 & CSS3)

Nos regimos por la [Google HTML/CSS Style Guide.](https://google.github.io/styleguide/htmlcssguide.html)

- **Semántica:** Uso obligatorio de etiquetas main, section, article y nav.

- **CSS BEM (Block Element Modifier):** Estructuramos las clases para evitar colisiones de estilos
  - Bloque: `.card`
  - Elemento: `.card__title`
  - Modificador: `.card__title--highlighted`

```html
<!-- Ejemplo de implementación semántica y BEM -->
<section class="crop-status">
  <h2 class="crop-status__title">Niveles de Humedad</h2>
  <button class="btn btn--success">Actualizar</button>
</section>
```

#### Lógica de Interacción (JavaScript ES6+)

Basado en la [Google JavaScript Style Guide.](https://google.github.io/styleguide/jsguide.html)

- **Inmutabilidad:** Priorizamos const sobre let. El uso de var queda estrictamente prohibido.

- **Programación Funcional:** Preferencia por funciones flecha (`=>`) y métodos de array (`map`, `filter`, `reduce`).

```javascript
const formatSensorData = (data) => {
  return data.map(reading => reading.toFixed(2));
};
```

#### Backend Robusto (Java & Spring Boot)

Seguimos los estándares de Clean Code y la guía de Google para Java.

- **Encapsulamiento:** Todo atributo de clase debe ser `private` y el acceso a métodos debe ser explícito (`public`, `protected`).

- **Inyección de Dependencias:** Preferimos la inyección por constructor sobre el uso de `@Autowired` en campos.

```java
public class SensorController {
    private final SensorService sensorService;

    public SensorController(SensorService sensorService) {
        this.sensorService = sensorService;
    }

    public ResponseEntity<String> getHumidity(Long id) {
        return ResponseEntity.ok("Reading: " + sensorService.getById(id));
    }
}
```

#### Desarrollo Móvil (Dart & Flutter)

Aplicamos las directrices de [Effective Dart.](https://dart.dev/effective-dart)

- **Tipado Fuerte:** Se debe declarar explícitamente el tipo de dato para evitar errores en tiempo de ejecución.

- **Widgets:** Dividir las interfaces en widgets pequeños y reutilizables.

```dart
class MoistureDisplay extends StatelessWidget {
  final double value;

  const MoistureDisplay({required this.value});

  @override
  Widget build(BuildContext context) {
    return Text('Humedad: $value%');
  }
}
```

**Comunicación del Negocio (Gherkin)**

Para nuestras pruebas de aceptación, utilizamos el lenguaje **Gherkin** con el fin de que los stakeholders entiendan el comportamiento del sistema sin leer código fuente.

- **Claridad:** Los archivos `.feature` deben describir procesos de negocio, no interacciones de UI (ej: usar "Inicia sesión" en lugar de "Hace click en el botón azul").

```gherkin
Feature: Monitoreo de Cultivos
  As a farmer
  I want to receive an alert when the soil is dry
  So that I can irrigate my crops on time

  Scenario: Detección de humedad baja
    Given the humidity sensor is active
    When the moisture level drops below 20%
    Then the system sends a notification to the mobile app
```

#### 6.1.4. Software Deployment Configuration

Para esta sección, el despliegue no es el final del camino, sino el inicio de la entrega de valor. Esta sección describe los protocolos y plataformas utilizados para transformar nuestro código fuente en productos digitales accesibles y funcionales. Hemos diseñado un ecosistema de despliegue híbrido que aprovecha lo mejor de cada proveedor de nube para garantizar alta disponibilidad y rendimiento.

#### Landing Page (GitHub Pages)

Nuestro portal informativo se despliega como un sitio estático optimizado, garantizando tiempos de carga mínimos y seguridad total.

- **Plataforma:** GitHub Pages.

- **Proceso de Despliegue:**

1. **Preparación: **Asegurar que el archivo principal sea un index.html en la raíz del repositorio SATECHO-static.

2. **Configuración de Origen:** Acceder a los Settings del repositorio en GitHub y navegar a la sección Pages.

3. **Activación:** Seleccionar la rama main como fuente de despliegue.

4. **Automatización:** GitHub generará automáticamente una URL bajo el dominio github.io. Cada push a la rama main actualizará el sitio en tiempo real.

#### Web Application (Vercel)

La aplicación administrativa de SATECHO, desarrollada en Vue.js, requiere un entorno ágil que soporte el renderizado moderno y despliegues atómicos.

- **Plataforma:** Vercel.

- Guía Detallada de Despliegue:

1. **Vinculación:** Iniciar sesión en Vercel e importar el repositorio `SATECHO-WebApp`.

2. **Configuración de Framework:** Vercel detectará automáticamente que se trata de un proyecto Vue.js. Validar que el comando de build sea `npm run build` y el directorio de salida sea `dist`.

3. **Variables de Entorno:** Configurar las variables `VUE_APP_API_URL` para apuntar a nuestro backend en Azure.

4. **Deployment:** Ejecutar el despliegue inicial. Vercel proporcionará una URL de previsualización para cada Pull Request y una URL productiva para la rama main.

#### Web Services - Backend (Azure App Service)

El corazón lógico de SATECHO, construido en Java con Spring Boot, se aloja en un entorno empresarial que garantiza escalabilidad y seguridad de datos.

- **Plataforma:** Azure App Service.

- **Proceso de Despliegue:**

1. **Instancia de Servicio:** Se crea un Web App en Azure seleccionando el stack de ejecución Java 17+ y el servidor web embebido.

2. **Pipeline de CI/CD:** Configuramos un archivo de flujo de trabajo en GitHub Actions que compile el proyecto usando Maven (mvn clean package).

3. **Publicación:** El artefacto .jar generado se envía automáticamente a Azure App Service mediante el perfil de publicación configurado en los Secrets de GitHub.

4. **Monitoreo:** Se habilita Application Insights para rastrear el rendimiento de los endpoints y posibles excepciones en tiempo real.

#### Mobile Application (Firebase App Distribution)

Para nuestra fase de prototipado y validación con usuarios clave, utilizamos un canal de distribución ágil antes del lanzamiento en tiendas oficiales.

- **Plataforma:** Firebase App Distribution.

- **Proceso de Despliegue:**

1. **Compilación:** Generar el paquete binario de la aplicación (.apk para Android o .ipa para iOS) desde el entorno de Flutter.

2. **Carga en Firebase:** Subir el binario a la consola de Firebase en la sección de App Distribution.

3. **Gestión de Testers:** Definir los correos electrónicos de los usuarios de prueba en SATECHO.

4. **Instalación:** Los usuarios reciben una invitación por correo para descargar la aplicación de forma segura a través de la app App Tester.

#### Embedded IoT Application (Firmware Over-The-Air)

El despliegue en hardware requiere un enfoque de actualización remota para evitar la intervención física en cada sensor instalado en el campo.

- **Método:** Actualización remota de firmware (OTA) y Flasheo Serial inicial.

- **Proceso de Despliegue:**

1. **Flasheo Inicial:** Durante la fabricación, se carga la versión estable mediante el Arduino IDE o PlatformIO.

2. **Preparación de Binarios:** Las nuevas versiones se compilan en archivos `.bin.`

3. **Almacenamiento de Updates:** Los binarios se cargan en Azure Blob Storage, el cual actúa como nuestro repositorio de firmware.

4. **Sincronización:** Los dispositivos ESP32 están programados para consultar periódicamente un endpoint de control. Si detectan una versión superior, descargan el binario de forma segura y reinician el sistema con el nuevo firmware.

<div class="page"></div>

## 6.2. Landing Page, Services & Applications Implementation

Tras consolidar los cimientos estratégicos del proyecto —trasladando los requisitos de negocio hacia un diseño de arquitectura robusto (C4 y diagramas de clase) y validando la experiencia de usuario (UX) mediante prototipos de alta fidelidad— entramos en la fase de materialización digital. En este apartado, la abstracción se convierte en ejecución: cada componente de la solución, desde la lógica embebida en los sensores hasta la interfaz de gestión en la nube, se desarrolla bajo un estándar de ingeniería de software de alto nivel.

El ecosistema de SATECHO se despliega a través de una suite de productos interconectados que comprenden:

- **Interfaces de Usuario:** Landing Page (captación), Aplicación Web (administración) y Aplicación Móvil (monitoreo en campo).

- **Núcleo de Datos:** REST API (procesamiento central) y Edge Services (gestión de latencia).

- **Hardware Layer:** Aplicación embebida para el control y lectura de sensores en tiempo real.

Para garantizar una entrega continua y controlada, la implementación se ha orquestado en tres ciclos iterativos (Sprints). Cada Sprint actúa como un hito evolutivo donde los objetivos definen el alcance técnico, permitiendo que la solución crezca de forma modular, segura y, sobre todo, alineada con las necesidades reales del sector agrícola.

### 6.2.1. Sprint 1

Dentro de este primer sprint, detallamos el proceso completo de implementación, pruebas, documentación y despliegue de los distintos componentes que conforman la solución DittoBox. Esto incluye el desarrollo de nuestra Landing Page, que sirve como punto de entrada y presentación de nuestro producto al público general, así como la implementación de los Servicios Web, Aplicaciones Web, Aplicaciones Móviles y Aplicaciones Embebidas que constituyen el núcleo funcional de nuestra propuesta.

A lo largo de esta sección, explicamos cómo hemos abordado cada fase del ciclo de vida del desarrollo de software para estos componentes, desde la planificación inicial y el diseño, hasta la ejecución de pruebas y el despliegue en entornos de producción. Detallamos las tecnologías utilizadas, los desafíos enfrentados y las soluciones implementadas para asegurar que cada componente cumpla con los requisitos establecidos y proporcione una experiencia de usuario óptima.

#### 6.2.1.1. Sprint Planning 1

<table>
  <tr>
    <td>Sprint #</td>
    <td>Sprint 1</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Sprint Planning Background</strong></td>
  </tr>
  <tr>
    <td>Date</td>
    <td>2026-05-06</td>
  </tr>
  <tr>
    <td>Time</td>
    <td>21:35 p.m (GMT-5)</td>
  </tr>
  <tr>
    <td>Location</td>
    <td>Remoto, mediante la plataforma de reuniones Discord</td>
  </tr>
  <tr>
    <td>Prepared By</td>
    <td>Huamani Sánchez, José Diego</td>
  </tr>
  <tr>
    <td>Attendees (to planning meeting)</td>
    <td>Estrada Cajamune, Abraham Andrés / Gamio Upiachihua, Brenda Lucía / Quispe Erasmo, Raul Ronaldo / Palacios, Yasser Renteria </td>
  </tr>
  <tr>
    <td colspan="2"><strong>Sprint Goal & User Stories</strong></td>
  </tr>
  <tr>
    <td>Sprint 1 Goal</td>
    <td>
<strong>Nuestro objetivo</strong> es establecer la identidad digital de SATECHO y validar el flujo de interacción principal de la plataforma. <br>
<strong>Creemos que esto</strong> genera confianza inicial en el mercado y proporciona a nuestros clientes del sector agrícola capacidades para la toma de decisiones basadas en datos. <br>
<strong>Esto se confirmará cuando</strong> los clientes potenciales interactúen con la propuesta de valor en nuestra página de inicio y los usuarios internos puedan autenticarse de forma segura y visualizar los datos preliminares de los sensores a través del panel de control.
    </td>
  </tr>
  <tr>
    <td>Sprint 1 Velocity</td>
    <td>41</td>
  </tr>
  <tr>
    <td>Sum of Story Points</td>
    <td>41</td>
  </tr>
</table>

#### 6.2.1.2. Aspect Leaders and Collaborations

Iniciamos nuestra trayectoria transformando la complejidad en orden. Durante este Sprint 1, definimos los pilares estratégicos del proyecto mediante una arquitectura de contextos delimitados, blindando la lógica de negocio desde la seguridad hasta el monitoreo operativo en los exigentes entornos de retail y restaurantes. Esta visión se traduce en acción a través de nuestra Matriz LACX, una brújula de colaboración que asigna responsabilidades claras para garantizar la cohesión del producto. Bajo este esquema de trabajo, el equipo ha convergido para dar vida a 41 puntos de historia, asegurando que cada funcionalidad no sea solo un requisito cumplido, sino una pieza clave de una infraestructura escalable y resiliente.

| Team Member (Last Name, First Name) |  GitHub Username  |     IAM     |     OnBoarding    | i18n | Dashboard |
| :---------------------------------- | :----------------: | :---------: | :---------: | :-------------------: | :--------------: 
| Huamani Sánchez, José Diego       |  `ProgramadorHuamani`  | **L** |            |           C           |                  |
| Estrada Cajamune, Abraham Andrés        |     `Abraham0310`     |            |      **L**      |           C           |        C        |
| Gamio Upiachihua, Brenda Lucía         |     `B-Gamio`     |            |      C      |                      |          **L**        |
| Quispe Erasmo, Raul Ronaldo      |    `Raul-QE`   |      C      |            |                      |        C        |
| Palacios, Yasser Renteria        |      `Mitos20`     |            |      C      |      **L**      |                  |

#### 6.2.1.3. Sprint Backlog 1

Alineado con los objetivos estratégicos definidos en nuestra planificación, este backlog constituye la hoja de ruta técnica diseñada para materializar el primer incremento funcional de la plataforma. El propósito central de este ciclo se divide en dos frentes críticos: en primer lugar, el despliegue de una Landing Page de alto impacto orientada a proyectar el valor de negocio del ecosistema; en segundo lugar, la construcción de la interfaz frontend de la Aplicación Web. Esta última habilitará las capacidades esenciales que permitirán a los administradores de restaurantes y tiendas retail gestionar perfiles, autenticarse de manera segura, controlar existencias en inventario, administrar dispositivos IoT y registrar transacciones comerciales de forma intuitiva.

Para transformar esta visión en un desarrollo ágil y ejecutable, el equipo realizó una deconstrucción de los requisitos de negocio en Historias de Usuario, las cuales fueron posteriormente atomizadas en tareas técnicas específicas de implementación y pruebas. Todo este flujo de trabajo, junto con la medición de la velocidad del equipo y el cumplimiento de los puntos de historia, se gestiona y audita centralizadamente a través de Jira, garantizando una trazabilidad absoluta y visibilidad del progreso en tiempo real para toda la organización.

**Proyecto en Jira:** [https://satecho.atlassian.net/jira/software/projects/SCRUM/boards/1](https://satecho.atlassian.net/jira/software/projects/SCRUM/boards/1)


![Sprint-Backlog-1 - SATECHO](./assets/images/sprint-1/Sprint-Backlog-1.png)

A continuación, se presenta la tabla con las tareas designadas junto con cada uno de los miembros del equipo para que se sean completados de manera satisfactoria durante este primer sprint.

# Sprint 1 – Sprint Backlog
 
| Sprint 1 | Sprint Backlog 1 | | | | | | |
|----------|-----------------|----------------|-------|-------------|-------------------|-------------|--------|
| **User Story** | **Title** | **Work Item/Task** | **Title** | **Description** | **Estimation (SP)** | **Assigned to** | **Status** |
| EP-001-US001 | US-01: Browse Landing Page Content | EP-001-US001-T01 | Design the main structure and content of the landing page | As a visitor, I want to browse landing page content so that I can understand the product's value proposition and available plans. | 2 | Jose Huamani | Done |
| | | EP-001-US001-T02 | Implement the plans and value proposition section | | | Yasser Palacios | Done |
| EP-001-US005 | US-02: Browse Landing as Agronomist Visitor | EP-001-US005-T01 | Develop the benefits section for agronomist consultants | As an agronomist visitor, I want to browse the landing page so that I can see the benefits tailored to consultants. | 1 | Brenda Gamio | Done |
| EP-001-US006 | US-03: Watch Product Demo Video | EP-001-US006-T01 | Integrate and configure the product demo video player | As a visitor, I want to watch the product demo video so that I can understand real-world use cases before signing up. | 1 | Abraham Estrada | Done |
| EP-001-US007 | US-04: Request Commercial Demo | EP-001-US007-T01 | Develop the commercial demo request form | As a visitor, I want to request a commercial demo so that a representative can contact me to evaluate the solution. | 2 | Raul Quispe | Done |
| | | EP-001-US007-T02 | Implement request notification and confirmation | | | Jose Huamani | Done |
| EP-001-US002 | US-05: Register as Lead | EP-001-US002-T01 | Develop account creation logic for new users | As a visitor, I want to register as a lead so that I can create my account and start the onboarding process. | 3 | Yasser Palacios | Done |
| | | EP-001-US002-T02 | Implement security validations on the registration form | | | Abraham Estrada | Done |
| | | EP-001-US002-T03 | Redirect the user to the onboarding flow after successful registration | | | Raul Quispe | Done |
| EP-001-US003 | US-06: Verify Email Account | EP-001-US003-T01 | Implement verification email dispatch with token | As a newly registered user, I want to verify my email account so that I can confirm my identity and activate my access. | 3 | Brenda Gamio | Done |
| | | EP-001-US003-T02 | Develop account validation and activation flow | | | Jose Huamani | Done |
| | | EP-001-US003-T03 | Handle token expiration and verification email resend | | | Yasser Palacios | In-Progress |
| EP-001-US004 | US-07: Complete Onboarding Wizard | EP-001-US004-T01 | Design and implement the initial setup wizard | As a newly registered user, I want to complete the onboarding wizard so that I can configure my plot data, irrigation zones, and get guided into the platform from day one. | 5 | Abraham Estrada | Done |
| | | EP-001-US004-T02 | Develop the plot configuration and crop data step | | | Raul Quispe | Done |
| | | EP-001-US004-T03 | Implement irrigation zone configuration in the wizard | | | Brenda Gamio | In-Progress |
| | | EP-001-US004-T04 | Integrate welcome screen and platform end guide | | | Jose Huamani | To-Do |
| EP-002-US001 | US-08: View Real-Time Soil Dashboard | EP-002-US001-T01 | Implement real-time soil moisture and temperature visualization | As an agriculturist, I want to view the real-time soil dashboard so that I can monitor moisture, EC, pH, and temperature of my parcels at any time. | 8 | Yasser Palacios | In-Progress |
| | | EP-002-US001-T02 | Develop EC and pH widgets with real-time updates | | | Abraham Estrada | In-Progress |
| | | EP-002-US001-T03 | Implement parcel selector on the dashboard | | | Raul Quispe | To-Do |
| | | EP-002-US001-T04 | Integrate visual alerts for out-of-range values | | | Brenda Gamio | To-Do |
| | | EP-002-US001-T05 | Perform dashboard performance testing with real-time data | | | Jose Huamani | To-Do |
| EP-007-TS001 | TS-01: Implement Lazy Loading and Code Splitting for Dashboard Modules | EP-007-TS001-T01 | Configure lazy loading for dashboard modules | As a Developer, I want the system to implement lazy loading of dashboard modules so that the initial load time is reduced. | 5 | Yasser Palacios | To-Do |
| | | EP-007-TS001-T02 | Implement code splitting by routes and critical components | | | Abraham Estrada | To-Do |
| | | EP-007-TS001-T03 | Measure and document improvement in initial load times | | | Raul Quispe | To-Do |
| EP-007-TS002 | TS-02: Implement Global State Management for Dashboard | EP-007-TS002-T01 | Select and integrate a global state manager in the web frontend | As a Developer, I want to implement a global state manager on the web frontend so that sensor data, alerts, and configuration are synchronized between components without redundant API calls. | 5 | Brenda Gamio | To-Do |
| | | EP-007-TS002-T02 | Centralize sensor data and alerts state | | | Jose Huamani | To-Do |
| | | EP-007-TS002-T03 | Eliminate redundant API calls through shared state | | | Yasser Palacios | To-Do |
| EP-007-TS003 | TS-03: Internationalization Support | EP-007-TS003-T01 | Configure the internationalization library (i18n) in the project | As a Developer, I want the system to support internationalization so that the platform can be used comfortably without language barriers. | 3 | Abraham Estrada | To-Do |
| | | EP-007-TS003-T02 | Implement dynamic language switching and translation files | | | Raul Quispe | To-Do |
| EP-007-TS004 | TS-04: Accessibility Compliance | EP-007-TS004-T01 | Implement ARIA labels across all interface components | As a Developer, I want the system to comply with accessibility standards so that users with disabilities can access all features without barriers. | 3 | Brenda Gamio | To-Do |

#### 6.2.1.4. Development Evidence for Sprint Review

Este apartado constituye el compendio de evidencia técnica y operativa que respalda los hitos alcanzados durante este primer ciclo de desarrollo, donde la materialización del software se ha concentrado en desplegar las versiones iniciales de la Landing Page y la Aplicación Web para sentar las bases de interacción y gobernanza de la plataforma. En ese sentido, el esfuerzo del equipo se distribuyó estratégicamente de manera simultánea; por un lado, se consolidó la Landing Page como una vitrina digital de alto impacto con diseño internacionalizado y contenido visual que integra con éxito los módulos de beneficios, planes de suscripción y redirecciones interactivas, mientras que, por otro lado, se desarrolló la Aplicación Web bajo un riguroso enfoque de Domain-Driven Design (DDD) validado provisionalmente mediante la simulación de servicios con Beeceptor, desplegando las interfaces críticas. Finalmente, como garantía de transparencia, rigor de ingeniería y control de configuración, este bloque sirve de antesala para el registro cronológico de _commits_ que certifica la autoría, el propósito y la evolución del código fuente integrado satisfactoriamente en este sprint.

| Repository              | Branch                   | Commit Id                                | Commit Message                                                                                                 | Commited On |
|-------------------------|--------------------------|------------------------------------------|----------------------------------------------------------------------------------------------------------------|-------------|
| Landing-Page-SATECHO   | main                   | 2392bd0 | chore: initial commit.                                                                                         | 12/05/26    |
| Landing-Page-SATECHO   | feature/navigation-bar              | d3b8b7d | feat(navigation): add the navigation bar about the differents section into the landing page that the visitors can watch commit.                                                    | 12/05/26    |
| Landing-Page-SATECHO   | feature/hero-section           | d78a3f6 | feat(hero): add the main content about the phareses and a little description about the SATECHO product commit.                                  | 12/05/26    |
| Landing-Page-SATECHO   | feature/stadistics-benefits-section      | 7216027 | feat(stadistics): add the quantitative values about the benefits to use the SATECHO Solution representing into these section commit.                                                                                         | 12/05/26    |
| Landing-Page-SATECHO   | feature/information-architecture                   | e0b8e0f | Merge pull request #3 from S-A-T-E-C-H-O/feature/stadistics-benefits-section                                                          | 12/05/26    |
| Landing-Page-SATECHO   | develop                   | 0fbd062 | Build(hosting): execute initial deployment of landing.                             | 14/05/26    |
| Web-Application-SATECHO    | main                   | 14a4ba0 | Initial commit        | 13/05/26    |
| Web-Application-SATECHO    | feature/initial-config                 | 8941169 | feat: complete initial frontend configuration        | 13/05/26    |
| Web-Application-SATECHO    | feature/auth                   | 695ff43 | refactor(auth): componentize registration flow and improve verification viewsstadistics-benefits-section        | 14/05/26    |
| Web-Application-SATECHO    | feature/auth                    | 72267da | feat: connect auth flow to beeceptor   | 14/05/26    |
| Web-Application-SATECHO    | feature/auth                    | f6d23c6 | docs: document beeceptor auth mock    | 14/05/26    |
| Web-Application-SATECHO    | feature/auth                    | 8b8be32 | chore: add pnpm-lock.yaml    | 14/05/26    |
| Web-Application-SATECHO    | feature/onboarding                   | dfa4f78 | add onboarding flow    | 15/05/26    |
| Web-Application-SATECHO    | feature/dashboards                  | d600b13 | feat: add agricultural dashboard    | 15/05/26    |
| Web-Application-SATECHO    | feature/dashboards                  | d600b13 | fix: improve dashboard interactions | 15/05/26    |
| Web-Application-SATECHO    | feature/auth-onboarding-dashboard-sync         | 7544e70 | feat: sync auth onboarding data with dashboard | 15/05/26    |
| Web-Application-SATECHO    | feature/i18n       | 6cc792c | feat(web-app): implement i18n support for english and spanish translations | 15/05/26    |
| Web-Application-SATECHO    | feature/deploy       | ee046e3 | build(web-app): execute initial deployment of the dashboard to firebase | 15/05/26    |

#### 6.2.1.5. Testing Suite Evidence for Sprint Review

Dado el carácter de este primer sprint, enfocado en el despliegue visual de la **Landing Page** y la validación de interfaces mediante una API simulada (Beeceptor), no se han estructurado scripts de testing automatizado en este ciclo. Al priorizar la arquitectura base y la experiencia UX sobre lógica persistente, la suite de pruebas se posterga estratégicamente para los próximos sprints, colindando con la integración de los servicios reales.

#### 6.2.1.6. Execution Evidence for Sprint Review

En este apartado, se presenta la ejecución de los productos digitales desarrollados en esta primer sprint junto con su evidencia de despliegue para el acceso desde cualquier dispositivo y por cualquier usuario.

Es de esta manea que se se muestran las capturas de pantalla y enlaces de acceso a cada producto implementado para reflejar el resultado y el recorrido relacionado a la usabilidad que el usuario tengan dentro de las mismas.

#### Landing Page

En primera instancia, se evidencia la ejecución oficial alcanzanda del desarrollo de la Landing Page para este Sprint 1, consolidando sus objetivos en habilitar secciones clave para que los visitantes a la página puedan comprender el giro del negocio, la propuesta de valor ofrecida y la infomración asociada a los grandes resultados que lograron otros clientes al utilizar nuestro servicio.

A continuación, se presenta el vídeo de demostración donde se evidencia la navegación y los flujos implementados en la interación de los cuales vienen a ser:

- **Acerca de nosotros:** Sección que muestra información sobre la startup SATECHO.
- **Beneficios:** Sección que presenta los beneficios que ofrece la plataforma para cada segmento objetivo.
- **Planes de pagos:** Sección que muestra los diferentes planes de pago con los diversos beneficios que ofrece para el monitoreo/sewguimiento del cultivo.

![Referential Video - Landing Page](./assets/images/sprint-1/Landing-Page-Execution-Video.png)

**Landing Page - SATECHO:** [Landing Page - Video](https://upcedupe-my.sharepoint.com/:v:/g/personal/u202110458_upc_edu_pe/IQAzgRZhyeACQ7t-xSswqGFuAROOoE3IEV-bGoTvCeJOn-M?e=hGWKTQ&nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJTdHJlYW1XZWJBcHAiLCJyZWZlcnJhbFZpZXciOiJTaGFyZURpYWxvZy1MaW5rIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXcifX0%3D)

**Sección Hero**

Introduce la propuesta de valor central de la plataforma mediante un mensaje de impacto y un llamado a la acción diseñado para cautivar a agricultores y agrónomos desde el primer segundo.

![Hero-Section](./assets/images/sprint-1/Hero-Section.png)

**Beneficios**

Detalla de forma visual y analítica las ventajas competitivas del sistema, destacando la eliminación de suposiciones empíricas gracias al monitoreo automatizado de variables críticas en tiempo real.

![Benefits-Section](./assets/images/sprint-1/Benefits-Section.png)

**Registro - Segmento Objetivo Agrónomo**

Punto de conversión estratégico diseñado para captar perfiles técnicos agrícolas, permitiéndoles registrarse para acceder a un ecosistema optimizado de toma de decisiones basada en datos veraces.

![Register-Section](./assets/images/sprint-1/Register-Section.png)

**Demo Promocional**

Espacio audiovisual interactivo que evidencia el funcionamiento práctico de nuestras interfaces web y móviles, validando la navegación del ecosistema automatizado ante potenciales clientes.

![Promotional-Section](./assets/images/sprint-1/Promotional-Demo-Section.png)

**Planes de Pago**

Matriz comercial transparente que desglosa las opciones de suscripción, adaptando los servicios de monitoreo a las necesidades operativas de pequeños productores y grandes empresas agrícolas.

![Payment-Plans-Section](./assets/images/sprint-1/Payment-Plans-Section.png)

**Formulario de Contacto**

Canal de comunicación directa diseñado para resolver consultas personalizadas, facilitando un puente directo entre el equipo de soporte técnico y los usuarios interesados en la tecnología.

![Contact-Forms-Section](./assets/images/sprint-1/Forms-Contact-Section.png)

**Footer**

Cierre institucional que consolida los enlaces de navegación rápida, políticas legales, redes sociales y derechos reservados, reafirmando la identidad corporativa y seriedad de la organización.

![Footer-Section](./assets/images/sprint-1/Footer-Section.png)

#### Web Application

Por consiguiente, la sección sobre el **Web Application** evidencia el desarrollo para la navegación e interacción del usuario - comenzando por el registro de su cuenta, hasta la visualización de cada uno de los módulos para el monitoreo y configuración tanto de su perfil de usuario como las hectáreas que está realizando seguimiento. 

Mediante el siguiente vídeo, se evidencias los flujos implementados de los cuales podemos apreciar los siguientes:

[Referential Video - Web Application](./assets/images/sprint-1/Web-Application-Execution-Evidence.png)

**Landing Page - SATECHO:** [Web Application - Video](https://upcedupe-my.sharepoint.com/:v:/g/personal/u202110458_upc_edu_pe/IQChu96vm6jCSLCSP2Y-AbjgAZ4_lsSfu0sH6sJZoUdHH9g?e=9Dnaaf&nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJTdHJlYW1XZWJBcHAiLCJyZWZlcnJhbFZpZXciOiJTaGFyZURpYWxvZy1MaW5rIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXcifX0%3D)

**Login**

Interfaz de acceso seguro que valida las credenciales del usuario, garantizando un ingreso protegido al ecosistema de monitoreo de la plataforma.

![Login-Section](./assets/images/sprint-1/Login-Section.png)

**Create Account**

Formulario de registro inicial estructurado para recopilar los datos esenciales e iniciar el flujo de alta en el sistema.

![Create-Account-Section](./assets/images/sprint-1/Create-Account-Section.png)

**User Account**

Sección de tipificación donde se define la identidad y el rol específico del usuario dentro de la infraestructura de control.

![User-Account-Section](./assets/images/sprint-1/User-Account-Section.png)

**Password**

Módulo de seguridad dedicado a la creación y validación de contraseñas robustas bajo criterios exigentes de protección de datos.

![Password-Section](./assets/images/sprint-1/Password-Section.png)

**Succesfully Creation Account**

Pantalla de confirmación y éxito que valida la correcta persistencia del nuevo perfil antes de avanzar a la configuración operativa.

![Successfully-Creation-Account-Section](./assets/images/sprint-1/Succefully-Creation-Account.png)

**Configuration Profile**

Asistente secuencial de parametrización donde el usuario configura sus datos, establece umbrales de riego y pre-selecciona los dispositivos IoT a vincular.

![Configuration-Profile](./assets/images/sprint-1/Confguration-Profile.png)

![Irrigation-Configuration-Profile](./assets/images/sprint-1/Irrigation-Configuration-Section.png)

![IoT-Devices-Selection-Section](./assets/images/sprint-1/Iot-Devices-Selection.png)

**Dashboard**

Centro de control principal que unifica y visualiza las métricas críticas en tiempo real, eliminando suposiciones mediante gráficos predictivos y claros.

![Dashboard-Section](./assets/images/sprint-1/Dashboard-Section.png)

**Security**

Panel de gobernanza técnica diseñado para administrar credenciales, tokens de acceso y la seguridad general de la cuenta del usuario.

![Security-Section](./assets/images/sprint-1/Security-Section.png)

**Notification**

Módulo de alertas tempranas encargado de reflejar las notificaciones críticas del sistema ante cualquier alteración en las variables del cultivo.

![Notification-Section](./assets/images/sprint-1/Notification-Section.png)

**Suscription**

Interfaz comercial que permite gestionar el estado de los planes de pago actuales y escalar los servicios según las necesidades del terreno.

![Suscription-Section](./assets/images/sprint-1/Suscriptions-Section.png)

**IoT Devices Section**

Inventario operativo dedicado a listar, monitorear el estado de conexión y administrar de forma centralizada cada hardware (ESP32) desplegado.

![Iot-Devices-Section](./assets/images/sprint-1/IoT-Devices-Section.png)

#### 6.2.1.7. Services Documentation Evidence for Sprint Review

Esta sección expone el estado de la documentación y los contratos de interfaz establecidos para los servicios de la plataforma durante el Sprint 1. Con el objetivo de garantizar el desacoplamiento técnico y permitir que el equipo de desarrollo frontend avanzara sin dependencias del backend definitivo, se implementó una estrategia táctica de emulación de servicios (API Mocking) utilizando la plataforma Beeceptor. Esta aproximación metodológica permitió modelar los esquemas de datos y validar el comportamiento de la solución web de forma idéntica a un entorno productivo.

Para esta entrega inicial, se diseñaron, estructuraron y documentaron cuatro endpoints críticos que simulan las operaciones esenciales del sistema (abarcando flujos de autenticación, gestión de perfiles, métricas del Dashboard y aprovisionamiento de hardware IoT). Aunque en este ciclo las respuestas consisten en cargas útiles fijas (JSON estáticos), estos servicios actúan como el contrato formal y la arquitectura base sobre la cual se desplegará el REST API real en Java con Spring Boot y su documentación definitiva con OpenAPI/Swagger en los sprints subsecuentes.

A continuación, se mencionan los _endpoints_ simulados para esta fase de validación de experiencia de usuario:

- https://satecho-auth.free.beeceptor.com
- https://satecho-onboarding.free.beeceptor.com
- https://satecho-farm.free.beeceptor.com
- https://satecho-operations.free.beeceptor.com

#### 6.2.1.8. Software Deployment Evidence for Sprint Review

El viaje hacia la nube comienza en la terminal de comandos dentro del directorio raíz del proyecto local. El primer paso crítico es "despertar" las capacidades de Firebase en nuestra carpeta de trabajo y vincularla con un proyecto en la consola de Google.

![Configuration-Firebase-Web-App-Deploy](./assets/images/sprint-1/Configuration-Firebase-Web-App-Deploy.png)

Como se observa en la Figura, el ingeniero ejecuta el comando firebase init hosting. Tras confirmar el inicio del proceso, la herramienta nos guía por un asistente visual. En este escenario, hemos optado por la opción "Create a new project" (Crear un nuevo proyecto). Es aquí donde definimos la identidad única de nuestra aplicación en la nube; para este ejemplo, hemos establecido tanto el ID como el nombre del proyecto como agrosafe-web-app. Una vez que la herramienta confirma con éxito la creación de los recursos en Google Cloud Platform, estamos listos para la configuración operativa.

**Fase 2: Parametrización del Entorno de Hosting**

Con el proyecto creado en la nube, debemos indicarle a Firebase qué archivos locales debe subir y cómo debe comportarse el servidor al recibirlos. Este paso es crucial para asegurar que la arquitectura de nuestra aplicación (ya sea una página estática o una Single Page Application bajo DDD) funcione correctamente.

![Define-parameters-to-configure-deployment-Web-App](./assets/images/sprint-1/Define-parameters-to-configure-deployment-Web-App.png)

Dicha figura ilustra esta fase de parametrización. El asistente nos formula preguntas clave:

Directorio Público: Definimos dist como la carpeta que contiene los archivos finales listos para producción (resultado de nuestro proceso de construcción o build).

Single-Page App: Respondemos "Yes" para configurar las reglas de reescritura de URL, asegurando que todas las rutas apunten a index.html, vital para la navegación fluida de nuestra Web App.

Automatización: Para este hito inicial, hemos declinado la configuración de builds automáticos con GitHub Actions ("No") para mantener el despliegue bajo control manual directo.

Al finalizar este asistente, Firebase confirma la creación de los archivos de configuración .firebaserc y firebase.json, marcando el éxito de la inicialización.

**Fase 3: Ejecución del Despliegue (The Push to Cloud)**

Este es el momento de la verdad. Con todo configurado, procedemos a transferir nuestros archivos locales desde la carpeta dist hacia los servidores globales de Firebase.

![Successfully-Web-App-Deployment](./assets/images/sprint-1/Successfully-Web-App-Deployment.png)

Como se muestra en la Figura Z (image_3.png), el ingeniero ejecuta el comando final: firebase deploy --only hosting. La terminal actúa como un diario de bitácora en tiempo real: vemos cómo Firebase inicia el proceso, detecta los archivos en la carpeta dist (en este caso, 3 archivos), realiza la carga completa, finaliza la versión y, finalmente, libera la nueva actualización. La confirmación "+ Deploy complete!" es el indicador del éxito, proporcionándonos de inmediato la URL pública operativa (ej. https://agrosafe-web-app.web.app) y el enlace directo a la consola de administración.

**Fase 4: Verificación en la Consola de Administración**

El proceso no termina hasta que verificamos el estado del despliegue en el panel de control oficial. Esto nos da la certeza absoluta de que la versión productiva corresponde a lo ejecutado.

![Firebase-Monitoring-Web-App-Deployment](./assets/images/sprint-1/Firebase-Monitoring-Web-App-Deployment.png)

![Firebase-Monitoring-Landing-Deployment](./assets/images/sprint-1/Firebase-Monitoring-Landing-Deployment.png)

Finalmente, nos muestra la vista de la consola web de Firebase para el proyecto agrosafe-web-app. En la sección de "Hosting", podemos confirmar visualmente el "Historial de implementaciones". El panel ratifica que la versión ha sido "Implementada" exitosamente (en este ejemplo, el 15 de mayo de 2026 a las 11:02 a.m.) e identifica al miembro del equipo responsable de dicha acción. Esta trazabilidad garantiza el control de configuración requerido para el Spring Review.

#### 6.2.1.9. Team Collaborations Insights during Sprint

**Landing Page**

Con el objetivo de consolidar una _Landing Page_ que no solo informe, sino que proyecte legitimidad y capture el interés del segmento objetivo, el equipo sustituyó el desarrollo lineal por un flujo de trabajo paralelo y coordinado. Esta estrategia de co-creación se fundamentó en una descomposición modular de la interfaz, donde las responsabilidades fueron asignadas por bloques específicos (Hero, Funcionalidades, Beneficios, Planes de Pago y Formulario de Contacto), permitiendo a cada desarrollador operar con autonomía sin generar fricciones en el código base.

La integridad del repositorio se salvaguardó mediante la adopción estricta de un protocolo de comunicación atómica en Git. Cada miembro ejecutó contribuciones frecuentes y acotadas, documentadas bajo reglas semánticas claras, lo que simplificó los procesos de auditoría interna y trazabilidad de cambios. Asimismo, la integración de código se rigió bajo un modelo de calidad estricto: ninguna funcionalidad fue fusionada directamente en la rama central de integración (develop); en su lugar, se canalizaron a través de **Pull Requests** (PRs) donde un responsable o responsables del equipo evaluan la conformidad de la misma para su aprobación o su rechazo junto con comentarios para que se puedan levantar estas observaciones. Este esfuerzo técnico se complementó con un control de calidad estético (QA Visual) enfocado en la responsividad multi-dispositivo y en una rigurosa estandarización del árbol de directorios para los recursos estáticos (src/public/assets/images), asegurando un proyecto limpio y escalable.

Las métricas e indicadores visuales presentados a continuación —extraídos directamente de los insights analíticos de GitHub— certifican el ritmo de trabajo, la distribución del esfuerzo y la madurez colaborativa del equipo en este ciclo inicial:

![Team-Collaboration-Insights-Landing](./assets/images/sprint-1/Team-Collaboration-Insights-Landing-Sprint1.png)

**Web Application**

De manera simultánea a los esfuerzos de maquetación comercial, el Sprint 1 albergó funcionalidad de la Aplicación Web, un hito de alta complejidad técnica que abarcó el despliegue de las interfaces críticas para la operación del negocio, tales como la sección de Dashboard, Seguridad, Gestión de los Dispositivos IoT y las notificaciones. Para mitigar la entropía y el riesgo de colisiones en el código fuente ante un volumen tan robusto de entregables, el equipo adoptó una estrategia de desarrollo altamente coordinada basada en los principios de **Domain-Driven Design (DDD)**. Esta aproximación arquitectónica nos permitió segmentar la lógica y las vistas en contextos delimitados bien definidos, asegurando que la responsabilidad de cada componente estuviera aislada y permitiendo adoptar un desarrollo en paralelo con una comprensión nítida del dominio del sistema.

Asimismo, ante la ausencia temporal de servicios backend productivos, el equipo implementó una estrategia de desacoplamiento temprano mediante la emulación de respuestas con un **Fake API** (Beeceptor); este enfoque de simulación permitió inyectar datos estáticos fijos y modelar los contratos de consumo de manera idéntica a una infraestructura real, desbloqueando las pruebas de experiencia de usuario de forma inmediata. Finalmente, el rigor metodológico se consolidó mediante una política de trazabilidad absoluta, donde cada _commit_ regular incorporó metadatos estructurados que enlazaban directamente el cambio de código con su respectiva tarea y punto de historia dentro de la planificación de Jira, blindando el ciclo de auditoría del proyecto.

El comportamiento analítico de estas interacciones se ven respaldados a continuación por las métricas de colaboración provistas por los insights de GitHub:

![Team-Collaboration-Insights-Web-Application](./assets/images/sprint-1/Team-Collaboration-Insights-Web-Application-Sprint1.png)

### 6.2.2. Sprint 2

En este apartado se detalla cada uno de los progresos y mejoras alcazandos por el equipo durante el desarrollo del segundo sprint del proyecto **AgroSafe**, destacando para el lado del _Landing Page_, la implementación de las secciones del video _"about-the-Product"_, la sección de integrantes del equipo de desarrollo de la startup **Satecho** y la eliminación de interacciones y secciones dedicadas a ofrecer planes _freemium_ (esto con el objetivo de que **Satecho**, al utilizar tecnología IoT, necesita solvencia monetaria para seguir progresando e innovando en su solución). Por otro lado, en relación al **Web Application**, se corrigió las vistas asociadas a la autenticación - debido a que, una cuenta registrada en la aplicación, debía configurar su perfil "agregando por su cuenta" el tipo de sensor y dispositivo IoT que utilizará en su escenario.

Luego de precisar las mejoras implementadas, adicionalmente, se priorizó el desarrollo de las nuevas funcionalidades dedicadas para el **Web Application** agregando las vistas de asociadas al monitoreo y el dashboard; por consiguiente, se elaboró las primeras versiones de los nuevos productos tales como el **RESTFUL API**, **Embedded** (para la recolección de los datos del ambiente mediante los sensores de tierra y humedad), el **Edge API** y el **Mobile Application** - orientadas a las funcionalidades de Dashboard, Parcerlas, Control de Riesgo y Registro de Actividad para el Agricultor; por otro lado, para el ingeniero agrónomo, se desarrollará las funcionalidades respecto al seguimiento de clientes, alertas y agenda.

#### 6.2.2.1. Sprint Planning 2

<table>
  <tr>
    <td>Sprint #</td>
    <td>Sprint 2</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Sprint Planning Background</strong></td>
  </tr>
  <tr>
    <td>Date</td>
    <td>2026-05-25</td>
  </tr>
  <tr>
    <td>Time</td>
    <td>23:00 p.m (GMT-5)</td>
  </tr>
  <tr>
    <td>Location</td>
    <td>Asynchronous session organized within the Discord communication platform</td>
  </tr>
  <tr>
    <td>Prepared By</td>
    <td>Huamani Sánchez, José Diego</td>
  </tr>
  <tr>
    <td>Attendees (to planning meeting)</td>
    <td>Estrada Cajamune, Abraham Andrés / Gamio Upiachihua, Brenda Lucía / Quispe Erasmo, Raul Ronaldo / Palacios, Yasser Renteria</td>
  </tr>
  <tr>
    <td>Sprint 1 Review Summary</td>
    <td>During the previous sprint, the team implemented the sections associated with the startup description, solution overview, benefits, payment plans, and contact form — with the purpose of communicating SATECHO's commitment to its proposed solution to <em>leads</em> on the Landing Page. Additionally, the team implemented key sections related to indicator monitoring, Security, Notifications, Subscription, and the IoT section for the web application; this progress allowed the team to complete the vast majority of the core features planned for the application.</td>
  </tr>
  <tr>
    <td>Sprint 1 Retrospective Summary</td>
    <td>According to the retrospective session held with the entire SATECHO team, we highlighted the proactivity and planned coordination among all team members to align the expected progress for Sprint 1 and successfully present a first version to our stakeholders. However, we unanimously identified as areas for improvement that, given the large number of deliverables within a very limited timeframe, progress dependency became centralized on individual contributors — since members tended to work independently, the sheer magnitude of development caused delays and created bottlenecks for continuing both the report and the implementation of digital artifacts. As a result of these issues, the team restructured its work planning approach by experimentally adopting the <q>Team Software Process</q> framework to measure team-level delivery maturity and agility, identify gaps, and track improvements in collaboration and deliverable metrics through measurable outcomes.</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Sprint Goal & User Stories</strong></td>
  </tr>
  <tr>
    <td>Sprint 2 Goal</td>
    <td>
<strong>Our focus is on</strong> delivering a complete agricultural monitoring experience with real-time IoT sensor data to independent farmers and agronomists, accessible from the Web Application and their mobile devices, backed by a premium value proposition visible on the Landing Page. <br>
<strong>We believe it delivers</strong> faster soil-evidence-based irrigation and agronomic decision-making to farmers and agronomists on the platform, and greater product confidence to agricultural sector visitors evaluating the premium subscription plan. <br>
<strong>This will be confirmed when</strong> farmers can view the hydric status of their parcels in real time and remotely activate irrigation from both the Web Application and the Mobile Application; when agronomists can supervise assigned client parcels and send agronomic recommendations through the platform; and when Landing Page visitors can evaluate SATECHO's premium value proposition and initiate the registration process without team intervention.
    </td>
  </tr>
  <tr>
    <td>Sprint 2 Velocity</td>
    <td>81</td>
  </tr>
  <tr>
    <td>Sum of Story Points</td>
    <td>81</td>
  </tr>
</table>

#### 6.2.2.2. Aspect Leaders and Collaborations

Durante el Sprint 2, la complejidad de la entrega se multiplicó exponencialmente al incorporar seis productos de software de forma simultánea: la segunda versión de la Landing Page, la versión final de la Aplicación Web, la primera versión del RESTful API, la primera versión de la Aplicación Móvil, la primera versión del Edge API y la primera versión de la Aplicación Embebida. Para gestionar este desafío de forma ordenada, el equipo adoptó el marco de trabajo **Team Software Process (TSP)**, que define con precisión los líderes de cada aspecto y sus colaboradores, reduciendo la ambigüedad en la toma de decisiones y eliminando las colas de espera que afectaron la velocidad del sprint anterior.

| Team Member (Last Name, First Name) |  GitHub Username  | Landing Page v2 | Web App v2 | REST API | Mobile App | Edge API | Embedded |
| :---------------------------------- | :----------------: | :---------: | :---------: | :---------: | :---------: | :---------: | :---------: |
| Huamani Sánchez, José Diego       |  `ProgramadorHuamani`  | C | C | **L** | C | | |
| Estrada Cajamune, Abraham Andrés        |     `Abraham0310`     | C | C | C | **L** | | C |
| Gamio Upiachihua, Brenda Lucía         |     `B-Gamio`     | **L** | **L** | C | C | | |
| Quispe Erasmo, Raul Ronaldo      |    `Raul-QE`   | | C | C | | **L** | C |
| Palacios, Yasser Renteria        |      `Mitos20`     | C | C | C | C | C | **L** |

#### 6.2.2.3. Sprint Backlog 2

Este segundo sprint representa el hito de mayor densidad técnica del proyecto, con la integración vertical completa del ecosistema SATECHO: desde el firmware embebido en los sensores ESP32 hasta las interfaces web y móviles que consumen los datos en tiempo real. El backlog fue diseñado para cubrir simultáneamente seis productos de software bajo el principio de entrega de valor continua, priorizando la arquitectura de extremo a extremo (E2E) sobre funcionalidades aisladas.

**Proyecto en Jira:** [https://satecho.atlassian.net/jira/software/projects/SCRUM/boards/1](https://satecho.atlassian.net/jira/software/projects/SCRUM/boards/1)

![Sprint-Backlog-2 - SATECHO](./assets/images/sprint-2/Sprint-Backlog-2.png)

# Sprint 2 – Sprint Backlog

| Sprint 2 | Sprint Backlog 2 | | | | | | |
|----------|-----------------|----------------|-------|-------------|-------------------|-------------|--------|
| **User Story** | **Title** | **Work Item/Task** | **Title** | **Description** | **Estimation (SP)** | **Assigned to** | **Status** |
| EP-001-US008 | US-08: View About-the-Product Video | EP-001-US008-T01 | Integrate product demo video section in landing page | As a visitor, I want to watch an explanatory video about SATECHO's product so that I can understand how the solution works before contacting a representative. | 2 | Brenda Gamio | Done |
| EP-001-US009 | US-09: View Startup Team Members | EP-001-US009-T01 | Design and implement the team members section | As a visitor, I want to see the startup team members section so that I can know who is behind the product and build trust in the organization. | 2 | Brenda Gamio | Done |
| EP-001-US010 | US-10: Browse Premium-Only Plans | EP-001-US010-T01 | Remove freemium tiers and update pricing section to premium model | As a visitor, I want to browse the available premium subscription plans so that I can evaluate the commercial offer before contacting the SATECHO team. | 1 | Yasser Palacios | Done |
| EP-001-US004 | US-11: Complete Onboarding Wizard (Fix) | EP-001-US004-T05 | Implement irrigation zone removal with minimum zone validation | As a newly registered user, I want to remove an irrigation zone during onboarding so that I can correct my initial configuration before activating the system. | 2 | Abraham Estrada | Done |
| | | EP-001-US004-T06 | Add removable protocol templates to onboarding wizard | | | Brenda Gamio | Done |
| | | EP-001-US004-T07 | Validate personal data fields before proceeding to step 3 of onboarding | | | Brenda Gamio | Done |
| EP-002-US002 | US-12: View Agronomist Analysis Dashboard | EP-002-US002-T01 | Implement analysis and soil thresholds management views for agronomist | As an agronomist, I want to view analysis dashboards and configure soil thresholds so that I can monitor critical crop parameters remotely. | 5 | Brenda Gamio | Done |
| | | EP-002-US002-T02 | Develop account management and device monitoring views for agronomist | | | Brenda Gamio | Done |
| | | EP-002-US002-T03 | Implement irrigation control and perimeter security views for agronomist dashboard | | | Brenda Gamio | Done |
| EP-002-US003 | US-13: Manage Agronomist Profile and Plans | EP-002-US003-T01 | Implement profile management and notification settings for agronomist | As an agronomist, I want to manage my professional profile and notification preferences so that I receive relevant alerts from my assigned clients. | 3 | Brenda Gamio | Done |
| | | EP-002-US003-T02 | Implement plan system view for agronomist account | | | Brenda Gamio | Done |
| EP-002-US004 | US-14: Manage Priority Cases and Alerts | EP-002-US004-T01 | Develop priority cases queue and critical alert detail views for agronomist | As an agronomist, I want to review a prioritized queue of critical cases so that I can respond immediately to the most urgent situations in my clients' fields. | 3 | Brenda Gamio | Done |
| EP-002-US005 | US-15: View Real-Time Telemetry Dashboard | EP-002-US005-T01 | Implement telemetry dashboard with salinity chart and security event log | As a farmer, I want to view real-time telemetry data including salinity and security events so that I have a complete picture of my field conditions. | 5 | Abraham Estrada | Done |
| | | EP-002-US005-T02 | Add telemetry route and integrate TelemetryDashboardView into navigation | | | Abraham Estrada | Done |
| EP-002-US006 | US-16: Monitor IoT Device Fleet | EP-002-US006-T01 | Implement DeviceFleetView with fleet monitoring, telemetry metrics, device actions and maintenance management | As a farmer, I want to monitor the health and status of all my IoT devices from a single view so that I can detect connectivity failures or maintenance needs proactively. | 5 | Abraham Estrada | Done |
| | | EP-002-US006-T02 | Develop NotificationsRulesView for configuring alert thresholds per device | | | Abraham Estrada | Done |
| EP-007-TS029 | TS-05: Implement IAM Bounded Context - REST API | EP-007-TS029-T01 | Implement domain model entities and rules for identity management | As a Developer, I want the system to have a complete Identity and Access Management bounded context so that authentication, authorization and user account lifecycle are centrally managed. | 8 | José Huamani | Done |
| | | EP-007-TS029-T02 | Implement authentication and user use cases in application layer | | | José Huamani | Done |
| | | EP-007-TS029-T03 | Implement persistence repositories and security configuration in infrastructure layer | | | José Huamani | Done |
| | | EP-007-TS029-T04 | Expose REST API endpoints and request/response resources | | | José Huamani | Done |
| | | EP-007-TS029-T05 | Add account verification and resend verification commands and endpoints | | | José Huamani | Done |
| EP-007-TS030 | TS-06: Implement Onboarding Bounded Context - REST API | EP-007-TS030-T01 | Add domain layer commands, queries and events for farm and zone management | As a Developer, I want the system to have a complete Onboarding bounded context so that farmers can register their farms and irrigation zones through the REST API. | 5 | José Huamani | Done |
| | | EP-007-TS030-T02 | Implement infrastructure persistence layer for Farm and IrrigationZone entities | | | Raul Quispe | Done |
| | | EP-007-TS030-T03 | Implement command and query services for Farm and Zone management | | | Raul Quispe | Done |
| | | EP-007-TS030-T04 | Add resources and command assemblers for farm and zone REST endpoints | | | José Huamani | Done |
| EP-007-TS031 | TS-07: Implement MQTT Integration and BI Bounded Context - REST API | EP-007-TS031-T01 | Add MQTT actuator publisher and integrate with irrigation session commands | As a Developer, I want the backend to publish actuator commands via MQTT so that the irrigation hardware responds to commands from the platform. | 8 | José Huamani | Done |
| | | EP-007-TS031-T02 | Implement SoilTelemetryMqttListener to consume telemetry from ESP32 devices | | | José Huamani | Done |
| | | EP-007-TS031-T03 | Add query and resource models for fleet health, irrigation and notifications | | | Raul Quispe | Done |
| EP-003-US001 | US-17: Scaffold Farmer Mobile App | EP-003-US001-T01 | Create initial Flutter project with feature-based bounded context architecture | As a farmer, I want to access a dedicated mobile application so that I can monitor my crops and control irrigation from my smartphone. | 5 | Abraham Estrada | Done |
| | | EP-003-US001-T02 | Implement role-based navigation and login flow | | | Abraham Estrada | Done |
| EP-003-US002 | US-18: Monitor Irrigation and Soil in Real-Time (Mobile) | EP-003-US002-T01 | Implement DeviceStatusList with 15-second polling for irrigation status | As a farmer, I want to see real-time status of my devices and active irrigation sessions on my mobile app so that I can make timely decisions in the field. | 8 | Abraham Estrada | Done |
| | | EP-003-US002-T02 | Integrate real-time updates for irrigation sessions and sensor metrics | | | Abraham Estrada | Done |
| | | EP-003-US002-T03 | Fix responsive layout and overflow issues across mobile screens | | | Abraham Estrada | Done |
| EP-003-US003 | US-19: Access Agronomist Workspace (Mobile) | EP-003-US003-T01 | Implement agronomist workspace features: client tracking, alerts and schedule | As an agronomist, I want to access a dedicated workspace on the mobile app so that I can manage my clients, view critical alerts and organize my schedule. | 5 | Abraham Estrada | Done |
| | | EP-003-US003-T02 | Connect mobile application to real REST API infrastructure | | | Abraham Estrada | Done |
| EP-005-TS009 | TS-08: Implement Device Authentication - Edge API | EP-005-TS009-T01 | Define device entity and repository interface in domain layer | As a Developer, I want the Edge API to authenticate ESP32 devices via API key (MAC address) so that only registered devices can submit telemetry data. | 3 | Raul Quispe | Done |
| | | EP-005-TS009-T02 | Implement authentication service and infrastructure persistence layer | | | Raul Quispe | Done |
| | | EP-005-TS009-T03 | Expose device registration and authentication REST endpoints | | | Raul Quispe | Done |
| EP-002-TS007 | TS-09: Implement Soil Data Capture - Edge API | EP-002-TS007-T01 | Define soil reading entity and domain service with boundary validation | As a Developer, I want the Edge API to receive, validate and persist soil telemetry from ESP32 devices so that the data can be forwarded reliably to the cloud backend. | 5 | Raul Quispe | Done |
| | | EP-002-TS007-T02 | Implement MQTT publisher for soil readings and cloud sync service with heartbeat | | | Raul Quispe | Done |
| | | EP-002-TS007-T03 | Expose soil monitoring REST endpoint with API key authentication | | | Raul Quispe | Done |
| EP-003-TS001 | TS-10: Implement PIR Movement Classification - Edge API | EP-003-TS001-T01 | Define PIR event entity, classification domain service and repository | As a Developer, I want the Edge API to classify PIR events as perimeter security alerts so that critical security events are separated from normal activity. | 3 | Raul Quispe | Done |
| | | EP-003-TS001-T02 | Implement MQTT publisher for PIR events and REST endpoint | | | Raul Quispe | Done |
| EP-002-TS011 | TS-11: Implement Testing Suite - Edge API | EP-002-TS011-T01 | Add unit tests for SoilReadingService domain boundaries and PIR classification service | As a Developer, I want a comprehensive test suite for the Edge API so that regressions are detected automatically before each deployment. | 3 | Raul Quispe | Done |
| | | EP-002-TS011-T02 | Add integration tests for soil reading application service using SQLite | | | Raul Quispe | Done |
| | | EP-002-TS011-T03 | Add acceptance tests for device registration and soil monitoring REST endpoints | | | Raul Quispe | Done |
| EP-006-TS012 | TS-12: Implement ESP32 Firmware - Event-Driven Architecture | EP-006-TS012-T01 | Implement sensor abstraction layer with FC28, HR202L, DHT11 and DS18B20 drivers | As a Developer, I want the ESP32 firmware to read all soil and ambient sensors in a FreeRTOS event-driven architecture so that no CPU cycles are wasted in polling loops. | 5 | Yasser Palacios | Done |
| | | EP-006-TS012-T02 | Implement connectivity management and MQTT telemetry serialization | | | Yasser Palacios | Done |
| | | EP-006-TS012-T03 | Implement actuator control module for irrigation valve management | | | Yasser Palacios | Done |
| | | EP-006-TS012-T04 | Add safety mechanisms and watchdog timers for fault tolerance | | | Yasser Palacios | Done |
| | | EP-006-TS012-T05 | Implement MAC address capture for device authentication with Edge API | | | Yasser Palacios | Done |

#### 6.2.2.4. Development Evidence for Sprint Review

En este Sprint 2, el alcance del desarrollo se expandió significativamente para cubrir la integración vertical completa del ecosistema SATECHO. Se materializaron las primeras versiones funcionales de los seis productos de software que conforman la solución: la versión actualizada de la Landing Page y la Aplicación Web, el RESTful API con sus primeros contextos acotados funcionales, la Aplicación Móvil con roles diferenciados para agricultor y agrónomo, el Edge API con procesamiento local de telemetría, y el firmware embebido para el ESP32 con arquitectura orientada a eventos. A continuación, se presenta el registro cronológico de commits que certifica la autoría, el propósito y la evolución del código fuente integrado satisfactoriamente en este sprint.

| Repository | Branch | Commit Id | Commit Message | Committed On |
|---|---|---|---|---|
| Landing-Page-SATECHO | feature/about-product-section | feat: add about-the-product video section | feat(hero): add product demo video integration to landing page. | 26/05/26 |
| Landing-Page-SATECHO | feature/team-section | feat: add startup team members section | feat(team): add team members presentation section with roles and photos. | 26/05/26 |
| Landing-Page-SATECHO | feature/premium-plans | feat: update plans to premium-only model | feat(pricing): remove freemium tiers and update subscription section to premium-only model. | 27/05/26 |
| Web-Application-SATECHO | feature/error-pages | e2d08a8 | feat(error-pages): add styled 404 page and wildcard route handling. | 26/05/26 |
| Web-Application-SATECHO | feature/onboarding | 6c89776 | feat(onboarding): add irrigation zone removal with minimum zone validation. | 26/05/26 |
| Web-Application-SATECHO | feature/onboarding | 9b09c91 | feat(feature/onboarding): add removable protocol templates. | 28/05/26 |
| Web-Application-SATECHO | feature/dashboard-agronomo | 99ed4fc | feat(feature/dashboard-agronomo): implement analysis and thresholds management views. | 28/05/26 |
| Web-Application-SATECHO | feature/auth | 3ea9754 | fix(feature/auth): validate personal data before proceeding to step 3. | 28/05/26 |
| Web-Application-SATECHO | feature/dashboard-agronomo | ccbede2 | feat(dashboard-agronomist): add priority cases queue and critical alert detail views. | 09/06/26 |
| Web-Application-SATECHO | feature/dashboard-agronomo | 5d3a7d7 | feat(feature/dashboard-agronomo): implement account management, device monitoring and irrigation/security improvements. | 09/06/26 |
| Web-Application-SATECHO | feature/dashboard-agronomo | ff10bef | feat(feature/dashboard-agronomo): implement profile management, plan system and notification settings. | 10/06/26 |
| Web-Application-SATECHO | feature/dashboard | cc69724 | feat: add telemetry dashboard with salinity chart and security event log. | 15/06/26 |
| Web-Application-SATECHO | feature/dashboard | 206a626 | feat: add telemetry route and import TelemetryDashboardView. | 15/06/26 |
| Web-Application-SATECHO | feature/dashboard | f410c43 | feat(feature/dashboard): add DeviceFleetView with fleet monitoring, telemetry metrics, device actions, maintenance management and responsive UI. | 18/06/26 |
| Web-Application-SATECHO | feature/dashboard | 4925205 | feat(feature/dashboard): add NotificationsRulesView with script, template and css. | 18/06/26 |
| Web-Application-SATECHO | main | 334ce29 | chore: update deployed connection. | 20/06/26 |
| Web-API-Service-SATECHO | main | d8d4491 | build: rename artifact to com.satecho.agrosafe.platform. | 26/05/26 |
| Web-API-Service-SATECHO | feature/shared | dba183a | feat(shared): add domain event and exception handling infrastructure with RabbitMQ integration. | 27/05/26 |
| Web-API-Service-SATECHO | feature/shared | 2911ef1 | feat(shared): add security configuration for API with CSRF disabled and Swagger access. | 27/05/26 |
| Web-API-Service-SATECHO | feature/bc-iam | 2990c3b | feature/bc-iam(domain): core domain model entities and rules for identity management. | 29/05/26 |
| Web-API-Service-SATECHO | feature/bc-iam | 470c49a | feature/bc-iam(application): implement authentication and user use cases. | 29/05/26 |
| Web-API-Service-SATECHO | feature/bc-iam | 26c0193 | feature/bc-iam(interfaces): expose rest api endpoints and request/response resources. | 29/05/26 |
| Web-API-Service-SATECHO | feature/bc-iam | 0db5b61 | feat(iam): enhance security and persistence layers with role and user entities, update logging practices. | 03/06/26 |
| Web-API-Service-SATECHO | feature/bc-iam | 04206cd | feat(iam): refactor controllers to use application services and improve response handling. | 03/06/26 |
| Web-API-Service-SATECHO | feature/onboarding | 0da1be3 | feat(onboarding): add domain layer with commands, queries and events classes for farm and zone management. | 09/06/26 |
| Web-API-Service-SATECHO | feature/onboarding | d48de1a | feat(onboarding): implement infrastructure persistence layer for Farm and IrrigationZone entities with corresponding assemblers and repositories. | 09/06/26 |
| Web-API-Service-SATECHO | feature/onboarding | 2dbbcf7 | feat(onboarding): implement command and query services for Farm and Zone management. | 09/06/26 |
| Web-API-Service-SATECHO | feature/onboarding | a3062ac | feat(onboarding): add resources and command assemblers for farm and zone management. | 09/06/26 |
| Web-API-Service-SATECHO | feature/bc-iam | ce68c91 | feat(iam): add commands for account verification and user role management. | 10/06/26 |
| Web-API-Service-SATECHO | feature/bc-iam | 6c671e4 | feat(iam): implement user and role persistence layers with corresponding assemblers and repositories. | 10/06/26 |
| Web-API-Service-SATECHO | feature/bc-iam | a98637c | feat(iam): integrate resend email service and update user verification logic. | 10/06/26 |
| Web-API-Service-SATECHO | feature/bi | d025614 | feat(bi): add MQTT actuator publisher and integrate with irrigation session commands. | 15/06/26 |
| Web-API-Service-SATECHO | feature/bi | 3fdc3f5 | feat(bi): add SoilTelemetryMqttListener and SoilTelemetry handling via MQTT. | 15/06/26 |
| Web-API-Service-SATECHO | feature/bi | 03d4f9c | feat(bi): update MQTT actuator commands and add edge API key configuration. | 15/06/26 |
| Web-API-Service-SATECHO | main | 879addd | fix(merge): resolve conflict markers in IAM and Onboarding files. | 16/06/26 |
| Mobile-Application-SATECHO | main | e2e08f5 | first commit. | 30/05/26 |
| Mobile-Application-SATECHO | feature/farmer | e45c3f1 | feat: scaffold farmer mobile app. | 30/05/26 |
| Mobile-Application-SATECHO | feature/agronomist | f59f88c | feat: add agronomist workspace features. | 08/06/26 |
| Mobile-Application-SATECHO | feature/auth | e1fdb74 | feat: add mock login and role selection. | 08/06/26 |
| Mobile-Application-SATECHO | feature/auth | a761b89 | feat: add role based navigation smoke tests. | 08/06/26 |
| Mobile-Application-SATECHO | develop | ca29d07 | merge(develop): integrate agronomist workspace features and real API infrastructure. | 12/06/26 |
| Mobile-Application-SATECHO | feature/devices | 1836328 | feat(devices, irrigation): DeviceStatusList + 15s polling for irrigation status. | 12/06/26 |
| Mobile-Application-SATECHO | feature/ui | 66bcf26 | fix(ui): responsive layout — fix overflows and adaptive padding. | 12/06/26 |
| Mobile-Application-SATECHO | feature/irrigation | 9a0f91f | feat(irrigation): integrate real-time updates for irrigation sessions and sensor metrics. | 15/06/26 |
| Mobile-Application-SATECHO | develop | d6b834e | refactor(structure): reorganize to feature-based bounded contexts. | 20/06/26 |
| Edge-API-SATECHO | main | 908bfdc | first commit. | 15/06/26 |
| Edge-API-SATECHO | develop | 5017544 | add initial main function and entry point. | 15/06/26 |
| Edge-API-SATECHO | feature/chore-shared-infrastructure | ba75fed | feat(shared): implement cloud sync service with telemetry and heartbeat functionality. | 16/06/26 |
| Edge-API-SATECHO | feature/soil-data-capture | dd99912 | feat(soil): add soil reading entity, repository, and MQTT publisher. | 16/06/26 |
| Edge-API-SATECHO | feature/device-authentication | da894e1 | feat(iam): add device entity, repository, and authentication service. | 16/06/26 |
| Edge-API-SATECHO | feature/movement-classification | f83d65c | feat(pir): add PIR event handling, define entities, models, and services for event classification and MQTT publishing. | 16/06/26 |
| Edge-API-SATECHO | feature/unit-tests | 9019e7f | feat(tests): add unit tests for PIR and soil reading services. | 21/06/26 |
| Edge-API-SATECHO | feature/integration-tests | b15921f | feat(tests): add integration tests for soil reading application service. | 21/06/26 |
| Edge-API-SATECHO | feature/acceptance-tests | 1bd047c | test: add unit tests for device registration and soil monitoring APIs. | 21/06/26 |
| Embedded-Application-SATECHO | main | 0da17ab | feat: add connectivity management, safety mechanisms, sensor abstraction, and telemetry serialization. | 15/06/26 |
| Embedded-Application-SATECHO | main | 1f65733 | refactor: sensor and telemetry modules for event-driven architecture. | 15/06/26 |
| Embedded-Application-SATECHO | main | 75cc57b | refactor: actuator control and telemetry for event-driven architecture. | 15/06/26 |
| Embedded-Application-SATECHO | main | d6538be | feat: update capturing mac address. | 21/06/26 |

#### 6.2.2.5. Testing Suite Evidence for Sprint Review

Durante este segundo sprint, el equipo consolidó su primera suite de pruebas automatizadas centrada en el **Edge API**, el componente más crítico de la cadena de ingesta de datos, dado que actúa como filtro y validador de toda la telemetría proveniente del hardware embebido antes de ser sincronizada con la nube. La decisión de priorizar el Edge para las pruebas responde a que cualquier error en la validación de rangos o en la autenticación de dispositivos se propaga hacia todos los sistemas superiores. Las pruebas se implementaron con **pytest** bajo tres capas:

**Capa 1 - Pruebas Unitarias de Dominio (Domain Layer)**

Validan las reglas de negocio del servicio `SoilReadingService`, asegurando que ningún valor de sensor fuera de rango pueda persistirse en el sistema.

| Archivo de Test | Escenario de Prueba | Resultado Esperado |
|---|---|---|
| `tests/domain/test_soil_reading_service.py` | Lectura con todos los campos válidos | Entidad creada con `is_valid = True` |
| `tests/domain/test_soil_reading_service.py` | Humedad en límites [0%, 100%] | Sin excepción |
| `tests/domain/test_soil_reading_service.py` | Humedad fuera de rango (-0.1, 100.1) | `ValueError` con mensaje "moisture" |
| `tests/domain/test_soil_reading_service.py` | Conductividad eléctrica en límites [0, 20 dS/m] | Sin excepción |
| `tests/domain/test_soil_reading_service.py` | Conductividad fuera de rango (-1, 20.1) | `ValueError` con mensaje "ec" |
| `tests/domain/test_soil_reading_service.py` | pH en límites [0, 14] | Sin excepción |
| `tests/domain/test_soil_reading_service.py` | pH fuera de rango (-0.1, 14.1) | `ValueError` con mensaje "ph" |
| `tests/domain/test_soil_reading_service.py` | Temperatura en límites [-10°C, 60°C] | Sin excepción |
| `tests/domain/test_soil_reading_service.py` | Valores no numéricos en campos de sensor | `ValueError` con mensaje "Sensor values must be numeric" |
| `tests/domain/test_soil_reading_service.py` | `recorded_at` como string ISO 8601 | Campo parseado correctamente con timezone UTC |
| `tests/domain/test_soil_reading_service.py` | `recorded_at` nulo | Asignación automática de timestamp UTC actual |
| `tests/domain/test_pir_classification_service.py` | Clasificación de eventos PIR por tipo | Evento clasificado correctamente (intrusión vs movimiento normal) |

**Capa 2 - Pruebas de Integración (Application Layer)**

Validan la interacción entre el servicio de aplicación y la capa de persistencia con una base de datos SQLite de prueba, verificando el ciclo completo de almacenamiento y recuperación.

| Archivo de Test | Escenario de Prueba | Resultado Esperado |
|---|---|---|
| `tests/application/test_soil_reading_application_service.py` | Registrar una lectura válida y recuperarla por ID | Lectura persistida con todos los campos correctos |
| `tests/application/test_soil_reading_application_service.py` | Consultar lecturas por `device_id` | Lista de lecturas filtradas correctamente |

**Capa 3 - Pruebas de Aceptación de API (Interfaces Layer)**

Validan el comportamiento del cliente HTTP contra los endpoints REST del Edge API, cubriendo los escenarios de autenticación, validación de payload y respuestas de error.

| Archivo de Test | Escenario de Prueba | Código HTTP Esperado |
|---|---|---|
| `tests/interfaces/test_soil_api.py` | POST `/api/v1/soil-monitoring/readings` sin API Key | `401 Unauthorized` |
| `tests/interfaces/test_soil_api.py` | POST sin `device_id` en header | `401 Unauthorized` |
| `tests/interfaces/test_soil_api.py` | POST sin `farm_id` en body | `400 Bad Request` |
| `tests/interfaces/test_soil_api.py` | POST con campos ESP32 válidos (`humidity_fc28`, `salinity_hr202l`, `soil_temp_ds18b20`) | `201 Created` con respuesta JSON completa |
| `tests/interfaces/test_soil_api.py` | POST con campos legacy válidos (`moisture`, `ec`, `temperature`) | `201 Created` |
| `tests/interfaces/test_soil_api.py` | POST con valor de sensor fuera de rango (moisture=999) | `400 Bad Request` con mensaje "moisture" |
| `tests/interfaces/test_iam_api.py` | POST `/api/v1/iam/devices` para registrar nuevo dispositivo | `201 Created` con `device_id` y `api_key` |
| `tests/interfaces/test_iam_api.py` | GET `/api/v1/iam/devices` para listar dispositivos registrados | `200 OK` con lista de dispositivos |

#### 6.2.2.6. Execution Evidence for Sprint Review

Esta sección consolida la evidencia de ejecución de todos los productos digitales entregados en el Sprint 2, presentando capturas de pantalla representativas de los flujos implementados en cada componente de la solución SATECHO.

#### Landing Page (v2)

La segunda versión de la Landing Page incorpora tres cambios estratégicos: la sección de video demostrativo del producto, la sección del equipo de la startup y la migración completa al modelo comercial premium (eliminando las opciones freemium). Estos cambios consolidan la propuesta de valor y la transparencia organizacional ante los potenciales clientes.

**Video About-the-Product**

Sección audiovisual integrada que demuestra el flujo operativo completo de SATECHO, desde la lectura de sensores hasta la visualización en el dashboard, validando la propuesta de valor ante visitantes indecisos.

![About-Product-Video-Section](./assets/images/sprint-2/About-Product-Video-Section.png)

**Team Section**

Sección institucional que presenta al equipo fundador de SATECHO con fotografías y roles, construyendo confianza y credibilidad ante potenciales clientes del sector agrícola.

![Team-Section](./assets/images/sprint-2/Team-Section.png)

**Planes Premium**

Versión actualizada de la sección de planes de pago, exclusivamente con opciones premium que reflejan la inversión en hardware IoT y soporte técnico especializado requeridos por el modelo de negocio.

![Premium-Plans-Section](./assets/images/sprint-2/Premium-Plans-Section.png)

#### Web Application (v2)

La versión final de la Aplicación Web amplía significativamente el alcance funcional con vistas especializadas para ambos segmentos objetivo: el agricultor y el agrónomo.

Mediante el siguiente vídeo, se evidencian los flujos implementados en este sprint:

![Referential Video - Web Application v2](./assets/images/sprint-2/Web-Application-v2-Execution-Evidence.png)

**Web Application v2 - SATECHO:** [Web Application v2 - Video](https://upcedupe-my.sharepoint.com/:v:/g/personal/u202110458_upc_edu_pe/sprint2-web-app)

**Dashboard Agrónomo - Análisis y Umbrales**

Vista especializada para el ingeniero agrónomo que permite monitorear análisis de suelo y configurar umbrales críticos por cultivo, habilitando alertas automáticas ante condiciones adversas.

![Agronomist-Analysis-Dashboard](./assets/images/sprint-2/Agronomist-Analysis-Dashboard.png)

**Dashboard Agrónomo - Gestión de Cuenta y Dispositivos**

Panel de administración que centraliza la gestión de cuenta del agrónomo, el monitoreo de dispositivos IoT de sus clientes asignados y el control de sesiones de riego activas.

![Agronomist-Account-Devices-View](./assets/images/sprint-2/Agronomist-Account-Devices-View.png)

**Dashboard Agrónomo - Cola de Casos Prioritarios**

Vista de gestión de urgencias que organiza las alertas críticas de todos los clientes del agrónomo en una cola priorizada, con acceso directo al detalle de cada incidente.

![Priority-Cases-Queue-View](./assets/images/sprint-2/Priority-Cases-Queue-View.png)

**Dashboard Agrónomo - Gestión de Perfil y Planes**

Módulo de configuración personal del agrónomo que permite actualizar datos profesionales, preferencias de notificación y el plan de suscripción activo.

![Agronomist-Profile-Plans-View](./assets/images/sprint-2/Agronomist-Profile-Plans-View.png)

**Dashboard Agricultor - Telemetría en Tiempo Real**

Vista de monitoreo continuo con gráficos de salinidad del suelo y registro histórico de eventos de seguridad perimetral, consolidando las métricas más críticas para la toma de decisiones.

![Telemetry-Dashboard-View](./assets/images/sprint-2/Telemetry-Dashboard-View.png)

**Dashboard Agricultor - Flota de Dispositivos IoT**

Vista de inventario operativo que centraliza el estado de conexión, las métricas de telemetría, las acciones disponibles y el historial de mantenimiento de toda la flota ESP32 desplegada en el campo.

![Device-Fleet-View](./assets/images/sprint-2/Device-Fleet-View.png)

**Reglas de Notificación**

Vista de configuración de alertas que permite al agricultor definir umbrales personalizados por dispositivo y tipo de métrica, determinando qué condiciones disparan notificaciones al móvil.

![Notification-Rules-View](./assets/images/sprint-2/Notification-Rules-View.png)

#### Mobile Application

La primera versión de la Aplicación Móvil implementa los flujos principales para ambos roles de usuario, con arquitectura Clean Architecture orientada a funcionalidades (feature-based bounded contexts) y conexión al REST API real.

Mediante el siguiente vídeo, se evidencian los flujos implementados en este sprint:

![Referential Video - Mobile Application](./assets/images/sprint-2/Mobile-Application-Execution-Evidence.png)

**Mobile Application - SATECHO:** [Mobile Application - Video](https://upcedupe-my.sharepoint.com/:v:/g/personal/u202110458_upc_edu_pe/sprint2-mobile-app)

**Login y Selección de Rol**

Pantalla de autenticación con selección de rol (agricultor / agrónomo) que redirige al usuario al workspace correspondiente según sus permisos asignados en el backend.

![Mobile-Login-Role-Selection](./assets/images/sprint-2/Mobile-Login-Role-Selection.png)

**Dashboard del Agricultor**

Centro de control móvil que muestra el estado de las parcelas, las métricas de telemetría del suelo en tiempo real y las sesiones de riego activas con actualización automática cada 15 segundos.

![Mobile-Farmer-Dashboard](./assets/images/sprint-2/Mobile-Farmer-Dashboard.png)

**Estado de Dispositivos e Irrigación**

Lista de dispositivos IoT con indicadores de conectividad en tiempo real y controles directos para iniciar o detener sesiones de riego de forma remota desde el campo.

![Mobile-Device-Status-Irrigation](./assets/images/sprint-2/Mobile-Device-Status-Irrigation.png)

**Workspace del Agrónomo**

Vista de seguimiento de clientes, gestión de alertas críticas asignadas y agenda de visitas técnicas, optimizando la operativa diaria del consultor agrícola desde su dispositivo móvil.

![Mobile-Agronomist-Workspace](./assets/images/sprint-2/Mobile-Agronomist-Workspace.png)

#### Edge API

La primera versión del Edge API implementa tres módulos bajo Clean Architecture: autenticación de dispositivos (IAM), captura de telemetría del suelo (Soil) y clasificación de eventos de seguridad perimetral (PIR).

![Edge-API-Execution-Evidence](./assets/images/sprint-2/Edge-API-Execution-Evidence.png)

#### Embedded Application (ESP32)

La primera versión del firmware SATECHO implementa una arquitectura FreeRTOS completamente orientada a eventos (0% bucles de polling), con cuatro sensores activos: FC28 (humedad de suelo, GPIO33), HR202L (salinidad/CE, GPIO14/32), DHT11 (temperatura ambiente, GPIO26) y DS18B20 (temperatura de suelo, GPIO25), junto con un sensor PIR de seguridad perimetral (GPIO27).

![Embedded-Application-Execution-Evidence](./assets/images/sprint-2/Embedded-Application-Execution-Evidence.png)

#### 6.2.2.7. Services Documentation Evidence for Sprint Review

Durante este Sprint 2, se desplegó la primera versión funcional del **RESTful API** de SATECHO, construida en Java con Spring Boot bajo una arquitectura de Domain-Driven Design (DDD) con Clean Architecture. La documentación interactiva de los endpoints se expone mediante **Swagger UI / OpenAPI 3.0**, accesible en la instancia de Azure App Service.

Los contextos acotados implementados en este sprint y sus endpoints principales son los siguientes:

**Bounded Context: IAM (Identity & Access Management)**

| Método | Endpoint | Descripción |
|---|---|---|
| POST | `/api/v1/authentication/sign-up` | Registro de nuevo usuario (agricultor o agrónomo) |
| POST | `/api/v1/authentication/sign-in` | Autenticación y obtención de JWT token |
| POST | `/api/v1/authentication/verify-account` | Verificación de cuenta mediante token de email |
| POST | `/api/v1/authentication/resend-verification` | Reenvío del email de verificación |
| GET | `/api/v1/users/{id}` | Consulta de datos del usuario autenticado |

**Bounded Context: Onboarding**

| Método | Endpoint | Descripción |
|---|---|---|
| POST | `/api/v1/farms` | Creación de una nueva granja/parcela para el agricultor |
| GET | `/api/v1/farms/{farmId}` | Consulta de datos de una granja específica |
| GET | `/api/v1/farms/user/{userId}` | Listado de todas las granjas de un usuario |
| POST | `/api/v1/farms/{farmId}/irrigation-zones` | Creación de zona de riego dentro de una granja |
| GET | `/api/v1/farms/{farmId}/irrigation-zones` | Listado de zonas de riego de una granja |
| DELETE | `/api/v1/farms/{farmId}/irrigation-zones/{zoneId}` | Eliminación de una zona de riego |

**Bounded Context: BI (Business Intelligence / MQTT Integration)**

| Método | Endpoint | Descripción |
|---|---|---|
| GET | `/api/v1/fleet/health` | Estado de salud general de la flota de dispositivos IoT |
| GET | `/api/v1/irrigation/sessions/active` | Sesiones de riego activas en tiempo real |
| GET | `/api/v1/notifications/critical` | Alertas críticas pendientes de revisión |
| POST | `/api/v1/irrigation/sessions/{sessionId}/command` | Envío de comando de actuador vía MQTT (start/stop irrigación) |

La documentación interactiva de los endpoints se expone mediante Swagger UI, permitiendo a los desarrolladores del frontend y del equipo de QA probar los contratos directamente desde el navegador sin necesidad de herramientas adicionales.

![Swagger-API-Documentation](./assets/images/sprint-2/Swagger-API-Documentation.png)

Adicionalmente, el **Edge API** expone los siguientes endpoints REST consumidos directamente por el firmware ESP32 y por el backend para sincronización de telemetría:

| Método | Endpoint | Descripción |
|---|---|---|
| POST | `/api/v1/iam/devices` | Registro de nuevo dispositivo ESP32 (obtención de API key) |
| GET | `/api/v1/iam/devices` | Listado de dispositivos registrados |
| POST | `/api/v1/soil-monitoring/readings` | Ingesta de lectura de telemetría de suelo desde ESP32 (autenticado por `X-API-Key`) |
| POST | `/api/v1/security/pir-events` | Registro de evento de seguridad perimetral detectado por sensor PIR |

#### 6.2.2.8. Software Deployment Evidence for Sprint Review

En este sprint, el despliegue se extendió a cuatro plataformas adicionales para dar soporte a los nuevos componentes de la solución.

**Backend REST API (Azure App Service)**

El RESTful API construido en Java con Spring Boot se desplegó en Azure App Service mediante un proceso de empaquetado con Maven y publicación automática desde GitHub Actions.

1. **Empaquetado:** Ejecución de `mvn clean package -DskipTests` para generar el artefacto `.jar` optimizado.

2. **Pipeline de CI/CD:** Configuración del workflow de GitHub Actions que detecta cambios en la rama `main` y dispara el build y despliegue automático.

3. **Publicación en Azure:** El artefacto `.jar` se envía a Azure App Service mediante el perfil de publicación configurado en los Secrets del repositorio.

4. **Verificación:** Confirmación del despliegue exitoso mediante el endpoint `/actuator/health` de Spring Boot Actuator.

![Backend-Azure-Deployment](./assets/images/sprint-2/Backend-Azure-Deployment.png)

**Mobile Application (Firebase App Distribution)**

La primera versión de la aplicación Flutter fue compilada y distribuida a los usuarios de prueba mediante Firebase App Distribution.

1. **Compilación:** Generación del paquete `.apk` desde Android Studio con `flutter build apk --release`.

2. **Carga en Firebase:** Subida del binario a la consola de Firebase en la sección App Distribution.

3. **Distribución:** Envío de invitaciones a los testers del equipo para validación del flujo completo en dispositivos reales.

![Mobile-Firebase-Distribution](./assets/images/sprint-2/Mobile-Firebase-Distribution.png)

**Web Application (Vercel)**

La versión v2 de la Aplicación Web mantuvo el despliegue continuo en Vercel, con actualización automática de la URL productiva al integrarse cambios en la rama `main`.

![Web-Application-Vercel-Deployment](./assets/images/sprint-2/Web-Application-Vercel-Deployment.png)

**Landing Page (GitHub Pages)**

La versión v2 de la Landing Page fue publicada automáticamente en GitHub Pages al realizar el merge de los cambios a la rama `main` del repositorio correspondiente.

![Landing-Page-GHPages-Deployment](./assets/images/sprint-2/Landing-Page-GHPages-Deployment.png)

#### 6.2.2.9. Team Collaborations Insights during Sprint

**Visión General del Sprint**

El Sprint 2 representó el mayor desafío colaborativo del proyecto al requerir la coordinación simultánea de seis repositorios con interdependencias técnicas directas. Para gestionar esta complejidad sin generar bloqueos, el equipo implementó una sesión de kickoff asíncrona donde se definieron los contratos de API (payloads JSON) entre el Edge API, el backend y las aplicaciones cliente antes de comenzar cualquier implementación. Este enfoque de "contract-first" permitió que los cinco desarrolladores trabajaran en paralelo sin necesidad de esperar por servicios reales.

**Landing Page v2 y Web Application v2**

El trabajo sobre los dos productos frontales del ciclo continuó bajo el modelo de ramas de funcionalidad atomizadas con Pull Requests obligatorios. El mayor volumen de commits en este periodo se concentró en la expansión del dashboard para el rol de agrónomo, que requirió múltiples iteraciones de feedback entre el líder de aspecto y los colaboradores para asegurar la coherencia visual y funcional entre las vistas.

![Team-Collaboration-Insights-Web-Application](./assets/images/sprint-2/Team-Collaboration-Insights-Web-Application-Sprint2.png)

**REST API (Backend)**

El backend comenzó su desarrollo en paralelo desde la primera semana del sprint, arrancando con los bounded contexts de IAM y Onboarding. La metodología de trabajo adoptó el patrón de "feature branches por contexto acotado", lo que permitió que cada capa (dominio, aplicación, infraestructura, interfaces) fuera desarrollada e integrada secuencialmente dentro de la misma rama, manteniendo el ciclo de feedback corto y los Pull Requests manejables en tamaño.

![Team-Collaboration-Insights-Backend](./assets/images/sprint-2/Team-Collaboration-Insights-Backend-Sprint2.png)

**Mobile Application**

El equipo de la aplicación móvil arrancó desde cero con un scaffold inicial que estableció la arquitectura base (feature-based bounded contexts con Clean Architecture), sobre la cual se construyeron los flujos de agricultor y agrónomo de forma incremental. La decisión de utilizar el mock de roles antes de conectar el API real permitió validar la experiencia de usuario antes de que el backend estuviera disponible, reduciendo el tiempo de integración final.

![Team-Collaboration-Insights-Mobile](./assets/images/sprint-2/Team-Collaboration-Insights-Mobile-Sprint2.png)

**Edge API**

El Edge API fue el repositorio con el proceso de desarrollo más estructurado del sprint, dado que siguió el ciclo completo de TDD (Test-Driven Development) para las tres capas de prueba: unitaria, integración y aceptación. Esta disciplina, aunque más lenta al inicio, garantizó que cada endpoint entregado tuviera cobertura de pruebas verificable antes de ser integrado al pipeline de comunicación con el firmware ESP32.

![Team-Collaboration-Insights-Edge](./assets/images/sprint-2/Team-Collaboration-Insights-Edge-Sprint2.png)

**Embedded Application**

### 6.2.3. Sprint 3

Este tercer sprint cierra el ciclo de valor del MVP SATECHO completando la cadena de alerta proactiva de extremo a extremo: desde la detección de movimiento en el ESP32 y la superación de umbrales de suelo en el Edge API, hasta la entrega de notificaciones push en el dispositivo móvil del agricultor. El sprint integra el motor de alertas de suelo (salinity, temperatura, estrés hídrico), el servicio de notificaciones push vía FCM, la sincronización de eventos PIR con el cloud, la autenticación biométrica y la integración MQTT en tiempo real en la Mobile Application.

#### 6.2.3.1. Sprint Planning 3

<table>
  <tr>
    <td>Sprint #</td>
    <td>Sprint 3</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Sprint Planning Background</strong></td>
  </tr>
  <tr>
    <td>Date</td>
    <td>2026-06-23</td>
  </tr>
  <tr>
    <td>Time</td>
    <td>22:00 p.m (GMT-5)</td>
  </tr>
  <tr>
    <td>Location</td>
    <td>Asynchronous session organized within the Discord communication platform</td>
  </tr>
  <tr>
    <td>Prepared By</td>
    <td>Huamani Sánchez, José Diego</td>
  </tr>
  <tr>
    <td>Attendees (to planning meeting)</td>
    <td>Estrada Cajamune, Abraham Andrés / Gamio Upiachihua, Brenda Lucía / Quispe Erasmo, Raul Ronaldo / Palacios, Yasser Renteria</td>
  </tr>
  <tr>
    <td>Sprint 2 Review Summary</td>
    <td>During Sprint 2, the team completed the full vertical integration of the SATECHO ecosystem across six simultaneous software products: Landing Page v2 (product demo video, team section, premium-only plans), Web Application v2 (agronomist dashboards, real-time telemetry and device fleet views for farmers), REST API v1 (IAM, Onboarding, and BI bounded contexts with MQTT integration), Mobile Application v1 (farmer and agronomist workspaces with role-based navigation and real API connectivity), Edge API v1 (device authentication, soil telemetry ingestion, PIR event classification, and a full three-layer test suite), and Embedded Firmware v1 (FreeRTOS event-driven architecture with FC28, HR202L, DS18B20, DHT11, and PIR sensors, plus irrigation valve control).</td>
  </tr>
  <tr>
    <td>Sprint 2 Retrospective Summary</td>
    <td>The adoption of the Team Software Process (TSP) framework in Sprint 2 proved effective in reducing bottlenecks by clarifying aspect leadership across six repositories, enabling five contributors to work in parallel. The contract-first API approach — agreeing on JSON payloads before implementation — was identified as the key enabler for parallel development without integration delays. For Sprint 3, the team maintains the TSP structure and redirects its focus toward closing the alert pipeline end-to-end rather than introducing new product scopes, keeping the sprint goal tightly bounded to observable farmer outcomes.</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Sprint Goal & User Stories</strong></td>
  </tr>
  <tr>
    <td>Sprint 3 Goal</td>
    <td>
<strong>Our focus is on</strong> completing the proactive alert pipeline — delivering PIR perimeter intrusion detection with push notifications, critical soil alerts (salinity and temperature), and real-time MQTT updates to the Mobile Application. <br>
<strong>We believe it delivers</strong> immediate, eyes-free awareness to independent farmers who need to respond to field threats and crop-damage risks without actively monitoring any screen, protecting crops and property around the clock. <br>
<strong>This will be confirmed when</strong> a farmer receives a push notification on their mobile device within 30 seconds of a PIR person-detection event on their parcel; when a farmer receives a critical salinity or temperature push notification within 30 seconds of a threshold breach; and when farmers can review the full classified security event history, configure active surveillance zones, and authenticate irrigation commands with biometrics from the Mobile Application.
    </td>
  </tr>
  <tr>
    <td>Sprint 3 Velocity</td>
    <td>67</td>
  </tr>
  <tr>
    <td>Sum of Story Points</td>
    <td>67</td>
  </tr>
</table>

#### 6.2.3.2. Aspect Leaders and Collaborations

Sprint 3 consolidates the alert and notification pipeline across the REST API, Mobile Application, Edge API, and Embedded layers. The TSP structure is maintained from Sprint 2, with the same aspect leaders redirecting their focus toward the remaining components required for MVP closure. No Landing Page changes are scoped for this sprint.

| Team Member (Last Name, First Name) | GitHub Username | Web App v3 | REST API v2 | Mobile App v2 | Edge API v2 | Embedded v2 |
| :---------------------------------- | :----------------: | :---------: |:-----------:| :---------: | :---------: | :---------: |
| Huamani Sánchez, José Diego | `ProgramadorHuamani` | C |    **L**    | | | |
| Estrada Cajamune, Abraham Andrés | `Abraham0310` | C |      C      | **L** | | |
| Gamio Upiachihua, Brenda Lucía | `B-Gamio` | **L** |      C      | C | | |
| Quispe Erasmo, Raul Ronaldo | `Raul-QE` | |      C      | | **L** | |
| Palacios, Yasser Renteria | `Mitos20` | |             | C | C | **L** |

#### 6.2.3.3. Sprint Backlog 3

Este tercer sprint prioriza la integración del motor de alertas de suelo (EP-002-TS004), el servicio de notificaciones push (EP-008-TS018), la sincronización de eventos PIR hacia el cloud (EP-003-TS007, EP-005-TS015), el subscriber de actuador con buffer offline (EP-005-TS019), y las mejoras clave de la Mobile Application: autenticación biométrica, integración MQTT en tiempo real y visualización de eventos de seguridad.

**Proyecto en Jira:** [https://satecho.atlassian.net/jira/software/projects/SCRUM/boards/1](https://satecho.atlassian.net/jira/software/projects/SCRUM/boards/1)

![Sprint-Backlog-3 - SATECHO](./assets/images/sprint-3/Sprint-Backlog-3.png)

# Sprint 3 – Sprint Backlog

| Sprint 3 | Sprint Backlog 3 | | | | | | |
|---|---|---|---|---|---|---|---|
| **User Story** | **Title** | **Work Item/Task** | **Title** | **Description** | **Estimation (SP)** | **Assigned to** | **Status** |
| EP-002-TS004 | TS-01: Implement Soil Alert Engine (Backend) | EP-002-TS004-T01 | Implement AlertEngineService consuming SoilReadingCreated events from RabbitMQ | As a Developer, I want an engine that evaluates each soil reading against configurable thresholds and generates typed alerts automatically so that critical conditions trigger timely notifications. | 8 | José Huamani | To-do |
| | | EP-002-TS004-T02 | Implement ThresholdRepository with default thresholds per sensor type (moisture, EC, temperature) | | | José Huamani | To-do |
| | | EP-002-TS004-T03 | Implement hysteresis logic and automatic RESOLVED transition when values return to safe range | | | José Huamani | To-do |
| EP-008-TS018 | TS-02: Implement Push Notification Service (Backend) | EP-008-TS018-T01 | Implement NotificationApplicationService with @RabbitListener for AlertCreated events | As a Developer, I want a service that processes alert events and sends push notifications via FCM so that farmers are notified in real time. | 5 | José Huamani | To-do |
| | | EP-008-TS018-T02 | Integrate Firebase Admin SDK and implement FCM device token storage and dispatch logic | | | José Huamani | To-do |
| EP-003-TS008 | TS-03: Implement PIR Debounce and Filtering (Embedded) | EP-003-TS008-T01 | Add PIR_DEBOUNCE_MS=3000 to satecho_config.h and debounce check to mqttCommandTask using millis() | As a Developer, I want the ESP32 to discard duplicate PIR triggers within 3000ms so that a single physical motion event does not generate multiple alerts. | 3 | Yasser Palacios | To-do |
| EP-003-TS007 | TS-04: Implement Edge PIR API + Cloud Sync | EP-003-TS007-T01 | Implement _sync_pir_once() calling cloud_client.post_security_event() per PIR event with synced=False | As a Developer, I want the Edge to synchronize classified PIR events to the cloud backend individually via periodic sync so that security data is reliably propagated. | 5 | Raul Quispe | To-do |
| | | EP-003-TS007-T02 | Integrate PIR sync into _run_loop() alongside soil sync using asyncio.gather() | | | Raul Quispe | To-do |
| EP-005-TS015 | TS-05: Implement Edge PIR Cloud Sync | EP-005-TS015-T01 | Verify _sync_pir_once() marks events synced=True on 2xx response and retains synced=False on failure | As a Developer, I want PIR events with synced=False to be individually sent to the cloud in each 60-second sync cycle so that no security events are lost. | 3 | Raul Quispe | To-do |
| EP-005-TS019 | TS-06: Implement Edge Actuator Command Subscriber with Offline Buffer | EP-005-TS019-T01 | Implement actuator_command_subscriber.py with MQTT subscription on agrosafe/+/devices/+/actuator/command | As a Developer, I want the Edge to forward actuator commands to the ESP32 when online and buffer them when the device is temporarily disconnected so that commands are not lost. | 5 | Raul Quispe | To-do |
| | | EP-005-TS019-T02 | Implement device_tracker.py with mark_seen(), is_online() (ONLINE_WINDOW_SECONDS=60), and buffer drain on reconnect | | | Raul Quispe | To-do |
| EP-008-US020 | US-01: Critical Alert Push Notifications | EP-008-US020-T01 | Implement FCM token registration endpoint and token persistence from Mobile App on login | As a farmer, I want to receive push notifications when critical alerts are detected so that I can act quickly even when the app is closed. | 5 | Abraham Estrada | To-do |
| | | EP-008-US020-T02 | Validate end-to-end push delivery: soil threshold breach → AlertCreated → FCM → device notification | | | Abraham Estrada | To-do |
| EP-008-US021 | US-02: In-App Notification Center | EP-008-US021-T01 | Implement NotificationsScreen in Flutter with chronological list, mark-as-read action, and badge decrement on navigation bar | As a farmer, I want to view a history of all received alerts and mark them as read so that I can review them at my convenience. | 3 | Abraham Estrada | To-do |
| EP-002-US005 | US-03: Receive Critical Salinity Alerts | EP-002-US005-T01 | Wire EC > 5 dS/m threshold into AlertEngineService and confirm AlertCreated event triggers FCM push with message "Critical salinity in parcel [name]" | As a farmer, I want to receive alerts when the electrical conductivity of my soil exceeds the critical threshold so that I can prevent crop damage. | 3 | José Huamani | To-do |
| EP-002-US006 | US-04: Receive Critical Temperature Alerts | EP-002-US006-T01 | Wire soil temperature > 40°C threshold into AlertEngineService and confirm AlertCreated event triggers FCM push notification | As a farmer, I want to be alerted if soil temperature exceeds dangerous levels so that I can protect my crops. | 3 | José Huamani | To-do |
| EP-003-US001 | US-05: Receive Intrusion Alerts | EP-003-US001-T01 | Implement SecurityAlert creation on PERSON classification received from cloud PIR sync, publish to RabbitMQ for FCM dispatch with message "Person detected in [parcel name]" | As a farmer, I want to receive an alert when the PIR sensor detects a person on my parcel so that I can protect my crops. | 5 | Brenda Gamio | To-do |
| EP-003-US002 | US-06: View Security Event History | EP-003-US002-T01 | Implement security history table in Web App with PERSON/ANIMAL/WIND classification filter, pulse duration, frequency per minute, and CSV export | As a farmer, I want to view the history of classified PIR events so that I can understand the activity on my parcels. | 3 | Brenda Gamio | To-do |
| EP-003-US003 | US-07: Configure Security Zones | EP-003-US003-T01 | Implement zone enable/disable toggle bound to zone_id; suppress alert generation for disabled zones | As a farmer, I want to configure which zones of my farm have active PIR monitoring so that I can customize surveillance coverage. | 3 | Brenda Gamio | To-do |
| EP-004-US007 | US-08: View Security Events in Mobile App | EP-004-US007-T01 | Implement SecurityScreen in Flutter with event classification list (PERSON/ANIMAL/WIND), timestamp, and pulse duration; ensure push notification is delivered via FCM when app is closed | As a farmer, I want to review PIR events from the mobile app and receive intrusion push notifications even when the app is not open. | 3 | Abraham Estrada | To-do |
| EP-002-TS008 | TS-07: Biometric Authentication (Mobile App) | EP-002-TS008-T01 | Integrate local_auth package for fingerprint/Face ID; store and retrieve JWT via FlutterSecureStorage on successful biometric verification | As a Developer, I want to integrate biometric authentication in the Flutter app so that critical irrigation actions require secure identity confirmation. | 5 | Abraham Estrada | To-do |
| | | EP-002-TS008-T02 | Handle biometrics unavailable (disable option) and 3-consecutive-failure fallback to password login | | | Abraham Estrada | To-do |
| EP-004-TS010 | TS-08: MQTT Mobile Integration (Real Time) | EP-004-TS010-T01 | Implement MqttService singleton using mqtt_client package; subscribe to agrosafe/{farmId}/devices/{deviceId}/status and update SensorBloc via event | As a Developer, I want to integrate MQTT in the Flutter app so that real-time sensor state updates are received without polling every 15 seconds. | 5 | Abraham Estrada | To-do |
| | | EP-004-TS010-T02 | Implement exponential backoff reconnection with up to 5 retry attempts on MQTT connection loss | | | Abraham Estrada | To-do |

El firmware del ESP32 fue desarrollado de forma completamente independiente al inicio, adoptando una arquitectura FreeRTOS orientada a eventos que elimina los bucles de polling. La integración con el Edge API se realizó en la fase final del sprint mediante la implementación del módulo de captura de dirección MAC para la autenticación y la configuración del cliente MQTT para la publicación de telemetría hacia el broker Mosquitto del Edge.