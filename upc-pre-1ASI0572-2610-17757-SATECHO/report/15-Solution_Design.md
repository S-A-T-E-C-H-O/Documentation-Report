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
### 5.2.3. SEO Tags and Meta Tags
### 5.2.4. Searching Systems.
### 5.2.5. Navigation Systems.
## 5.3. Landing Page UI Design.

En esta sección, el equipo de diseño traduce las decisiones tomadas en torno a la experiencia de usuario (UX) y la arquitectura de la información en una propuesta de interfaz de usuario (UI) para la página de aterrizaje de **SATECHO**. El objetivo es comunicar de forma efectiva el valor de la agricultura de precisión tanto a agricultores como a agrónomos.

#### Diseño y Arquitectura de Información
La propuesta de la Landing Page para SATECHO sigue el enfoque de **"Profesionalismo Orgánico"**, priorizando una navegación intuitiva y una jerarquía visual clara que transmita confianza técnica y calidez humana.

Se han integrado los siguientes pilares de diseño:
*   **Jerarquía visual:** Uso de tipografía Manrope en pesos Bold para encabezados de gran tamaño, facilitando que los mensajes de valor y los CTAs (Call to Action) sean lo primero que el usuario identifique.
*   **Diseño inclusivo y accesible:** El uso de colores suaves como el crema (`#FAF9F5`) para el fondo y verdes profundos (`#476649`) para la acción asegura un contraste adecuado (cumpliendo WCAG AA) y una lectura cómoda bajo diversas condiciones de iluminación.
*   **Sistema de diseño coherente:** Todos los componentes, desde las tarjetas de características hasta los selectores de planes, utilizan un radio de curvatura de 12px y sombras sutiles, manteniendo la cohesión con el ecosistema de aplicaciones web y móviles de SATECHO.

### 5.3.1. Landing Page Wireframe

La estructura del wireframe para la versión de escritorio se divide en las siguientes secciones estratégicas, diseñadas para guiar al usuario desde el interés inicial hasta la conversión:

#### 1. Header (Encabezado)
Incluye el logotipo de SATECHO a la izquierda, un menú de navegación centrado con los enlaces principales (Inicio, Funcionalidades, Planes, Demo, Contacto) y los botones de acción para "Iniciar Sesión" y un CTA destacado para "Registrarse".

<img src="./assets/images/wireframes/landing_wireframe_header.png" alt="Image color" width="500"/><br>

#### 2. Sección Hero
Presenta la propuesta de valor principal: "Monitoreo inteligente de suelo e irrigación". Contiene un título de alto impacto, una descripción breve de los beneficios (ahorro de agua y optimización) y dos botones principales: "Empieza tu prueba gratuita" y "Ver demo". A la derecha, un marcador de posición para la imagen principal del producto.

<img src="./assets/images/wireframes/landing_wireframe_hero.png" alt="Image color" width="500"/><br>

#### 3. Sección de Estadísticas
Un cinturón de datos clave que muestra métricas de éxito del sistema, como "10k+ Usuarios Activos" y "30% Ahorro de Agua", validando la eficacia de la plataforma de forma inmediata.

<img src="./assets/images/wireframes/landing_wireframe_statistics.png" alt="Image color" width="500"/><br>

#### 4. Sección de Características (Features)
Utiliza iconos y descripciones breves para destacar las funcionalidades técnicas del ecosistema SATECHO: Monitoreo en tiempo real (sensores ESP32), automatización de riego y seguridad perimetral.

<img src="./assets/images/wireframes/landing_wireframe_process.png" alt="Image color" width="500"/><br>

#### 5. Sección para Agrónomos
Un bloque diferenciado con fondo negro marca que comunica las herramientas específicas para agricultores: monitoreo multi-parcela, reportes marca blanca y análisis de datos históricos.

<img src="./assets/images/wireframes/landing_wireframe_farmers.png" alt="Image color" width="500"/><br>

#### 6. Sección de Proceso
Un flujo visual de 3 pasos que explica lo sencillo que es comenzar: (1) Instalación de sensores, (2) Conexión a la nube y (3) Control total desde el dispositivo y solicitud de la demo.

<img src="./assets/images/wireframes/landing_wireframe_demo.png" alt="Image color" width="500"/><br>

#### 7. Planes y Precios
Presentación comparativa de las suscripciones (Básico, Pro y Enterprise), destacando el plan "Pro" como el más popular para operaciones medianas.

<img src="./assets/images/wireframes/landing_wireframe_plans.png" alt="Image color" width="500"/><br>

#### 8. Forms (Pie de página)
Formulario con diferentes secciones para poner tu nombre completo, email, telefono, tamaño de operación (hectáreas) y el rol.

<img src="./assets/images/wireframes/landing_wireframe_footer.png" alt="Image color" width="500"/><br>

#### 8. Footer (Pie de página)
Información de contacto corporativa, enlaces legales (Privacidad, Términos) y accesos directos a redes sociales o soporte técnico vía WhatsApp.

<img src="./assets/images/wireframes/landing_wireframe_footer.png" alt="Image color" width="500"/><br>


### 5.3.2. Landing Page Mock-up.
## 5.4. Applications UX/UI Design.
### 5.4.1. Applications Wireframes.

En esta fase, hemos desarrollado de manera conjunta los wireframes para visualizar detalladamente la arquitectura y el diseño de las interfaces de usuario. Gracias a este esfuerzo colaborativo, transformamos los requisitos funcionales en esquemas gráficos precisos, definiendo así la distribución y presentación de cada componente en la aplicación definitiva.

#### Web Application Wireframes

Para la versión de escritorio, el diseño se enfocó en maximizar el uso del espacio en pantalla, estableciendo una jerarquía visual clara y una navegación expansiva.

#### Mobile Application Wireframes
En la versión móvil, la prioridad fue la optimización del espacio, la ergonomía y la accesibilidad táctil.

### 5.4.2. Applications Wireflow Diagrams.
### 5.4.2. Applications Mock-ups.
### 5.4.3. Applications User Flow Diagrams.
## 5.5. Applications Prototyping.
## 5.6. IoT Device Design.