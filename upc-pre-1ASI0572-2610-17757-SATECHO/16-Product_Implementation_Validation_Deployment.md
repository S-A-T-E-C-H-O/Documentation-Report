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