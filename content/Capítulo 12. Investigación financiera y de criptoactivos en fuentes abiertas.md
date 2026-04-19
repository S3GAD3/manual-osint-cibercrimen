# Capítulo 12. Investigación financiera y de criptoactivos en fuentes abiertas

---

## 1. Introducción

El dinero deja rastros. Esta afirmación, que constituye uno de los principios fundacionales de la investigación criminal financiera, adquiere una dimensión nueva y de gran utilidad operativa cuando se aplica al entorno digital. Las investigaciones de cibercrimen generan, casi invariablemente, indicios de naturaleza económica: una empresa cuyo nombre aparece en una pasarela de pago fraudulenta, una dirección de wallet a la que se dirigen los fondos de las víctimas, un administrador que figura como responsable de varias webs de inversión, una transacción blockchain que conecta dos extremos hasta entonces inconexos. Todos ellos son observables económicos que, antes de cualquier diligencia formal, pueden ser explotados a través de fuentes abiertas.

La investigación financiera en fuentes abiertas no es un sustituto de las diligencias patrimoniales, los requerimientos judicializados ni las consultas a bases de datos policiales reservadas. Es, en cambio, una fase previa y complementaria que permite orientar hipótesis, ampliar el contexto relacional, detectar estructuras económicas y priorizar líneas de actuación con un coste de recursos muy reducido y una capacidad de obtención de información muy significativa. Cuando se realiza con método, con conocimiento de herramientas y con la debida prudencia interpretativa, puede transformar un dato aislado en una línea de investigación sólida.

Este capítulo aborda esa capacidad. No pretende describir el sistema financiero internacional ni explicar la arquitectura técnica de la blockchain. Pretende enseñar al investigador a trabajar: cómo recibir un dato económico o blockchain, qué hacer con él desde el primer momento, qué herramientas usar, qué puede esperar encontrar, cómo interpretar los resultados y cómo integrar esos hallazgos con las capacidades institucionales de las que dispone. La investigación financiera en abierto exige método, contexto, contraste y prudencia. Estos cuatro elementos estructuran todo el capítulo.

---

## 2. Finalidad investigadora del capítulo

Este capítulo cumple una función eminentemente aplicada dentro del manual. Su propósito no es introducir al lector en la teoría del análisis financiero forense ni en el derecho penal económico, sino dotarle de criterio operativo y conocimiento práctico para investigar empresas, administradores, webs corporativas, wallets y transacciones en fuentes abiertas, dentro de un flujo de trabajo profesional y reproducible.

La investigación financiera y de criptoactivos resulta especialmente valiosa en el espectro del cibercrimen porque la mayoría de las actividades delictivas digitales tienen un componente económico trazable: la estafa de inversión necesita una plataforma de captación, una sociedad de fachada o una dirección de recepción de fondos; el ransomware opera a través de wallets de cobro; el phishing bancario termina en una cuenta o en una dirección blockchain receptora; el fraude del CEO requiere una empresa o un IBAN de destino; la venta fraudulenta en comercio electrónico utiliza pasarelas de pago o cuentas asociadas a entidades mercantiles. En todos estos contextos, el elemento económico puede ser el hilo que permita avanzar cuando la información puramente técnica o de identidad digital es escasa o inexistente.

El investigador que concluya este capítulo debe ser capaz de comenzar una investigación a partir de cualquier indicio económico o blockchain, seguir una secuencia de trabajo coherente, utilizar herramientas reales con criterio, interpretar los resultados con rigor y articular sus hallazgos dentro del expediente policial o judicial de forma documentada y útil.

---

## 3. Objeto de análisis y punto de partida

En el contexto de la investigación OSINT financiera, el objeto de análisis puede adoptar formas muy distintas. Conviene que el investigador las identifique y distinga desde el primer momento, porque cada tipología exige un tratamiento diferente y abre líneas de indagación específicas.

Una **empresa o persona jurídica** es una entidad registrada ante un registro mercantil o equivalente, que tiene existencia legal, número de identificación, domicilio registrado, objeto social, órganos de administración y, en muchos casos, información pública accesible. En el contexto del cibercrimen, las empresas pueden actuar como fachada para operaciones fraudulentas, como vehículos de blanqueo, como proveedoras formales de servicios realmente ilícitos o como simples pantallas para dotar de apariencia de legitimidad a una plataforma o a una transacción. La empresa puede no tener actividad real alguna: puede haber sido creada únicamente para recibir fondos, para abrir cuentas bancarias o para aparecer en los términos y condiciones de una web fraudulenta.

Un **administrador, apoderado o beneficiario registral** es una persona física o jurídica que, con independencia del control económico real de la entidad, figura públicamente en registros como responsable legal de la misma. El administrador es un pivote de enorme valor porque su identidad puede cruzarse con otras empresas, con otros dominios, con registros de otro tipo o con información personal visible en fuentes abiertas.

Una **web corporativa** o **dominio asociado a una actividad económica** puede contener, o puede haber contenido, información útil: datos de contacto, menciones a administradores, términos legales, condiciones de uso, avisos de privacidad, registros de empresa, pasarelas de pago o referencias mercantiles. Incluso cuando la web ya no está activa, puede recuperarse a través de capturas de archivo.

Una **wallet** o **dirección blockchain** es una cadena alfanumérica que funciona como receptora y emisora de transacciones en una red de activos digitales. No contiene por sí misma ningún dato personal identificativo, pero tiene un historial transaccional público, puede estar etiquetada en exploradores o en servicios especializados, puede haber recibido fondos de otras direcciones con identidad conocida o sospechosa, y puede mostrar patrones de actividad que resultan útiles para el análisis. La wallet no acredita identidad: para establecer la relación entre una dirección y una persona concreta son necesarias diligencias adicionales.

Una **transacción blockchain** es el registro inmutable de una transferencia de valor entre dos o más direcciones en una red descentralizada. Aporta datos sobre importe, fecha y hora, comisión, confirmaciones y, en muchas redes, datos adicionales del contrato inteligente involucrado. Es el eslabón básico del análisis de flujo.

Un **observable económico** de otra naturaleza puede ser un IBAN visible en un correo de phishing, una referencia a una cuenta de pago en una factura falsa, un identificador de transacción PayPal, un código QR de pago, un nombre de plataforma de trading o el logotipo de una pasarela de pago en una web. Cada uno de estos elementos puede actuar como punto de entrada en una investigación financiera en abierto.

La pregunta que el investigador debe formularse ante cualquiera de estos objetos de análisis es siempre la misma: ¿qué me dice este dato sobre la estructura económica o relacional del sujeto o la actividad que investigo, y a qué otras entidades o indicios me puede conectar?

---

## 4. La información financiera y blockchain como pivote de investigación y contexto económico

El concepto de pivote investigador es central en OSINT: un dato que, al ser analizado, genera nuevos datos y abre nuevas líneas de indagación. Los elementos económicos, societarios y blockchain son pivotes de primer orden porque combinan, con gran frecuencia, trazabilidad pública, volumen de información estructurada y capacidad de enlace con otras entidades.

Una sociedad mercantil que aparece en la web de una falsa plataforma de inversión no es solo un nombre. Es un número de identificación fiscal, una fecha de constitución, un domicilio registrado, uno o varios administradores, una posible historia de modificaciones estatutarias, vinculaciones con otras sociedades a través de sus administradores y, en muchos casos, un historial de presentación de cuentas, de incidencias registrales o de litigios. Cada uno de esos elementos puede conectar con otro dato de la investigación o abrir una nueva vía de análisis.

Un administrador que figura en esa sociedad puede ser también administrador de otras entidades en otras jurisdicciones. Puede tener una presencia visible en LinkedIn, en portales profesionales o en registros de propiedad. Puede aparecer como contacto técnico o administrativo en otros dominios. Puede haber sido objeto de noticias o de procedimientos judiciales. El cruce de su nombre con fuentes registrales de varios países puede revelar una estructura de entidades que actúan coordinadamente.

Una wallet que recibe los fondos de las víctimas puede mostrar un comportamiento de vaciado sistemático hacia otra dirección, que a su vez conecta con un servicio de intercambio conocido. Esa dirección de intercambio puede estar etiquetada en exploradores públicos. El servicio al que se dirigen los fondos puede tener una identidad registrada, una base jurisdiccional y un historial de colaboración o de resistencia a las autoridades. El rastro blockchain no identifica a una persona, pero puede revelar la arquitectura financiera del esquema delictivo y permitir al investigador formular hipótesis precisas sobre la cadena de lavado.

El valor de la información financiera en abierto aumenta exponencialmente cuando se combina con otras dimensiones del análisis OSINT. Una empresa sin actividad real que aparece en una web fraudulenta y cuyo administrador tiene vinculación con dominios registrados en las mismas fechas desde el mismo registrador que otras webs de inversión similares constituye una convergencia de indicios que tiene un peso analítico muy superior al de cualquiera de ellos por separado. Esa convergencia no prueba, por sí sola, la autoría, pero permite formular hipótesis sólidas, orientar diligencias y priorizar líneas de investigación.

El investigador debe comprender que investigar finanzas en abierto no es buscar el dato que cierre la investigación, sino construir un contexto económico, relacional y operativo que haga la investigación más eficiente, más precisa y mejor fundamentada.

---

## 5. Análisis inicial del indicio económico, societario o blockchain y contextualización del hallazgo

El primer contacto con un indicio económico o blockchain debe gestionarse con orden y sin precipitación. Antes de consultar cualquier herramienta, el investigador debe responder a un conjunto de preguntas básicas que estructuran el análisis posterior.

El primer examen debe determinar la **naturaleza exacta del dato**: ¿es un nombre de empresa, un número de identificación fiscal, un administrador, una dirección blockchain, un hash de transacción, un IBAN, un dominio corporativo o una referencia a una pasarela de pago? La naturaleza del dato determina qué fuentes son pertinentes y en qué orden deben consultarse.

Debe establecerse a continuación el **contexto de aparición**: ¿en qué momento y de qué fuente se ha obtenido este indicio? ¿Fue aportado por una víctima, extraído de una web fraudulenta, identificado en un correo de phishing, obtenido de una captura de pantalla, hallado en un archivo adjunto o localizado durante el análisis de infraestructura digital? El contexto de aparición influye en la plausibilidad del dato y en las hipótesis que pueden formularse.

El investigador debe comprobar la **validez formal y la plausibilidad técnica** del dato antes de invertir tiempo en su análisis. Una dirección blockchain puede verificarse rápidamente en cuanto a su formato y red. Una sociedad puede verificarse en cuanto a su número de identificación. Un IBAN puede comprobarse su estructura y país de origen. Esta verificación básica previene errores de análisis derivados de datos mal transcritos, manipulados o falsos.

Una vez verificado el formato, procede la **extracción de los primeros metadatos útiles**: fecha de registro de la sociedad, país de jurisdicción, tipo jurídico, red blockchain en la que opera la wallet, volumen transaccional visible, fecha de primera y última transacción. Estos metadatos permiten formular las primeras hipótesis de trabajo y orientar la selección de herramientas.

El investigador debe registrar, desde este momento, el **contexto del hallazgo**, incluyendo la fecha y hora de consulta, la fuente exacta, el estado de la información en ese momento y la cadena de pasos seguida. La preservación del contexto tiene valor documental propio y es indispensable para la reproducibilidad del análisis.

---

## 6. Flujo de trabajo del investigador a partir de un dato financiero, societario o wallet

El flujo de trabajo que se describe a continuación es de carácter general y adaptable. No todos los casos requieren el mismo nivel de profundidad en cada fase, y el investigador debe aplicar criterio para determinar cuándo una línea merece mayor desarrollo y cuándo conviene mantenerse en el nivel de contextualización orientadora.

**Fase 1. Recepción y caracterización del dato inicial.** El investigador recibe un indicio económico, societario o blockchain y determina su tipo, su formato, su procedencia y su plausibilidad. Registra el dato exacto, su contexto de aparición y la hipótesis inicial que lo motiva.

**Fase 2. Verificación básica y comprobación de formato.** Se comprueba que el dato es válido en su estructura: la dirección blockchain respeta el formato de la red correspondiente, el nombre de empresa corresponde a una entidad registrada, el IBAN tiene una estructura de país coherente con el contexto. Esta fase no exige herramientas complejas: un explorador de red para wallets, un buscador registral básico para empresas. Su objetivo es confirmar que el dato merece análisis antes de invertir recursos adicionales.

**Fase 3. Consulta de fuentes registrales abiertas.** Para datos societarios, el investigador consulta los registros mercantiles del país de constitución de la entidad o sus equivalentes en otras jurisdicciones, así como agregadores de información corporativa que concentren datos de múltiples fuentes. Esta fase produce los primeros datos estructurados: administradores registrados, fecha de alta, cambios de estatutos, objeto social, domicilio. Para wallets, esta fase corresponde al primer acceso al explorador de red para visualizar el historial básico de transacciones.

**Fase 4. Ampliación societaria relacional.** Si el dato inicial era una empresa, el investigador pasa a analizar sus vínculos: ¿quiénes son los administradores actuales y anteriores? ¿Esos administradores figuran en otras empresas? ¿Esas otras empresas tienen relación con la actividad investigada? ¿La sociedad ha tenido cambios frecuentes de administración o domicilio, lo que podría indicar uso instrumental? Si el dato inicial era un administrador, la pregunta equivalente es: ¿en cuántas y cuáles otras entidades figura ese administrador, en qué países, y cuándo?

**Fase 5. Análisis de la presencia digital corporativa.** El investigador examina la web asociada a la empresa, su dominio, su historial de cambios, sus datos de registro técnico y su relación con otros dominios o entidades. Se analiza si la empresa tiene una presencia digital coherente con su actividad declarada, si sus datos de contacto son verificables, si su aviso legal o sus términos y condiciones contienen información adicional y si el dominio fue creado en fechas próximas a la puesta en marcha del esquema delictivo.

**Fase 6. Análisis de flujo blockchain.** Si el dato inicial era una wallet o una transacción, el investigador analiza el historial completo de la dirección: volumen total recibido y enviado, número de transacciones, fecha de primera y última actividad, contrapartes principales y comportamiento de vaciado o acumulación. Se identifican las direcciones de mayor interacción y se comprueba si alguna de ellas está etiquetada en exploradores o en bases de datos públicas. Se analiza si los fondos se dirigen a servicios conocidos.

**Fase 7. Detección de patrones de reutilización, concentración o dispersión.** En el análisis societario, se buscan patrones de reutilización de administradores, domicilios, registradores de dominio o vías de contacto que conecten varias entidades aparentemente independientes. En el análisis blockchain, se estudia si una misma dirección aparece en múltiples transacciones vinculadas a víctimas distintas, si los fondos se concentran en un nodo antes de moverse hacia un servicio, o si se dispersan en múltiples direcciones como mecanismo de opacidad.

**Fase 8. Contraste con otras fuentes abiertas.** Los hallazgos de las fases anteriores se contrastan con otras fuentes abiertas: noticias, bases de datos de fraude, registros judiciales públicos, reportajes de periodismo de investigación, alertas de organismos reguladores, listas de entidades no autorizadas publicadas por supervisores financieros como la CNMV o la EBA. Esta fase permite calibrar el valor del hallazgo y detectar si la estructura investigada tiene antecedentes conocidos.

**Fase 9. Integración con capacidades policiales e institucionales.** Los hallazgos de fuentes abiertas se trasladan al expediente y se valora qué diligencias formales pueden enriquecerse con la información obtenida: consultas a bases de datos policiales, petición de información a registros, requerimientos a proveedores de servicios de activos virtuales, solicitudes a través de canales de cooperación internacional o, cuando proceda, auxilio judicial.

**Fase 10. Valoración del hallazgo.** El investigador valora la fuerza del hallazgo obtenido: ¿es un indicio aislado de valor contextual, una convergencia de indicios que apoya una hipótesis con fuerza razonable, o una mera coincidencia que no añade valor? La valoración debe ser explícita y documentada.

**Fase 11. Preservación y documentación del flujo.** Se documenta el flujo completo: qué se buscó, cuándo, en qué herramienta, qué se encontró, qué se interpretó y qué decisiones se tomaron a partir de cada hallazgo. Esta documentación es la que garantiza la reproducibilidad del análisis y su valor probatorio potencial.

---

## 7. Herramientas y recursos prácticos para la investigación financiera y de criptoactivos

### 7.1 Investigación societaria y registral en fuentes abiertas

La investigación de empresas en fuentes abiertas debe partir, siempre que sea posible, de los registros oficiales del país de constitución de la entidad. Muchos países tienen portales de consulta públicos que permiten acceder a datos básicos de personas jurídicas: número de identificación, denominación social, domicilio, administradores registrales y situación actual. En España, el Registro Mercantil Central ofrece un buscador público de denominaciones, y el Servicio de Interoperabilidad de los Registros permite consultas básicas. Los registros del Reino Unido, a través de Companies House, son especialmente accesibles y ricos en información: ofrecen gratuitamente nombre, dirección, personas con control significativo, cuentas depositadas y historial de cambios, con una API de acceso libre. El Registro de los Países Bajos, el registro belga Crossroads Bank for Enterprises, el registro francés del INSEE y Sirene, y los equivalentes de los países nórdicos tienen niveles de apertura comparables. El investigador debe localizar y consultar directamente el registro correspondiente antes de acudir a agregadores.

**OpenCorporates** es el mayor agregador público de información empresarial del mundo, con datos de más de doscientos registros en distintas jurisdicciones. Su valor principal para el investigador reside en tres capacidades: la búsqueda por nombre de empresa, que permite localizar entidades similares o idénticas registradas en varios países; la búsqueda por persona, que permite encontrar todas las sociedades en las que una persona figura como administrador o con otro tipo de rol registral; y la exploración de vínculos corporativos, que permite detectar redes de entidades conectadas por administradores comunes.

El dato de entrada puede ser el nombre exacto o aproximado de una empresa, el nombre de un administrador o un número de identificación conocido. OpenCorporates devuelve una ficha de cada entidad con la información disponible del registro de origen, incluyendo, cuando existen, los administradores registrados. Su valor operativo está en la comparación entre jurisdicciones y en la detección de administradores comunes entre varias entidades. Sus limitaciones son relevantes: la información refleja lo que aparece en los registros oficiales en el momento de la actualización, no el control económico real ni la estructura de beneficiarios finales; algunos registros no ofrecen datos de administradores individuales; y la actualización puede no ser inmediata. El error frecuente es interpretar los datos de OpenCorporates como descripción del control real de una sociedad, cuando en realidad describen únicamente su composición registral.

En el contexto de una investigación de cibercrimen, OpenCorporates resulta especialmente útil cuando se ha detectado el nombre de una empresa en una web de falsas inversiones, en un correo de phishing o en una pasarela de pago, y se necesita establecer quién figura como responsable registral, en qué fecha se constituyó y qué otras entidades conectan con los mismos administradores. Una sociedad constituida pocos meses antes de la aparición de la plataforma fraudulenta, con un administrador que simultáneamente figura en otras entidades de jurisdicciones de baja transparencia, y con un domicilio registrado en un servicio de agentes registrados sin presencia real, es un patrón que emerge con claridad a través de este tipo de búsqueda relacional.

### 7.2 Enriquecimiento corporativo y análisis relacional avanzado

**Aleph**, la plataforma de búsqueda de datos de OCCRP (Organized Crime and Corruption Reporting Project), constituye una herramienta de naturaleza diferente. No es un registro empresarial, sino un motor de búsqueda que integra decenas de bases de datos de distinta procedencia: listas de sanciones internacionales, registros de beneficiarios reales, datos filtrados de relevancia pública, declaraciones patrimoniales, listas de personas políticamente expuestas, registros de offshore de jurisdicciones opacas, declaraciones de activos de funcionarios públicos y documentos periodísticos de investigación de acceso libre.

El dato de entrada principal es un nombre de persona o de empresa. Aleph cruza ese nombre con todas las bases de datos indexadas y devuelve los resultados de coincidencia, con indicación de la fuente y, cuando está disponible, el documento original. Su valor operativo es máximo cuando se investigan personas o entidades con posible conexión a estructuras de crimen organizado, corrupción, capital offshore o entidades sancionadas. También resulta muy útil para detectar si un administrador figura en listas de sanciones o en registros de paraísos fiscales como los Panama Papers, los FinCEN Files, los Pandora Papers o los OpenLux.

Sus limitaciones son igualmente importantes: no es un registro completo ni actualizado de forma continua; los documentos presentes son los que han sido objeto de filtración o publicación periodística, no toda la información corporativa del mundo; la coincidencia de un nombre en una base de datos de entidades offshore no implica por sí misma actividad delictiva; y la plataforma requiere registro gratuito para acceso completo. El error más frecuente es tratar una aparición en los Panama Papers o en los FinCEN Files como prueba de irregularidad, cuando en realidad solo indica presencia en estructuras offshore o en movimientos de fondos que la propia base de datos señala como sospechosos pero no necesariamente ilícitos.

Para el investigador de cibercrimen, Aleph funciona mejor como herramienta de contraste en la fase de valoración del hallazgo: una vez identificado un administrador o una entidad a través de fuentes registrales, la consulta en Aleph puede revelar si esa persona o entidad tiene antecedentes en contextos de investigación periodística o aparece en listas de control que apuntan a un perfil de riesgo elevado.

Complementariamente, herramientas como **Sayari**, **Orbis** de Bureau van Dijk o **LexisNexis Business Insight** ofrecen capacidades similares o superiores en términos de cobertura y análisis relacional automatizado, aunque su acceso no es gratuito y su disponibilidad en unidades policiales depende de los contratos institucionales existentes. En entornos sin acceso a estas plataformas de pago, la combinación de OpenCorporates y Aleph con consultas directas a registros nacionales cubre la mayor parte de las necesidades de una investigación societaria básica y relacional.

### 7.3 Investigación de webs corporativas, dominios y exposición económica visible

El análisis de la presencia digital corporativa permite contextualizar la información registral y detectar incoherencias que son especialmente indicativas en fraudes de inversión o plataformas de servicios ilegítimas. El investigador debe examinar si la web de la empresa tiene contenido coherente con su actividad declarada, si los datos de contacto son verificables, si el aviso legal menciona a una persona jurídica concreta con número de identificación, si las condiciones de uso hacen referencia a una entidad con jurisdicción identificable y si el diseño o el contenido coincide con otras plataformas conocidas por ser fraudulentas.

Las herramientas de registro de dominio permiten determinar cuándo fue registrado el dominio, qué registrador se utilizó y, cuando la información no está protegida por privacidad, quién figura como titular. La plataforma **DomainTools** y el servicio **ICANN WHOIS** son puntos de partida habituales. El historial de cambios de un dominio puede consultarse a través de servicios como **ViewDNS** o **SecurityTrails**, que también permiten ver qué IPs ha resuelto un dominio a lo largo del tiempo y qué otros dominios han compartido infraestructura con él, un dato de gran valor cuando se detecta reutilización de infraestructura entre varias plataformas fraudulentas.

**Wayback Machine**, el servicio de archivo web de Internet Archive, permite recuperar versiones históricas de webs que ya no están activas o que han sido modificadas. Cuando una plataforma de falsas inversiones ha desaparecido, sus capturas archivadas pueden contener datos de contacto, términos legales, menciones de entidades y pasarelas de pago que ya no son accesibles en la versión actual. Este recurso es especialmente valioso cuando se investigan fraudes online cuya infraestructura ha sido desactivada tras la denuncia.

### 7.4 Análisis blockchain y exploración de wallets y transacciones

El análisis de activos digitales en fuentes abiertas parte de una premisa fundamental: las redes blockchain públicas registran todas sus transacciones en un libro mayor distribuido, accesible a cualquier persona con conexión a internet. Esto convierte el historial de transacciones de cualquier dirección pública en información de libre acceso. Lo que no es accesible en fuentes abiertas es la identidad del titular de esa dirección: esa información requiere diligencias formales dirigidas a los servicios donde el usuario se registró.

**Etherscan** es el explorador de referencia para la red Ethereum y sus activos compatibles con el estándar ERC-20, que incluye la inmensa mayoría de los tokens emitidos en ICOs, plataformas DeFi, exchanges descentralizados y muchos de los esquemas de fraude de inversión basados en criptoactivos. El dato de entrada puede ser una dirección de wallet, un hash de transacción, el nombre de un token o la dirección de un contrato inteligente.

Cuando el investigador introduce una dirección en Etherscan, obtiene el saldo actual, el valor en moneda fiat estimado, la lista completa de transacciones entrantes y salientes con fecha, importe y dirección de contraparte, la lista de tokens ERC-20 asociados y, en muchos casos, etiquetas públicas que identifican la dirección como perteneciente a un servicio conocido: un exchange centralizado, una plataforma DeFi, un protocolo conocido o una entidad etiquetada como sospechosa o sancionada. El investigador debe prestar atención particular a las etiquetas: cuando los fondos recibidos de una víctima terminan en una dirección etiquetada como perteneciente a un exchange conocido, eso orienta directamente hacia qué entidad debe recibir un requerimiento de información sobre los datos del titular de la cuenta de destino.

El análisis de flujo básico en Etherscan consiste en seguir la cadena de transacciones desde la dirección receptora inicial. Si esa dirección vacía regularmente sus fondos hacia otra dirección, y esa segunda dirección los envía a un exchange etiquetado, el investigador ha identificado ya la arquitectura básica del flujo de lavado. No ha identificado a ninguna persona, pero ha establecido el camino que siguieron los fondos y el servicio final al que llegaron.

La limitación principal de Etherscan es su especificidad a la red Ethereum. No sirve para investigar transacciones en Bitcoin, en Tron, en Solana ni en otras redes. El investigador debe identificar la red antes de seleccionar el explorador. Una dirección que comienza por «0x» corresponde a Ethereum o redes compatibles. Una dirección que comienza por «T» corresponde generalmente a la red Tron. Una dirección en formato bech32 (comienza por «bc1») corresponde a Bitcoin en su formato nativo más reciente. Las confusiones de red son un error frecuente y pueden llevar a análisis completamente inútiles.

**TRONSCAN** es el explorador equivalente para la red Tron, que en los últimos años ha adquirido especial relevancia en fraudes de inversión y extorsión porque es la red más utilizada para transacciones en USDT (Tether) de bajo coste. Muchas plataformas de falsas inversiones utilizan USDT sobre Tron como mecanismo de captación de fondos, precisamente por su facilidad de uso, su velocidad y sus bajas comisiones. El investigador que recibe una dirección de wallet asociada a una estafa de inversión en la que se usó USDT debe verificar si la dirección corresponde a la red Tron antes de seleccionar la herramienta de exploración.

TRONSCAN funciona de manera análoga a Etherscan: permite visualizar el historial completo de transacciones de una dirección, el saldo de TRX y de tokens como USDT-TRC20, las transferencias entre contratos y, cuando están disponibles, las etiquetas públicas de entidades conocidas. El análisis de flujo sigue la misma lógica: localizar las contrapartes principales, comprobar si están etiquetadas y seguir el recorrido de los fondos hacia servicios de mayor nivel de identificación.

Para la red Bitcoin, los exploradores de referencia son **Blockchain.com Explorer**, **Mempool.space** y **Blockchair**. Blockchair merece mención especial porque es un explorador multi-chain que permite buscar el mismo hash de transacción o la misma dirección en múltiples redes simultáneamente, lo que resulta especialmente útil cuando el investigador no conoce con certeza la red a la que pertenece una dirección o cuando la actividad sospechosa abarca varias redes.

**Breadcrumbs** y **Metasleuth** son herramientas de análisis de flujo con visualización gráfica que permiten representar las conexiones entre direcciones de forma visual. Son útiles para comunicar el análisis a superiores, magistrados o jueces, y para detectar patrones de dispersión o concentración que no son evidentes en la lista de transacciones. Su uso requiere que el investigador ya haya identificado las direcciones principales de interés a través de exploradores básicos.

### 7.5 Etiquetado, contexto y trazabilidad básica de direcciones

El etiquetado público de direcciones blockchain es una de las fuentes de contexto más valiosas en el análisis de criptoactivos. Cuando un explorador muestra que una dirección está etiquetada como perteneciente a un exchange concreto, a una plataforma de pagos o a una entidad con algún tipo de identificación pública, ese dato permite determinar el destino probable de los fondos y orientar los requerimientos formales.

**Crystal Blockchain** y **Chainalysis Reactor** son herramientas profesionales de análisis blockchain con bases de datos de etiquetado muy amplias. No son de acceso gratuito, pero muchas unidades policiales europeas tienen acceso a alguna de ellas a través de convenios o de licencias institucionales. Cuando están disponibles, ofrecen un nivel de análisis de flujo, clustering y atribución de entidades muy superior al que proporcionan los exploradores públicos. El investigador debe conocer su existencia y su utilidad aunque no tenga acceso directo a ellas, porque puede existir cooperación con unidades que sí lo tengan.

**AMLBot** y **GetBlock** ofrecen consultas básicas de comprobación de riesgo de direcciones con datos de etiquetado abierto. No sustituyen a las herramientas profesionales, pero pueden aportar un contexto inicial de forma gratuita o con coste reducido.

### 7.6 Correlación con aliases, correos, teléfonos, dominios y perfiles

Los datos societarios y blockchain deben cruzarse sistemáticamente con las otras dimensiones del análisis OSINT. Un administrador registral puede ser buscado en bases de datos de brechas de seguridad para identificar correos o contraseñas reutilizadas. Un dominio corporativo puede cruzarse con el historial de infraestructura para localizar otros dominios del mismo operador. Una dirección de correo visible en la web de una empresa puede ser el mismo correo con el que se registró el administrador en un foro, en una plataforma de trading o en un canal de Telegram que está siendo investigado.

Las herramientas de búsqueda inversa de correos, como **Hunter.io** para la verificación de correos corporativos, o las plataformas de análisis de brechas como **Have I Been Pwned** para correos comprometidos, pueden aportar ese cruce cuando se trabaja con correos visibles en fuentes abiertas. En ningún caso deben usarse para acceder a información privada no publicada ni para operaciones que excedan el ámbito del análisis de información en fuentes abiertas legítimas.

---

## 8. Uso combinado de fuentes abiertas y herramientas policiales

El análisis en fuentes abiertas no es el punto final de la investigación financiera o de criptoactivos. Es su fase de orientación y enriquecimiento. Los hallazgos obtenidos a través de las herramientas descritas tienen un valor propio como contexto analítico y como apoyo a la formulación de hipótesis, pero su plena explotación investigadora requiere la integración con capacidades institucionales.

Cuando el análisis en abierto ha identificado que una empresa figura como receptora de fondos en una plataforma fraudulenta, las consultas a bases de datos policiales de antecedentes de personas jurídicas o de personas físicas vinculadas a esa entidad pueden verificar si existen procedimientos previos relacionados con las mismas personas o estructuras. Esa verificación cruzada, que el investigador de cibercrimen puede realizar a través de sus propias bases institucionales, transforma un hallazgo de fuente abierta en un indicio con respaldo adicional.

Cuando el flujo blockchain ha permitido identificar que los fondos de las víctimas se dirigen a un exchange o proveedor de servicios de activos virtuales con domicilio conocido, ese hallazgo fundamenta directamente un requerimiento formal o una solicitud de información dirigida a ese proveedor, bien directamente a través del sistema policial, bien por vía de cooperación internacional si el servicio está registrado en otra jurisdicción. La Europol y su plataforma de información financiera, las vías de cooperación con la CARIN (Camden Assets Recovery Inter-agency Network) y los mecanismos de solicitud a través de Interpol son cauces que el investigador debe conocer para trasladar de forma eficiente los hallazgos de fuentes abiertas hacia diligencias formales internacionales.

Cuando el análisis societario ha identificado un patrón de empresas vinculadas por administradores comunes en varias jurisdicciones, ese hallazgo puede fundamentar una solicitud de información a través de instrumentos de cooperación judicial internacional como la Orden Europea de Investigación o los canales de asistencia judicial mutua. La investigación en abierto permite enfocar esa solicitud con precisión: en lugar de solicitar información genérica sobre una persona, el investigador puede solicitar información específica sobre determinadas entidades, cuentas, movimientos o relaciones ya identificadas en el análisis previo.

El trabajo en fuentes abiertas también puede orientar las diligencias patrimoniales formales realizadas ante el juez instructor. Las medidas de investigación patrimonial que permiten el acceso a información bancaria o a datos de titularidad de activos requieren una fundamentación fáctica suficiente. El análisis OSINT puede aportar exactamente esa fundamentación: la identificación de una sociedad, la localización de sus administradores, la detección del flujo de fondos hacia un servicio concreto y la convergencia de esos datos con la denuncia de las víctimas son elementos que permiten formular una solicitud de medida patrimonial con mucha mayor precisión y fundamentación que una denuncia que solo describe el hecho de la pérdida.

El investigador debe aprender a ver las fuentes abiertas como una fase de preparación que hace más eficientes las diligencias formales, no como un instrumento alternativo a ellas. La información obtenida en abierto sobre administradores, entidades y flujos blockchain no puede suplir la obtención formal de datos de titularidad de cuentas, de registros de identificación de usuarios de exchanges o de datos bancarios protegidos. Pero puede hacer que la solicitud de esa información sea más precisa, más fundamentada y más productiva.

---

## 9. Interpretación de hallazgos, cautelas y errores frecuentes

La interpretación de los resultados del análisis financiero en fuentes abiertas exige rigor analítico y prudencia epistemológica. El investigador debe distinguir entre varias categorías de hallazgo que tienen implicaciones analíticas y probatorias muy distintas.

La **exposición económica pública** es el nivel más básico: una persona o entidad tiene presencia visible en contextos de actividad económica o financiera. Por sí sola, no implica irregularidad ni participación en actividad delictiva.

La **relación societaria registral** indica que una persona figura en los registros mercantiles como administrador, apoderado u otro tipo de responsable de una entidad. No implica control económico real, ni beneficio, ni conocimiento de la actividad delictiva. Las estructuras de testaferros, administradores formales sin control real y personas con representación sin poder efectivo son habituales en entidades instrumentales, precisamente porque su función es interponer un eslabón registral entre el beneficiario real y la estructura visible.

La **proximidad transaccional blockchain** indica que una dirección ha enviado fondos a otra, o que dos direcciones comparten una transacción. No implica vinculación de titularidad, ni coordinación consciente, ni participación en el esquema delictivo. Las técnicas de clustering que permiten a las herramientas profesionales de análisis blockchain agrupar direcciones bajo un mismo operador tienen una tasa de error no nula y requieren validación.

La **coincidencia relacional** indica que dos personas o entidades comparten administrador, domicilio, registrador de dominio o infraestructura técnica. Es un indicio de conexión que puede tener gran valor en el contexto correcto, pero que no basta por sí solo para establecer coordinación ni actividad delictiva.

Los errores de interpretación más frecuentes son los siguientes. El primero es confundir al **administrador registral con el beneficiario real**: en investigaciones de fraude organizado, quien figura en el registro es frecuentemente una persona sin control efectivo sobre la entidad ni conocimiento de su uso ilícito. El segundo es confundir la **wallet receptora con el beneficiario final**: la dirección que recibe fondos de las víctimas no suele ser la dirección final del beneficiario; los fondos se mueven en varias etapas antes de llegar al destino con mayor control. El tercero es **sobreinterpretar la etiqueta de un exchange**: que los fondos lleguen a un exchange implica que alguien con cuenta en ese exchange recibió los fondos, no que el exchange sea cómplice ni que la identidad del titular sea inmediatamente accesible. El cuarto es tratar una **empresa instrumental como actor con actividad real**: muchas sociedades utilizadas en fraudes no tienen ninguna actividad económica legítima ni ningún activo propio; su análisis contable o de cuentas depositadas no refleja la actividad económica del esquema, sino el movimiento formal de fondos que se ha querido atribuirle. El quinto es **depender de una sola fuente mercantil** sin contrastarla con el registro original, lo que puede llevar a trabajar con datos desactualizados o incompletos.

---

## 10. Aspectos jurídicos, deontológicos y probatorios específicos

La información societaria y blockchain accesible en fuentes abiertas es, por definición, información pública. Su consulta y análisis no requiere autorización judicial ni policial específica. Sin embargo, su tratamiento en el marco de una investigación policial exige atención a varios aspectos que determinan tanto su valor probatorio como la corrección metodológica del procedimiento.

En cuanto a la **legitimidad del acceso**, el investigador actúa dentro del marco de sus funciones cuando consulta registros públicos, exploradores blockchain y bases de datos abiertas para obtener información relevante para una investigación en curso. Esta consulta no constituye una injerencia en derechos fundamentales y no requiere autorización especial. No obstante, cuando el análisis OSINT lleva al acceso a datos que, aunque accesibles técnicamente, han sido publicados sin autorización de su titular o que pertenecen a una categoría especialmente protegida, el investigador debe valorar si ese acceso es adecuado y documentar las razones que lo justifican.

En cuanto al **tratamiento de datos personales**, la Ley Orgánica 7/2021 de protección de datos personales en el ámbito de prevención, detección, investigación y enjuiciamiento de infracciones penales y de ejecución de sanciones penales establece las bases de legitimación y las garantías aplicables al tratamiento de datos personales en el contexto de la investigación policial. El investigador debe ser consciente de que, aunque los datos sean públicamente accesibles, su incorporación a un expediente de investigación los convierte en objeto de tratamiento sujeto a esta normativa, y que la finalidad de ese tratamiento debe ser coherente con la investigación en curso.

En cuanto al **valor probatorio**, la información obtenida de fuentes abiertas puede incorporarse al expediente como dato de contexto, como fundamento de hipótesis y como base para la solicitud de diligencias formales. Para que tenga valor probatorio directo, debe estar adecuadamente preservada y documentada: capturas de pantalla con metadatos de fecha y hora, documentación del flujo de consulta, descripción del estado de la información en el momento de la consulta y, cuando sea posible, uso de herramientas de preservación web que generen evidencia con mayor solidez documental.

La **prudencia en la comunicación de resultados** es un imperativo deontológico. El investigador no debe comunicar a terceros, dentro ni fuera de la institución, información obtenida durante el análisis de fuentes abiertas si esa comunicación puede poner en peligro la investigación, alertar al sujeto investigado o vulnerar la presunción de inocencia. Los hallazgos deben incorporarse al expediente a través de los cauces procedimentales establecidos, no difundirse de forma informal ni utilizarse para finalidades ajenas a la investigación.

---

## 11. Caso práctico aplicado

### Caso práctico: plataforma de inversión fraudulenta con estructura societaria instrumental y fondos canalizados a través de USDT-Tron

**Supuesto de hecho.**
La unidad de cibercrimen recibe una denuncia de varias víctimas que refieren haber invertido importes de entre tres mil y veinte mil euros en una plataforma de trading denominada «CryptoVault Pro», accesible a través del dominio cryptovaultpro.com. La plataforma prometía rentabilidades garantizadas del tres por ciento semanal, con panel de control personalizado y gestor de cuenta asignado. Tras un periodo inicial de aparentes beneficios, la plataforma bloqueó los intentos de retirada alegando problemas técnicos, y posteriormente desapareció sin devolver los fondos. Las víctimas aportaron capturas de pantalla de la plataforma, del panel de usuario y de las instrucciones de pago recibidas, en las que se indicaba que los depósitos debían realizarse en USDT sobre la red Tron, a una dirección específica.

**Dato o indicio de partida.**
Dirección de wallet Tron: TRxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx (formato real omitido por razones metodológicas). Nombre de empresa visible en el pie de página de la web: «CryptoVault Pro Ltd.». Dominio: cryptovaultpro.com.

**Hipótesis de trabajo.**
La plataforma opera un esquema de estafa de inversión mediante una empresa instrumental creada con fines de apariencia de legitimidad. Los fondos se reciben en una dirección de wallet Tron en USDT y son trasladados posteriormente a exchanges u otras direcciones para dificultar su trazabilidad. El dominio y la empresa pueden conectarse con otras infraestructuras similares a través de datos registrales y técnicos.

**Actuaciones realizadas.**

En primer lugar, el investigador verifica el formato de la dirección Tron y accede a TRONSCAN. La dirección muestra un saldo de USDT cercano a cero, pero un historial de transacciones entrantes que suma aproximadamente ciento cuarenta mil USDT en un periodo de cuatro meses. El análisis de las transacciones salientes muestra que los fondos se enviaban regularmente, dentro de las 24-48 horas de recepción, a otra dirección Tron. Esa segunda dirección aparece etiquetada en TRONSCAN como asociada a un exchange de activos virtuales conocido con sede registrada fuera de la Unión Europea.

A continuación, el investigador consulta el dominio en ICANN WHOIS y en SecurityTrails. El dominio fue registrado hace seis meses, con privacidad de datos del titular activada, a través de un registrador con sede en Islas Vírgenes Británicas. SecurityTrails muestra que dos dominios adicionales con nombres similares fueron registrados en las mismas fechas, con el mismo registrador y resolviendo a IPs en el mismo rango. Esos dominios corresponden a plataformas de inversión con nombres diferentes pero diseños idénticos o muy similares, lo que sugiere una operación en serie.

El investigador busca «CryptoVault Pro Ltd.» en OpenCorporates. Localiza una entidad con esa denominación exacta registrada en un registro de sociedades del Caribe, con tres meses de antigüedad. El administrador registrado es una persona física cuyo nombre es buscado en Aleph: aparece en una filtración de datos de una jurisdicción offshore como asociado a otras tres entidades de similar antigüedad y perfil, dos de ellas vinculadas a dominios previamente identificados en el paso anterior.

Adicionalmente, el aviso legal de la web, recuperado a través de Wayback Machine antes de que fuera desactivada, contiene una dirección de correo electrónico de soporte. Esa dirección se cruza con otras fuentes y aparece en un foro de alertas de inversión como dirección de contacto de una plataforma denunciada en otro país meses antes.

**Hallazgos obtenidos.**
La investigación ha identificado una arquitectura financiera con los siguientes elementos: una wallet Tron receptora de fondos de víctimas que vacía regularmente hacia un exchange de tercera jurisdicción; una empresa instrumental reciente sin actividad real identificable, vinculada por su administrador a otras entidades de perfil análogo; tres dominios de operación en serie registrados con la misma infraestructura; y una dirección de contacto ya asociada a denuncias previas por estafa de inversión.

**Análisis e interpretación.**
Los hallazgos son convergentes y apuntan a una estructura de operación deliberada y sistemática, no a un incidente aislado. La recurrencia del patrón en varios dominios y entidades, la datación simultánea de los registros y la presencia del administrador en varias estructuras similares indica una operación organizada, no un actor individual. No obstante, ninguno de los hallazgos establece por sí solo la identidad del beneficiario real ni acredita la vinculación personal del administrador registral con el control efectivo del esquema.

**Explotación policial y documental.**
El investigador incorpora los hallazgos al atestado como diligencias de investigación en fuentes abiertas, con preservación documentada de cada consulta. Formula una solicitud de información al exchange identificado a través de los canales de cooperación internacional, identificando la dirección de destino de los fondos, el periodo de actividad y el importe aproximado. Solicita a la unidad de cooperación internacional la identificación de otras unidades que puedan haber investigado los dominios relacionados. Propone al instructor la adopción de medidas de investigación patrimonial sobre las entidades identificadas.

**Lecciones operativas.**
El análisis de TRONSCAN en la primera fase fue determinante para identificar el flujo de fondos hacia un exchange conocido, lo que orientó directamente los requerimientos de información. La búsqueda en OpenCorporates reveló el administrador registral como pivote de conexión entre varias entidades instrumentales. La consulta de SecurityTrails permitió identificar la operación en serie. La combinación de fuentes abiertas con la recuperación del archivo web fue esencial para recuperar datos de contacto que ya habían sido eliminados. La investigación muestra que la acreditación de la responsabilidad individual del beneficiario real requería diligencias formales que el análisis OSINT no podía suplir, pero que sí podía fundamentar con precisión.

---

## 12. Conclusiones operativas

La información financiera, societaria y blockchain constituye un objeto de análisis de primer orden en la investigación OSINT aplicada al cibercrimen. Su valor no radica en que permita identificar de forma concluyente a un sujeto o acreditar de forma definitiva su responsabilidad, sino en que permite construir contexto económico, relacionar actores y estructuras, detectar patrones de actividad delictiva organizada y formular hipótesis de trabajo que orientan con precisión las diligencias formales.

Las herramientas disponibles en fuentes abiertas para la investigación societaria y blockchain son numerosas, accesibles y de calidad suficiente para una fase de investigación exploratoria y orientadora. OpenCorporates, Aleph, Etherscan, TRONSCAN, Blockchair y los demás recursos descritos en este capítulo no son nombres en una lista: son instrumentos con una función investigadora concreta dentro de un flujo de trabajo profesional. Su utilidad depende de que el investigador sepa cuándo usarlos, qué puede esperar obtener de ellos y cómo interpretar sus resultados sin sobreestimar su alcance.

La prudencia interpretativa es inseparable del análisis financiero en fuentes abiertas. Un administrador registral no es necesariamente el beneficiario real. Una wallet receptora no es necesariamente el destinatario final. Una empresa instrumental no es necesariamente quien controla el esquema. La coincidencia relacional no es autoría. El investigador que interioriza estas distinciones no trabaja peor: trabaja con mayor rigor, formula hipótesis más sólidas y construye expedientes más resistentes.

El análisis en fuentes abiertas debe integrarse con coherencia en la investigación formal. Sus hallazgos deben documentarse, preservarse y utilizarse como base de diligencias más sólidas, no como reemplazo de ellas. Cuando el trabajo en abierto ha identificado la arquitectura financiera de un esquema delictivo, el investigador dispone de una base de trabajo muy superior a la que tendría sin ese análisis previo. Esa es su función: hacer la investigación más eficiente, más precisa y mejor fundamentada.

---

## 13. Checklist final de trabajo

**Recepción y verificación del dato inicial**
- Naturaleza del dato identificada: empresa, administrador, wallet, transacción, dominio, IBAN u otro observable económico.
- Formato verificado: dirección blockchain válida en la red correcta; nombre de empresa con NIF/número de identificación contrastado; dominio con estructura válida.
- Contexto de aparición registrado: fuente, fecha, circunstancias de obtención.
- Hipótesis de trabajo formulada.

**Investigación societaria**
- Registro oficial del país de constitución consultado.
- Búsqueda en OpenCorporates realizada con nombre de empresa y nombre de administrador.
- Vínculos corporativos del administrador identificados en otras entidades.
- Consulta en Aleph/OCCRP realizada para detección de presencia en listas de sanciones, offshore o bases de investigación periodística.
- Antigüedad, domicilio y objeto social analizados en relación con el contexto del caso.
- Presencia digital de la empresa examinada: web, dominio, historial de cambios, aviso legal.

**Análisis de dominio e infraestructura**
- Fecha de registro del dominio verificada en WHOIS.
- Historial de IPs consultado en SecurityTrails o equivalente.
- Dominios compartiendo infraestructura identificados.
- Versiones históricas de la web recuperadas en Wayback Machine si procede.

**Análisis blockchain**
- Red blockchain identificada correctamente antes de seleccionar el explorador.
- Explorador adecuado utilizado: Etherscan para Ethereum/ERC-20, TRONSCAN para Tron/TRC-20, explorador Bitcoin para BTC.
- Historial completo de transacciones examinado: importe total, periodos de actividad, contrapartes principales.
- Comportamiento de vaciado o concentración identificado.
- Etiquetas públicas de contrapartes comprobadas.
- Fondos dirigidos a exchanges u otras entidades identificadas y registradas.

**Contraste y enriquecimiento**
- Hallazgos contrastados con fuentes adicionales: alertas de reguladores, noticias, foros de alerta de inversión.
- Correlación con aliases, correos u otros datos de la investigación realizada.
- Patrones de reutilización de infraestructura, administradores o vías de contacto identificados.

**Valoración e integración institucional**
- Fuerza del hallazgo valorada explícitamente: indicio aislado, convergencia de indicios o contexto complementario.
- Diligencias formales identificadas que pueden beneficiarse de los hallazgos: requerimientos a exchanges, solicitudes de información, medidas patrimoniales, cooperación internacional.
- Posibles coincidencias con bases de datos policiales valoradas.

**Preservación y documentación**
- Capturas preservadas con metadatos de fecha y hora.
- Flujo de consulta documentado: qué herramienta, cuándo, qué se encontró, qué se interpretó.
- Estado de la información en el momento de la consulta registrado.
- Hallazgos incorporados al expediente a través de los cauces procedimentales correspondientes.