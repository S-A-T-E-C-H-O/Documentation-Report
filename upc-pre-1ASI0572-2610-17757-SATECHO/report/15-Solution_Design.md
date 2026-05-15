# Capítulo V: Solution UI/UX Design
## 5.1. Style Guidelines.
En esta sección se establecen las directrices visuales y de experiencia de usuario implementadas en la plataforma SATECHO. El objetivo principal del diseño es transformar datos técnicos complejos provenientes de sensores IoT en información clara, intuitiva y accionable para agricultores e ingenieros agrónomos.
### 5.1.1. General Style Guidelines.
Esta sección define los lineamientos generales vinculados al diseño visual, abarcando desde la identidad de marca hasta el tono comunicacional. A continuación, se presentan las principales decisiones y referencias adoptadas:

#### Branding:
- **Identidad Visual**:
SATECHO presenta una identidad visual moderna y tecnológica inspirada en la agricultura inteligente y la automatización de cultivos. La interfaz busca transmitir seguridad, confianza, monitoreo constante e innovación accesible.

- **Logotipo**:
El logotipo utiliza una composición minimalista basada en elementos naturales y tecnológicos, integrando tonos verdes relacionados con agricultura sostenible, elementos geométricos suaves que representan conectividad IoT y tipografía sans-serif moderna para transmitir claridad y simplicidad.

#### Typography:
- **Fuente primaria**: Se utiliza la tipografía sans-serif Manrope para títulos y encabezados principales, reforzando una estética moderna, tecnológica y minimalista dentro del ecosistema visual de SATECHO. El color principal utilizado es el verde suave #7A9A7A, transmitiendo naturaleza, estabilidad y monitoreo inteligente.
- **Fuente secundaria**: Para cuerpos de texto, descripciones y contenido informativo, se utiliza la tipografía Inter, debido a su alta legibilidad en dispositivos móviles y paneles digitales. El color principal empleado es #2C3440, proporcionando claridad visual y una lectura cómoda en pantallas.
- **Fuente terciaria**: Para etiquetas, indicadores secundarios, filtros y estados complementarios, se utiliza la tipografía Inter acompañada del color #764229, permitiendo establecer jerarquía visual y diferenciación entre elementos interactivos e informativos.
- **Neutral**: Los textos auxiliares, placeholders y estados inactivos utilizan el color neutral #767774, ayudando a reducir el ruido visual y manteniendo una interfaz limpia y equilibrada.
- **Tamaño**: La jerarquía tipográfica fue diseñada para facilitar la identificación inmediata de información crítica como niveles de humedad, salinidad, nitrógeno y alertas del sistema IoT. Los títulos utilizan tamaños amplios y pesos Bold, mientras que las descripciones y etiquetas emplean tamaños medianos y pequeños para conservar una experiencia minimalista y enfocada en la toma rápida de decisiones. <br>
<img src="./assets/images/style-guidelines/GeneralTypography.png" alt="Image typography" width="500"/><br>

#### Colors:
- **Paleta de colores**: La paleta utiliza tonos naturales y terrosos que transmiten sostenibilidad, tecnología agrícola y confianza. El verde principal #5E7A5E representa vegetación, estabilidad y control eficiente del riego. El gris verdoso secundario #8C8F8F aporta equilibrio visual y una sensación tecnológica/moderna sin perder el enfoque natural. El tono tierra terciario #D4A373 conecta con el suelo agrícola y añade calidez a la interfaz. Finalmente, el color neutral claro #FAF9F6 mantiene limpieza visual, amplitud y facilita la lectura de la información en dashboards y paneles de monitoreo.
- **Contrastes**: El contraste entre el verde principal y el fondo neutral genera una excelente legibilidad para textos, métricas y navegación principal. El uso del tono tierra como color de acento permite destacar elementos importantes como botones CTA, alertas de humedad o estados activos sin romper la armonía visual. El gris secundario funciona bien para componentes secundarios, bordes y estados inactivos, creando jerarquía visual clara dentro de la aplicación. En conjunto, la combinación mantiene un balance entre tecnología y naturaleza, ideal para una web app de control de riego agrícola. <br>
<img src="./assets/images/style-guidelines/ColorSystem.png" alt="Image color" width="500"/><br>


## 5.1.2. Web, Mobile and IoT  Guidelines 

Este documento establece los estándares de diseño visual e interacción para el ecosistema SATECHO, asegurando coherencia, accesibilidad y eficiencia operativa en sus tres plataformas: Aplicación Web (Escritorio), Aplicación Móvil y Dispositivos IoT de campo.

### 5.1.2.1. Web Application Style Guidelines 

Orientada a la administración central, análisis profundo y supervisión técnica por parte de Agrónomos y Administradores de Sistema.

#### 5.1.2.1.1. Estructure y Layout

- **Grid:** Sistema de 12 columnas con un ancho máximo de contenedor de 1440px.
- **Navegación:** Sidebar lateral persistente a la izquierda (ancho fijo: 256px). Permite acceso rápido a Dashboard, Zonas, Seguridad, Dispositivos y Ajustes.
- **Jerarquía:** El contenido principal se organiza en tarjetas modulares con sombras sutiles para separar niveles de información sin saturar la vista.

#### 5.1.2.1.2 Specific Components

- **Tablas de Datos:** Filas con hover state en `#F4F3F1`. Uso de badges de estado (Normal, Atención, Crítico) para filtrado visual rápido.
- **Gráficos de Monitoreo:** Líneas suaves con puntos de datos claros. Uso de la paleta de marca para diferenciar variables (Humedad: Azul, Temp: Naranja, EC: Púrpura).

### 5.1.2.2 Mobile Application  Guidelines 

Diseñada para la operación en campo, priorizando el uso con una sola mano y la legibilidad bajo luz solar directa.

#### 5.1.2.2.1 Navigation and Gestures

- **Barra Inferior:** Centro de navegación con los 5 destinos principales: Inicio, Parcelas, Alertas, Tareas y Más.
- **Acciones Rápidas:** Uso de tarjetas grandes (mínimo 44px de altura táctil) para activar riegos o registrar actividades.
- **Feedback Táctil:** Los botones y elementos interactivos deben mostrar un estado de pulsación claro (escala ligera o cambio de opacidad).

#### 5.1.2.2.2 "Soft Minimalist" Aesthetics

- **Tarjetas:** Esquinas redondeadas (12px-16px) y sombras muy suaves (`0 4px 20px rgba(0,0,0,0.05)`).
- **Color:** Uso predominante de fondos claros (`#FAF9F5`) para evitar la fatiga visual. Los acentos verdes se usan solo en elementos activos para guiar el ojo.


### 5.1.2.3 IoT Application  Guidelines 

Estándares para la interacción con el hardware físico (sensores, válvulas y estaciones meteorológicas).

#### 5.1.2.3.1 Device Visualization

- **LCD/OLED:** Información alfanumérica clara. Prioridad: [Nombre de Zona] + [Valor Crítico].
- **Señalización LED:**
  - **Verde Continuo:** Operación normal / Válvula abierta.
  - **Rojo Parpadeante:** Error de conexión / Batería crítica.
  - **Ámbar:** Fuera de umbral de seguridad.

#### 5.1.2.3.2 Data Consistency

Los términos utilizados en el hardware (ej. "Hum. Suelo", "Zona A1") deben ser idénticos a los mostrados en la App y la Web para evitar confusiones al operario.


### 5.1.2.4 Visual Foundations (Design Tokens)

#### 5.1.2.4 Color Palette (Organic Professionalism)

- **Surface (Fondo):** `#FAF9F5`
- **Surface Dim (Secundario):** `#DADAD6`
- **Primary Green (Marca):** `#476649`
- **Primary Light (Acentos):** `#7A9A7A`
- **Text (Charcoal):** `#1A1C18`
- **Alert Red (Error):** `#BC4749`

#### 5.1.2.4.1 Typography: Manrope

- **Headlines (Bold):** Tracking -2%, para títulos de sección.
- **Body (Regular):** 16px, line-height 1.5.
- **Labels (Semibold):** 12px, para metadatos y categorías.

#### 5.1.2.4.2 Iconography

Uso exclusivo de **Material Symbols (Rounded)**.

- **Activos:** Rellenos (Filled) en color `#476649`.
- **Inactivos:** Estilo contorno (Outline) en color Slate/Gris.

### 5.1.2.5 Accessibility and States

- **Contraste:** Todos los textos deben cumplir con el estándar WCAG AA (mínimo 4.5:1).
- **Error States:** Mensajes de error siempre acompañados de un icono descriptivo y un color de soporte (Earth Red).
- **Loading:** Spinners o esqueletos (Skeletons) siguiendo el tono de la marca para evitar la sensación de latencia.

## 5.2. Information Architecture.
### 5.2.1. Organization Systems.
### 5.2.2. Labeling Systems.

En esta sección se presenta el sistema de etiquetado (labeling system) para el ecosistema integral de SATECHO. Este sistema prioriza la claridad semántica, la sencillez visual y el uso de términos familiares para el sector agrícola, manteniendo la estética de "Profesionalismo Orgánico" definida en nuestros estándares.

Se ha buscado una coherencia absoluta entre el lenguaje técnico de los agrónomos y el lenguaje operativo de los agricultores, facilitando la adopción tecnológica y reduciendo la carga cognitiva en entornos de campo.

### A. Landing Page
El etiquetado en el sitio público utiliza un lenguaje directo, tecnológico y enfocado en la eficiencia de recursos.

#### Navigation Sections:
*   **Inicio:** Sección de bienvenida con la propuesta de valor de agricultura inteligente.
*   **Funcionalidades:** Detalle técnico de los sensores, automatización y análisis de datos.
*   **Planes:** Modelos de suscripción adaptados al tamaño de la operación (Hectáreas).
*   **Demo:** Acceso a una vista previa interactiva del panel de control.
*   **Contacto:** Canal directo para asesoría técnica y comercial.

#### Call-to-Action Buttons (CTA):
*   **"Registrarse" / "Probar gratis":** Invita al usuario a iniciar la configuración de su predio.
*   **"Iniciar Sesión":** Acceso seguro para usuarios registrados (Agricultores, Agrónomos, Admins).
*   **"Solicitar Demo":** Petición de asesoría personalizada.
*   **"Contactar experto":** Enlace directo a soporte o ventas vía WhatsApp.

### B. Web Application 
El etiquetado se adapta dinámicamente según el rol del usuario para optimizar los flujos de trabajo especializados.

#### Farmer Dashboard
*   **Dashboard:** Resumen operativo de clima, estado de zonas y alertas críticas hoy.
*   **Zonas y Riego:** Control directo de válvulas y monitoreo de humedad/EC por parcela.
*   **Seguridad:** Visualización de eventos de cámaras y alertas perimetrales.
*   **Dispositivos:** Listado técnico de salud de sensores, puertas de enlace (Edge) y baterías.
*   **Historial:** Registro histórico de riegos ejecutados (automáticos y manuales).

#### Agronomist Dashboard:
*   **Cartera de Clientes:** Listado de predios bajo supervisión con indicadores de riesgo.
*   **Análisis Pro:** Herramientas de comparación de datos históricos y tendencias de suelo.
*   **Recomendaciones:** Módulo para redactar y enviar propuestas técnicas a los agricultores.
*   **Agenda:** Calendario de visitas técnicas programadas a campo.

#### Administration Dashboard (Admin):
*   **Infraestructura:** Estado global de servidores, nodos IoT y conectividad rural.
*   **Usuarios:** Gestión de permisos y roles del sistema.
*   **Configuración Global:** Ajuste de umbrales por defecto y ventanas de mantenimiento.

### C. Mobile Application
Optimizada para la consulta rápida y la operación táctil en exteriores, utiliza etiquetas concisas en español.

#### Bottom Navigation Bar:
*   **Inicio:** Resumen de "Hoy" y acceso rápido a riegos pendientes.
*   **Parcelas:** Mapa o lista de sectores con telemetría en tiempo real.
*   **Alertas:** Centro de notificaciones urgentes (Humedad crítica, Fallo de sensor).
*   **Tareas:** Lista de actividades programadas o recomendaciones del agrónomo.
*   **Más:** Acceso a perfil, ajustes de notificaciones y modo offline.

### D. Form Labels and Operational Buttons
Estandarización de entradas de datos para garantizar la integridad de la base de datos agrícola.

#### Form Fields:
*   **"Nombre del Predio":** Identificador de la finca o instalación.
*   **"Superficie (ha)":** Tamaño de la operación en hectáreas.
*   **"Tipo de Cultivo":** Selección (Maíz, Soja, Trigo, etc.) para aplicar umbrales biológicos.
*   **"Humedad Actual (%)":** Lectura porcentual del sensor de suelo.
*   **"Umbral Crítico":** Punto de activación de alerta automática.

#### Operational Action Buttons:
*   **"Abrir Válvula" / "Cerrar Válvula":** Comandos manuales de irrigación.
*   **"Registrar Actividad":** Botón para documentar fertilización u observaciones.
*   **"Sincronizar":** Forzar actualización de datos en zonas de baja conectividad.
*   **"Guardar Configuración":** Confirma cambios en umbrales o horarios.
*   **"Marcar como revisado":** Resuelve visualmente un evento de seguridad.

### E. IoT Interface 
Etiquetas minimalistas para pantallas de cristal líquido (LCD) de 16x2 caracteres.

*   **"Hum. Suelo":** Etiqueta para el valor de humedad.
*   **"Temp. Amb":** Temperatura capturada por el nodo.
*   **"Válvula: ON/OFF":** Estado del actuador de riego.
*   **"Buscando WiFi...":** Estado de conexión del dispositivo ESP32.

### 5.2.3. SEO Tags and Meta Tags
### 5.2.4. Searching Systems.
## 5.2.5. Navigation Systems.
## 5.3. Landing Page UI Design.
### 5.3.1. Landing Page Wireframe.
### 5.3.2. Landing Page Mock-up.
## 5.4. Applications UX/UI Design.
### 5.4.1. Applications Wireframes.
### 5.4.2. Applications Wireflow Diagrams.
### 5.4.2. Applications Mock-ups.
### 5.4.3. Applications User Flow Diagrams.
## 5.5. Applications Prototyping.
## 5.6. IoT Device Design.