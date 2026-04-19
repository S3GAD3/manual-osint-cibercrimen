# Capítulo 13. Correlación de entidades y análisis relacional en fuentes abiertas

---

## 1. Introducción

La investigación de cibercrimen produce, con frecuencia, un volumen elevado de observables que, considerados por separado, tienen escaso valor. Un correo electrónico hallado en un foro de fraude, un número de teléfono reutilizado en varios anuncios, un alias recurrente en distintas plataformas, una dirección de wallet que aparece en registros dispersos: ninguno de estos elementos, examinado en aislamiento, resulta suficiente para orientar una investigación hacia una persona o estructura con solidez metodológica. El salto cualitativo se produce cuando esos observables comienzan a relacionarse entre sí de forma coherente, cuando empiezan a emerger patrones, cuando varios hilos convergen en los mismos nodos y cuando el investigador es capaz de leer esa convergencia con rigor analítico.

La correlación de entidades y el análisis relacional constituyen, precisamente, la fase en que los datos dejan de ser inventario y se convierten en estructura. No se trata de una operación mecánica de conexión entre puntos, ni de una mera representación gráfica de coincidencias. Es una actividad interpretativa que exige método, contexto, contraste y prudencia. Correlacionar bien no consiste en encontrar todas las conexiones posibles entre todos los datos disponibles, sino en identificar qué relaciones tienen significado investigador, cuál es la naturaleza de ese significado, qué fuerza probatoria o indiciaria puede atribuírsele y cómo debe orientar el trabajo posterior.

En el ámbito del cibercrimen, esta fase adquiere una relevancia especial. Las estructuras delictivas digitales se sustentan, con frecuencia, en ecosistemas de identidades reutilizadas, infraestructuras compartidas, comunidades de operadores y activos que se reciclan. La persona que comete una estafa de inversión bajo un alias determinado puede usar el mismo correo para registrar un dominio de phishing, el mismo teléfono para crear una cuenta en una plataforma de pagos y la misma wallet para recibir fondos en un esquema completamente distinto. Esa reutilización de recursos no es accidental: forma parte del patrón operativo. Y detectarla, articularla y documentarla con solvencia metodológica es, precisamente, la tarea que este capítulo pretende enseñar.

---

## 2. Finalidad investigadora del capítulo

Este capítulo ocupa un lugar central en el manual porque aborda la fase en que el analista deja de recolectar y comienza a estructurar. La mayoría de los capítulos anteriores están orientados a la obtención de información: cómo buscar en redes sociales, cómo analizar dominios, cómo rastrear criptomonedas, cómo explotar metadatos o imágenes. Este capítulo enseña qué hacer con todo eso una vez que se dispone de un conjunto suficientemente amplio de observables.

La finalidad concreta del capítulo es doble. Por un lado, ofrece un marco conceptual mínimo pero riguroso para entender qué son las entidades y los vínculos como objetos de análisis, qué tipos de relaciones pueden identificarse y cómo debe evaluarse su fuerza. Por otro, y con mayor énfasis, desarrolla una metodología práctica y operativa para construir un análisis relacional útil: qué fases sigue, qué herramientas apoyan cada fase, cómo se documenta el proceso y cómo se integran los hallazgos con las capacidades policiales e institucionales disponibles.

El análisis relacional resulta especialmente valioso en el cibercrimen porque muchos de los modelos delictivos digitales —fraude por compromiso de correo empresarial, esquemas piramidales en línea, campañas de phishing industrializadas, sextorsión a escala, mercados de datos robados— se articulan mediante redes de actores, recursos e infraestructuras que solo son comprensibles cuando se examinan como sistema. No basta con identificar a un titular de cuenta o a un administrador de dominio: es necesario entender cómo ese nodo se conecta con el resto de la estructura, qué papel cumple y qué líneas de ampliación puede abrir.

---

## 3. Objeto de análisis y punto de partida

El concepto fundamental sobre el que descansa este capítulo es el de entidad. A efectos del análisis relacional en OSINT, una entidad es cualquier elemento observable con capacidad de establecer relaciones con otros elementos dentro del universo de datos disponible. Una entidad puede ser una persona real, un alias digital, una dirección de correo electrónico, un número de teléfono, un dominio, una dirección IP, una wallet de criptomonedas, una cuenta en red social, una empresa o persona jurídica, un número de identificación, una imagen o cualquier otro artefacto que pueda conectarse, compararse o contrastarse con otros elementos del mismo conjunto.

El vínculo, por su parte, es la relación que existe o puede inferirse entre dos entidades. No todo vínculo tiene el mismo valor. Algunos son directos: la misma dirección de correo figura como contacto en dos perfiles distintos. Otros son indirectos: un alias aparece en un foro de fraude y ese mismo foro es señalado como punto de distribución de una campaña de phishing que utiliza un dominio registrado por una dirección de correo ya conocida en la investigación. Entre ambos extremos existe un espectro amplio de relaciones con distinto grado de certeza, distinta naturaleza y distinto valor operativo.

El observable relacional es el dato concreto, extraído de fuentes abiertas, que da soporte empírico a un vínculo. No basta con afirmar que dos entidades están relacionadas: debe existir un observable que respalde esa afirmación y que sea susceptible de documentación y contraste. La ausencia de un observable verificable no invalida una hipótesis, pero sí la sitúa en un plano conjetural que debe ser expresamente reconocido.

Las preguntas que el análisis relacional permite formular son preguntas de convergencia: ¿qué otras entidades comparten infraestructura con esta? ¿A qué otras cuentas o actividades está vinculado este alias? ¿Este número de teléfono aparece en contextos distintos y coherentes? ¿Esta wallet ha sido utilizada en operaciones que conectan con otros actores ya identificados? ¿Esta comunidad digital agrupa a personas que también participan en otras comunidades de interés investigador? La respuesta a estas preguntas no se obtiene por deducción lógica, sino por análisis metódico de datos reales, con todo lo que eso implica en términos de incertidumbre, parcialidad y necesidad de contraste.

---

## 4. La entidad y el vínculo como núcleo del análisis relacional

El análisis relacional se sustenta en la noción de que las entidades no existen en el vacío. Toda entidad con relevancia investigadora ha sido creada, utilizada, reutilizada o expuesta por alguien, en algún momento, con algún propósito. Esa actividad deja rastros, y los rastros conectan entidades entre sí. La tarea del analista consiste en identificar esas conexiones, valorarlas y extraer de ellas consecuencias útiles para la investigación.

Dentro de una investigación de cibercrimen, las entidades pueden funcionar como pivotes cuando aparecen en múltiples contextos de forma recurrente y coherente. Un correo electrónico que aparece como contacto en un perfil de LinkedIn, como remitente de correos de phishing y como titular de un dominio fraudulento no es una coincidencia trivial: es un nodo con alto valor relacional que merece ser examinado con detenimiento. Lo mismo ocurre con un alias que reaparece en distintos foros especializados, siempre vinculado al mismo tipo de actividad; o con una wallet que recibe fondos de víctimas identificadas en distintas investigaciones.

El valor de una entidad como pivote no depende únicamente de la cantidad de vínculos que presenta, sino de la coherencia contextual de esos vínculos. Diez conexiones dispersas entre sí y sin contexto compartido tienen menos valor analítico que tres conexiones que apuntan consistentemente en la misma dirección. La coherencia es un criterio de calidad que debe guiar la valoración relacional desde el principio.

Los vínculos, a su vez, pueden clasificarse según su naturaleza en varias categorías que conviene distinguir con precisión. Los vínculos técnicos son los que se derivan de infraestructura compartida: mismas IPs, mismo servidor de nombres, mismo proveedor de hosting, mismo bloque de registro WHOIS, mismo hash de imagen. Los vínculos contextuales emergen de la aparición de entidades en los mismos espacios, comunidades o conversaciones. Los vínculos operativos son los que revelan colaboración o coordinación en la ejecución de actividades delictivas. Los vínculos económicos conectan actores a través de flujos de fondos, pagos o beneficios compartidos. Los vínculos sociales se derivan de relaciones interpersonales constatables en fuentes abiertas. Los vínculos cronológicos apuntan a una secuencia temporal significativa entre acciones o entidades. Y los vínculos meramente aparentes son aquellos que, a primera vista, sugieren una relación pero que, examinados con rigor, carecen de respaldo empírico suficiente o pueden explicarse por coincidencia, reutilización comercial de infraestructura o error de interpretación.

Esta taxonomía no es un sistema rígido: en la práctica, muchos vínculos son de naturaleza mixta. Pero disponer de un marco de clasificación permite al investigador describir con mayor precisión lo que ha encontrado, comunicarlo con claridad y valorar su fuerza con método.

---

## 5. Análisis inicial de entidades, relaciones y contextualización del hallazgo

Cuando un investigador se enfrenta a un conjunto de observables procedentes de distintas fuentes y fases de la investigación, la primera tarea no consiste en trazar conexiones, sino en hacer inventario. Es necesario identificar con precisión qué entidades están presentes, de qué tipo son, de qué fuente proceden, en qué contexto aparecen y qué calidad tiene el dato de base.

Esta fase inicial de inventario y clasificación es metodológicamente crítica porque determina la solidez de todo el análisis posterior. Una entidad mal identificada —por ejemplo, confundir un alias de foro con un nombre real, o asumir que dos correos con formato similar corresponden a la misma persona— puede contaminar todo el grafo relacional. La calidad del análisis depende de la calidad del dato de partida, y eso exige verificar la procedencia de cada observable, contrastar cuando sea posible y señalar expresamente el grado de certeza asociado a cada entidad.

Una vez clasificadas las entidades por tipo —personas, cuentas, correos, teléfonos, dominios, wallets, empresas, imágenes, comunidades— el investigador debe examinar qué relaciones pueden establecerse de manera directa a partir de los datos disponibles. Este examen inicial debe ser descriptivo, no interpretativo: se trata de anotar qué conexiones existen, no de extraer conclusiones. Las conclusiones vendrán después, cuando el análisis tenga suficiente estructura.

El contexto de aparición de cada entidad es un dato tan importante como la entidad misma. No es lo mismo encontrar un alias en un foro de venta de datos robados que en un grupo de debate sobre criptomonedas legítimo. No es lo mismo encontrar un correo como titular de un dominio activo que como dato registrado hace seis años en una plataforma ya extinta. El contexto temporal, el contexto funcional y el contexto relacional de cada entidad deben documentarse desde el principio porque condicionarán la interpretación posterior.

La formulación de hipótesis de trabajo debe aparecer en esta fase de forma provisional y explícitamente condicional. Una hipótesis no es una conclusión prematura: es una proposición verificable que orienta el trabajo siguiente. «El alias X y la dirección de correo Y parecen corresponder a la misma persona o grupo» es una hipótesis válida que merece ser sometida a contraste. «El alias X y la dirección de correo Y corresponden a Z» es una conclusión que aún no está justificada.

---

## 6. Flujo de trabajo del investigador para construir un análisis relacional útil

El flujo de trabajo que se describe a continuación está diseñado para ser realista, adaptable y operativamente útil. No sustituye al criterio del investigador: lo apoya y estructura.

**Primera fase: recopilación y registro de observables.** Antes de comenzar el análisis relacional, el investigador debe disponer de un registro ordenado de todos los observables obtenidos hasta ese momento. Ese registro debe incluir, para cada observable, su contenido exacto, su fuente, la fecha de obtención, el método empleado y el contexto de aparición. Esta documentación inicial es la base del análisis y también la garantía de trazabilidad metodológica. En esta fase no se desecha nada: incluso los observables de calidad dudosa deben registrarse, con nota sobre sus limitaciones.

**Segunda fase: identificación y clasificación de entidades.** A partir del registro de observables, el investigador identifica las entidades presentes y las clasifica por tipo. Es recomendable usar un sistema de identificadores únicos para cada entidad —una referencia interna que permita manejarlas sin ambigüedad— y anotar, para cada una, el observable que la respalda. En esta fase deben señalarse también las entidades con incertidumbre: aquellas cuya identidad no está completamente verificada o cuya presencia en el conjunto de datos responde a una inferencia, no a un dato directo.

**Tercera fase: identificación de relaciones directas.** El investigador recorre el conjunto de entidades y anota qué relaciones directas existen entre ellas a partir de los observables disponibles. Por «directa» se entiende aquella relación que está respaldada por al menos un observable que conecta explícitamente las dos entidades. Por ejemplo: el correo A aparece como titular del dominio B; el alias C aparece en el mismo hilo de foro que el alias D; la wallet E recibe fondos de la dirección F. Cada relación debe documentarse con referencia al observable que la sustenta.

**Cuarta fase: identificación de relaciones indirectas y patrones.** Una vez registradas las relaciones directas, el investigador busca relaciones indirectas: entidades que no comparten un observable directo pero que están conectadas a través de una o más entidades intermedias. En esta fase comienzan a emerger los patrones: cadenas de entidades que comparten infraestructura, grupos de cuentas con comportamiento homogéneo, redes de dominios con características técnicas comunes. Es también en esta fase donde deben identificarse los nodos de alta conectividad —aquellos que presentan más vínculos que el resto— y los pivotes —entidades que conectan grupos o clusters que, de otro modo, aparecerían desconectados.

**Quinta fase: valoración de la fuerza de cada vínculo.** No todas las relaciones tienen el mismo peso analítico. El investigador debe asignar a cada vínculo un nivel de fuerza: fuerte, cuando el observable es robusto, verificado y coherente con el contexto; medio, cuando el observable existe pero presenta alguna limitación o ambigüedad; débil, cuando la relación se apoya en indicios escasos o en inferencias de segundo orden; aparente o espurio, cuando el vínculo puede explicarse por coincidencia técnica, reutilización comercial de infraestructura o error de interpretación. Esta valoración no es definitiva: puede revisarse a medida que aparecen nuevos datos o que los existentes se contrastan mejor.

**Sexta fase: análisis de convergencia.** La convergencia es el fenómeno por el que varias entidades, de naturaleza distinta y procedentes de fuentes distintas, apuntan coherentemente en la misma dirección. Una hipótesis respaldada por un único observable tiene valor orientativo pero escasa solidez. Esa misma hipótesis respaldada por tres o cuatro observables independientes, coherentes entre sí y sin contradicciones significativas, tiene un valor analítico notablemente mayor. El investigador debe buscar activamente convergencia: buscar nuevos observables que permitan confirmar o refutar las relaciones ya identificadas y examinar si las distintas líneas del análisis apuntan al mismo conjunto de entidades o se dispersan.

**Séptima fase: integración cronológica.** La secuencia temporal de los observables puede reforzar o debilitar una hipótesis relacional. Si el correo A fue creado antes de que apareciera el alias B, que a su vez fue usado antes de que se registrara el dominio C, esa secuencia puede ser coherente con una narrativa de actividad progresiva de un mismo actor. Si, por el contrario, la cronología es contradictoria —por ejemplo, si una entidad aparece activa después de que se tenga constancia de su baja— eso exige revisión. El análisis cronológico no es un adorno: es una herramienta de verificación que debe integrarse en el flujo desde el principio.

**Octava fase: identificación de líneas de ampliación.** A partir del análisis relacional construido, el investigador debe identificar qué entidades o vínculos merecen examen adicional. Algunas entidades habrán sido completamente agotadas en fuentes abiertas y no ofrecen posibilidad de ampliación por esa vía. Otras presentarán pivotes que aún no han sido investigados en profundidad. Esta fase consiste en priorizar: qué nodo debe examinarse a continuación, qué fuente debe consultarse para verificar una relación, qué diligencia formal podría añadir información que las fuentes abiertas no proporcionan.

**Novena fase: documentación del análisis.** El proceso de análisis relacional debe quedar documentado con el mismo rigor que cualquier otra diligencia de investigación. Eso significa registrar no solo los resultados sino el razonamiento: por qué se estableció determinada relación, qué observable la sustenta, qué nivel de fuerza se le asignó y por qué, qué hipótesis se examinaron y cuáles fueron descartadas y por qué motivo. Un análisis relacional bien documentado no solo es más sólido desde el punto de vista metodológico: también es más defendible si llega a ser cuestionado en sede judicial o en un proceso de revisión interna.

---

## 7. Herramientas y recursos prácticos para la correlación de entidades y el análisis relacional

Las herramientas disponibles para apoyar el análisis relacional son diversas, y su valor depende de cómo se integran en un flujo de trabajo metodológicamente sólido. Ninguna herramienta sustituye al analista: todas son instrumentos que amplifican o estructuran capacidades humanas, pero no compensan la falta de rigor en la definición de entidades, la pobreza del dato de partida o la ausencia de contraste. Lo que sigue es una descripción orientada al uso investigador real, no una ficha técnica de software.

### 7.1. Herramientas de organización y estructuración de entidades

Antes de cualquier visualización o análisis de grafos, el investigador necesita organizar su conjunto de entidades y vínculos de forma que sea operable. La herramienta más sencilla y universalmente disponible es una hoja de cálculo estructurada con columnas para entidad A, tipo de entidad A, entidad B, tipo de entidad B, tipo de relación, observable que sustenta el vínculo, fuente, fecha y nivel de fuerza asignado. Esta estructura tabular, aunque poco sofisticada, es la base de cualquier análisis posterior y tiene la ventaja de ser transparente, portable, editable y fácilmente auditable. Su limitación es que no permite visualizar la red de forma intuitiva ni detectar clusters o patrones de alto nivel sin ayuda adicional.

Para investigaciones con mayor volumen de entidades, herramientas como Obsidian —orientada a la creación de notas vinculadas— permiten construir una base de conocimiento relacional en la que cada entidad es un nodo y cada vínculo es un enlace. Su vista de grafo integrada ofrece una visualización básica pero funcional, útil para una primera exploración del conjunto. Su principal limitación para análisis más complejos es la escasa capacidad de análisis cuantitativo o métrico.

### 7.2. Maltego

Maltego es la herramienta más ampliamente utilizada en el ámbito OSINT para la construcción y visualización de grafos relacionales, y merece un tratamiento detallado.

Su funcionamiento se basa en el concepto de *transform*: una operación que toma una entidad de entrada —un correo, un dominio, una IP, un nombre, una cuenta de red social— y devuelve un conjunto de entidades relacionadas extraídas de diversas fuentes públicas o comerciales. El investigador parte de una entidad semilla —por ejemplo, el correo electrónico encontrado como titular de un dominio fraudulento— y ejecuta transforms sucesivos que van expandiendo el grafo: a qué dominios está asociado ese correo, qué registros DNS tienen esos dominios, qué otras direcciones IP comparten servidor, qué cuentas de redes sociales están vinculadas, etcétera.

El dato de entrada puede ser cualquiera de los tipos de entidad soportados por la plataforma: dirección de correo, número de teléfono, dominio, IP, nombre de persona, organización, dirección de bitcoin, username, número IMEI, o cualquier entidad para la que exista un transform disponible. Los resultados se visualizan directamente en el grafo y se pueden enriquecer con datos procedentes de fuentes externas integradas mediante la biblioteca de transforms de Maltego Hub, que incluye conectores con servicios como Shodan, VirusTotal, Have I Been Pwned, FullContact, Hunter.io y muchos otros.

En un flujo de trabajo real, Maltego resulta especialmente valioso en la fase de expansión relacional: cuando el investigador ya tiene identificadas algunas entidades semilla y quiere explorar qué más está conectado con ellas sin necesidad de ejecutar manualmente decenas de consultas en herramientas distintas. El grafo resultante no es, en sí mismo, un análisis: es una representación de relaciones candidatas que el investigador debe examinar, filtrar y valorar.

Sus limitaciones son conocidas. La versión gratuita limita sensiblemente el número de transforms y el volumen de entidades manejables. Algunos transforms requieren licencias de terceros con coste. La automatización del proceso puede generar grafos muy densos y difíciles de interpretar si no se aplica criterio de selección desde el principio. Y, fundamentalmente, Maltego muestra lo que las fuentes conectadas contienen: si las fuentes son incompletas, el grafo será incompleto, sin que ello resulte necesariamente visible. El investigador no debe interpretar la ausencia de resultados como ausencia de relaciones, ni la presencia de resultados como confirmación de vínculos significativos. Maltego propone; el analista decide.

Un error frecuente en el uso de Maltego es ejecutar todos los transforms disponibles sobre todas las entidades, sin criterio previo, y luego tratar de interpretar el grafo resultante. El resultado habitual es un grafo inmanejable con cientos o miles de nodos, del que es difícil extraer conclusiones relevantes. El uso correcto exige disciplina: seleccionar los transforms pertinentes para la hipótesis que se está investigando, filtrar los resultados a medida que se expande, anotar manualmente los vínculos que tienen valor para la investigación y marcar aquellos que son ruido o contexto irrelevante.

### 7.3. i2 Analyst's Notebook

i2 Analyst's Notebook es una plataforma de análisis relacional y visualización desarrollada originalmente por i2 Group, hoy integrada en el ecosistema IBM, ampliamente implantada en entornos policiales, de inteligencia y de análisis de fraude a escala institucional.

A diferencia de Maltego, que está orientado a la expansión automática de entidades desde fuentes externas, i2 Analyst's Notebook es fundamentalmente una herramienta de estructuración, representación y análisis de datos que el investigador introduce manualmente o importa desde fuentes externas. Su fortaleza reside en la capacidad para construir grafos relacionales de alta densidad, representar cronologías de eventos vinculadas al grafo, visualizar flujos de comunicación o económicos, identificar clusters, calcular métricas de red y generar representaciones visuales de alta calidad para documentación y presentación.

En un flujo de trabajo real, i2 Analyst's Notebook suele ser la herramienta en la que el analista monta el análisis definitivo tras haber completado la fase de recolección y correlación inicial. Los datos recogidos con Maltego, con consultas manuales a fuentes abiertas, con análisis de comunicaciones o con información procedente de otras fuentes se importan o introducen en i2 para construir el grafo integrado. El investigador puede entonces añadir entidades de otras fuentes —registros policiales, datos de cooperación, información de investigaciones paralelas— sin mezclar la procedencia de los datos pero sí integrando su representación relacional.

Una de sus funciones más valiosas para la investigación de cibercrimen es la representación de líneas de tiempo vinculadas a entidades: permite visualizar en un mismo espacio tanto la red de actores como la secuencia cronológica de eventos, lo que facilita detectar patrones temporales, solapamientos de actividad o secuencias relevantes. También permite representar flujos económicos, lo que es especialmente útil en investigaciones de fraude, lavado de activos o ransomware.

Su limitación más relevante en el contexto de este manual es que es una herramienta de uso institucional, con licencia comercial no trivial, cuya implantación en unidades policiales depende de decisiones organizativas y presupuestarias. No es una herramienta de acceso individual generalizado. Pero su uso dentro de las unidades que la tienen disponible debe ser conocido y correcto, y a eso va dirigida esta descripción.

El error más frecuente en el uso de i2 en entornos policiales es utilizarlo como herramienta de dibujo en lugar de como herramienta de análisis: construir grafos visualmente elaborados que reflejan hipótesis preconcebidas sin someterlas a contraste, o representar relaciones cuya base empírica es débil sin señalarlo expresamente. El grafo de i2 puede parecer muy convincente visualmente y ser analíticamente muy frágil si los vínculos que lo componen no están suficientemente respaldados.

### 7.4. Gephi

Gephi es una herramienta de análisis y visualización de grafos de código abierto, especialmente útil cuando el investigador necesita aplicar métricas de red sobre grandes conjuntos de entidades y relaciones.

Su fortaleza reside en la capacidad de procesar grafos con miles de nodos y aristas, calcular métricas como centralidad de grado, betweenness centrality, modularidad y detección de comunidades, y producir visualizaciones que permiten identificar visualmente los nodos más relevantes, los clusters naturales y las estructuras de la red. Estas métricas son especialmente útiles cuando el investigador trabaja con datos exportados de plataformas digitales —listas de seguidores y seguidos en redes sociales, registros de comunicaciones, listas de transacciones de blockchain— y quiere identificar actores centrales, intermediarios y comunidades.

El dato de entrada de Gephi es un fichero de grafo en formato GEXF, GraphML, CSV de nodos y aristas u otros formatos estándar. El investigador debe preparar ese fichero previamente, ya sea exportándolo desde otra herramienta, construyéndolo a partir de datos estructurados o convirtiéndolo desde un formato de hoja de cálculo. Gephi no tiene capacidad de recolección de datos: es una herramienta de análisis y visualización de datos ya preparados.

En un flujo de trabajo real, Gephi puede ser útil en varias situaciones. Cuando el investigador ha obtenido datos de una red social mediante scraping o API y quiere analizar la estructura de interacciones de un grupo o comunidad sospechosa: quién tiene más conexiones, quién actúa como puente entre subgrupos, qué cuentas están en el centro de la red y cuáles son periféricas. Cuando trabaja con datos de transacciones de criptomonedas y quiere visualizar el flujo de fondos como grafo para identificar actores centrales o detectar estructuras de mezcla. Cuando ha construido manualmente una matriz de entidades y relaciones y quiere explorar su estructura antes de proceder a un análisis más detallado.

La limitación principal de Gephi para uso investigador es que requiere que el investigador tenga cierta familiaridad con los conceptos básicos de análisis de grafos para interpretar correctamente las métricas que calcula. Una puntuación alta de *betweenness centrality* significa que un nodo es un puente importante entre partes de la red; pero eso no implica necesariamente que sea el actor más relevante desde el punto de vista investigador. La interpretación de los resultados debe hacerse siempre en contexto y con criterio analítico, no mecánicamente.

### 7.5. Herramientas de apoyo a la cronología y a la secuencia de eventos

La dimensión temporal del análisis relacional raramente recibe suficiente atención, pese a que puede ser decisiva para valorar hipótesis. Herramientas como Timeline JS, Timeglider o incluso líneas de tiempo construidas manualmente en herramientas de presentación permiten organizar visualmente la secuencia de aparición de entidades, la cronología de eventos y la relación temporal entre observables. En i2 Analyst's Notebook, la representación cronológica vinculada al grafo es especialmente potente. En Maltego, la fecha de los datos puede exportarse y visualizarse externamente. En cualquier caso, el investigador debe mantener un registro cronológico paralelo al grafo relacional porque ambas dimensiones —estructura y tiempo— son complementarias e igualmente necesarias.

### 7.6. Herramientas de correlación con observables OSINT específicos

Para la correlación de infraestructuras digitales —dominios, IPs, servidores, certificados— herramientas como Shodan, Censys, SecurityTrails, RiskIQ o DomainTools permiten cruzar observables técnicos e identificar infraestructura compartida. Por ejemplo, dos dominios que comparten el mismo servidor de correo, el mismo certificado TLS o el mismo proveedor de alojamiento presentan un vínculo técnico que puede tener relevancia investigadora. Estas herramientas no ofrecen análisis relacional en sentido estricto, pero proporcionan observables de calidad que se pueden integrar en el grafo.

Para la correlación de identidades digitales a través de redes sociales y plataformas, herramientas como Sherlock, WhatsMyName o la búsqueda manual sistemática en plataformas permiten identificar la presencia de un alias en distintos servicios. Cuando un alias aparece en cinco plataformas distintas con el mismo nombre y características similares, eso es un observable relacional que debe documentarse y ponderarse.

Para la correlación de imágenes, las herramientas de búsqueda inversa —Google Lens, TinEye, Yandex Images— permiten detectar reutilización de fotografías de perfil, documentos escaneados o imágenes vinculadas a actividades fraudulentas. La reaparición de la misma imagen en contextos distintos puede ser un vínculo técnico de considerable valor, especialmente en casos de suplantación de identidad o en perfiles de apoyo en redes sociales vinculados a operaciones de ingeniería social.

---

## 8. Uso combinado del análisis relacional en fuentes abiertas y herramientas policiales

El análisis relacional construido a partir de fuentes abiertas no es un producto final: es una entrada de valor para el trabajo policial e institucional. Su función en ese contexto es orientar, focalizar y enriquecer, no sustituir.

Una de las aplicaciones más inmediatas del análisis relacional OSINT en el trabajo policial es la priorización de líneas de investigación. Cuando el investigador ha construido un grafo con varias docenas de entidades y ha identificado los nodos de mayor conectividad, puede decidir con mayor criterio cuáles merecen una comprobación formal mediante bases de datos policiales, registros administrativos o solicitudes de información a terceros. Sin ese análisis previo, la selección de diligencias puede ser aleatoria o excesivamente amplia; con él, puede ser precisa y argumentada.

Las bases de datos policiales y los sistemas de inteligencia institucionales contienen información que no está disponible en fuentes abiertas: antecedentes, identificaciones previas, alertas de cooperación, registros de diligencias anteriores. Cruzar los hallazgos relacionales obtenidos en fuentes abiertas con esas bases permite contrastar hipótesis, confirmar identidades que en OSINT son solo aliases y detectar conexiones que no habrían emergido en un análisis puramente abierto.

La integración debe hacerse de forma explícita y documentada. No basta con que el investigador realice mentalmente la conexión entre lo que ha encontrado en OSINT y lo que figura en las bases internas: debe quedar constancia de que la hipótesis relacional fue formulada a partir de fuentes abiertas, de que fue verificada mediante comprobación interna y de que el resultado de esa verificación, ya sea positivo o negativo, fue incorporado al análisis. Esta trazabilidad es esencial tanto para la calidad del análisis como para su eventual utilización en un procedimiento judicial.

En términos de diligencias formales, el análisis relacional puede también orientar la decisión sobre qué entidades merecen una solicitud de datos a proveedores de servicios de comunicaciones o plataformas digitales, una solicitud de cooperación internacional, una diligencia de entrada y registro dirigida a incautar determinados dispositivos o una petición de medida de investigación tecnológica al órgano jurisdiccional competente. La calidad del análisis previo influye directamente en la precisión de estas solicitudes y, por tanto, en la utilidad de la información que pueden devolver.

La cooperación operativa con otras unidades o con organismos internacionales como Europol, Interpol o la red de unidades especializadas en cibercrimen puede también beneficiarse de un análisis relacional sólido. Compartir no solo datos aislados sino una estructura relacional contextualizada aumenta el valor de la aportación y facilita la comprensión de la investigación por parte de los interlocutores externos.

---

## 9. Interpretación de hallazgos, cautelas y errores frecuentes

El principal riesgo del análisis relacional es la sobreinterpretación. La capacidad del cerebro humano para detectar patrones —y para percibir patrones donde no los hay— es bien conocida. Cuando un investigador lleva tiempo trabajando en una investigación y ha construido mentalmente una hipótesis sobre los actores implicados, existe una tendencia natural a interpretar los nuevos datos de manera que confirmen esa hipótesis. Este sesgo de confirmación es el enemigo número uno del análisis relacional riguroso.

La medida más efectiva contra el sesgo de confirmación es el hábito de formular activamente hipótesis alternativas y buscar observables que las refuten. Para cada relación identificada, el investigador debe preguntarse: ¿puede explicarse este vínculo de otra manera? ¿Existe alguna explicación inocente, técnica o contextual que justifique la conexión sin necesidad de postular una relación investigadora? Si la respuesta es afirmativa, el vínculo debe valorarse con cautela y buscarse respaldo adicional antes de incorporarlo al análisis con nivel de fuerza alto.

Otros errores frecuentes incluyen la confusión entre correlación técnica y relación investigadora. Dos dominios que comparten el mismo proveedor de hosting comercial no están necesariamente vinculados desde el punto de vista de la autoría: pueden compartir esa infraestructura simplemente porque es el proveedor más barato o más accesible. Lo mismo ocurre con el uso de VPNs o proxies comunes, con perfiles en redes sociales que usan la misma plataforma de gestión o con wallets que operan en el mismo exchange. El contexto técnico puede generar coincidencias que no tienen valor investigador.

La confusión entre interacción y pertenencia es otro error habitual. El hecho de que un perfil haya comentado publicaciones de otro, o de que dos usuarios compartan un grupo en Telegram, no implica que pertenezcan a la misma organización ni que colaboren activamente. Estas interacciones pueden tener valor orientativo, pero requieren contraste antes de ser incorporadas al análisis como vínculos de fuerza alta.

La falta de actualización cronológica del análisis es también un problema recurrente. Un análisis relacional construido en un momento determinado puede quedar obsoleto rápidamente si las entidades cambian de estado —cuentas eliminadas, dominios caducados, wallets vaciadas— o si nuevas investigaciones añaden información que modifica el grafo. El análisis relacional debe ser tratado como un documento vivo, que se actualiza a medida que avanza la investigación y que registra los cambios en el estado de cada entidad.

---

## 10. Aspectos jurídicos, deontológicos y probatorios específicos

El análisis relacional en fuentes abiertas se desarrolla, en su mayor parte, a partir de datos que son públicamente accesibles. Sin embargo, la publicidad de un dato no implica que su uso investigador sea ilimitado ni que su procesamiento para la construcción de perfiles relacionales esté exento de consideraciones jurídicas.

El Reglamento General de Protección de Datos y su transposición en el ordenamiento español, así como la normativa específica aplicable al tratamiento de datos personales por las autoridades competentes con fines de prevención, investigación, detección o enjuiciamiento de infracciones penales —regulada en España por la Ley Orgánica 7/2021— establecen un marco de principios que delimita la legitimidad del tratamiento: finalidad, proporcionalidad, minimización de datos, exactitud y limitación del plazo de conservación. El investigador debe tener presente que construir un perfil relacional extenso sobre una persona a partir de datos abiertos puede constituir un tratamiento de datos personales sujeto a ese marco, incluso cuando los datos individuales considerados aisladamente son públicos.

Desde el punto de vista probatorio, el análisis relacional construido a partir de fuentes abiertas tiene naturaleza indiciaria, no acreditativa. Ningún análisis OSINT, por sólido que sea, acredita por sí solo la autoría de un hecho delictivo, la pertenencia a una organización o la participación en una actividad ilícita. Su valor reside en orientar la investigación, formular hipótesis verificables y focalizar las diligencias que sí pueden producir prueba directa o semidirecta. Confundir el valor indiciario con el valor probatorio es un error metodológico grave que puede comprometer la calidad de la investigación y, eventualmente, la validez de la actuación policial.

La documentación del proceso de análisis no solo es una buena práctica: es una exigencia metodológica y, en ciertos contextos, una necesidad de cara a la defensa de las actuaciones en sede judicial. El investigador debe ser capaz de explicar, en términos comprensibles y verificables, por qué estableció cada vínculo, qué observable lo sustenta, qué nivel de fuerza le asignó y qué conclusiones extrae de él. La opacidad metodológica no es sostenible en un análisis que puede tener consecuencias sobre derechos fundamentales.

---

## 11. Caso práctico aplicado

### Caso práctico: Entramado de identidades reutilizadas en una campaña de inversión fraudulenta

**Supuesto de hecho.**

La unidad recibe una denuncia por inversión fraudulenta. La víctima fue contactada mediante un perfil de LinkedIn que ofrecía asesoría financiera, invirtió fondos a través de una plataforma web de aspecto profesional y, tras un período de aparente rentabilidad, fue instada a realizar pagos adicionales. La plataforma dejó de ser accesible y los contactos cesaron. El importe defraudado supera los treinta mil euros.

**Dato o indicio de partida.**

La víctima proporciona el dominio de la plataforma fraudulenta, el correo de contacto con el que se comunicó con el supuesto asesor y el nombre del perfil de LinkedIn que la captó. La plataforma ya no responde, pero el dominio sigue siendo resoluble.

**Hipótesis de trabajo.**

La plataforma fraudulenta no es un caso aislado, sino parte de un conjunto de activos operados por los mismos actores o el mismo grupo, que probablemente reutilizan infraestructura, correos o aliases en distintos esquemas o víctimas.

**Actuaciones realizadas.**

El investigador parte del dominio y ejecuta un análisis WHOIS que devuelve una dirección de correo de registro. Esa dirección se introduce en Maltego como entidad semilla. Los transforms revelan que el mismo correo figura como contacto en otros dos dominios registrados en el mismo período, con un patrón de nomenclatura similar. Los tres dominios comparten bloque de IP y servidor de alojamiento.

Se amplía la consulta a SecurityTrails para revisar el historial de registros DNS de los tres dominios. Uno de ellos, ya caducado, aparece vinculado en una búsqueda de Google a un hilo de un foro de alertas de fraude donde varios usuarios describen un esquema idéntico al relatado por la víctima. En ese hilo aparece un alias que también ha sido empleado en otro foro especializado, esta vez como vendedor de cuentas en una plataforma de pagos.

El alias se introduce en Maltego y en herramientas de búsqueda de usernames. Se identifica el mismo alias en cuatro plataformas distintas: dos foros de inversión, una plataforma de mensajería y un marketplace de segunda mano. Los perfiles presentan características similares: fotos de perfil distintas pero con rasgos de generación artificial, actividad concentrada en períodos específicos y ausencia de historia anterior.

La búsqueda inversa de imagen sobre la foto de perfil del LinkedIn que captó a la víctima devuelve coincidencias en otros dos perfiles de LinkedIn con distinto nombre pero actividad similar, registrados en fechas próximas. Los tres perfiles dirigen a la misma plataforma o a plataformas con el mismo patrón visual.

La wallet de criptomonedas facilitada por la plataforma para recibir fondos se analiza con herramientas de análisis de blockchain públicas. Las transacciones revelan movimientos hacia una segunda wallet que ha recibido fondos de otras direcciones identificadas en denuncias previas registradas en el sistema policial.

Todo el análisis se monta en i2 Analyst's Notebook, integrando las entidades de fuentes abiertas con la información procedente del sistema policial. El grafo resultante muestra tres clusters interconectados: infraestructura de dominios y correos, identidades digitales y aliases, y flujos de fondos. El nodo que conecta los tres clusters es la dirección de correo de registro inicial.

**Hallazgos obtenidos.**

Tres dominios con infraestructura compartida, dos correos adicionales relacionados, cinco aliases con presencia en foros de fraude e inversión, seis perfiles de LinkedIn aparentemente falsos con patrón común, una wallet de recepción vinculada a otra con historial de fraude conocido, y un patrón de actividad cronológicamente coherente que sugiere ciclos de operación de entre cuatro y ocho semanas por plataforma.

**Análisis e interpretación.**

La convergencia de observables de naturaleza distinta —técnica, contextual, económica y visual— apunta a una estructura de operación coordinada. La reutilización de infraestructura, la uniformidad del patrón de actividad y la conexión a través de flujos económicos refuerzan la hipótesis de que no se trata de un actor único sino de un esquema con cierto grado de organización. Sin embargo, el análisis en fuentes abiertas no permite atribuir autoría ni confirmar si se trata de un solo operador con múltiples perfiles o de un grupo con distribución de roles. Esa determinación requiere diligencias formales.

**Explotación policial y documental.**

El análisis relacional construido en i2 se utiliza como base para solicitar al órgano jurisdiccional medidas de investigación tecnológica sobre los tres dominios identificados, dirigidas a obtener datos de registro e información de los titulares reales de los contratos de alojamiento. Se elabora también una solicitud de cooperación internacional a través del canal Europol para contrastar si los aliases identificados aparecen en investigaciones similares en otros estados miembros. La wallet con historial conocido se remite a la unidad de análisis de criptoactivos para seguimiento extendido. El caso práctico completo se documenta como atestado con anexo técnico que incluye la metodología del análisis, las fuentes consultadas, los observables obtenidos y el grafo relacional como material gráfico de soporte.

**Lecciones operativas.**

El análisis relacional permitió transformar una denuncia aislada en la identificación de una infraestructura más amplia, posiblemente responsable de víctimas adicionales aún no denunciadas. La clave fue la disciplina en la documentación inicial, la búsqueda activa de convergencia entre observables de distinta naturaleza y la integración del análisis abierto con información procedente del sistema policial. El grafo relacional no fue un adorno visual: fue el instrumento que permitió comprender la estructura y formular solicitudes de diligencias precisas y argumentadas.

---

## 12. Conclusiones operativas

La correlación de entidades y el análisis relacional constituyen una de las fases más exigentes y, al mismo tiempo, más productivas de la investigación OSINT aplicada al cibercrimen. Su valor reside en la capacidad de transformar observables dispersos en estructuras comprensibles, de pasar del dato al patrón y de orientar el trabajo investigador con criterio y precisión.

Pero ese valor solo se materializa cuando el análisis se realiza con método. La calidad del dato de partida, la correcta clasificación de entidades, la valoración honesta de la fuerza de cada vínculo, la búsqueda activa de convergencia y la resistencia al sesgo de confirmación son los pilares sobre los que descansa un análisis relacional sólido. Las herramientas disponibles —Maltego, i2 Analyst's Notebook, Gephi y otras— pueden amplificar enormemente esas capacidades, pero no pueden suplir su ausencia.

El investigador debe terminar este capítulo con la convicción de que correlacionar bien no es encontrar todo lo que se puede encontrar, sino entender qué significa lo que se ha encontrado, ser capaz de explicarlo con rigor y saber cuándo es suficiente para orientar una diligencia formal y cuándo no lo es. La prudencia analítica no es timidez investigadora: es la condición de posibilidad de un análisis que pueda sostenerse, comunicarse y defenderse.

---

## 13. Checklist final de trabajo

**Identificación y registro de entidades**

- Todas las entidades han sido identificadas, clasificadas por tipo y registradas con referencia a su observable de soporte.
- Se ha documentado la fuente, la fecha y el método de obtención de cada observable.
- Las entidades con incertidumbre de identificación han sido marcadas expresamente como tales.

**Análisis de relaciones**

- Se han identificado las relaciones directas entre entidades con soporte observable verificado.
- Se han identificado las relaciones indirectas y los patrones emergentes.
- Cada vínculo ha sido clasificado por tipo de relación y valorado por nivel de fuerza.
- Se han buscado activamente hipótesis alternativas y posibles explicaciones inocentes para cada vínculo.

**Cronología y convergencia**

- Se ha construido o verificado una línea de tiempo de los observables principales.
- Se ha analizado si la cronología refuerza o debilita las hipótesis relacionales.
- Se ha verificado si existen convergencias entre observables de distinta naturaleza que apunten en la misma dirección.

**Herramientas y visualización**

- Las herramientas empleadas han sido seleccionadas en función de la hipótesis investigadora, no de manera indiscriminada.
- El grafo o la representación visual construida refleja únicamente relaciones con soporte empírico.
- Los resultados obtenidos por herramientas automáticas han sido revisados y filtrados con criterio analítico.

**Documentación del análisis**

- El proceso de análisis ha sido documentado de forma que permita reconstruir el razonamiento, no solo el resultado.
- Las fuentes, los métodos y los niveles de fuerza asignados a cada vínculo constan explícitamente.
- Los vínculos descartados y las hipótesis refutadas han sido también registrados con su justificación.

**Integración con capacidades policiales**

- Los nodos o entidades que merecen comprobación formal han sido identificados y priorizados.
- Los hallazgos han sido contrastados con bases de datos policiales o sistemas de inteligencia disponibles cuando ha sido pertinente.
- Las diligencias formales propuestas están argumentadas en el análisis relacional previo.

**Cautelas interpretativas**

- No se han formulado conclusiones de autoría o pertenencia que excedan lo que los observables permiten sostener.
- El análisis está redactado en términos que distinguen claramente entre certeza, hipótesis fundada e indicios orientativos.
- El análisis relacional está presentado como fundamento de nuevas diligencias, no como prueba en sí mismo.