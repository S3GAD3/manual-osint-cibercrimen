# Capítulo 15. Automatización, IA y gestión del conocimiento OSINT aplicada al cibercrimen

## 1. Introducción

La investigación de cibercrimen genera volúmenes de información que ningún investigador puede procesar manualmente con eficiencia sostenida. Una sola investigación por estafa masiva puede involucrar cientos de direcciones de correo electrónico, decenas de dominios, múltiples alias, registros de pasarelas de pago, perfiles en plataformas de terceros, capturas de pantalla, metadatos, denuncias cruzadas y documentación bancaria dispersa. Si a eso se añade la exigencia de producir diligencias, oficios, matrices relacionales y notas internas, el coste cognitivo del trabajo tiende a sobrepasar la capacidad de cualquier equipo pequeño.

En este contexto, la automatización de tareas repetitivas, el uso de modelos de lenguaje como apoyo analítico y la construcción de sistemas organizados de gestión del conocimiento no representan una tendencia tecnológica que haya que seguir, sino una respuesta práctica y necesaria a un problema real. No se trata de incorporar herramientas por modernidad, sino de resolver con mayor eficiencia problemas concretos que aparecen todos los días en la práctica investigadora: normalizar datos de distintas fuentes, identificar si una entidad ya ha sido investigada, resumir grandes volúmenes de texto, redactar un primer borrador de nota analítica, localizar una conexión entre casos anteriores o recuperar una metodología que funcionó.

Sin embargo, la automatización sin método genera un problema distinto: ruido, falsas correlaciones, pérdida de contexto y dependencia acrítica de resultados que ningún profesional ha validado. La inteligencia artificial, en particular los modelos de lenguaje, puede producir resúmenes incorrectos, extraer entidades con errores, generar cronologías inconsistentes o proporcionar respuestas plausibles pero falsas. Utilizar estas herramientas sin supervisión activa, sin trazabilidad y sin criterio metodológico equivale a introducir un factor de error sistemático en la investigación.

Este capítulo parte de esa doble realidad para desarrollar una propuesta profesional, aplicada y controlada: cómo integrar automatización, modelos de lenguaje y gestión del conocimiento en una investigación OSINT de cibercrimen de forma que refuercen el criterio del investigador, no que lo sustituyan.

## 2. Finalidad investigadora del capítulo

Este capítulo cumple una función específica dentro del manual: trasladar al lector de la pregunta "¿puede la IA ayudarme en mi trabajo?" a la pregunta "¿cómo la integro de forma útil, controlada y metodológicamente sólida en mi flujo de trabajo cotidiano?". No es un capítulo de introducción a la inteligencia artificial ni un catálogo de herramientas. Es un capítulo de metodología aplicada.

El investigador de cibercrimen que trabaja en una unidad de policía judicial necesita, fundamentalmente, trabajar mejor y más rápido sin perder control sobre lo que hace. La automatización le permite externalizar en máquinas las tareas que no requieren juicio analítico. La IA le permite tratar en segundos volúmenes de texto que le llevarían horas. La gestión del conocimiento le permite no redescubrir lo que ya ha investigado y construir sobre el trabajo acumulado. Ninguna de las tres cosas tiene valor si no está integrada en un método profesional.

El cibercrimen, además, tiene características que hacen especialmente necesaria esta integración: los delitos se cometen a escala, los actores utilizan múltiples identidades y plataformas, las evidencias son volátiles y dispersas, los casos se repiten con variaciones mínimas y el conocimiento acumulado en una investigación es directamente aplicable a otras. Un sistema bien construido de automatización y gestión del conocimiento puede marcar una diferencia operativa real.

## 3. Objeto de análisis y punto de partida

Para el propósito de este capítulo, tres conceptos funcionan de forma complementaria y deben diferenciarse con precisión antes de desarrollarlos.

La **automatización útil** consiste en trasladar a un proceso mecánico, repetible y predecible aquellas tareas del flujo investigador que no requieren interpretación contextual. Normalizar el formato de una lista de correos electrónicos, extraer dominios de una colección de URLs, convertir un conjunto de fechas a un formato estandarizado, buscar un identificador en múltiples fuentes abiertas siguiendo una secuencia fija o generar una cronología provisional a partir de un registro estructurado son tareas automatizables porque su lógica es estable y su resultado verificable.

La **IA de apoyo analítico** hace referencia al uso de modelos de lenguaje, ya sean accesibles en línea o desplegados localmente, para asistir al investigador en tareas que requieren procesamiento de lenguaje natural: resumir textos, extraer entidades nombradas, comparar dos perfiles escritos, clasificar mensajes por tipología, reformular un hallazgo en lenguaje formal o redactar un primer borrador de nota analítica. Estas tareas no son puramente mecánicas, pero tampoco exigen el nivel de juicio que corresponde al investigador. Son tareas de apoyo cuyo resultado siempre debe revisarse.

La **gestión del conocimiento investigador** es el conjunto de prácticas, estructuras y herramientas que permiten al investigador y a su equipo retener, organizar, recuperar y explotar el conocimiento acumulado: entidades, relaciones, metodologías, hallazgos, fuentes, plantillas, cronologías y productos analíticos anteriores. Una investigación bien documentada internamente vale mucho más que la misma investigación sin estructura, porque permite enlazar casos, retomar trabajo anterior, formar a nuevos investigadores y producir informes con menor coste operativo.

Estos tres elementos se combinan de forma natural en el trabajo del investigador que ha alcanzado cierto nivel de madurez metodológica. El reto no es aprender a usar herramientas concretas, sino construir un flujo de trabajo coherente que los integre con control.

## 4. La automatización y la IA como apoyo al método investigador

El error más frecuente al introducir automatización o IA en una investigación es tratarla como un sustituto del juicio analítico. La automatización no investiga: ejecuta. La IA no concluye: procesa lenguaje y devuelve texto estadísticamente probable. El investigador es quien interpreta, quien contrasta, quien valida y quien decide. Esta distinción no es retórica: es metodológica y tiene consecuencias directas sobre la calidad, la validez y la utilidad del trabajo.

La automatización reduce la carga repetitiva. Cuando un investigador dedica tres horas a normalizar manualmente una lista de miles de correos electrónicos procedentes de múltiples fuentes en formatos distintos, ese tiempo no está disponible para el análisis. Si esa normalización puede realizarse mediante un proceso automatizado en minutos, el investigador recupera tiempo analítico. Lo mismo aplica a la búsqueda sistemática de un conjunto de identificadores en fuentes abiertas, a la generación de una cronología provisional a partir de registros ordenados por fecha o a la agrupación de hallazgos por categorías predefinidas.

Los modelos de lenguaje añaden una dimensión diferente. No solo ejecutan procesos repetitivos, sino que pueden procesar grandes volúmenes de texto y producir síntesis, extracciones o clasificaciones. Un investigador que tiene ante sí cincuenta páginas de intercambios de mensajes de una plataforma de comunicación puede pedirle a un modelo que identifique las entidades nombradas, que agrupe los mensajes por tema, que resuma los puntos clave o que detecte incoherencias internas. El resultado no es una conclusión investigadora: es un material de trabajo que el investigador revisa, corrige y utiliza como punto de partida.

Hay, sin embargo, tareas que no deben delegarse a la automatización ni a la IA. La valoración de la credibilidad de una fuente, la interpretación de un patrón de comportamiento en el contexto de un caso concreto, la decisión sobre qué líneas de investigación priorizar, la elaboración de un informe con valor probatorio o la formulación de hipótesis sobre la identidad de un sospechoso son tareas que exigen juicio humano, contexto acumulado y responsabilidad profesional. Delegarlas en un proceso automático o en un modelo de lenguaje no solo es metodológicamente incorrecto: puede tener consecuencias sobre la validez de la investigación y sobre la protección de derechos fundamentales.

El investigador debe, por tanto, desarrollar la capacidad de identificar qué tipo de tarea tiene delante antes de decidir cómo abordarla. Esa clasificación previa es la base de un uso eficiente y controlado de la automatización y la IA.

## 5. Análisis inicial de tareas, procesos y necesidades de organización del conocimiento

Antes de introducir ninguna herramienta de automatización o modelo de IA en un flujo investigador, es necesario hacer un análisis inicial de las propias tareas. Esto no requiere semanas de preparación: basta con revisar de forma sistemática qué hace el investigador y con qué frecuencia.

Las preguntas clave son las siguientes. ¿Hay tareas que el investigador repite en casi todas las investigaciones? ¿Hay procesos que siempre siguen la misma secuencia? ¿Hay tipos de información que siempre necesita en el mismo formato? ¿Hay conocimiento acumulado en investigaciones anteriores que podría reutilizarse? ¿Hay pasos que consumen mucho tiempo sin añadir valor analítico? ¿Hay información que se pierde porque no existe una estructura que la retenga?

Las tareas que más habitualmente son automatizables en OSINT de cibercrimen incluyen la normalización de formatos de datos, la extracción de indicadores de compromiso desde bloques de texto, la búsqueda de un conjunto de identificadores en fuentes abiertas, la generación de estructuras de cronología provisional, la detección de duplicados o entidades repetidas en un conjunto de datos, la clasificación inicial de hallazgos por tipo o categoría y la preparación de plantillas de documentación.

Las tareas que no son automatizables o cuya automatización sin supervisión es inapropiada incluyen la valoración de relevancia de un hallazgo para la hipótesis de trabajo, la determinación del valor probatorio de una evidencia, la interpretación de relaciones entre actores, la formulación de líneas de investigación, la redacción de diligencias con valor oficial, la comunicación con autoridades y la adopción de decisiones sobre el curso de la investigación.

Respecto a la organización del conocimiento, el análisis inicial debe identificar qué tipos de entidades aparecen repetidamente en las investigaciones del equipo, qué tipos de relaciones son relevantes, qué tipo de productos documentales se generan, qué metodologías han funcionado, qué fuentes han resultado útiles y cómo se estructura internamente el conocimiento de cada caso. Esta información permite diseñar una arquitectura de gestión del conocimiento adaptada al trabajo real, no a un modelo genérico.

## 6. Flujo de trabajo del investigador en un sistema híbrido humano + automatización + IA

Este es el núcleo operativo del capítulo. Lo que se describe a continuación es una secuencia profesional de trabajo que puede adaptarse a distintos casos y contextos, pero que refleja los principios de control, trazabilidad y eficiencia que deben guiar cualquier integración de automatización e IA en la investigación OSINT.

### Fase 1: Recepción y caracterización inicial del caso

Antes de aplicar ninguna herramienta, el investigador lee el material inicial, identifica los datos disponibles y formula una hipótesis de trabajo provisional. En esta fase no hay automatización ni IA. El investigador debe entender qué tiene, qué le falta y qué quiere comprobar. Esta fase es completamente humana y no delegable.

### Fase 2: Estructuración de los datos de partida

Los datos brutos que llegan al investigador rara vez están en un formato homogéneo. Pueden ser documentos PDF, capturas de pantalla, listados de correos, volcados de mensajes, hojas de cálculo con datos bancarios o registros extraídos de plataformas. La automatización puede intervenir aquí de forma significativa: convertir formatos, extraer texto de documentos, normalizar columnas, eliminar duplicados, separar campos. Este trabajo puede hacerse con herramientas de *scripting* básico, flujos automatizados o entornos de proceso de datos. El resultado es una colección ordenada de datos sobre la que trabajar.

### Fase 3: Extracción inicial de entidades y relaciones

Con los datos estructurados, el investigador puede usar un modelo de lenguaje para hacer una primera pasada de extracción: identificar personas, organizaciones, dominios, números de teléfono, direcciones de correo, monederos de criptomonedas, fechas relevantes y relaciones aparentes entre ellos. El modelo produce un listado provisional. El investigador lo revisa, corrige errores de extracción, elimina entidades irrelevantes y valida las relaciones identificadas. Este resultado va al sistema de gestión del conocimiento del caso.

### Fase 4: Búsqueda asistida y enriquecimiento

A partir de las entidades validadas, el investigador puede lanzar búsquedas en fuentes abiertas de forma sistemática. En esta fase, la automatización puede ayudar a ejecutar búsquedas repetitivas sobre múltiples fuentes siguiendo una secuencia estándar. El modelo de lenguaje puede ayudar a resumir los resultados obtenidos por fuente o a identificar patrones en el conjunto. El investigador supervisa los resultados, descarta lo irrelevante y registra los hallazgos significativos.

### Fase 5: Comparación y cruce con conocimiento previo

El investigador consulta su base de conocimiento para comprobar si alguna entidad ya ha aparecido en investigaciones anteriores, si un dominio ya fue registrado, si un alias es conocido o si una metodología fue utilizada en otro caso. Esta consulta puede hacerse manualmente o mediante búsqueda asistida dentro del sistema de conocimiento propio. Si se trabaja con un sistema de búsqueda sobre documentación propia, el modelo puede ayudar a formular consultas y a recuperar información relevante de notas anteriores.

### Fase 6: Elaboración de cronología y mapa relacional provisional

Con los hallazgos del caso organizados, el investigador puede generar una cronología provisional y un primer mapa relacional. La automatización puede ayudar a ordenar los eventos por fecha y agrupar los que afectan a una misma entidad. El modelo puede ayudar a producir un borrador textual de la cronología. El investigador revisa, corrige y completa lo que falta. Este producto no tiene valor probatorio por sí mismo: es una herramienta de trabajo interno.

### Fase 7: Síntesis analítica y formulación de hipótesis

El investigador, a partir de los hallazgos verificados, las entidades cruzadas, la cronología y el mapa relacional, elabora su análisis. El modelo de lenguaje puede ayudar a redactar un primer borrador de nota analítica o a estructurar los argumentos. El investigador reescribe, añade contexto, elimina lo que el modelo ha malinterpretado y produce la versión final. Esta versión es suya y lo refleja: la IA fue una herramienta de apoyo, no el autor del análisis.

### Fase 8: Producción documental

Los hallazgos y el análisis se trasladan a los productos documentales adecuados: nota interna, matriz relacional, diligencia de investigación, oficio a otra unidad o borrador de atestado. La IA puede ayudar en la redacción de borradores, especialmente para secciones repetitivas o de estructura conocida. El investigador revisa, adapta al estilo formal requerido y firma lo que produce. Ningún documento oficial puede atribuirse a la IA.

### Fase 9: Registro en el sistema de gestión del conocimiento

Una vez cerrada una fase o un caso, el investigador registra en su base de conocimiento las entidades nuevas, las relaciones confirmadas, las metodologías empleadas, los resultados obtenidos y las fuentes consultadas. Este paso, que tiende a omitirse por presión de tiempo, es el que garantiza que el trabajo realizado tenga valor acumulativo y pueda ser recuperado y reutilizado.

### Fase 10: Trazabilidad y documentación del proceso

El investigador debe dejar constancia de qué tareas fueron asistidas por automatización o IA, con qué herramienta, qué tipo de supervisión se ejerció y qué modificaciones se realizaron sobre los resultados automáticos. Esta trazabilidad tiene valor metodológico, deontológico y, llegado el caso, procesal.

## 7. Herramientas, recursos y enfoques prácticos para automatización, IA y gestión del conocimiento

### 7.1. Automatización básica y flujos repetitivos

Las tareas repetitivas del investigador pueden gestionarse con herramientas de *scripting* sencillo o entornos de automatización de flujos. No es necesario ser programador para aprovechar estas capacidades: muchas de ellas están disponibles en entornos de bajo código o sin código.

Python es el lenguaje más útil para el investigador OSINT que quiere automatizar tareas. Permite procesar listas de datos, hacer llamadas a APIs abiertas, normalizar formatos, extraer texto de documentos y generar informes estructurados. Un script sencillo que tome una lista de correos y compruebe el dominio en registros DNS puede ahorrar horas de trabajo manual. El investigador no necesita dominar Python a nivel avanzado: bastan nociones suficientes para modificar y adaptar scripts ya escritos.

Las hojas de cálculo avanzadas, con fórmulas, macros y funciones de limpieza de datos, siguen siendo herramientas de automatización básica extremadamente útiles para la normalización, el agrupamiento y la comparación de datos estructurados. Su ventaja es que no requieren conocimientos técnicos especializados y permiten trabajar con datos tabulares de forma rápida y visual.

En cuanto a las limitaciones de esta capa de automatización, el error más frecuente es construir procesos frágiles que funcionan bien con un tipo de entrada pero fallan cuando los datos tienen un formato distinto. Cualquier proceso automatizado debe ser validado antes de su uso regular con distintos tipos de datos reales.

### 7.2. Extracción, clasificación y estructuración de datos

La extracción automática de entidades nombradas es una de las aplicaciones más valiosas para el investigador OSINT. Existen herramientas y bibliotecas especializadas en reconocimiento de entidades nombradas en texto en castellano e inglés que permiten identificar automáticamente personas, organizaciones, lugares, fechas y elementos de otro tipo en bloques de texto extensos.

Para la extracción de indicadores de compromiso desde bloques de texto, existen herramientas específicas que identifican automáticamente IPs, dominios, *hashes*, correos electrónicos, URLs y otros patrones propios del análisis de cibercrimen. Estas herramientas son valiosas para procesar rápidamente informes de inteligencia de amenazas o volcados de comunicaciones.

La limitación principal de la extracción automática es la precisión. Los sistemas cometen errores tanto por defecto —dejando pasar entidades relevantes— como por exceso —extrayendo elementos que no son relevantes en el contexto del caso—. La revisión humana del resultado es obligatoria.

### 7.3. IA generativa y apoyo analítico: modelos de lenguaje

Los modelos de lenguaje grandes son herramientas de apoyo analítico con un potencial significativo para el investigador OSINT, siempre que se utilicen dentro de un marco metodológico claro. Sus aplicaciones prácticas más útiles en investigación de cibercrimen incluyen las siguientes.

La síntesis de textos extensos permite al investigador obtener un resumen estructurado de un conjunto de mensajes, un informe largo o una serie de documentos. El modelo produce un texto que reduce el tiempo de lectura inicial. El investigador verifica que el resumen no omite elementos relevantes y que no introduce distorsiones.

La extracción de entidades y relaciones en lenguaje natural es útil cuando el texto no tiene estructura formal. El investigador puede pedirle al modelo que identifique personas, organizaciones, fechas y relaciones en un bloque de texto conversacional. El resultado es una extracción provisional que debe validarse.

La comparación de textos o perfiles permite al investigador pedirle al modelo que compare dos conjuntos de mensajes o dos perfiles escritos e identifique similitudes de estilo, vocabulario o contenido. Esta comparación no tiene valor pericial, pero puede orientar líneas de investigación.

La redacción de borradores es útil para generar una primera versión de una nota analítica, un resumen de hallazgos o la sección descriptiva de un informe. El investigador proporciona los datos y el contexto, y el modelo produce un borrador que el investigador revisa, reescribe y adapta.

La priorización asistida permite pedirle al modelo que, dado un conjunto de hallazgos y una hipótesis de trabajo, sugiera qué líneas de investigación parecen más prometedoras. Esta sugerencia no sustituye el criterio del investigador, pero puede ayudar a estructurar el pensamiento o a identificar elementos que se habían pasado por alto.

### 7.4. Ollama y modelos locales de lenguaje

Ollama es una plataforma que permite desplegar y ejecutar modelos de lenguaje grandes de forma completamente local, sobre el hardware del propio equipo, sin conexión a servidores externos. Para el investigador policial, esto tiene un valor fundamental: permite utilizar la capacidad analítica de los modelos de lenguaje sin transmitir ningún dato a terceros.

En el contexto de una investigación policial, los datos con los que trabaja el investigador incluyen frecuentemente información personal de víctimas y sospechosos, datos bancarios, comunicaciones privadas, identificadores digitales y material obtenido en el ejercicio de diligencias con restricción de acceso. Subir este tipo de información a servicios en la nube, plataformas de IA accesibles públicamente o servidores externos de terceros está expresamente prohibido por la normativa de protección de datos, en particular el Reglamento General de Protección de Datos y la Ley Orgánica 7/2021 de protección de datos personales tratados para fines de prevención, detección, investigación y enjuiciamiento de infracciones penales. Cualquier tratamiento de datos personales protegidos debe realizarse en entornos controlados y bajo el amparo de la base jurídica adecuada.

Un modelo local desplegado con Ollama opera completamente en el dispositivo del investigador. No hay transferencia de datos. No hay registro de consultas en servidores externos. No hay exposición de información sensible fuera del entorno de trabajo. Esta arquitectura hace que los modelos locales sean la única opción admisible cuando se trabaja con datos personales, materiales de investigación en curso o información clasificada.

El funcionamiento práctico de Ollama es accesible para usuarios sin formación técnica avanzada: se instala sobre el sistema operativo del equipo, se descarga un modelo de lenguaje compatible y se accede a él mediante una interfaz de línea de comandos o a través de una interfaz gráfica que puede añadirse por separado. Existen modelos de distintos tamaños y capacidades que pueden ejecutarse en equipos con hardware moderado, aunque la calidad del resultado mejora con hardware más potente.

Los modelos locales disponibles a través de esta plataforma incluyen variantes de distintas familias con capacidades diferenciadas: algunos están optimizados para síntesis de texto, otros para razonamiento, otros para instrucción y respuesta. El investigador debe seleccionar el modelo adecuado en función de la tarea y verificar su rendimiento con datos propios antes de integrarlo en su flujo de trabajo.

La limitación principal de los modelos locales frente a los modelos en la nube es la capacidad computacional: los modelos más potentes requieren hardware especializado. Sin embargo, para las tareas de apoyo analítico descritas en este capítulo —síntesis, extracción, comparación, clasificación, borrador de redacción— modelos de tamaño moderado ofrecen resultados suficientemente útiles en equipos de trabajo convencionales.

### 7.5. Sistemas RAG y búsqueda sobre conocimiento propio

Un sistema RAG (*Retrieval-Augmented Generation*) es un enfoque que combina un modelo de lenguaje con una base de documentos propia. Cuando el investigador hace una consulta, el sistema busca primero en sus propios documentos los fragmentos más relevantes y se los proporciona al modelo como contexto antes de que genere la respuesta. El resultado es que el modelo responde basándose en el conocimiento del investigador, no solo en su entrenamiento general.

Para el investigador OSINT, esto tiene un valor práctico muy concreto. Imaginemos que tiene una base de documentos con notas de casos anteriores, informes analíticos, registros de entidades, cronologías y metodologías documentadas. Un sistema RAG le permite hacer consultas en lenguaje natural sobre esa base: "¿ha aparecido este dominio antes?", "¿qué metodología usamos en el caso de fraude de inversión del año pasado?", "¿hay algún alias parecido a este en casos anteriores?". El sistema recupera los fragmentos relevantes y el modelo produce una respuesta contextualizada.

Este tipo de sistema puede desplegarse completamente en local utilizando Ollama como motor de lenguaje y herramientas de indexación de documentos de código abierto como la suite que ofrece AnythingLLM, que permite construir una base de conocimiento sobre documentos propios con interfaz gráfica y sin necesidad de programación avanzada. Esta combinación, Ollama más AnythingLLM sobre infraestructura local controlada, es especialmente adecuada para unidades de cibercrimen que necesitan trabajar con datos sensibles en entornos sin conexión exterior o con acceso restringido.

La limitación principal de estos sistemas es la calidad de la base de conocimiento: si los documentos no están bien estructurados, no tienen buena cobertura o no han sido actualizados, el sistema devolverá resultados de baja calidad. La inversión en documentar bien el propio trabajo es la que determina la utilidad de estas herramientas.

### 7.6. Obsidian como herramienta de gestión del conocimiento investigador

Obsidian es una aplicación de gestión del conocimiento basada en notas en formato Markdown enlazadas entre sí. Su arquitectura es especialmente adecuada para el investigador OSINT porque permite construir una base de conocimiento vinculada donde cada entidad, caso, metodología o hallazgo es una nota que puede enlazarse con otras.

En el contexto de una investigación de cibercrimen, Obsidian permite al investigador crear una nota por cada entidad relevante (persona, dominio, alias, organización, número de teléfono), una nota por cada caso activo o cerrado, una nota por cada metodología documentada, una nota por cada fuente habitual y una nota por cada producto analítico generado. Los enlaces entre notas crean automáticamente un grafo de relaciones visible que puede explorarse visualmente.

La funcionalidad de búsqueda de Obsidian permite localizar cualquier término en toda la base de conocimiento. Los sistemas de etiquetado permiten agrupar notas por tipo, estado o relevancia. La posibilidad de crear plantillas asegura que la documentación de nuevos casos siga siempre la misma estructura, lo que facilita la recuperación de información y la comparabilidad entre casos.

Una base de conocimiento bien mantenida en Obsidian puede convertirse en la memoria institucional de una unidad investigadora: recoge lo que se ha aprendido, cómo se investigó, qué funcionó, qué no y qué entidades o patrones se han repetido a lo largo del tiempo. Si varios investigadores de la misma unidad trabajan sobre la misma base (posible mediante repositorios compartidos en sistemas controlados), el conocimiento se vuelve colectivo.

La limitación de Obsidian es que requiere disciplina de uso: su valor es directamente proporcional a la regularidad con la que el investigador documenta su trabajo. Una base de conocimiento desactualizada o fragmentaria pierde gran parte de su utilidad.

### 7.7. Plantillas y estructuras reutilizables

Las plantillas son una forma sencilla y poderosa de automatización documental. Una plantilla de documentación de caso, de perfil de entidad, de análisis de dominio, de cronología de hechos o de nota analítica permite al investigador estructurar rápidamente su trabajo sin partir de cero cada vez.

Las plantillas deben incluir los campos y secciones que se necesitan de forma sistemática, sin exceso ni defecto. Deben adaptarse al tipo de caso, al tipo de entidad o al tipo de producto documental. Y deben mantenerse actualizadas conforme el equipo aprende qué información es realmente necesaria.

## 8. Uso combinado de automatización, IA, conocimiento estructurado y herramientas policiales

La automatización y la IA no operan en un vacío. En el trabajo real de una unidad de cibercrimen, los productos generados con estas herramientas deben integrarse con los sistemas, procedimientos y herramientas institucionales propias de la policía judicial.

La automatización puede preparar y ordenar el trabajo previo a las diligencias formales. Cuando el investigador necesita solicitar información a una operadora, a una entidad financiera o a una plataforma tecnológica, llega a ese momento con mayor eficiencia si sus datos están ya normalizados, sus entidades identificadas y su hipótesis estructurada. La calidad de una solicitud formal mejora cuando el investigador tiene claro qué pide y por qué.

La IA puede ayudar a sintetizar y a comparar la información obtenida a través de canales institucionales, pero no puede validar esa información ni puede sustituir el criterio del investigador sobre qué tiene valor probatorio y qué no. El análisis que se incorpora a un atestado es responsabilidad del investigador, no del modelo.

El conocimiento organizado facilita la coordinación entre investigadores de la misma unidad y entre unidades distintas. Cuando la documentación de un caso está bien estructurada, un investigador que se incorpora al equipo o que recibe el caso puede situarse rápidamente. Cuando las metodologías están documentadas, un nuevo miembro del equipo puede aplicarlas sin partir de cero. Cuando los hallazgos están registrados con trazabilidad, pueden aportarse como antecedentes en diligencias posteriores.

Los productos generados con apoyo de automatización o IA deben etiquetarse internamente como tales. En una nota analítica, debe quedar claro qué partes fueron generadas con apoyo de un modelo y qué partes son elaboración del investigador. Esta distinción no tiene por qué aparecer en el documento final oficial, pero debe constar en la trazabilidad interna del proceso de investigación.

La integración con sistemas policiales internos implica también respetar los flujos de aprobación, clasificación y distribución de documentos establecidos institucionalmente. Ningún producto analítico generado con apoyo de IA tiene valor oficial hasta que el investigador responsable lo ha revisado, modificado en lo necesario, firmado y tramitado conforme al procedimiento establecido.

## 9. Interpretación de resultados, cautelas y errores frecuentes

Los resultados generados por automatización o por modelos de lenguaje no son verdades: son materiales de trabajo que requieren revisión. El investigador debe adoptar una postura crítica sistemática ante cualquier *output* automático.

Los errores de extracción son frecuentes en tareas de reconocimiento de entidades. Un modelo puede extraer como nombre propio lo que es un cargo, confundir un seudónimo con un nombre real, omitir entidades relevantes por el formato del texto o introducir entidades que no aparecen en el texto original. Siempre debe revisarse la extracción contra el documento fuente.

Las alucinaciones son el error más grave de los modelos de lenguaje. Un modelo puede generar información factualmente incorrecta con total aparente seguridad: inventar fechas, atribuir hechos a personas equivocadas, generar citas inexistentes o fabricar relaciones causales. En una investigación, una alucinación no detectada puede orientar erróneamente una línea de trabajo. La verificación sistemática de cualquier afirmación concreta generada por un modelo es obligatoria.

La pérdida de contexto ocurre cuando el modelo trabaja con un fragmento de texto sin tener el contexto completo del caso. Un mensaje analizado aisladamente puede llevar a conclusiones diferentes que el mismo mensaje analizado en el contexto del hilo completo. El investigador debe asegurarse de que el contexto proporcionado al modelo es suficiente y representativo.

La automatización excesiva es un riesgo sistémico. Cuando un investigador delega demasiadas fases del trabajo en procesos automáticos, pierde la visión directa sobre los datos y puede dejar pasar anomalías importantes que no encajan en las categorías que el proceso reconoce. La supervisión humana periódica de los datos en bruto es necesaria aunque existan procesos automatizados sobre ellos.

La confianza acrítica en los resultados automáticos es especialmente peligrosa cuando el investigador tiene prisa o cuando el resultado parece muy coherente. La plausibilidad de una salida automática no garantiza su exactitud. Cuanto más relevante sea el resultado para la investigación, mayor debe ser el nivel de verificación antes de usarlo.

La mezcla de datos sensibles sin control es un error con consecuencias legales y operativas. Si el investigador introduce en un modelo externo o en una plataforma en la nube datos personales, identificadores de sospechosos, información bancaria o material de investigación reservado, está realizando un tratamiento de datos ilegítimo y potencialmente irreversible. Todo trabajo con datos sensibles debe realizarse en entornos locales controlados.

## 10. Aspectos jurídicos, deontológicos, de seguridad y probatorios específicos

El uso de automatización e IA en la investigación policial plantea cuestiones que van más allá de la eficiencia técnica. Existen obligaciones jurídicas, exigencias deontológicas y criterios de seguridad que el investigador debe conocer y aplicar.

### Protección de datos personales

Los datos personales de víctimas, sospechosos o terceros que aparecen en una investigación penal están protegidos por la Ley Orgánica 7/2021, que transpone la Directiva (UE) 2016/680 sobre tratamiento de datos por autoridades competentes para fines de prevención, detección, investigación y enjuiciamiento de infracciones penales. El tratamiento de estos datos debe respetar los principios de limitación de finalidad, minimización y seguridad. Cualquier transmisión de estos datos a servicios externos, incluidos servicios de IA en la nube, debe tener cobertura legal expresa y cumplir con los requisitos de seguridad aplicables. En la práctica, y salvo cobertura institucional específica, los datos personales protegidos no deben subirse a plataformas de IA externas bajo ninguna circunstancia durante una investigación policial activa.

### Trazabilidad del proceso

El investigador debe poder explicar, en cualquier momento posterior, qué tareas se realizaron de forma automática o asistida por IA, con qué herramienta, en qué momento y con qué supervisión. Esta trazabilidad no tiene por qué incorporarse a los documentos oficiales, pero debe constar en la documentación interna del caso. En caso de impugnación o revisión, el investigador debe poder demostrar que el juicio analítico fue humano y que los productos automáticos fueron revisados.

### Diferenciación entre apoyo y conclusión

Un borrador generado por un modelo no es una nota analítica firmada por el investigador. Una extracción automática no es una diligencia acreditada. Una síntesis generada por IA no es un informe pericial. Los productos automáticos o asistidos tienen valor como materiales de trabajo interno; su conversión en documentos oficiales requiere revisión, validación, reescritura y firma del investigador responsable.

### Seguridad del entorno de trabajo

Las herramientas de automatización y los modelos desplegados localmente deben instalarse sobre sistemas con las medidas de seguridad adecuadas: actualizaciones al día, control de acceso, separación de entornos de investigación y uso personal, y cumplimiento de las políticas de seguridad de la información institucionales. El uso de modelos locales no elimina el riesgo si el equipo no está adecuadamente protegido.

### Imparcialidad y criterio profesional

El investigador que usa IA como apoyo debe ser consciente de que los modelos pueden reflejar sesgos en sus salidas. Una clasificación automática puede sobreestimar o subestimar ciertos tipos de entidades o relaciones según los patrones de su entrenamiento. El investigador debe mantener su propio criterio y no asumir que un resultado estadístico de un modelo refleja una verdad objetiva.

## 11. Caso práctico aplicado

### Caso práctico: Investigación de una red de estafa por inversión en criptomonedas con múltiples víctimas y estructura operativa distribuida

#### Supuesto de hecho

La unidad recibe treinta y siete denuncias en un período de cuatro meses, todas relacionadas con una presunta plataforma de inversión en criptomonedas que prometía rentabilidades extraordinarias. Las víctimas entregaron fondos mediante transferencia bancaria y posterior conversión a criptomonedas según instrucciones de la plataforma. Los importes defraudados oscilan entre dos mil y cuarenta mil euros por víctima. La suma total declarada supera los trescientos mil euros.

#### Dato o indicio de partida

Dos de los dominios utilizados por la plataforma están activos en el momento de inicio de la investigación. Las denuncias contienen capturas de pantalla de la interfaz, de conversaciones con supuestos asesores de inversión y de transferencias realizadas. Los asesores utilizaban distintos nombres y contactaban por distintos canales: WhatsApp, Telegram y correo electrónico. Se identifican al menos quince alias distintos a lo largo de las denuncias.

#### Hipótesis de trabajo

Existe una organización que opera bajo múltiples identidades, con una estructura distribuida de captación y con al menos dos dominios activos. Parte de los actores pueden estar coordinados desde infraestructura compartida. Los fondos transitaron por cuentas bancarias intermedias antes de convertirse en criptomonedas.

#### Actuaciones realizadas

En primer lugar, el investigador crea una estructura de caso en Obsidian con una nota de caso principal, notas individuales para cada alias identificado, notas para cada dominio y una plantilla de cronología de hechos. A continuación, procesa las treinta y siete denuncias mediante un *script* sencillo que extrae y normaliza en formato homogéneo los datos estructurados: nombre del alias, canal de comunicación, dominio, número de cuenta, importe y fecha de transferencia. El resultado es una hoja normalizada de datos con cuatrocientas veintisiete entradas.

Sobre los textos de las conversaciones aportadas en las denuncias, el investigador usa un modelo local desplegado con Ollama para extraer entidades y para identificar patrones de vocabulario repetido entre los distintos asesores. La extracción es revisada y corregida manualmente. Se detecta que tres alias distintos utilizan expresiones idénticas y estructuras de argumentación prácticamente calcadas, lo que sugiere un guion compartido o un mismo operador bajo múltiples identidades.

Los dominios identificados son analizados con herramientas de análisis de infraestructura: se comprueban los registros DNS, se identifica la IP de alojamiento, se buscan dominios en el mismo rango de IPs y se consultan bases de datos de registros históricos. Dos dominios adicionales comparten infraestructura con los iniciales.

#### Hallazgos obtenidos

Se identifican cuatro dominios vinculados a la misma infraestructura, con registros en los dieciocho meses anteriores. Tres de los quince alias iniciales presentan patrones de comunicación que sugieren un mismo operador. Se detectan cuatro números de cuenta distintos que recibieron transferencias, todos en entidades bancarias españolas, con titulares en distintas provincias. Se identifican doce billeteras de criptomonedas distintas a las que derivaron los fondos según las instrucciones aportadas por las víctimas.

#### Análisis e interpretación

El investigador consolida los hallazgos en su base de conocimiento: vincula los dominios, los alias, las cuentas y las billeteras en el mapa relacional de Obsidian. El grafo resultante muestra dos grupos de entidades con escasa vinculación directa entre sí, lo que puede indicar dos células operativas distintas o dos momentos del ciclo de vida de la organización. La hipótesis de trabajo se refina: puede haber más de un núcleo operativo bajo la misma marca fraudulenta.

El modelo local ayuda a generar un primer borrador de nota analítica que el investigador revisa, corrige y amplía con los elementos de contexto que el modelo no tenía. El producto final es elaboración del investigador.

#### Explotación policial y documental

Los hallazgos son trasladados al sistema de trabajo institucional. Se preparan los oficios de solicitud de información a las entidades bancarias, con identificadores precisamente delimitados. Se documenta la metodología utilizada con indicación de qué pasos fueron automatizados y cuáles fueron realizados directamente por el investigador. El caso se registra en la base de conocimiento con las entidades identificadas, las relaciones confirmadas y las líneas de investigación pendientes, de modo que pueda retomarse o ampliarse sin pérdida de contexto.

#### Lecciones operativas

La normalización automatizada de datos de treinta y siete denuncias en formato heterogéneo permitió al investigador trabajar sobre un conjunto coherente en un tiempo muy inferior al que habría requerido un proceso manual. El uso del modelo local para el análisis de texto de las conversaciones orientó rápidamente una línea de investigación relevante (el guion compartido) que habría sido muy difícil de identificar por lectura manual de ese volumen de texto. La gestión en Obsidian garantizó que toda la información fuera accesible, enlazada y recuperable. En ningún momento se subió información personal o datos de las víctimas a servicios externos.

## 12. Conclusiones operativas

La automatización, la IA y la gestión del conocimiento no son complementos opcionales de la investigación OSINT de cibercrimen: son, en la medida en que se integran con criterio y método, multiplicadores de capacidad investigadora. Su valor no está en la herramienta en sí, sino en la forma en que el investigador las incorpora a su flujo de trabajo.

Un investigador que automatiza las tareas repetitivas libera tiempo para el análisis. Un investigador que usa un modelo de lenguaje con supervisión activa puede procesar en minutos volúmenes de texto que antes le costaban horas. Un investigador que mantiene una base de conocimiento bien estructurada no redescubre cada vez lo que ya investigó y puede construir sobre el trabajo de su equipo.

Pero ninguna de estas capacidades tiene valor sin control metodológico. La automatización mal diseñada genera ruido. Los modelos sin supervisión producen errores y alucinaciones. El conocimiento mal organizado no se recupera. Y cualquier proceso que prescinda del juicio analítico del investigador o que trabaje con datos sensibles fuera de un entorno controlado incurre en riesgos que pueden comprometer la investigación, la protección de datos y la validez probatoria del trabajo.

El investigador de policía judicial que integra estas herramientas con madurez metodológica no las usa para hacer menos: las usa para hacer mejor, con mayor sistematización, con mayor eficiencia y con mayor capacidad de escalar su trabajo a la dimensión real del cibercrimen contemporáneo. Esa integración no es instantánea: requiere aprendizaje, ajuste, documentación y revisión continua. Pero el resultado es una práctica investigadora más sólida, más trazable y más capaz de responder a investigaciones complejas con recursos sostenibles.

## 13. Checklist final de trabajo

### Análisis previo y planificación

- [ ] He identificado qué tareas en este caso son repetitivas o estructurables antes de comenzar a trabajar.
- [ ] He definido qué tareas automatizaré y qué tareas exigen mi criterio directo.
- [ ] He revisado si este caso o entidades similares están registrados en mi base de conocimiento.

### Tratamiento de datos y seguridad

- [ ] He verificado que no voy a utilizar servicios externos en la nube para procesar datos personales de víctimas o sospechosos.
- [ ] He comprobado que las herramientas que voy a utilizar operan en un entorno local o controlado apropiado para los datos del caso.
- [ ] He adoptado las medidas de seguridad institucionales aplicables al entorno de trabajo.

### Automatización y extracción

- [ ] He normalizado los datos de entrada antes de aplicar cualquier proceso automático.
- [ ] He revisado manualmente los resultados de la extracción automática de entidades.
- [ ] He comprobado que los resultados automatizados son coherentes con los datos originales.

### Uso de modelos de lenguaje

- [ ] He proporcionado al modelo el contexto suficiente y representativo para la tarea.
- [ ] He verificado cada afirmación concreta generada por el modelo contra las fuentes originales.
- [ ] He identificado y corregido posibles alucinaciones, omisiones o distorsiones en la salida.
- [ ] Los borradores generados por el modelo han sido reescritos y validados por mí antes de cualquier uso oficial.

### Gestión del conocimiento

- [ ] He registrado las nuevas entidades y relaciones del caso en mi base de conocimiento.
- [ ] He documentado la metodología empleada de forma que pueda recuperarse y reutilizarse.
- [ ] He enlazado este caso con casos anteriores relevantes identificados en la base.

### Trazabilidad y documentación

- [ ] He dejado constancia interna de qué tareas fueron asistidas por automatización o IA.
- [ ] He documentado las herramientas utilizadas y el nivel de supervisión ejercido.
- [ ] Los documentos oficiales del caso son elaboración mía y así consta.

### Integración institucional

- [ ] Los productos analíticos generados con apoyo automático han sido revisados, adaptados y firmados por mí antes de su tramitación oficial.
- [ ] He seguido los flujos de aprobación y distribución institucionales aplicables al caso.
- [ ] He verificado que el tratamiento de datos realizado es compatible con el marco legal vigente.