# Capítulo 5. Investigación práctica de correos electrónicos en fuentes abiertas

---

## 1. Introducción

El correo electrónico es, en el contexto de la investigación de cibercrimen,
uno de los datos de partida más frecuentes y, cuando se trabaja con método,
uno de los más productivos. Aparece en casi todas las tipologías de cibercrimen:
como remitente de un mensaje de phishing, como dato de contacto en un anuncio
fraudulento, como identificador de registro en una plataforma investigada,
como elemento visible en la bio de un perfil o como dirección vinculada a
un dominio de infraestructura. Su ubicuidad no es casualidad: el correo
electrónico sigue siendo el eje de autenticación de casi todos los servicios
digitales, lo que lo convierte en un identificador con una estabilidad y una
capacidad de pivote que pocos otros datos pueden igualar.

Pero la frecuencia con que aparece no implica que su investigación sea sencilla
ni que sus resultados deban tomarse al pie de la letra. Un correo electrónico
puede ser una cuenta personal activa de una persona real, un buzón creado
exclusivamente para una operación de fraude, una dirección construida para
imitar legitimidad o una cuenta temporal abandonada hace años. La diferencia
entre esos casos es analíticamente crítica, y distinguirlos requiere más que
una búsqueda aislada: requiere un flujo de trabajo estructurado, el uso
combinado de herramientas adecuadas y la interpretación prudente de los
resultados.

Este capítulo está concebido para enseñar exactamente eso: cómo investigar
un correo electrónico en fuentes abiertas con criterio profesional, desde
el análisis inicial del dato hasta la explotación de los pivotes que genera,
pasando por el uso de herramientas como Epieos, Holehe, MXToolbox o EmailRep
dentro de una secuencia de trabajo real.

---

## 2. Finalidad investigadora del capítulo

La función de este capítulo dentro del manual es eminentemente práctica. Si
los capítulos anteriores establecieron los fundamentos metodológicos,
jurídicos y de seguridad operacional de la investigación OSINT, este capítulo
aplica esos fundamentos a uno de los objetos de investigación más habituales
en cibercrimen: el correo electrónico.

Su aportación al lector es doble. Por un lado, proporciona un marco analítico
para entender el correo electrónico no como un simple dato de contacto, sino
como un identificador multidimensional con capacidad de revelar redes de
actividad, patrones de reutilización y relaciones entre entidades digitales.
Por otro, desarrolla una metodología de trabajo concreta, con herramientas
reales y fases claramente definidas, que el investigador puede aplicar desde
el primer día en casos reales de phishing, fraude, suplantación, estafas
online e ingeniería social.

---

## 3. Objeto de análisis y punto de partida

### 3.1. El correo electrónico como objeto de investigación OSINT

A efectos de este capítulo, el correo electrónico se analiza desde tres
perspectivas complementarias: como identificador digital, como nodo relacional
y como observable técnico.

Como **identificador digital**, el correo es una cadena única vinculada a
una cuenta en un proveedor. Su posible reutilización en múltiples servicios
a lo largo del tiempo lo convierte en un anclaje de identidad de considerable
valor investigativo.

Como **nodo relacional**, el correo puede vincular aliases, nombres, dominios,
perfiles sociales, números de teléfono y wallets que, separados, parecen
datos aislados, pero que juntos construyen una identidad digital con estructura
y coherencia.

Como **observable técnico**, el correo —especialmente cuando se dispone
legítimamente del mensaje original— contiene en sus cabeceras información
sobre la infraestructura de envío que puede orientar la investigación hacia
servidores, proveedores y rutas técnicas relevantes.

### 3.2. Contextos de aparición

El correo puede llegar al investigador por múltiples vías: la víctima lo
aporta como remitente del mensaje de fraude; el investigador lo identifica
en el registro WHOIS de un dominio fraudulento; aparece en la bio de un perfil
investigado; figura como dato de contacto en un anuncio de compraventa; o
emerge como pivote durante la investigación de un alias o un teléfono. En
todos esos casos, las preguntas iniciales son las mismas: ¿qué tipo de cuenta
es esta? ¿Dónde más aparece? ¿Está vinculada a otros elementos conocidos de
la investigación? ¿Qué puede decirnos su dominio sobre el proveedor y la
naturaleza del servicio?

---

## 4. El correo electrónico como identificador digital y pivote de investigación

### 4.1. Estabilidad y reutilización como vectores de valor

El correo electrónico tiende a ser un identificador más estable que otros
datos digitales de alta volatilidad. Cambiar de dirección de correo implica
actualizar el registro en todos los servicios donde ha sido utilizado, lo
que desincentiva la rotación frecuente. Esta estabilidad hace que un correo
con historial de uso activo sea, con frecuencia, el anclaje más consistente
de una identidad digital.

La reutilización es el factor que multiplica ese valor: cuando el mismo correo
ha sido usado como identificador en múltiples plataformas, cada aparición
adicional amplía el perfil de actividad y puede vincular conductas aparentemente
separadas. El correo que aparece en el registro de un dominio fraudulento,
en el perfil de una red social y en el historial de anuncios de una plataforma
de compraventa no es simplemente un correo electrónico: es el eje de una
identidad digital con trayectoria.

### 4.2. Tipología de correos desde la perspectiva investigativa

El investigador debe identificar desde el inicio el tipo de cuenta que tiene
ante sí, porque esa clasificación condiciona las expectativas y la estrategia.

El **correo personal de uso habitual** —habitualmente en proveedores masivos
como Gmail, Outlook o Yahoo— puede tener una larga historia de reutilización.
El **correo funcional o específico** fue creado para un propósito concreto
y su radio de aparición es más limitado. El **correo operativo delictivo**
fue creado deliberadamente para actividades ilícitas, frecuentemente en
proveedores sin verificación de identidad como ProtonMail o Tutanota, y tiene
menor potencial de pivot personal aunque puede tener valor técnico. El
**correo desechable o temporal** —generado por servicios como Guerrilla Mail
o Temp-mail— tiene vida útil muy corta y valor investigativo como identificador
casi nulo, aunque su presencia puede ser indicativa del tipo de actividad
que se intentó ocultar.

---

## 5. Análisis inicial del correo y contextualización del hallazgo

### 5.1. Lectura analítica del identificador

El primer paso, antes de consultar cualquier herramienta, es leer el correo
con atención analítica. La parte local —lo que precede al arroba— puede
contener fragmentos de nombre o apellido, un alias reutilizable, una fecha
o una secuencia con significado propio. El dominio —lo que sigue al arroba—
informa sobre el proveedor: si es un servicio masivo y gratuito, un proveedor
orientado a la privacidad, un dominio corporativo o un dominio propio que
puede investigarse de forma independiente.

Esta lectura inicial permite formular hipótesis preliminares antes de iniciar
la búsqueda: ¿es probable que el alias de la parte local sea el mismo que
usa en otras plataformas? ¿El dominio es de un proveedor que verifica la
identidad de sus usuarios o de uno que no lo hace? ¿La combinación de nombre
y número parece una dirección de uso habitual o una dirección generada para
una ocasión?

### 5.2. Contextualización del hallazgo

El correo siempre aparece en un contexto, y ese contexto es inseparable del
dato. Un mismo email que aparece como remitente de un mensaje de phishing
y como titular del registro WHOIS de un dominio fraudulento tiene un perfil
de riesgo y un potencial investigativo distintos al mismo email apareciendo
como contacto en un anuncio de compraventa. Antes de iniciar cualquier
búsqueda, el investigador debe documentar con precisión dónde apareció el
correo, cuándo, qué actividad lo rodeaba y qué datos lo acompañaban.

---

## 6. Flujo de trabajo del investigador a partir de un correo electrónico

Este apartado describe la secuencia profesional que el investigador debe
seguir cuando recibe un correo electrónico como dato de partida. No es un
protocolo rígido, sino un marco de referencia que debe adaptarse al tipo
de investigación y al contexto del hallazgo.

**Fase 1: análisis y normalización del dato.** El investigador registra el
correo exactamente tal como fue obtenido, analiza su estructura —parte local
y dominio— y formula las hipótesis iniciales descritas en el apartado anterior.
Verifica que el formato es válido —que tiene una parte local, un símbolo
arroba y un dominio con extensión reconocible— antes de iniciar búsquedas.

**Fase 2: contextualización.** El investigador documenta el contexto exacto
de aparición del correo: fuente, fecha, datos que lo acompañaban y su relación
con los hechos investigados. Este paso no requiere herramientas externas,
pero es fundacional para todo lo que sigue.

**Fase 3: análisis del dominio y del proveedor.** El investigador investiga
el dominio del correo. Si se trata de un proveedor conocido —Gmail, Outlook,
Yahoo, ProtonMail—, la información sobre el dominio en sí es limitada, pero
informa sobre la naturaleza del servicio. Si es un dominio propio —una empresa,
una organización o una infraestructura específica—, debe investigarse en
profundidad usando las herramientas descritas en el capítulo décimo:
registros WHOIS, DNS, MX, subdominios y certificados. En este punto conviene
usar **MXToolbox** para verificar los registros de correo del dominio y
detectar posibles configuraciones relevantes.

**Fase 4: comprobación de reputación.** El investigador consulta el correo
en servicios de evaluación de reputación como **EmailRep** para obtener una
primera señal sobre su historial: antigüedad estimada, presencia en
filtraciones, indicadores de actividad maliciosa registrada o señales de
que se trata de una dirección desechable. Este paso es rápido y aporta un
contexto de riesgo inicial antes de invertir tiempo en búsquedas más profundas.

**Fase 5: búsqueda de exposición pública.** El investigador realiza búsquedas
en motores generalistas con el correo entre comillas, en todas sus variantes
relevantes, para localizar publicaciones, perfiles, anuncios o registros en
que el email haya sido publicado de forma pública. Esta búsqueda puede revelar
actividad que las herramientas especializadas no capturan.

**Fase 6: enriquecimiento con herramientas especializadas.** El investigador
utiliza herramientas como **Epieos** para obtener información adicional
vinculada al correo: nombres de usuario asociados, servicios en que está
registrado, avatar vinculado y datos de perfil visibles. Esta fase es la más
productiva en términos de densidad informativa y debe combinarse con la
verificación manual de cada resultado.

**Fase 7: comprobación de presencia en servicios.** El investigador utiliza
herramientas como **Holehe** para verificar de forma sistematizada si el
correo ha sido utilizado como identificador de registro en un conjunto amplio
de plataformas y servicios. Los resultados orientan las búsquedas manuales
posteriores.

**Fase 8: investigación de pivotes.** A partir de los hallazgos obtenidos
en las fases anteriores —aliases identificados, nombres visibles, teléfonos,
dominios asociados, perfiles en plataformas—, el investigador identifica los
pivotes más relevantes y los investiga siguiendo los procedimientos de los
capítulos correspondientes.

**Fase 9: análisis de cabeceras** (cuando se dispone legítimamente del mensaje
original). Si el correo fue aportado por la víctima en formato nativo, el
investigador analiza las cabeceras técnicas para obtener información adicional
sobre la ruta del mensaje y la posible IP de origen. Esta fase se desarrolla
en el apartado 8.

**Fase 10: valoración, preservación y documentación.** El investigador evalúa
la coherencia del conjunto de hallazgos, valora la fuerza de cada resultado,
preserva los hallazgos relevantes con sello temporal y hash, y documenta el
proceso seguido de forma suficientemente detallada para su explotación
posterior.

---

## 7. Herramientas y recursos prácticos para la investigación de correos electrónicos

### 7.1. Herramientas de reputación y evaluación contextual inicial

**EmailRep** es un servicio de evaluación de reputación de direcciones de
correo electrónico. Acepta como entrada una dirección de email y devuelve
un perfil de reputación que incluye: indicadores de si la dirección parece
pertenecer a un correo desechable o temporal, señales de antigüedad estimada,
presencia en filtraciones de datos conocidas, indicadores de actividad
sospechosa registrada y, en algunos casos, información sobre la presencia
de la dirección en servicios de perfiles vinculados. Su valor operativo
principal está en la **fase 4 del flujo**: proporciona en segundos una primera
señal de contexto que permite al investigador calibrar las expectativas antes
de invertir tiempo en búsquedas más profundas.

El investigador debe interpretar sus resultados con criterio: una reputación
baja o una señal de actividad maliciosa registrada no equivale a prueba de
implicación en el caso, pero justifica priorizar esa línea de investigación.
Una reputación neutral tampoco descarta actividad delictiva, especialmente
si el correo es reciente o si el proveedor no está bien indexado en las bases
de datos de EmailRep. Su limitación principal es la cobertura: direcciones
en proveedores de nicho o en dominios propios pueden no estar bien representadas.

### 7.2. Herramientas de enriquecimiento de identidad digital

**Epieos** es actualmente una de las herramientas de enriquecimiento de correo
electrónico más útiles disponibles en abierto para el investigador. Acepta
como entrada una dirección de correo electrónico y consulta múltiples fuentes
para devolver información asociada: nombres de usuario vinculados, servicios
en los que aparece registrado, imagen de avatar cuando está disponible a
través de servicios como Gravatar, y en algunos casos datos de perfil visibles
en plataformas que asocian públicamente el correo a una identidad.

Su uso más productivo está en la **fase 6 del flujo de trabajo**, tras la
comprobación inicial de reputación. Los resultados que devuelve deben
entenderse como indicios de búsqueda, no como atribuciones verificadas: si
Epieos muestra que el correo investigado está vinculado a un perfil de
Instagram con un nombre determinado, eso no confirma que ese perfil pertenezca
al titular del correo, sino que existe una asociación técnica entre ambos
que debe verificarse manualmente y contrastarse con otros hallazgos.

El investigador debe acceder directamente a cada plataforma indicada en los
resultados de Epieos y verificar la coherencia de la información: ¿el perfil
vinculado tiene actividad real? ¿La foto, la bio y el nombre son consistentes
con otros datos ya conocidos del caso? ¿Existen contradicciones que sugieran
que la asociación no corresponde al mismo sujeto? La verificación manual
es insustituible y debe realizarse antes de incorporar cualquier resultado
de Epieos como hallazgo activo.

La limitación principal de Epieos es su dependencia de las APIs y bases de
datos que consulta, cuya cobertura y actualización son variables. Un resultado
negativo no indica ausencia de actividad, sino ausencia de actividad en las
fuentes que la herramienta indexa.

### 7.3. Herramientas de comprobación de presencia en plataformas y servicios

**Holehe** es una herramienta de código abierto diseñada para verificar si
una dirección de correo electrónico ha sido utilizada como identificador de
registro en un conjunto amplio de plataformas y servicios. Su mecanismo de
funcionamiento se basa en el uso de los procesos de recuperación de contraseña
de cada plataforma —sin acceder a ninguna cuenta ni comprometer ningún
servicio— para determinar si el correo está registrado: si la plataforma
responde con un mensaje de «correo registrado», Holehe lo registra como
positivo; si responde con «correo no encontrado», lo registra como negativo.

Su uso principal está en la **fase 7 del flujo de trabajo**. El resultado
es una lista de plataformas en las que el correo tiene o no tiene cuenta
registrada. El valor operativo es alto porque permite identificar rápidamente
en qué servicios debe realizarse una búsqueda manual posterior para obtener
información de perfil visible.

El investigador debe tener presente dos limitaciones fundamentales. Primera:
un resultado positivo en Holehe indica que el correo tiene cuenta en esa
plataforma, no que el perfil esté activo ni que contenga información relevante.
Segunda: algunos servicios pueden devolver falsos positivos —indicar que el
correo está registrado cuando en realidad no lo está, como resultado de sus
mecanismos de privacidad— o falsos negativos. Por ello, los resultados de
Holehe deben contrastarse con verificación manual directa en las plataformas
con mayor relevancia para el caso.

Una consideración operativa importante: Holehe genera múltiples peticiones
a los servicios consultados en un período breve. El investigador debe ejecutarlo
desde un entorno técnico segregado y con las cautelas de OPSEC descritas en
el capítulo cuarto, especialmente cuando la investigación requiere evitar
señales hacia el objetivo.

### 7.4. Herramientas de análisis del dominio y del proveedor de correo

**MXToolbox** es un servicio de análisis de registros DNS con especial
utilidad para el análisis de infraestructura de correo. Su función principal
en la investigación de un email está en la **fase 3 del flujo de trabajo**,
cuando el dominio del correo es propio —no un proveedor masivo— y merece
investigación independiente.

Para un dominio de correo propio, MXToolbox permite: verificar los registros
MX y conocer qué servidores gestionan el correo del dominio; comprobar si
existen registros SPF, DKIM y DMARC que otorgan autenticidad al correo enviado
desde ese dominio —su ausencia o mala configuración puede ser indicativa en
investigaciones de phishing—; consultar si el dominio o sus IPs asociadas
aparecen en listas negras de correo; y obtener una visión rápida de la
infraestructura técnica del dominio. En investigaciones de phishing por correo,
el análisis con MXToolbox del dominio remitente puede revelar si fue configurado
específicamente para envío malicioso o si es un dominio legítimo comprometido.

Para correos en proveedores masivos —Gmail, Outlook—, MXToolbox no proporciona
información sobre el titular individual, pero puede usarse para verificar el
estado del dominio y su configuración de correo.

**SecurityTrails**, descrita en mayor profundidad en el capítulo décimo,
complementa a MXToolbox permitiendo consultar el historial DNS del dominio
y, especialmente, realizar búsquedas inversas por correo electrónico en
registros WHOIS históricos: si el correo investigado ha sido utilizado como
dato de registro de algún dominio, esta búsqueda lo revelaría.

### 7.5. Herramientas de búsqueda de exposición en filtraciones de datos

Los servicios de verificación de exposición en filtraciones de datos conocidas
permiten comprobar si una dirección de correo aparece en incidentes de
seguridad documentados. **Have I Been Pwned** es el servicio más reconocido
en este ámbito: permite introducir una dirección de correo y obtener información
sobre en qué filtraciones conocidas aparece esa dirección. Cuando el correo
aparece en una filtración, puede obtenerse información adicional sobre los
datos incluidos en esa filtración —nombre de usuario, contraseña hasheada,
datos de perfil—, lo que puede enriquecer la investigación.

El investigador debe tratar esta información con las mismas cautelas de
proporcionalidad y minimización descritas en el capítulo jurídico. Los datos
procedentes de filtraciones son datos de carácter personal obtenidos sin
consentimiento, y su tratamiento en el marco de una investigación policial
está sujeto a exigencias específicas.

### 7.6. Herramientas de búsqueda de presencia pública

Los **motores de búsqueda generalistas** —Google, Bing— con el correo entre
comillas son el punto de entrada más básico y frecuentemente productivo para
localizar publicaciones, perfiles, anuncios o registros en que el email ha
sido publicado de forma pública. La búsqueda debe realizarse con el correo
completo entre comillas. Conviene también buscar solo la parte local —el
identificador antes del arroba— como posible alias reutilizable en otras
plataformas.

Para localizar si el mismo correo está asociado a un avatar visible en blogs
y gestores de contenido, la consulta del servicio **Gravatar** con el hash
MD5 del correo puede revelar si existe un perfil de avatar asociado, lo que
a veces incluye nombre, bio y enlaces a otros perfiles.

### 7.7. Herramientas de preservación y documentación

La preservación de los hallazgos vinculados a un correo electrónico debe
seguir los principios generales del manual: sello temporal verificable, hash
del contenido preservado, registro de la fuente y descripción del método de
obtención. Las herramientas de archivado web —Archive.today, Wayback Machine
con guardado activo— permiten preservar el estado de perfiles y páginas en
el momento de la investigación. Para los resultados de herramientas como
Epieos o Holehe, el investigador debe exportar o capturar los resultados
completos con registro de la fecha, la herramienta y el dato de entrada.

---

## 8. Análisis técnico básico y cabeceras de correo

### 8.1. Cuándo y cómo accede el investigador a las cabeceras

El análisis de cabeceras de un mensaje de correo solo es posible cuando el
investigador dispone legítimamente del mensaje en su formato nativo completo.
La vía más habitual es la aportación voluntaria por parte de la víctima del
mensaje fraudulento recibido. Un mensaje reenviado o capturado como imagen
no contiene las cabeceras originales con valor técnico.

### 8.2. Información relevante en las cabeceras

El campo **Received** registra el recorrido del mensaje entre servidores, de
más reciente a más antiguo. El primer campo Received del mensaje —el generado
por el servidor del remitente— puede incluir la dirección IP del dispositivo
que originó el envío, especialmente cuando el envío se realizó desde un
cliente de correo local. Esa IP puede orientar sobre la infraestructura de
envío o, en casos donde no se usa VPN, sobre la localización aproximada del
servidor remitente.

El campo **From** indica la dirección declarada del remitente, que puede
haber sido falsificada mediante *spoofing*. El campo **Return-Path** indica
la dirección de rebote real, que puede diferir del From en mensajes fraudulentos.
El campo **Message-ID** puede contener información sobre el dominio o la
infraestructura de origen del envío. Los campos **DKIM-Signature** y
**Received-SPF** indican si el mensaje pasó las verificaciones de autenticación
del dominio remitente, lo que puede ser relevante para determinar si el
dominio fue configurado para el envío legítimo o si fue comprometido.

Para el análisis de cabeceras, herramientas como **Google Admin Toolbox
Message Header Analyzer** o **MXToolbox Email Header Analyzer** permiten
pegar el texto de la cabecera y obtener una representación estructurada y
legible de su contenido, con identificación de los servidores y los tiempos
de procesamiento.

### 8.3. Límites interpretativos

El investigador debe aproximarse a las cabeceras con conciencia clara de sus
límites. Las cabeceras pueden ser falsificadas, especialmente los campos
visibles. La IP identificada puede pertenecer a un servidor de correo
intermediario, a un servicio de correo web, a una VPN o a un nodo de red de
anonimización. La interpretación de la IP requiere siempre contraste con otras
fuentes y, frecuentemente, la obtención de información adicional mediante
diligencias judiciales al proveedor del servicio.

---

## 9. Interpretación de hallazgos, cautelas y errores frecuentes

### 9.1. Distinción entre presencia, reutilización y atribución

El investigador debe mantener separados tres niveles de inferencia. La
**presencia** del correo en un contexto indica que esa dirección apareció
ahí. La **reutilización** en múltiples plataformas puede indicar que el mismo
sujeto la ha usado en distintos contextos. La **atribución personal firme**
—que ese correo corresponde inequívocamente a un sujeto concreto— requiere
corroboración independiente y, en la mayoría de los casos, diligencias
judiciales al proveedor del servicio.

### 9.2. Errores frecuentes

El **uso acrítico de herramientas automatizadas** es el error más habitual:
asumir que un resultado de Epieos o Holehe es una conclusión verificada cuando
en realidad es un indicio de búsqueda que requiere verificación manual.

La **dependencia de una sola herramienta** produce resultados incompletos:
cada herramienta tiene cobertura distinta, y un correo que no produce resultados
en Holehe puede producirlos en Epieos o en una búsqueda manual en plataformas
específicas.

La **sobreinterpretación de coincidencias** —asumir que la presencia del mismo
correo en dos contextos prueba una conexión significativa cuando puede ser
el resultado de una coincidencia o de datos antiguos— es un riesgo constante.

La **falta de preservación del contexto** —documentar solo el correo y no
el entorno en que apareció— produce hallazgos que pierden valor cuando son
cuestionados en el procedimiento.

La **interpretación errónea de cabeceras** —especialmente atribuir directamente
una IP a la ubicación del autor sin valorar los intermediarios técnicos— es
un error con consecuencias que pueden comprometer la solidez de la investigación.

---

## 10. Aspectos jurídicos, deontológicos y probatorios específicos

### 10.1. Límites de la investigación en fuentes abiertas

La búsqueda de la presencia pública de un correo, el análisis de su dominio,
la comprobación de su reputación y el uso de herramientas como Epieos, Holehe
o EmailRep son actividades que, con carácter general, pueden realizarse dentro
de los límites de la investigación en fuentes abiertas sin autorización
judicial específica. El acceso al contenido de una cuenta de correo, al buzón
de mensajes o a cualquier dato vinculado a esa cuenta que no sea de acceso
público requiere autorización judicial y la correspondiente solicitud al
proveedor del servicio.

### 10.2. Tratamiento del mensaje aportado por la víctima

Cuando la víctima aporta voluntariamente un mensaje en formato nativo completo,
ese mensaje puede ser analizado en su contenido y en sus cabeceras. El
investigador debe asegurarse de que el mensaje se preserva en formato original
—no solo como captura o reenvío—, documentar la forma en que fue entregado
y mantener la cadena de preservación desde el primer momento.

### 10.3. Preservación y valor probatorio

La preservación adecuada de los hallazgos —dato en contexto, fuente, método,
fecha y hora, sello temporal verificable, hash del archivo preservado— es
la condición que permite que un hallazgo en fuente abierta tenga valor en
el procedimiento. Un perfil vinculado al correo investigado que desaparece
antes de ser preservado es un hallazgo perdido.

---

## 11. Caso práctico aplicado

### Caso práctico: Identificación del operador de una campaña de fraude de soporte técnico a partir de un correo de contacto

**Supuesto de hecho**

Una unidad de policía judicial recibe varias denuncias de ciudadanos que
refieren haber sido contactados por teléfono por personas que se identificaban
como técnicos de una empresa informática reconocida, alertándoles de que su
ordenador tenía un virus y ofreciéndoles solución remota a cambio de un pago.
Tras acceder al pago, las víctimas fueron inducidas a instalar software de
acceso remoto y sufrieron la sustracción de datos bancarios. Varios denunciantes
conservan un correo electrónico al que se les remitió para confirmar el pago
y recibir las instrucciones de instalación del software.

**Dato o indicio de partida**

La dirección de correo electrónico desde la que se enviaron las instrucciones
de instalación: una cuenta en un proveedor gratuito con un identificador que
combina el nombre de una empresa de tecnología conocida con una secuencia
numérica.

**Hipótesis de trabajo**

El correo puede haber sido reutilizado en otros contextos relacionados con
la actividad fraudulenta —anuncios, plataformas, registros de servicios— y
puede estar vinculado a otros identificadores digitales del operador o de
la infraestructura.

**Actuaciones realizadas**

El investigador comienza con la lectura analítica del identificador: la parte
local imita el nombre de una empresa tecnológica conocida, lo que sugiere
una estrategia deliberada de apariencia de legitimidad. El proveedor es un
servicio de correo gratuito sin verificación de identidad, lo que limita las
expectativas de atribución directa.

Se consulta el correo en EmailRep, que indica que la dirección fue vista por
primera vez hace pocos meses, que no tiene historial de comunicación verificada
y que presenta indicadores de haber sido usada en contextos de baja reputación.
Este resultado justifica priorizar la investigación.

Se realiza búsqueda del correo en motores generalistas entre comillas. La
búsqueda devuelve resultados en un portal de denuncias de fraude online donde
varios usuarios lo han reportado como contacto de una estafa de soporte técnico.
Esos resultados se preservan de inmediato.

Se consulta el correo en Epieos. La herramienta devuelve que el correo está
vinculado a una imagen de avatar de Gravatar que muestra el logotipo de una
empresa tecnológica reconocida —indicio de suplantación— y que aparece asociado
a una cuenta en una plataforma de publicación de anuncios de servicios técnicos.

Se verifica manualmente la cuenta en la plataforma de anuncios. El perfil
contiene varios anuncios de servicios de soporte técnico publicados en fechas
coincidentes con el periodo denunciado, con un número de teléfono de contacto.
El anuncio y el perfil se preservan de inmediato con archivado web y sello
temporal.

Se ejecuta Holehe con el correo. Los resultados muestran presencia en tres
plataformas adicionales: dos redes sociales y un servicio de almacenamiento
en nube. Se accede manualmente a las redes sociales y se localizan perfiles
con el mismo avatar del logotipo suplantado, con actividad reciente y con
un alias recurrente en el nombre de usuario. Ambos perfiles se preservan.

El número de teléfono del anuncio se investiga siguiendo el procedimiento
del capítulo sexto, lo que revela presencia adicional en otras plataformas
de anuncios y en un portal de reportes de fraude telefónico.

**Hallazgos obtenidos**

El correo está vinculado a: una imagen de avatar de suplantación documentada;
un perfil en plataforma de anuncios con actividad en el periodo denunciado
y número de teléfono de contacto; presencia en dos redes sociales bajo el
mismo alias; y un número de teléfono que genera hallazgos adicionales en
otras plataformas.

**Análisis e interpretación**

La coherencia entre los hallazgos —mismo avatar de suplantación en múltiples
plataformas, alias recurrente, actividad coincidente con el periodo denunciado,
número de teléfono con presencia en portales de fraude— configura un indicio
relacional sólido que apunta hacia una operación organizada. La hipótesis de
reutilización deliberada del correo como eje operativo se considera confirmada
con base suficiente para escalar la investigación.

**Explotación policial y documental**

Los hallazgos se documentan en un informe de inteligencia con descripción
completa del flujo de trabajo seguido, las herramientas utilizadas en cada
fase, los resultados obtenidos y todos los archivos de preservación con sus
hashes y sellos temporales. El informe fundamenta la solicitud judicial de
información al proveedor del servicio de correo y al proveedor de la plataforma
de anuncios, así como al operador del número de teléfono identificado.

**Lecciones operativas**

Este caso ilustra el valor del flujo de trabajo escalonado: la consulta en
EmailRep orientó la priorización; Epieos reveló la presencia en la plataforma
de anuncios y el avatar de suplantación; Holehe orientó hacia tres plataformas
adicionales que la búsqueda manual confirmó; y la búsqueda del alias resultante
y del número de teléfono amplió la investigación con hallazgos adicionales.
Cada herramienta cumplió una función específica en una fase específica del
flujo, y ninguna fue usada de forma aislada ni acrítica.

---

## 12. Conclusiones operativas

El correo electrónico es, en el ecosistema del cibercrimen, uno de los datos
de partida con mayor potencial de pivot investigativo. Su estabilidad relativa,
su frecuente reutilización en múltiples servicios y su papel como eje de
autenticación en el ecosistema digital lo convierten en un identificador con
capacidad de revelar redes de actividad que, de otro modo, permanecerían
ocultas.

Ese potencial se realiza solo cuando el investigador sigue un flujo de trabajo
estructurado: la lectura analítica inicial, la comprobación de reputación
con EmailRep, el enriquecimiento con Epieos, la comprobación de presencia
en servicios con Holehe, el análisis del dominio con MXToolbox, la verificación
manual de cada resultado y la documentación rigurosa del proceso son los pasos
que convierten un correo electrónico en conocimiento investigativo útil.

La prudencia en la atribución, la verificación cruzada de los resultados y
el respeto al marco jurídico son las condiciones que hacen que ese conocimiento
sea también procesalmente sostenible.

---

## 13. Checklist final de trabajo

**Análisis inicial y contextualización**

- Registrar el correo en formato exacto y analizar su estructura: parte
  local y dominio.
- Documentar con precisión el contexto de aparición del correo.
- Formular hipótesis preliminares sobre el tipo de cuenta y su posible
  valor investigativo.

**Análisis del dominio y reputación**

- Si el dominio es propio: investigar con MXToolbox, SecurityTrails y
  registros WHOIS.
- Consultar el correo en EmailRep para obtener indicadores de reputación
  y contexto inicial.

**Búsqueda de presencia y enriquecimiento**

- Realizar búsqueda con el correo entre comillas en motores generalistas.
- Consultar el correo en Epieos y verificar manualmente cada resultado
  relevante.
- Ejecutar Holehe desde entorno técnico segregado y verificar manualmente
  las plataformas con resultados positivos relevantes para el caso.
- Verificar exposición en filtraciones de datos con Have I Been Pwned
  u otras fuentes equivalentes.

**Análisis de cabeceras** (si se dispone del mensaje original)

- Verificar que el mensaje está disponible en formato nativo completo.
- Analizar los campos Received para reconstruir la ruta del mensaje.
- Identificar posibles campos de IP de origen y valorar su fiabilidad
  técnica.
- Documentar el análisis técnico con descripción del método y los campos
  analizados.

**Investigación de pivotes**

- Identificar todos los datos adicionales revelados: nombres, aliases,
  teléfonos, dominios, perfiles.
- Priorizar los pivotes en función de las preguntas de investigación.
- Investigar cada pivote priorizado siguiendo los procedimientos de
  los capítulos correspondientes.

**Interpretación y explotación**

- Distinguir explícitamente entre presencia, reutilización y atribución.
- Contrastar cada resultado relevante con al menos una fuente independiente.
- Preservar todos los hallazgos relevantes con sello temporal y hash.
- Identificar qué diligencias adicionales requieren cobertura judicial.
- Elaborar el informe con descripción metodológica completa y archivos
  de preservación verificables.

---