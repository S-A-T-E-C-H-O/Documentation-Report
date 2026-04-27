# Capítulo IV - Solution Software Design

## 4.1. Strategic-Level Domain-Driven Design

El diseño estratégico de la plataforma AgroSafe se abordó mediante un proceso estructurado de Diseño Orientado al Dominio (DDD). El equipo empleó EventStorming como técnica fundamental para explorar, modelar y comprender el dominio del negocio, seguido de pasos de refinamiento progresivo para identificar contextos delimitados, visualizar flujos de mensajes, definir lienzos de contexto y establecer relaciones de mapeo de contexto.

### 4.1.1. Design-Level EventStorming
El proceso de Event Storming se realizó utilizando la herramienta MIRO, donde construimos todo el flujo de manera colaborativa. Iniciamos con la fase de Exploración No Estructurada, en la que analizamos e intercambiamos ideas sobre los eventos del dominio, siguiendo las buenas prácticas recomendadas. Para la identificación de estos eventos, consideramos criterios como su relevancia, frecuencia y temporalidad.

![EventStorming-step1](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/dl-eventstorming/es-events.png)

_Evidencia del desarrollo del primer paso del DDD._

---

Después, avanzamos al segundo paso, denominado **Timelines**, donde analizamos y debatimos la secuencia de los eventos del dominio.

El timeline describe el flujo de un sistema de riego inteligente que inicia con la captura de datos de sensores (humedad, pH y temperatura), analiza condiciones de estrés hídrico y genera un diagnóstico. Con base en ello, ejecuta el riego automáticamente hasta normalizar los valores y finalmente cierra el proceso sincronizando los datos. Después, avanzamos al segundo paso, denominado **Timelines**, donde analizamos y debatimos la secuencia de los eventos del dominio.

El timeline describe el flujo de un sistema de riego inteligente que inicia con la captura de datos de sensores (humedad, pH y temperatura), analiza condiciones de estrés hídrico y genera un diagnóstico. Con base en ello, ejecuta el riego automáticamente hasta normalizar los valores y finalmente cierra el proceso sincronizando los datos.

![EventStorming-step2](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/dl-eventstorming/es-timeline.png)

_Evidencia del desarrollo del segundo paso de DDD (Uno de los timelines)._

### 4.1.1.1 Candidate Context Discovery

Para hallar nuestros Candidate Context, continuamos con el paso 3 Pain Points, donde discutimos eventos del flujo que podrían ser cuellos de botella, pasos manuales que requieren automatización o riesgos técnicos críticos que podrían romper la experiencia del usuario o la integridad del cultivo.

En el timeline de Onboarding y Registro, un pain point es la validación de datos duplicados o erróneos en el formulario. Si el sistema no valida en tiempo real el correo o la contraseña, el usuario podría perder toda la información ingresada y abandonar el proceso de registro.

En este timeline, un pain point es la continuidad del wizard de configuración. Si el usuario abandona el flujo a la mitad, el sistema debe poder retomar exactamente donde se dejó; de lo contrario, la fricción aumenta y se pierde la conversión.

![EventStorming-step3.1](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-pain-points-1.png)

---

En el timeline de Riego y Control de Cultivo, un pain point es la latencia e intermitencia de red en zonas rurales. Específicamente, existe un riesgo crítico entre el Comando de apertura de válvula encolado y la Electroválvula abierta. Si la conexión falla en ese instante, el cultivo podría no recibir el agua necesaria a tiempo.

En este timeline, un pain point es la concurrencia de comandos. Dos usuarios (agricultor y agrónomo) podrían enviar comandos simultáneos para la misma zona generando un conflicto de estado en la electroválvula. Además, si un comando se ejecuta tras recuperar conexión pero supera los 30 minutos, podría regar un cultivo que ya fue hidratado manualmente, generando desperdicio hídrico.

![EventStorming-step3.2](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-pain-points-2.png)

---

En el timeline de Seguridad Perimetral, un pain point es el riesgo de falsas alarmas. Si el sensor PIR o el algoritmo de clasificación térmica en el Edge no distinguen adecuadamente entre viento, animales pequeños e intrusos humanos, se genera fatiga en el usuario y desconfianza en el sistema.En el timeline de Seguridad Perimetral, un pain point es el riesgo de falsas alarmas. Si el sensor PIR o el algoritmo de clasificación térmica en el Edge no distinguen adecuadamente entre viento, animales pequeños e intrusos humanos, se genera fatiga en el usuario y desconfianza en el sistema.

En este timeline, un pain point es la garantía de entrega de alertas en zonas rurales. Antes de enviar la notificación por WhatsApp, debemos asegurar que el mensaje llegue incluso con cobertura intermitente; de lo contrario, la alerta de intrusión es inútil.

![EventStorming-step3.3](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-pain-points-3.png)

---

En el timeline de Gestión de Cuentas y Suscripciones, un pain point es la integridad de los datos históricos. La suspensión de una cuenta por mora NO debe borrar los datos históricos del cultivo; el sistema debe conservar la información para cuando el cliente reactive su servicio.

En este timeline, un pain point es la seguridad de dispositivos perdidos. Un dispositivo IoT reportado como perdido pero con credenciales activas es un riesgo grave, ya que podría enviar telemetría falsa o manipular el riego remotamente.

![EventStorming-step3.4](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-pain-points-4.png)

---

En el timeline de Asesoría y Configuración de Umbrales, un pain point es la seguridad en la modificación manual. Si el agricultor ingresa un Umbral modificado manualmente con valor fuera de rango seguro, existe el riesgo de que un valor erróneo dañe el cultivo por sobre-riego o bloqueo salino.

En este timeline, un pain point es la sobrescritura de configuraciones. La Aplicación masiva de plantilla por parte del agrónomo podría sobrescribir ajustes previos personalizados por el agricultor sin que este se percate, generando conflictos operativos y desconfianza.

![EventStorming-step3.5](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-pain-points-5.png)

---

Después, continuamos con el cuarto paso del DDD llamado Pivotal Points, donde identificamos puntos o eventos comerciales importantes que indicaban un cambio drástico en el contexto, el estado del sistema o la fase del proceso. Estos eventos marcan fronteras naturales entre bounded contexts.

En el flujo de Onboarding e Identidad, el evento Email verificado por el usuario actúa como pivotal point. Marca el cambio irreversible de un visitante anónimo a un usuario autenticado, separando el contexto de adquisición del contexto de gestión de identidad y acceso.

![EventStorming-step4.1](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-pivotal-points-1.png)

---

En el flujo de Monitoreo y Diagnóstico, el evento Estrés hídrico detectado es pivotal. Indica que el sistema ha pasado de solo recolectar datos brutos (Lectura de humedad) a interpretar el estado fisiológico del cultivo, separando el monitoreo de suelo del diagnóstico agronómico.

En el flujo de Control de Riego, el evento Diagnóstico agronómico generado y posteriormente Riego iniciado son pivotes críticos. El primero separa la capa de análisis de la capa de ejecución; el segundo marca la transición del dominio de software al dominio físico (IoT Device/Actuator), donde una acción en el mundo real es irreversible.

![EventStorming-step4.2](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-pivotal-points-2.png)

---

En el flujo de Seguridad, el evento Evento clasificado como HUMANO es pivotal. Cambia el contexto de monitoreo pasivo a alerta crítica inmediata, disparando notificaciones externas y requiriendo una política de prioridad alta.

![EventStorming-step4.3](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-pivotal-points-3.png)

---

En el flujo de Gestión de Cuentas, los eventos Cuenta de cliente suspendida por mora y Cuenta reactivada tras regularizar pago son pivotes de estado de negocio. Condicionan el acceso a funcionalidades premium y la sincronización de dispositivos IoT.

![EventStorming-step4.4](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-pivotal-points-4.png)

---

En el flujo de Dispositivos IoT, el evento Dispositivo iot offline detectado (o falta de heartbeat en 5 min) es pivotal. Cambia el contexto de operación normal a estado de fallo, requiriendo políticas de caché local, encolamiento de comandos y notificación de soporte.

![EventStorming-step4.5](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-pivotal-points-5.1.png)

![EventStorming-step4.5](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-pivotal-points-5.2.png)

---

Con todo ello, comenzamos el paso de Commands, donde escribimos el desencadenante de ciertos eventos del dominio, así como el actor encargado.

![EventStorming-step5.1](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-commands-1.png)

![EventStorming-step5.2](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-commands-2.png)

![EventStorming-step5.3](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-commands-3.png)

![EventStorming-step5.4](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-commands-4.png)

![EventStorming-step5.5](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-commands-5.png)

![EventStorming-step5.6](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-commands-6.png)

![EventStorming-step5.7](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-commands-7.png)

![EventStorming-step5.8](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-commands-8.png)

![EventStorming-step5.9](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-commands-9.png)

![EventStorming-step5.10](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-commands-10.png)

---

Después proseguimos con el paso 6, Policies, donde identificamos eventos que debían ejecutarse en automático o necesitaban alguna política de negocio.

![EventStorming-step6.1](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-policies-1.png)

![EventStorming-step6.2](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-policies-2.png)

![EventStorming-step6.3](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-policies-3.png)

![EventStorming-step6.4](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-policies-4.png)

![EventStorming-step6.5](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-policies-5.png)

![EventStorming-step6.6](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-policies-6.png)

![EventStorming-step6.7](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-policies-7.png)

![EventStorming-step6.8](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-policies-8.png)

![EventStorming-step6.9](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-policies-9.png)

---

Con ello procedemos a discutir los Read Models, es decir, representaciones visuales que comprenden el flujo del dominio y sirven como proyecciones optimizadas para consultas.

![EventStorming-step7.1](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-read-models-1.png)

![EventStorming-step7.2](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-read-models-2.png)

![EventStorming-step7.3](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-read-models-3.png)

![EventStorming-step7.4](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-read-models-4.png)

![EventStorming-step7.5](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-read-models-5.png)

![EventStorming-step7.6](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-read-models-6.png)

![EventStorming-step7.7](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-read-models-7.png)

![EventStorming-step7.8](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-read-models-8.png)

![EventStorming-step7.9](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-read-models-9.png)

![EventStorming-step7.10](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-read-models-10.png)

![EventStorming-step7.11](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-read-models-11.png)

---

También empezamos a discutir el uso de Sistemas Externos, donde únicamente se encontró necesario en los siguientes servicios.

![EventStorming-step8.1](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-external-systems-1.png)

![EventStorming-step8.2](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-external-systems-2.png)

![EventStorming-step8.3](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-external-systems-3.png)

![EventStorming-step8.4](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-external-systems-4.png)

---

Después, se comenzó con la identificación de los Aggregates, para ello, tomamos criterios como granularidad, consistencia transaccional y estabilidad del ciclo de vida. Con esos criterios, se procedió a elegir los Aggregates principales.

![EventStorming-step9.1](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-aggregates-1.png)

![EventStorming-step9.2](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-aggregates-2.png)

![EventStorming-step9.3](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-aggregates-3.png)

![EventStorming-step9.4](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-aggregates-4.png)

![EventStorming-step9.5](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-aggregates-5.png)

![EventStorming-step9.6](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-aggregates-6.png)

![EventStorming-step9.7](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-aggregates-7.png)

![EventStorming-step9.8](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-aggregates-8.png)

![EventStorming-step9.9](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-aggregates-9.png)

![EventStorming-step9.10](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-aggregates-10.png)

![EventStorming-step9.11](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-aggregates-11.png)

---

Ya por último y después de un análisis y discusión grupal, los siguientes Bounded Contexts fueron elegidos, siguiendo algunas condiciones, como la separación de responsabilidades de negocio, cambios de lenguaje ubicuo y las fronteras marcadas por los pivotal points. Por ello, al final se eligió estos Bounded Contexts:

![EventStorming-step10](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-bounded-context-1.png)

![EventStorming-step10](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/candidate-context-discovery/es-bounded-context-2.png)

### 4.1.1.2 Domain Message Flows Modeling

En esta sección, el equipo explica y evidencia el proceso seguido para visualizar cómo deben colaborar los bounded contexts para resolver los casos que se presentan en el negocio para los usuarios del sistema. Para ello, aplicamos la técnica de visualización Domain Storytelling, la cual nos permite narrar las interacciones clave donde los mensajes y eventos cruzan las fronteras de los dominios.En esta sección, el equipo explica y evidencia el proceso seguido para visualizar cómo deben colaborar los bounded contexts para resolver los casos que se presentan en el negocio para los usuarios del sistema. Para ello, aplicamos la técnica de visualización Domain Storytelling, la cual nos permite narrar las interacciones clave donde los mensajes y eventos cruzan las fronteras de los dominios.

A continuación, se presentan los cuatro flujos de mensajería más relevantes para SATECHO, donde se evidencia la colaboración entre los contextos de Soil Monitor, Irrigation Control, Perimeter Security, Account Management y Agronomist Advisory.A continuación, se presentan los cuatro flujos de mensajería más relevantes para SATECHO, donde se evidencia la colaboración entre los contextos de Soil Monitor, Irrigation Control, Perimeter Security, Account Management y Agronomist Advisory.

#### 1. Riego Inteligente Automático

![Domain-Message-Flows-1](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/domain-message-flow-model/smart-irrigation.png)

_Este flujo muestra cómo el contexto de Monitoreo de Suelo dispara acciones en el contexto de Control de Riego._

---

#### 2. Alerta de Seguridad Perimetral

![Domain-Message-Flows-2](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/domain-message-flow-model/security-alert.png)

_Este flujo muestra la detección de un intruso y la notificación al agricultor._

---

#### 3. Suspensión de Cuenta por Mora

![Domain-Message-Flows-3](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/domain-message-flow-model/account-suspension.png)

_Este flujo muestra cómo el negocio afecta la operación técnica._

---

#### 4. Asesoría Remota del Agrónomo

![Domain-Message-Flows-4](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/domain-message-flow-model/remote-advisory.png)

_Este flujo muestra cómo el agrónomo consume datos para ayudar al cliente._

### 4.1.1.3 Bounded Context Canvases

De acuerdo con los bounded contexts definidos en puntos anteriores, se crearon sus respectivos Canvases. El equipo seleccionó cada contexto por orden de importancia estratégica para el negocio SATECHO, aplicando un proceso iterativo de refinamiento. A continuación, se detalla el diseño de cada uno:De acuerdo con los bounded contexts definidos en puntos anteriores, se crearon sus respectivos Canvases. El equipo seleccionó cada contexto por orden de importancia estratégica para el negocio SATECHO, aplicando un proceso iterativo de refinamiento. A continuación, se detalla el diseño de cada uno:De acuerdo con los bounded contexts definidos en puntos anteriores, se crearon sus respectivos Canvases. El equipo seleccionó cada contexto por orden de importancia estratégica para el negocio SATECHO, aplicando un proceso iterativo de refinamiento. A continuación, se detalla el diseño de cada uno:

#### 1. Soil Monitoring & Agronomic Diagnosis Context

![Bounded-Context-Canvas-1](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context-canvases/soil-monitoring-&-agronomic-diagnosis.png)

_Contexto Core: Es la razón de ser del negocio. Si esto falla, no hay valor._

---

#### 2. Irrigation & Actuator Control Context

![Bounded-Context-Canvas-2](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context-canvases/irrigation-&-actuator-control.png)

_Contexto Core: Ejecuta las decisiones físicas. Alto impacto en el campo._

---

#### 3. Perimeter Security & Classification Context

![Bounded-Context-Canvas-3](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context-canvases/perimeter-security-&-classification.png)

_Contexto Core: Diferenciador clave frente a la competencia._

---

#### 4. Account, Subscription & Billing Management Context

![Bounded-Context-Canvas-4](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context-canvases/account-subscription-&-billing-management.png)

_Contexto Supporting: Esencial para el modelo de negocio SaaS._

---

#### 5. IoT Device & Edge Management Context

![Bounded-Context-Canvas-5](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context-canvases/iot-device-&-edge-management.png)

_Contexto Supporting/Generic: Mantiene el "cuerpo" del sistema._

### 4.1.2. Context Mapping

En esta sección, explicamos y evidenciamos nuestro proceso de elaboración de un conjunto de context maps, los cuales visualizan las relaciones estructurales entre los bounded contexts identificados en nuestro proyecto. Para ello, revisamos minuciosamente la información recolectada durante el Event Storming y la elaboración de los Bounded Context Canvases, utilizándola para producir y refinar diseños candidatos. Este análisis estructural nos permite entender y alinear claramente los contextos para alcanzar los objetivos del negocio de manera eficiente, minimizando el acoplamiento técnico y maximizando la autonomía de los equipos de desarrollo.

Durante el proceso de mapeo, el equipo aplicó un enfoque iterativo de cuestionamiento estratégico, planteando preguntas clave para evaluar alternativas de diseño antes de consolidar la arquitectura final:
- **¿Qué pasaría si movemos esta capability a otro bounded context?**
    
    Se evaluó mover la *clasificación de eventos perimetrales* al contexto de `Soil Monitoring`. Sin embargo, esto mezclaría el lenguaje ubicuo agronómico con el de seguridad física, rompiendo la cohesión del dominio. Se decidió mantenerlo en `Perimeter Security` para preservar la especialización y permitir evoluciones independientes de los algoritmos de detección térmica.

- **¿Qué pasaría si descomponemos esta capability y movemos uno de los sub-capabilities a otro bounded context?**

    Se analizó separar la *ingestión de telemetría* de la *gestión de firmware/OTA* dentro de `IoT Device Management`. Aunque viable a escala enterprise, para la fase MVP añadiría latencia y complejidad de red innecesaria. Se mantuvo unificado con interfaces internas claras, priorizando la simplicidad operativa en campo.

- **¿Qué pasaría si partimos el bounded context en múltiples bounded contexts?**

  Se consideró dividir `Account & Subscription Management` en `Identity` y `Billing`. Dado que la validación de suscripción y el control de acceso están fuertemente acoplados en el modelo de negocio SaaS (la mora detiene el acceso inmediatamente), partirlos generaría transacciones distribuidas complejas. Se mantuvo como un único contexto Supporting con responsabilidades bien delimitadas internamente.

- **¿Qué pasaría si tomamos esta capability de estos 3 contexts y lo usamos para formar un nuevo context?**

  Se revisó la duplicación de lógica de *notificaciones* (WhatsApp, SMS, Push) en Security, Soil y Account. En lugar de crear un contexto independiente prematuramente, se optó por un patrón de **Open Host Service** con un **Published Language** ligero, permitiendo que cada contexto core publique eventos estandarizados que un módulo de dispatching consume sin acoplarse a la lógica de origen.

- **¿Qué pasaría si duplicamos una funcionalidad para romper la dependencia?**

  Se evaluó duplicar el catálogo de *umbrales de cultivo* en `Irrigation Control` para evitar consultas a `Soil Monitoring`. Esto violaría el principio de única fuente de verdad. Se descartó la duplicación y se estableció un contrato síncrono/asíncrono claro, priorizando la consistencia agronómica sobre la optimización de red.

- **¿Qué pasaría si creamos un shared service para reducir la duplicación entre múltiples bounded contexts?**

  Se analizó un **Shared Kernel** para autenticación y gestión de roles entre todos los contextos. Dado que `Account Management` debe evolucionar según regulaciones de pagos y seguridad sin afectar la lógica core de riego o diagnóstico, se rechazó el Shared Kernel por el alto riesgo de acoplamiento y se adoptó un modelo **Conformist** con tokens estandarizados.

- **¿Qué pasaría si aislamos los core capabilities y movemos los otros a un context aparte?**

  Esta pregunta consolidó la arquitectura final. Se aislaron explícitamente los contextos Core (`Soil Monitoring`, `Irrigation Control`, `Perimeter Security`) de los Supporting/Generic (`Account Management`, `IoT Device Management`). Esto permite que el equipo priorice la innovación en la propuesta de valor diferencial, mientras los contextos de soporte pueden ser reemplazados o integrados con soluciones SaaS externas en el futuro sin impactar el núcleo del negocio.

- **¿Qué pasaría si partimos el bounded context en múltiples bounded contexts?**

  Se consideró dividir `Account & Subscription Management` en `Identity` y `Billing`. Dado que la validación de suscripción y el control de acceso están fuertemente acoplados en el modelo de negocio SaaS (la mora detiene el acceso inmediatamente), partirlos generaría transacciones distribuidas complejas. Se mantuvo como un único contexto Supporting con responsabilidades bien delimitadas internamente.

- **¿Qué pasaría si tomamos esta capability de estos 3 contexts y lo usamos para formar un nuevo context?**

  Se revisó la duplicación de lógica de *notificaciones* (WhatsApp, SMS, Push) en Security, Soil y Account. En lugar de crear un contexto independiente prematuramente, se optó por un patrón de **Open Host Service** con un **Published Language** ligero, permitiendo que cada contexto core publique eventos estandarizados que un módulo de dispatching consume sin acoplarse a la lógica de origen.

- **¿Qué pasaría si duplicamos una funcionalidad para romper la dependencia?**

  Se evaluó duplicar el catálogo de *umbrales de cultivo* en `Irrigation Control` para evitar consultas a `Soil Monitoring`. Esto violaría el principio de única fuente de verdad. Se descartó la duplicación y se estableció un contrato síncrono/asíncrono claro, priorizando la consistencia agronómica sobre la optimización de red.

- **¿Qué pasaría si creamos un shared service para reducir la duplicación entre múltiples bounded contexts?**

  Se analizó un **Shared Kernel** para autenticación y gestión de roles entre todos los contextos. Dado que `Account Management` debe evolucionar según regulaciones de pagos y seguridad sin afectar la lógica core de riego o diagnóstico, se rechazó el Shared Kernel por el alto riesgo de acoplamiento y se adoptó un modelo **Conformist** con tokens estandarizados.

- **¿Qué pasaría si aislamos los core capabilities y movemos los otros a un context aparte?**

  Esta pregunta consolidó la arquitectura final. Se aislaron explícitamente los contextos Core (`Soil Monitoring`, `Irrigation Control`, `Perimeter Security`) de los Supporting/Generic (`Account Management`, `IoT Device Management`). Esto permite que el equipo priorice la innovación en la propuesta de valor diferencial, mientras los contextos de soporte pueden ser reemplazados o integrados con soluciones SaaS externas en el futuro sin impactar el núcleo del negocio.

#### Discusión de alternativas y aproximación final

Tras evaluar las alternativas, el equipo concluyó que la mejor aproximación es un mapa de contextos descentralizado con contratos explícitos, donde los contextos Core actúan como proveedores de valor agronómico y los Supporting actúan como habilitadores operativos y comerciales. Se priorizaron los patrones Customer/Supplier, Open Host Service (OHS) con Published Language, y Conformist, evitando por completo el uso de Shared Kernels para garantizar la independencia de despliegue y evolución.

1. **IoT Device Management Context — Soil Monitoring Context**

   *Relación clave:* **Customer/Supplier** con **Published Language**.

   `IoT Device Management` actúa como *Upstream* (Supplier), normalizando datos crudos de hardware y publicándolos mediante un lenguaje estandarizado de telemetría. `Soil Monitoring` es el *Downstream* (Customer), consumiendo estos datos sin conocer los detalles de comunicación MQTT o protocolos del ESP32. Esta relación desacopla la evolución del firmware de la lógica agronómica.
    
    ![Context-Mapping-1](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/context-mapping/iot-device-management.png)

    ![Context-Mapping-1](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/context-mapping/soil-monitoring-&-diagnosis.png)

---

2. **Soil Monitoring Context — Irrigation & Actuator Control Context**

   *Relación clave:* **Customer/Supplier** con **Anti-Corruption Layer (ACL)**.

   `Soil Monitoring` es el *Upstream*, generando diagnósticos y recomendaciones de riego. `Irrigation Control` es el *Downstream*, responsable de la ejecución física. Dado que el contexto de riego debe protegerse de cambios frecuentes en los algoritmos de diagnóstico, se implementa un ACL que traduce las recomendaciones agronómicas a comandos de actuador válidos y seguros, garantizando que fallos en el análisis no deriven en acciones físicas peligrosas.

    ![Context-Mapping-2](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/context-mapping/soil-monitoring-&-diagnosis.png)

    ![Context-Mapping-2](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/context-mapping/irrigation-control.png)

---

3. **Account & Subscription Management Context — Core Contexts (Soil, Irrigation, Security)**

   *Relación clave:* **Conformist** con **Open Host Service**.

   `Account Management` define las reglas de suscripción, acceso y facturación. Los contextos Core actúan como **Conformist**, adaptándose a las APIs y políticas expuestas por Account para validar permisos y estado de cuenta. Account expone un **Open Host Service** estable para consultas de suscripción, permitiendo que los contextos Core funcionen incluso si Account migra a un proveedor de billing externo en el futuro.

    ![Context-Mapping-3](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/context-mapping/subscriptions-&-payments.png)

    ![Context-Mapping-3](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/context-mapping/admin-biling-&-operations.png)

---

4. **Perimeter Security Context — Notification Dispatch**

   *Relación clave:* **Open Host Service** con **Published Language**.

   `Perimeter Security` publica eventos clasificados (`IntrusionDetected`, `FalseAlarmLogged`) mediante un contrato claro. El módulo de notificaciones se suscribe a estos eventos sin conocer la lógica de clasificación térmica. Esto permite escalar canales de alerta (WhatsApp, SMS, Email) sin modificar el código de seguridad.

    ![Context-Mapping-4](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/context-mapping/perimeter-security.png)

    ![Context-Mapping-4](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/context-mapping/notification.png)

---

5. **IoT Device Management Context ↔ Account & Subscription Management Context**

   *Relación clave:* **Customer/Supplier**.

   `Account Management` (Upstream) emite comandos de suspensión/reactivación por mora o reporte de pérdida. `IoT Device Management` (Downstream) debe conformarse a estas órdenes para invalidar credenciales o detener telemetría, asegurando la integridad comercial y de seguridad del servicio.

    ![Context-Mapping-5](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/context-mapping/subscriptions-&-payments.png)

    ![Context-Mapping-5](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/context-mapping/admin-biling-&-operations.png)

    ![Context-Mapping-5](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/context-mapping/iot-device-management.png)

## 4.2. Strategic-Level Domain-Driven Design

### 4.2.1. Bounded Context: Onboarding

Este bounded context gestiona la experiencia del visitante desde que llega a la landing page hasta que completa el wizard de inicio y accede al dashboard. Su responsabilidad es guiar al usuario por el proceso de selección de plan, registro y configuración inicial, garantizando que si el wizard es abandonado a mitad pueda retomarse desde donde se dejó.

#### Diccionario de Clases

![Onboarding-Dictionary](upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/onboarding/dictionary-onboarding-1.png)

![Onboarding-Dictionary](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/onboarding/dictionary-onboarding-2.png)

### 4.2.1.1. Domain Layer

![Onboarding-Domain-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/onboarding/onboarding-domain-layer.png)

### 4.2.1.2. Interface Layer

![Onboarding-Interface-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/onboarding/onboarding-interface-layer.png)

### 4.2.1.3. Application Layer

![Onboarding-Application-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/onboarding/onboarding-application-layer.png)

### 4.2.1.4. Infrastructure Layer

![Onboarding-Infrastructure-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/onboarding/onboarding-infrastructure-layer.png)

### 4.2.1.5. Bounded Context Software Architecture Component Level Diagrams

![Onboarding-Component-Level-Diagram](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/onboarding/onboarding-component.png)

### 4.2.1.6 Bounded Context Software Architecture Code Level Diagrams

### 4.2.1.6.1 Bounded Context Domain Layer Class Diagrams

![Onboarding-Domain-Class-Diagram](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/onboarding/onboarding-domain-layer-class-diagram.png)

### 4.2.1.6.2 Bounded Context Database Design Diagram

![Onboarding-Database-Design](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/onboarding/onboarding-database-design-diagram.png)

---

### 4.2.2. Bounded Context: Identity & Access Management

Gestiona el registro de usuarios (agricultores y agrónomos), autenticación, verificación de email, restablecimiento de contraseña, y los flujos de suspensión, reactivación y desactivación de cuentas gestionados por el staff.
#### Diccionario de Clases

![Identity-Access-Management-Dictionary](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/identity-access-management/dictionary-identity-access-management-1.png)

![Identity-Access-Management-Dictionary](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/identity-access-management/dictionary-identity-access-management-2.png)

### 4.2.2.1. Domain Layer

![Identity-Access-Management-Domain-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/identity-access-management/identity-access-management-domain-layer.png)

### 4.2.2.2. Interface Layer

![Identity-Access-Management-Interface-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/identity-access-management/identity-access-management-interface-layer.png)

### 4.2.2.3. Application Layer

![Identity-Access-Management-Application-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/identity-access-management/identity-access-management-application-layer.png)

### 4.2.2.4. Infrastructure Layer

![Identity-Access-Management-Infrastructure-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/identity-access-management/identity-access-management-infrastructure-layer.png)

### 4.2.2.5. Bounded Context Software Architecture Component Level Diagrams

![Identity-Access-Management-Component-Level-Diagram](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/identity-access-management/identity-access-management-component.png)

### 4.2.2.6 Bounded Context Software Architecture Code Level Diagrams

### 4.2.2.6.1 Bounded Context Domain Layer Class Diagrams

![Identity-Access-Management-Domain-Class-Diagram](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/identity-access-management/identity-access-management-domain-layer-class-diagram.png)

### 4.2.2.6.2 Bounded Context Database Design Diagram

![Identity-Access-Management-Database-Design](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/identity-access-management/identity-access-management-database-design-diagram.png)

---

### 4.2.3. Bounded Context: Subscriptions & Payments

Gestiona los planes de suscripción, el procesamiento de pagos a través de un proveedor externo y los flujos de suspensión, reactivación y cancelación de cuentas por mora.

#### Diccionario de Clases

![Subscriptions-Payments-Dictionary](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/subscriptions-payments/dictionary-subscriptions-payments-1.png)

![Subscriptions-Payments-Dictionary](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/subscriptions-payments/dictionary-subscriptions-payments-2.png)

### 4.2.3.1. Domain Layer

![Subscriptions-Payments-Domain-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/subscriptions-payments/subscriptions-payments-domain-layer.png)

### 4.2.3.2. Interface Layer

![Subscriptions-Payments-Interface-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/subscriptions-payments/subscriptions-payments-interface-layer.png)

### 4.2.3.3. Application Layer

![Subscriptions-Payments-Application-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/subscriptions-payments/subscriptions-payments-application-layer.png)

### 4.2.3.4. Infrastructure Layer

![Subscriptions-Payments-Infrastructure-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/subscriptions-payments/subscriptions-payments-infrastructure-layer.png)

### 4.2.3.5. Bounded Context Software Architecture Component Level Diagrams

![Subscriptions-Payments-Component-Level-Diagram](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/subscriptions-payments/subscriptions-payments-component.png)

### 4.2.3.6 Bounded Context Software Architecture Code Level Diagrams

### 4.2.3.6.1 Bounded Context Domain Layer Class Diagrams

![Subscriptions-Payments-Domain-Class-Diagram](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/subscriptions-payments/subscriptions-payments-domain-layer-class-diagram.png)

### 4.2.3.6.2 Bounded Context Database Design Diagram

![Subscriptions-Payments-Database-Design](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/subscriptions-payments/subscriptions-payments-database-design-diagram.png)

---

### 4.2.4. Bounded Context: Communication

Este bounded context gestiona el despacho de alertas y notificaciones hacia los usuarios finales. Según tu Event Storming, los componentes clave son **Notification Dispatch**, **Enviar Alerta** y la integración con **Twilio** como sistema externo.

#### Diccionario de Clases

![Communication-Dictionary](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/communication/dictionary-communication-1.png)

![Communication-Dictionary](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/communication/dictionary-communication-2.png)

### 4.2.4.1. Domain Layer

![Communication-Domain-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/communication/communication-domain-layer.png)

### 4.2.4.2. Interface Layer

![Communication-Interface-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/communication/communication-interface-layer.png)

### 4.2.4.3. Application Layer

![Communication-Application-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/communication/communication-application-layer.png)

### 4.2.4.4. Infrastructure Layer

![Communication-Infrastructure-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/communication/communication-infrastructure-layer.png)

### 4.2.4.5. Bounded Context Software Architecture Component Level Diagrams

![Communication-Component-Level-Diagram](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/communication/communication-component.png)

### 4.2.4.6 Bounded Context Software Architecture Code Level Diagrams

### 4.2.4.6.1 Bounded Context Domain Layer Class Diagrams

![Communication-Domain-Class-Diagram](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/communication/communication-domain-layer-class-diagram.png)

### 4.2.4.6.2 Bounded Context Database Design Diagram  

![Communication-Database-Design](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/communication/communication-database-design-diagram.png)

---

### 4.2.5. Bounded Context: IoT Device Management

Este bounded context gestiona el ciclo de vida completo de los dispositivos IoT físicos desplegados en campo. Según tu Event Storming, los agregados principales son **IoT Device** y el mecanismo de detección offline por heartbeat: si no se recibe un heartbeat en un rango de 5 minutos, el equipo es detectado como offline.

#### Diccionario de Clases

![IoT-Device-Management-Dictionary](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/iot-device-management/dictionary-iot-device-management-1.png)

![IoT-Device-Management-Dictionary](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/iot-device-management/dictionary-iot-device-management-2.png)

### 4.2.5.1. Domain Layer

![IoT-Device-Management-Domain-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/iot-device-management/iot-device-management-domain-layer.png)

### 4.2.5.2. Interface Layer

![IoT-Device-Management-Interface-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/iot-device-management/iot-device-management-interface-layer.png)

### 4.2.5.3. Application Layer

![IoT-Device-Management-Application-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/iot-device-management/iot-device-management-application-layer.png)

### 4.2.5.4. Infrastructure Layer

![IoT-Device-Management-Infrastructure-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/iot-device-management/iot-device-management-infrastructure-layer.png)

### 4.2.5.5. Bounded Context Software Architecture Component Level Diagrams

![IoT-Device-Management-Component-Level-Diagram](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/iot-device-management/iot-device-management-component.png)

### 4.2.5.6 Bounded Context Software Architecture Code Level Diagrams

### 4.2.5.6.1 Bounded Context Domain Layer Class Diagrams

![IoT-Device-Management-Domain-Class-Diagram](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/iot-device-management/iot-device-management-domain-layer-class-diagram.png)

### 4.2.5.6.2 Bounded Context Database Design Diagram  

![IoT-Device-Management-Database-Design](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/iot-device-management/iot-device-management-database-design-diagram.png)

---

### 4.2.6. Bounded Context: Soil Monitoring & Diagnosis

Este bounded context gestiona la experiencia del visitante desde que llega a la landing page hasta que completa el wizard de inicio y accede al dashboard. Su responsabilidad es guiar al usuario por el proceso de selección de plan, registro y configuración inicial, garantizando que si el wizard es abandonado a mitad pueda retomarse desde donde se dejó.

#### Diccionario de Clases

![Soil-Monitoring-Dictionary](upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/soil-monitoring-diagnosis/dictionary-soil-monitoring-diagnosis-1.png)

![Soil-Monitoring-Dictionary](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/soil-monitoring-diagnosis/dictionary-soil-monitoring-diagnosis-2.png)

![Soil-Monitoring-Dictionary](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/soil-monitoring-diagnosis/dictionary-soil-monitoring-diagnosis-3.png)

![Soil-Monitoring-Dictionary](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/soil-monitoring-diagnosis/dictionary-soil-monitoring-diagnosis-4.png)

### 4.2.6.1. Domain Layer

![Soil-Monitoring-Domain-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/soil-monitoring-diagnosis/soil-monitoring-diagnosis-domain-layer.png)

### 4.2.6.2. Interface Layer

![Soil-Monitoring-Interface-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/soil-monitoring-diagnosis/soil-monitoring-diagnosis-interface-layer.png)

### 4.2.6.3. Application Layer

![Soil-Monitoring-Application-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/soil-monitoring-diagnosis/soil-monitoring-diagnosis-application-layer.png)

### 4.2.6.4. Infrastructure Layer

![Soil-Monitoring-Infrastructure-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/soil-monitoring-diagnosis/soil-monitoring-diagnosis-infrastructure-layer.png)

### 4.2.6.5. Bounded Context Software Architecture Component Level Diagrams

![Soil-Monitoring-Component-Level-Diagram](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/soil-monitoring-diagnosis/soil-monitoring-diagnosis-component.png)

### 4.2.6.6 Bounded Context Software Architecture Code Level Diagrams

### 4.2.6.6.1 Bounded Context Domain Layer Class Diagrams

![Soil-Monitoring-Domain-Class-Diagram](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/soil-monitoring-diagnosis/soil-monitoring-diagnosis-domain-layer-class-diagram.png)

### 4.2.5.6.2 Bounded Context Database Design Diagram

![Soil-Monitoring-Database-Design](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/soil-monitoring-diagnosis/soil-monitoring-diagnosis-database-design-diagram.png)

---

### 4.2.7. Bounded Context: Irrigation & Actuator Control

Este bounded context gestiona el control físico de las electroválvulas de riego. Según tu Event Storming, los agregados principales son **Valve State**, **Irrigation Command** y **Offline Command Queue**, con tres flujos claramente diferenciados: **Flujo online**, **Flujo offline** y **Flujo conflictivo**.

#### Diccionario de Clases

![Soil-Monitoring-Dictionary](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/irrigation-acuator-control/dictionary-irrigation-acuator-control-1.png)

![Soil-Monitoring-Dictionary](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/irrigation-acuator-control/dictionary-irrigation-acuator-control-2.png)

### 4.2.7.1. Domain Layer

![Irrigation-Actuator-Control-Domain-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/irrigation-acuator-control/irrigation-acuator-control-domain-layer.png)

### 4.2.7.2. Interface Layer

![Irrigation-Actuator-Control-Interface-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/irrigation-acuator-control/irrigation-acuator-control-interface-layer.png)

### 4.2.7.3. Application Layer

![Irrigation-Actuator-Control-Application-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/irrigation-acuator-control/irrigation-acuator-control-application-layer.png)

### 4.2.7.4. Infrastructure Layer

![Irrigation-Actuator-Control-Infrastructure-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/irrigation-acuator-control/irrigation-acuator-control-infrastructure-layer.png)

### 4.2.7.5. Bounded Context Software Architecture Component Level Diagrams

![Irrigation-Actuator-Control-Component-Level-Diagram](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/irrigation-acuator-control/irrigation-acuator-control-component.png)

### 4.2.7.6 Bounded Context Software Architecture Code Level Diagrams

### 4.2.7.6.1 Bounded Context Domain Layer Class Diagrams

![Irrigation-Actuator-Control-Domain-Class-Diagram](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/irrigation-acuator-control/irrigation-acuator-control-domain-layer-class-diagram.png)

### 4.2.7.6.2 Bounded Context Database Design Diagram  

![Irrigation-Actuator-Control-Database-Design](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/irrigation-acuator-control/irrigation-acuator-control-database-design-diagram.png)

---

### 4.2.8. Bounded Context: Perimeter Security

Este bounded context gestiona la detección y clasificación de eventos perimetrales mediante el sensor PIR térmico del ESP32. Según tu Event Storming, los agregados principales son **PIR Event** y **Security Alert**, con tres flujos de clasificación claramente diferenciados: **Flujo humano**, **Flujo animal/viento** y la integración con el **Edge** para el procesamiento local de clasificación.

#### Diccionario de Clases

![Perimeter-Security-Dictionary](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/perimeter-security/dictionary-perimeter-security-1.png)

![Perimeter-Security-Dictionary](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/perimeter-security/dictionary-perimeter-security-2.png)

### 4.2.8.1. Domain Layer

![Perimeter-Security-Domain-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/perimeter-security/perimeter-security-domain-layer.png)

### 4.2.8.2. Interface Layer

![Perimeter-Security-Interface-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/perimeter-security/perimeter-security-interface-layer.png)

### 4.2.8.3. Application Layer

![Perimeter-Security-Application-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/perimeter-security/perimeter-security-application-layer.png)

### 4.2.8.4. Infrastructure Layer

![Perimeter-Security-Infrastructure-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/perimeter-security/perimeter-security-infrastructure-layer.png)

### 4.2.8.5. Bounded Context Software Architecture Component Level Diagrams

![Perimeter-Security-Component-Level-Diagram](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/perimeter-security/perimeter-security-component.png)

### 4.2.8.6 Bounded Context Software Architecture Code Level Diagrams

### 4.2.8.6.1 Bounded Context Domain Layer Class Diagrams

![Perimeter-Security-Domain-Class-Diagram](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/perimeter-security/perimeter-security-domain-layer-class-diagram.png)

### 4.2.8.6.2 Bounded Context Database Design Diagram

![Perimeter-Security-Database-Design](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/perimeter-security/perimeter-security-database-design-diagram.png)

---

### 4.2.9. Bounded Context: Business Intelligence

Este bounded context provee analítica estratégica para el Product Owner y el Project Manager. Según tu Event Storming, los agregados principales son **Business Metrics**, **Churn Record** y **Feature Usage Metrics**, con el pain point crítico de que los datos de churn deben cruzar información de Subscriptions con datos de uso.

#### Diccionario de Clases

![Business-Intelligence-Dictionary](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/business-intelligence/dictionary-business-intelligence-1.png)

![Business-Intelligence-Dictionary](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/business-intelligence/dictionary-business-intelligence-2.png)

### 4.2.9.1. Domain Layer

![Business-Intelligence-Domain-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/business-intelligence/business-intelligence-domain-layer.png)

### 4.2.9.2. Interface Layer

![Business-Intelligence-Interface-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/business-intelligence/business-intelligence-interface-layer.png)

### 4.2.9.3. Application Layer

![Business-Intelligence-Application-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/business-intelligence/business-intelligence-application-layer.png)

### 4.2.9.4. Infrastructure Layer

![Business-Intelligence-Infrastructure-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/business-intelligence/business-intelligence-infrastructure-layer.png)

### 4.2.9.5. Bounded Context Software Architecture Component Level Diagrams

![Business-Intelligence-Component-Level-Diagram](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/business-intelligence/business-intelligence-component.png)

### 4.2.9.6 Bounded Context Software Architecture Code Level Diagrams

### 4.2.9.6.1 Bounded Context Domain Layer Class Diagrams

![Business-Intelligence-Domain-Class-Diagram](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/business-intelligence/business-intelligence-domain-layer-class-diagram.png)

### 4.2.9.6.2 Bounded Context Database Design Diagram

![Business-Intelligence-Database-Design](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/business-intelligence/business-intelligence-database-design-diagram.png)

---

### 4.2.10. Bounded Context: Agronomist Advisory

Este bounded context gestiona las capacidades profesionales del ingeniero agrónomo. Según tu Event Storming, los agregados principales son **Agronomist Advisory** con sus flujos de **Monitoreo remoto**, **Reporte** y **Vinculación**, complementados por el aggregate **Technical Report** y la integración con el **PDF generator** como sistema externo.

#### Diccionario de Clases

![Agronomist-Advisory-Dictionary](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/agronomist-advisory/dictionary-agronomist-advisory-1.png)

![Agronomist-Advisory-Dictionary](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/agronomist-advisory/dictionary-agronomist-advisory-2.png)

### 4.2.10.1. Domain Layer

![Agronomist-Advisory-Domain-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/agronomist-advisory/agronomist-advisory-domain-layer.png)

### 4.2.10.2. Interface Layer

![Agronomist-Advisory-Interface-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/agronomist-advisory/agronomist-advisory-interface-layer.png)

### 4.2.10.3. Application Layer

![Agronomist-Advisory-Application-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/agronomist-advisory/agronomist-advisory-application-layer.png)

### 4.2.10.4. Infrastructure Layer

![Agronomist-Advisory-Infrastructure-Layer](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/agronomist-advisory/agronomist-advisory-infrastructure-layer.png)

### 4.2.10.5. Bounded Context Software Architecture Component Level Diagrams

![Agronomist-Advisory-Component-Level-Diagram](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/agronomist-advisory/agronomist-advisory-component.png)

### 4.2.10.6 Bounded Context Software Architecture Code Level Diagrams

### 4.2.10.6.1 Bounded Context Domain Layer Class Diagrams

![Agronomist-Advisory-Domain-Class-Diagram](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/agronomist-advisory/agronomist-advisory-domain-layer-class-diagram.png)

### 4.2.10.6.2 Bounded Context Database Design Diagram

![Agronomist-Advisory-Database-Design](/upc-pre-1ASI0572-2610-17757-SATECHO/report/assets/images/bounded-context/agronomist-advisory/agronomist-advisory-database-design-diagram.jpeg)