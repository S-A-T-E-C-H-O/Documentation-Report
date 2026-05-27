# Conclusiones

## Conclusiones y Recomendaciones

**AV1:**

A lo largo de esta primera fase, hemos consolidado los cimientos estratégicos y técnicos de nuestra startup, asegurando que cada decisión de desarrollo esté directamente alineada con una necesidad real del mercado y de nuestros usuarios. Ha sido un proceso sumamente retador, pero fundamental para mitigar riesgos en etapas futuras. Nuestro punto de partida fue el entendimiento profundo del ecosistema mediante la fase de descubrimiento. Iniciamos con un análisis exhaustivo a través de mapeos de experiencia en UXPressia y un estudio detallado de nuestros competidores directos. A través de la creación de perfiles de usuario, el diseño y análisis de entrevistas, y el proceso de descubrimiento de necesidades apoyado en mapas de empatía, logramos identificar los verdaderos puntos de dolor de nuestro público objetivo. Todo este esfuerzo de investigación nos permitió definir con precisión el mapa de impacto y estructurar un Product Backlog sólido, fundamentado en valor real.

Para asegurar que el equipo técnico y los stakeholders hablemos el mismo idioma, ejecutamos sesiones estratégicas de Big Picture Event Storming. Este ejercicio colaborativo dio como resultado nuestro Lenguaje Ubicuo, estandarizando los términos clave del negocio para evitar ambigüedades. A partir de esta base compartida, construimos historias de usuario multidimensionales, abarcando no solo la funcionalidad pura a través de historias técnicas y enfocadas en los desarrolladores, sino también garantizando la calidad final mediante historias centradas en la experiencia de usuario.

Posteriormente, tradujimos todas las necesidades del negocio a una estructura tecnológica escalable. Desglosamos el panorama general y evolucionamos hacia un Design Level Event Storming, completando los diez pasos metodológicos desde la definición del dominio hasta la comprensión de las líneas de tiempo. Con esto claro, maquetamos la primera versión de nuestra arquitectura utilizando el modelo C4, donde definimos el nivel de contexto, el nivel de contenedores y el diagrama de despliegue. Este proceso concluyó con el modelado del flujo de mensajes del dominio, lo que nos permitió establecer los contextos delimitados y las bases de integración que gobernarán todo el flujo de información en nuestra solución tecnológica.

A medida que pasemos a una etapa de desarrollo más intensiva, será imperativo sostener la gobernanza automatizada y la protección de nuestro código. Recomendamos mantener e iterar la estrategia que hemos implementado en nuestro repositorio mediante el uso del archivo de propietarios de código (CODEOWNERS) y las políticas de protección de ramas dentro de nuestro flujo de trabajo con Gitflow. Estas medidas de seguridad son vitales; ningún cambio debe integrarse a la rama principal sin cumplir la regla interna de que, siempre y cuando una de las dos áreas, gobernanza o calidad (QA), lo apruebe, el pase a producción pueda proceder. Esto nos prevendrá de riesgos operativos y asegurará la calidad continua.

Por último, a medida que el proyecto crezca, recomendamos realizar sesiones periódicas de actualización de nuestra documentación y flujos. El Lenguaje Ubicuo es un ente vivo, y mantenerlo actualizado evitará silos de información, garantizando que la visión del negocio siga siendo auténtica y se refleje perfectamente en el código fuente de la aplicación.

**TB1**

El desarrollo integral de SATECHO permitió consolidar una propuesta tecnológica orientada a responder de manera estratégica a las principales problemáticas que afectan actualmente al sector agrícola peruano, particularmente aquellas relacionadas con la gestión ineficiente del recurso hídrico y la vulnerabilidad frente a eventos de inseguridad en zonas rurales. A partir de los hallazgos obtenidos durante las fases de investigación, análisis de requerimientos y validación del dominio, se concluye que la integración de tecnologías IoT, automatización y monitoreo en tiempo real constituye una alternativa viable para optimizar la toma de decisiones agrícolas basadas en datos. Asimismo, la aplicación de enfoques como Lean UX y Domain-Driven Design permitió estructurar una solución alineada con las necesidades reales de agricultores e ingenieros agrónomos, garantizando coherencia entre la problemática identificada y la arquitectura funcional propuesta.

De igual manera, la incorporación del Capítulo V relacionado con el diseño UI/UX evidenció la importancia de construir experiencias digitales centradas en el usuario dentro de entornos agrícolas donde la alfabetización tecnológica puede ser limitada. La definición de lineamientos visuales, arquitecturas de información, sistemas de navegación, wireframes, mock-ups y prototipos interactivos permitió establecer una interfaz intuitiva, accesible y consistente para los diferentes canales de interacción de SATECHO, incluyendo aplicaciones web, móviles y componentes IoT. En consecuencia, se concluye que el diseño de experiencia de usuario no solo representa un componente estético dentro de la solución, sino un factor determinante para facilitar la adopción tecnológica y reducir la complejidad operativa percibida por los usuarios finales.

Por otro lado, el Capítulo VI permitió validar que la correcta gestión de la configuración de software, el control de versiones y la planificación ágil mediante Sprint Planning y Sprint Backlog constituyen elementos fundamentales para asegurar la trazabilidad, calidad y sostenibilidad del proyecto. La documentación de evidencias de desarrollo, pruebas, despliegue y colaboración evidenció un entorno de trabajo organizado y alineado con buenas prácticas de ingeniería de software, fortaleciendo la capacidad del equipo para desarrollar entregables funcionales y escalables. Del mismo modo, el uso de herramientas colaborativas como GitHub facilitó la integración continua de aportes, la revisión cruzada entre integrantes y el seguimiento estructurado del avance del proyecto, permitiendo mantener consistencia técnica y documental durante todo el ciclo de desarrollo.

En relación con las recomendaciones, se considera necesario que futuras iteraciones de SATECHO profundicen la etapa de validación experimental mediante pruebas piloto en entornos agrícolas reales, permitiendo medir con mayor precisión variables asociadas al ahorro hídrico, reducción de pérdidas productivas, efectividad de las alertas perimetrales y aceptación tecnológica por parte de los usuarios. Asimismo, se recomienda ampliar el alcance funcional del sistema incorporando capacidades predictivas apoyadas en modelos de Inteligencia Artificial y analítica avanzada, orientadas a anticipar patrones climáticos, enfermedades del cultivo y riesgos operacionales. Esto permitiría evolucionar desde un sistema de monitoreo reactivo hacia una plataforma inteligente de agricultura de precisión con mayor capacidad de adaptación y escalabilidad regional.

Finalmente, se recomienda mantener una estrategia de mejora continua tanto en el ámbito técnico como en la experiencia de usuario, priorizando la retroalimentación constante de agricultores e ingenieros agrónomos para garantizar que la solución conserve pertinencia frente a las dinámicas cambiantes del sector agrícola. Del mismo modo, resulta importante fortalecer la interoperabilidad entre los componentes físicos y digitales de la plataforma, optimizando aspectos relacionados con conectividad, eficiencia energética y tolerancia a condiciones ambientales adversas. En términos organizacionales, se sugiere continuar aplicando metodologías ágiles y estándares de documentación técnica que favorezcan la colaboración multidisciplinaria, la mantenibilidad del software y la sostenibilidad del proyecto a largo plazo, consolidando así a SATECHO como una propuesta tecnológica con potencial de impacto real dentro del ecosistema agroindustrial peruano y latinoamericano.

**AV2**



# Bibliografía

- Ayhan, Z., Arserim-Uçar, D. K., Alkan, D., Cikrikci Erunsal, S., Altan, A., & Emir, A. A. (2026). *Exploring Agricultural and Industrial Fruit-Based Waste/By-products for Eco-friendly Multifunctional Bio-based Food Packaging and Coating Materials.* Food and Bioprocess Technology 2026 19:5, 19(5), 225-. https://doi.org/10.1007/S11947-026-04269-2

- Gómez Flores, J. L., Ramos Rodríguez, M., González Jiménez, A., Farzamian, M., Herencia Galán, J. F., Salvatierra Bellido, B., Cermeño Sacristan, P., & Vanderlinden, K. (2022). *Depth-Specific Soil Electrical Conductivity and NDVI Elucidate Salinity Effects on Crop Development in Reclaimed Marsh Soils.* Remote Sensing 2022, Vol. 14, Page 3389, 14(14), 3389. https://doi.org/10.3390/RS14143389

- *La brecha de infraestructura de riego en el sector agropecuario | Conexión ESAN.* (n.d.). Retrieved May 25, 2026, from https://www.esan.edu.pe/conexion-esan/la-brecha-de-infraestructura-de-riego-en-el-sector-agropecuario

- *La crisis histórica del agro en Perú impacta y amenaza la agricultura familiar* | Ojo Público. (n.d.). Retrieved May 25, 2026, from https://ojo-publico.com/derechos-humanos/la-crisis-historica-del-agro-impacta-y-amenaza-la-agricultura-familiar

- Loconsole, D., Elia, M., Conversa, G., De Lucia, B., Cristiano, G., & Elia, A. (2025). *Soil Moisture Sensing Technologies: Principles, Applications, and Challenges in Agriculture.* Agronomy, 15(12), 2788. https://doi.org/10.3390/AGRONOMY15122788/S1

- Miller, T., Mikiciuk, G., Durlik, I., Mikiciuk, M., Łobodzińska, A., & Śnieg, M. (2025). *The IoT and AI in Agriculture: The Time Is Now—A Systematic Review of Smart Sensing Technologies.* Sensors 2025, Vol. 25, Page 3583, 25(12), 3583. https://doi.org/10.3390/S25123583

- Mishra, A. K., Das, R., George Kerry, R., Biswal, B., Sinha, T., Sharma, S., Arora, P., & Kumar, M. (2023). *Promising management strategies to improve crop sustainability and to amend soil salinity.* Frontiers in Environmental Science, 10, 962581. https://doi.org/10.3389/FENVS.2022.962581/FULL

- Pascoal, D., Silva, N., Adão, T., Lopes, R. D., Peres, E., & Morais, R. (2024). *A technical survey on practical applications and guidelines for IoT sensors in precision agriculture and viticulture.* Scientific Reports 2024 14:1, 14(1), 29793-. https://doi.org/10.1038/s41598-024-80924-y

- Shelden, M. C., & Munns, R. (2023). *Crop root system plasticity for improved yields in saline soils.* Frontiers in Plant Science, 14, 1120583. https://doi.org/10.3389/FPLS.2023.1120583

- Zhou, T., Ma, S., Liu, T., Yao, S., Li, S., & Gao, Y. (2025). *Integrating UAV-Based Multispectral Data and Transfer Learning for Soil Moisture Prediction in the Black Soil Region of Northeast China.* Agronomy, 15(3). https://doi.org/10.3390/AGRONOMY15030759

- Comisión Nacional de Palta Hass. (2023). *Estadísticas del sector palta Hass en Perú 2023*. https://www.prohass.gob.pe/

- Instituto Nacional de Estadística e Informática. (2012). *IV Censo Nacional Agropecuario 2012*. https://www.inei.gob.pe/estadisticas/indice-tematico/censos-nacionales/

- Instituto Nacional de Estadística e Informática. (2022). *Encuesta Nacional Agropecuaria 2022*. https://www.inei.gob.pe/media/MenuRecursivo/publicaciones_digitales/Est/Lib1926/

- Ministerio de Desarrollo Agrario y Riego. (2023). *Anuario estadístico de producción agrícola 2023*. https://www.gob.pe/midagri

- Ministerio de Desarrollo Agrario y Riego. (2025). *Reporte de superficie cultivada de arándanos para exportación*. Dirección de Estadística Agraria. https://www.gob.pe/midagri

- Organismo Supervisor de Inversión Privada en Telecomunicaciones. (2024). *Estudio de penetración de servicios de telecomunicaciones Erestel 2024*. https://www.osiptel.gob.pe/estadisticas/penetracion-de-servicios

- *CropX Agronomic Farm Management System.* (n.d.). Retrieved May 25, 2026, from https://cropx.com/

- *Irrigation monitoring sensors | Netafim.* (n.d.). Retrieved May 25, 2026, from https://www.netafimindia.com/digital-farming_old/netbeat/Monitor/

- *Maximize Results with Our Digital Farming Solution | Climate FieldView.* (n.d.). Retrieved May 25, 2026, from https://climate.com/en-us.html
SpaceAG | Te Acompañamos en la Digitalización de la Agricultura. (n.d.). Retrieved May 25, 2026, from https://www.spaceag.co/

# Anexos

## Anexo A - Videos de Exposiciones

Se mostrará cada una de los _speech_ elaborados por cada uno de los miembros del equipo de **SATECHO** durante cada una de las fases programadas del desarrollo de la solución de **AgroSafe**. La finalidad del mismo es compartir los avances alcazandos, definiendo desde la problemática, propuesta de valor, diseño y planificación y finalmente el desarrollo de los póstumos artefactos digitales que darán vida y practicidad a las funcionalidades de nuestros _stakeholders_, el cual vienen a ser los agricultores e ingenieros agrónomos respectivamente.

Cada uno de estas presentaciones multimedia serán catalogadas mediante códigos como **AV1**, **TB1**, **AV2** y **TB2** - segmentando las fases de entregables finales alcanzados durante cada sprint.

| Entrega | Enlace del Video | Resumen del contenido |
| :-- | :-- | :-- |
| AV1 | [upc-pre-202610-1asi0572-17757-satecho-expo-av1]() | Se describe el nacimiento del _startup_ **SATECHO** así como la identificación de la problemática principal que espera solventar en la actualidad siguiendo el enfoque _Lean UX Canvas_; por consiguiente, se detallada el _benchmarking_ entre las diferentes soluciones digitales que hay en la actualidad, la explicación de las características fundamentales para el diseño y organización de las entrevistas desarrolladas para luego recopilar las necesidades principales mediante la creación de las **User Stories** basándonos en el método _INVEST_. Finalmente, se explica el diagrama de C4, las casuísticas identificadas para el diseño del _EventStorming_ siguiendo la técnica de los 10 pasos. Con ello, se concluye el video describiendo cada uno de los **Bounded Context** junto con el diagrama de clases específico que se implementará en el desarrollo de cada uno de los artefactos digitales de la solución **AgroSafe**. |
| TB1 | [upc-pre-202610-1asi0572-17757-satecho-expo-tb1](https://upcedupe-my.sharepoint.com/:v:/g/personal/u202110458_upc_edu_pe/IQBQXbUbVJUoRJ-wvgBL9HDwAQABCaowxUoD-jjvkxxI8oI?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJTdHJlYW1XZWJBcHAiLCJyZWZlcnJhbFZpZXciOiJTaGFyZURpYWxvZy1MaW5rIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXcifX0%3D&e=l4FW6l) | Se especifica cada uno los _keypoints_ considerados para la definición de los colores, tipografía, _Information Architecture_, **Wireframes** y **MockUps** del _Landing Page_, _Mobile Application_ y _Web Application_; adicionalmente, se presentó la versión prototipada del artefacto tanto _Mobile_ como _Web_ y finalmente el detalle de planificación y organización de las actividades elaboradas en el presente Sprint 1 (abarcando la versión oficila del _Landing Page_ y la primera versión del _Web Application_).  |
| AV2 | [upc-pre-202610-1asi0572-17757-satecho-expo-av2]() | Se inicia el video dando la _review_ como _retrospective_ del pasado sprint para luego dar inicio a las actividades planificadas en el presente Sprint 2 donde se describen las funcionalidades abarcadas durante el desarrollo de la primera versión del _Mobile Application_, _Embedded Application_, _Edge API_ y _RESTFul API_. Por otro lado, se comentan los nuevos _updates_ asociados a las aplicaciones entregadas en el Sprint 1. |

## Anexo B - Videos de Entrevistas

En esta sección visualizarán el contenido multimedia acerca de las entrevitas desarrolladas a cada uno de los segmentos objetivos dedicados para comprender y solventar la necesidad crítica que presentan dentro del escenario de estudio, asentando las bases para la definición de los requisitos vitales sobre la implementación de una solución digital dentro de un ecosistema IoT.

| Sección | Características del video | Sobre el contenido | Entrega |
| :-- | :-- | :-- | :--: |
| Interviews Needfinding | **Cantidad de videos**: 1, **Nomenclartura:** upc-pre-202601-1asi0572-17757-Satecho-needfinding-sprint-1, **Formato:** .mp4, **Duración:** 27 minutos | Consolidado de las entrevistas dedicadas a los segmentos objetivos de **SATECHO** tales como: Agricultores e Ingenieros Agrónomos | **Enlace:** [https://n9.cl/0bz8yp](https://n9.cl/0bz8yp) |

## Anexo C - Acceso directo a las fuentes de estudio

Se comparte el enlace de cada uno de los artefactos desarrollados durante el transcurso de todo el ciclo de vida de la solución **SATECHO**. La finalidad es que cada uno de los usuarios puedan apreciar el contenido de forma más clarividente en caso el contenido visual adjunto al documento no sea muy comprensible a simple vista.

- **Lean UX Canvas:** [Lean UX Canvas](https://canva.link/j3j207no16f4q8k)

- **Big Picture EventStorming:** [Big Picture EventStorming](https://miro.com/welcomeonboard/aTFsb0swOGFVVVVnMjRmOGR1MkZTUkpqelpYQ3NNeHNFUkZhRmlwdW9FR0lxM2FVV0pHVkd5K1h4eGhneTFta3NwYXVDQnVWTzdzVWczODVCVThFbTZKd21YMlp3SVJxMjFWaStYV20xTzNiK0ZYVEJqOEpkczlXSXNYUUEwUWtyVmtkMG5hNDA3dVlncnBvRVB2ZXBnPT0hdjE=?share_link_id=240040668035)

- **Product Backlog:** [Product Backlog - SATECHO](https://satecho.atlassian.net/jira/software/projects/SCRUM/boards/1/backlog)

- **EventStorming:** [EventStorming - SATECHO](https://miro.com/welcomeonboard/cFFaS01jREdxQXE3OXlVQk1SU0U0TkZxR0hMYWZuRnRHRGtqSXdJOUpUUlZ4SjV0MFlFRGtTS3FWRUt6OFd6Q0Z2Q0xvVEwvNHYzV3R0TzBlZVZHdHFKd21YMlp3SVJxMjFWaStYV20xTzNqLzdFQkNucWw1YlB0VlZTQ0k2Rk1hWWluRVAxeXRuUUgwWDl3Mk1qRGVRPT0hdjE=?share_link_id=464211039948)

- **Figma:** [Figma - WireFrames / Mockups / Prototyping](https://satecho.atlassian.net/jira/software/projects/SCRUM/boards/1/backlog)