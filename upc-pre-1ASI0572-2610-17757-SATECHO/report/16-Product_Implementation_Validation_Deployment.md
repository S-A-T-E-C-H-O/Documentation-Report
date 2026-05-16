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
| Mobile Application   |                                             |
| REST Services API    | [https://github.com/S-A-T-E-C-H-O/Web-API-Service-SATECHO](https://github.com/S-A-T-E-C-H-O/Web-API-Service-SATECHO)                                            |
| Edge Services API    |                                             |
| Embedded Application |                                             |

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
El objetivo de este primer Sprint es establecer la base de identidad digital y la arquitectura funcional inicial de SATECHO, centrándose en el despliegue de una Landing Page de alto impacto orientada a captar clientes potenciales del sector agrícola y agrónomos interesados en la integridad de datos. Nos enfocaremos en proyectar nuestra solución como el fin de las suposiciones empíricas sobre el riego y la iluminación, sustituyéndolas por un monitoreo automatizado y veraz. <br> Simultáneamente, desarrollaremos el núcleo de la Web Application, implementando un sistema de Authentication Management y un Dashboard preliminar mediante un Fake API para validar la navegación, las reglas de acceso y la visualización de datos. <br> Con este avance, buscamos confirmar la viabilidad del flujo de usuario y la solidez de la interfaz, asegurando que nuestra infraestructura sea capaz de transformar la incertidumbre del campo en decisiones precisas y seguras desde cualquier dispositivo inteligente.
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

#### 6.2.1.3. Sprint Backlog 3

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
| EP-007-TS021 | TS-01: Implement Lazy Loading and Code Splitting for Dashboard Modules | EP-007-TS021-T01 | Configure lazy loading for dashboard modules | As a Developer, I want the system to implement lazy loading of dashboard modules so that the initial load time is reduced. | 5 | Yasser Palacios | To-Do |
| | | EP-007-TS021-T02 | Implement code splitting by routes and critical components | | | Abraham Estrada | To-Do |
| | | EP-007-TS021-T03 | Measure and document improvement in initial load times | | | Raul Quispe | To-Do |
| EP-007-TS022 | TS-02: Implement Global State Management for Dashboard | EP-007-TS022-T01 | Select and integrate a global state manager in the web frontend | As a Developer, I want to implement a global state manager on the web frontend so that sensor data, alerts, and configuration are synchronized between components without redundant API calls. | 5 | Brenda Gamio | To-Do |
| | | EP-007-TS022-T02 | Centralize sensor data and alerts state | | | Jose Huamani | To-Do |
| | | EP-007-TS022-T03 | Eliminate redundant API calls through shared state | | | Yasser Palacios | To-Do |
| EP-007-TS027 | TS-03: Internationalization Support | EP-007-TS027-T01 | Configure the internationalization library (i18n) in the project | As a Developer, I want the system to support internationalization so that the platform can be used comfortably without language barriers. | 3 | Abraham Estrada | To-Do |
| | | EP-007-TS027-T02 | Implement dynamic language switching and translation files | | | Raul Quispe | To-Do |
| EP-007-TS028 | TS-04: Accessibility Compliance | EP-007-TS028-T01 | Implement ARIA labels across all interface components | As a Developer, I want the system to comply with accessibility standards so that users with disabilities can access all features without barriers. | 3 | Brenda Gamio | To-Do |

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