# Capítulo 6. Investigación de números de teléfono en fuentes abiertas

---

## 1. Introducción

El número de teléfono ocupa, en el ecosistema del cibercrimen contemporáneo,
un lugar de gran interés investigativo. Su presencia en las investigaciones
es constante: aparece en denuncias de víctimas de estafa, en anuncios
fraudulentos, en perfiles de mensajería asociados a extorsiones, en campañas
de smishing, en registros de servicios digitales y en ecosistemas de fraude
que se apoyan en el teléfono como vector de contacto, de autenticación o de
construcción de identidad. Su relevancia como dato de partida es, en muchos
casos, comparable a la del correo electrónico: puede ser relativamente estable,
puede haber sido reutilizado en múltiples contextos y puede actuar como eje
de conexión entre entidades digitales que, de otro modo, resultarían difíciles
de vincular.

Sin embargo, el número de teléfono plantea al investigador en fuentes abiertas
un conjunto de retos específicos que no deben subestimarse. La cobertura de
las herramientas disponibles es desigual y depende en gran medida del nivel
de exposición pública del número. Los servicios de mensajería cifrada
presentan límites nítidos desde el punto de vista de lo que puede obtenerse
sin actuación judicial. Y la atribución de un número a una persona física
real —en lugar de a una tarjeta de operador prepago sin registro, a un servicio
de número virtual o a un teléfono compartido— requiere frecuentemente
corroboración por vías que van más allá del OSINT.

Este capítulo proporciona al investigador las herramientas conceptuales,
metodológicas y operativas para trabajar con números de teléfono como objetos
de investigación en fuentes abiertas, con criterio, con conocimiento de las
herramientas disponibles y con la prudencia que imponen las particularidades
de este tipo de dato.

---

## 2. Finalidad investigadora del capítulo

Este capítulo continúa la línea aplicativa iniciada en el capítulo anterior,
trasladando la metodología general de la investigación OSINT a un objeto
concreto y frecuente en las investigaciones de cibercrimen: el número de
teléfono. Su función dentro del manual es doble. Por un lado, desarrollar
el marco analítico necesario para entender qué puede y qué no puede obtenerse
en fuentes abiertas a partir de un número de teléfono. Por otro, proporcionar
una secuencia de trabajo clara, realista y aplicable en el trabajo cotidiano
de la policía judicial, con orientación sobre herramientas, interpretación
de resultados y documentación de hallazgos.

El capítulo resulta especialmente relevante en investigaciones de fraude en
compraventa en línea, estafas de inversión, suplantación de identidad,
smishing, fraude de soporte técnico, sextorsión, extorsión digital y cualquier
otro tipo de cibercrimen en que el teléfono desempeñe un papel funcional en
la actividad delictiva o aparezca como rastro de la identidad digital del
sujeto investigado. Su contenido está orientado a permitir que el lector,
al concluirlo, sea capaz de iniciar una investigación OSINT sobre un número
de teléfono con método y con conocimiento suficiente de las herramientas
disponibles.

---

## 3. Objeto de análisis y punto de partida

### 3.1. El número de teléfono como objeto de investigación OSINT

Un número de teléfono es, en su dimensión más básica, un identificador
numérico asignado por un operador de telecomunicaciones para enrutar
comunicaciones de voz y datos hacia un terminal o servicio específico. Pero
desde la perspectiva de la investigación en fuentes abiertas, su relevancia
trasciende esa función técnica. El número de teléfono es también, en muchos
contextos, un identificador de persona o de actividad: está vinculado al
proceso de registro y autenticación en múltiples servicios digitales, aparece
como dato de contacto en anuncios, perfiles y webs, y puede haber sido
reutilizado de forma consistente en distintos entornos como parte de una
identidad digital activa.

Como objeto de investigación OSINT, el número debe analizarse desde tres
perspectivas complementarias. Como **identificador**, puede vincularse a
cuentas de mensajería, perfiles sociales, registros en servicios, historial
de contacto y otros elementos de la identidad digital del sujeto. Como
**dato de exposición pública**, puede haber sido publicado voluntariamente
en anuncios, directorios, páginas de contacto o perfiles, lo que permite
su localización mediante búsqueda en abierto. Y como **pivote relacional**,
puede establecer conexiones entre entidades digitales que, confrontadas entre
sí, amplían el conocimiento disponible sobre el sujeto o la estructura
investigada.

### 3.2. Contextos de aparición y preguntas iniciales

El número de teléfono puede llegar al investigador de formas muy distintas.
La más frecuente es la aportación directa por la víctima: el número desde
el que se realizó la llamada fraudulenta, el contacto del vendedor estafador,
el número asociado al perfil de mensajería del extorsionador. En otros casos,
el investigador lo identifica de forma autónoma durante la exploración de
otros indicios: aparece en el anuncio vinculado a la actividad investigada,
en el perfil de usuario de una plataforma, en el registro de un servicio o
en datos visibles en redes sociales.

Independientemente de la vía de obtención, las preguntas que debe formular
el investigador ante un número de teléfono son sistemáticamente las mismas:
¿qué tipo de número es este y qué indica su estructura? ¿En qué otros contextos
ha aparecido? ¿Está vinculado a servicios de mensajería, perfiles sociales
o anuncios accesibles? ¿Existe evidencia de su reutilización? ¿Qué relaciones
puede establecer con otros elementos de la investigación? ¿Qué diligencias
adicionales serían necesarias para confirmar la atribución personal?

---

## 4. El número de teléfono como identificador digital y pivote de investigación

### 4.1. Estabilidad y reutilización como vectores de valor

A diferencia de una dirección IP dinámica o de un nombre de usuario que puede
cambiarse en minutos, un número de teléfono tiende a ser un identificador
relativamente estable para el usuario que lo emplea de forma cotidiana. Cambiar
de número implica actualizar todos los registros asociados —cuentas de
mensajería, servicios de autenticación, contactos— lo que desincentiva la
rotación frecuente. Esta estabilidad hace del número de teléfono un anclaje
identitario de interés comparable al del correo electrónico.

La reutilización del número en múltiples plataformas es el principal factor
que multiplica su valor investigativo. Un número que aparece como contacto
en un anuncio fraudulento, que también está registrado en un servicio de
mensajería con una foto de perfil visible, que aparece en varios anuncios
de distintas plataformas con características similares y que figura en el
historial de búsqueda de directorios de teléfono no es simplemente "un número
de teléfono": es un eje de actividad que conecta múltiples rastros digitales
y permite construir un perfil de conducta.

### 4.2. Tipología de números desde la perspectiva investigativa

La comprensión del tipo de número que tiene ante sí condiciona la estrategia
de investigación y las expectativas sobre lo que puede obtenerse.

Los **números móviles de operador convencional con contrato** suelen estar
registrados a nombre de una persona o empresa identificable, y su titularidad
puede obtenerse mediante diligencia judicial dirigida al operador. Son el
tipo de número con mayor potencial de atribución personal firme, aunque el
registro puede no corresponder al usuario real si el número ha sido cedido
o vendido.

Los **números prepago sin registro verificado** presentan más dificultades
de atribución, aunque la normativa española exige desde hace años el registro
de las tarjetas prepago. En la práctica, la calidad del registro varía y la
efectividad de las diligencias judiciales al operador puede depender de la
antigüedad de la activación y de las circunstancias del registro.

Los **números VoIP y números virtuales** son identificadores telefónicos
asignados a través de proveedores de servicios de voz sobre internet o de
servicios de número virtual, que pueden no estar asociados a ningún operador
de telecomunicaciones convencional ni a ningún terminal físico. Su atribución
mediante OSINT es frecuentemente muy limitada, y las diligencias judiciales
pueden dirigirse hacia proveedores de servicios ubicados en distintas
jurisdicciones.

Los **números desechables o de aplicaciones de número temporal** son aquellos
generados mediante aplicaciones que proporcionan un número de teléfono
funcional durante un período breve. Su valor investigativo como identificador
estable es nulo, aunque su presencia en un contexto determinado puede ser
relevante como indicio del tipo de actividad que se intenta proteger.

La identificación del tipo de número mediante OSINT no siempre es posible
con certeza, y el investigador debe evitar afirmaciones categóricas sobre la
naturaleza del número cuando los datos disponibles no permiten sustentarlas
con rigor.

---

## 5. Análisis inicial del número y contextualización del hallazgo

### 5.1. Normalización del número como primer paso

Antes de iniciar cualquier búsqueda, el investigador debe normalizar el número
de teléfono en un formato estándar internacional. La misma secuencia de dígitos
puede aparecer en fuentes distintas bajo formatos diferentes: con prefijo
internacional, sin él, con espacios, con guiones, con paréntesis o con puntos.
La búsqueda realizada solo en el formato en que el número aparece en el dato
de partida puede perder resultados relevantes que se encuentran bajo otro
formato en otras fuentes.

La normalización correcta requiere identificar el país de origen del número
a partir del prefijo internacional —o de su ausencia, en cuyo caso el contexto
de la investigación suele indicarlo—, construir el número en formato E.164
con el código de país completo, y generar además las variantes de formato más
frecuentes para usarlas en diferentes búsquedas: con y sin el símbolo más,
con y sin el cero inicial, con los separadores visuales más habituales.

Para un número español, por ejemplo, la secuencia de variantes incluiría la
forma con prefijo +34, la forma sin prefijo pero con el número completo, y
las variantes con espacios o guiones entre grupos de dígitos. Cada una de
esas variantes puede producir resultados distintos en los motores de búsqueda
y en las plataformas de anuncios.

### 5.2. Contextualización del hallazgo

El número de teléfono, como cualquier otro dato, debe analizarse dentro del
contexto en que fue encontrado antes de iniciar la búsqueda externa. Ese
contexto incluye: la plataforma o el entorno en que apareció, la actividad
con la que está asociado, los datos que lo acompañaban —nombre visible, dirección
de correo, alias, descripción del servicio ofrecido— y la fecha aproximada
de la actividad.

Esa contextualización inicial permite formular hipótesis preliminares que
orientarán la estrategia de búsqueda: ¿es probable que el número sea de uso
personal habitual del sujeto o fue creado específicamente para la actividad
investigada? ¿Está asociado a un perfil de mensajería que puede haberse
construido con información real? ¿Existe razón para pensar que ha sido
publicado en anuncios u otros contextos en que haya generado rastro en
abierto?

---

## 6. Búsqueda, reutilización y ampliación de la investigación a partir del número

### 6.1. Búsqueda de presencia pública

La búsqueda de la presencia pública de un número de teléfono en fuentes
abiertas puede abordarse desde varios ángulos complementarios que el
investigador debe combinar de forma sistemática.

La **búsqueda directa en motores generalistas** consiste en introducir el
número en sus distintas variantes de formato, entre comillas, en los principales
motores de búsqueda. Esta búsqueda puede revelar anuncios en plataformas de
compraventa, publicaciones en foros, páginas de contacto, webs comerciales,
directorios de empresas o cualquier otro espacio en que el número haya sido
publicado de forma pública. Es la búsqueda más básica y, con frecuencia,
la que produce los primeros resultados relevantes.

La **búsqueda en plataformas específicas** consiste en buscar el número
directamente en las plataformas más relevantes para el tipo de actividad
investigada: portales de compraventa de segunda mano, plataformas de anuncios
clasificados, directorios de empresas, portales inmobiliarios, foros temáticos
o redes sociales que permiten la búsqueda por número de teléfono. Esta búsqueda
puede revelar actividad que los motores generalistas no han indexado.

La **búsqueda en directorios inversos de teléfono** consiste en consultar
servicios especializados que, a partir de un número, devuelven información
sobre el titular o sobre las menciones del número en sus bases de datos. El
valor de estos directorios depende del país, del tipo de número y de la
antigüedad de los datos indexados, y sus resultados deben contrastarse antes
de asumirlos.

### 6.2. Investigación de reutilización en plataformas y servicios

La reutilización del número en múltiples plataformas es, como en el caso del
correo electrónico, uno de los vectores más valiosos de la investigación OSINT
sobre teléfonos. Un número que aparece como dato de contacto en varios anuncios
de distintas plataformas, que está vinculado a una cuenta de mensajería con
foto de perfil y nombre visible, y que figura en un directorio de empresas
bajo una denominación comercial específica no es un dato aislado: es un nodo
de actividad desde el que pueden construirse conexiones con otros elementos
de la investigación.

La investigación de reutilización debe abordarse de forma sistemática,
siguiendo una secuencia que va desde las fuentes más accesibles y de mayor
cobertura hasta las más específicas: primero la búsqueda en abierto en motores
generalistas, luego la búsqueda en plataformas específicas, después la
consulta de herramientas de enriquecimiento y finalmente la exploración de
los servicios de mensajería, con las cautelas que estos requieren.

### 6.3. El número como pivote hacia otros elementos de la investigación

Cada hallazgo vinculado al número de teléfono es un potencial pivote. Un
nombre visible en un perfil de mensajería puede buscarse de forma independiente
y revelar presencia en otras plataformas. Una foto de perfil puede ser
sometida a búsqueda inversa de imágenes. Un anuncio vinculado al número puede
contener una dirección de correo electrónico adicional o un alias que abre
nuevas líneas. Una empresa o denominación comercial asociada al número puede
investigarse a través de registros mercantiles o directorios.

La lógica del pivote debe aplicarse con el mismo criterio de delimitación
activa desarrollado en el capítulo metodológico: no todos los pivotes deben
seguirse simultáneamente, y la priorización debe responder a las preguntas
de investigación definidas y al principio de pertinencia.

---

## 7. Herramientas y recursos prácticos para la investigación de números de teléfono

### 7.1. Herramientas de normalización y validación

El primer bloque de herramientas que el investigador debe manejar son las
orientadas a la normalización y validación inicial del número. Antes de
realizar ninguna búsqueda, conviene verificar que el número tiene una estructura
válida para el país que indica su prefijo, que el rango corresponde a un tipo
de número conocido —móvil, fijo, VoIP, de servicio especial— y que el formato
empleado en las búsquedas es el correcto para cada plataforma.

Los servicios de validación de números telefónicos en línea permiten introducir
un número y obtener información básica sobre su estructura: país asignado,
tipo estimado de número según el rango, operador al que está asignado el rango
—que no necesariamente el actual titular— y formato internacional normalizado.
Herramientas como **NumLookup**, **Validnumber** o el motor de validación
integrado en plataformas de inteligencia como **Maltego** permiten esta
validación inicial. Su limitación fundamental es que operan sobre asignaciones
de rangos, no sobre titularidades individuales, por lo que informan sobre
el operador asignado al rango pero no sobre el usuario concreto.

### 7.2. Herramientas de búsqueda en abierto y directorios inversos

El segundo bloque funcional agrupa las herramientas orientadas a localizar
el número en el espacio público digital. Los motores de búsqueda generalistas
—Google, Bing— son el punto de entrada más básico, utilizados con el número
entre comillas y en sus distintas variantes de formato. La búsqueda de cada
variante de forma separada es importante porque distintas plataformas pueden
mostrar el mismo número bajo formatos distintos.

Los **directorios inversos de teléfono** son servicios especializados que
mantienen bases de datos de números telefónicos con información asociada,
construidas a partir de fuentes públicas, directorios comerciales, páginas
blancas y datos aportados por usuarios. En España, servicios como **Páginas
Blancas**, **Infobel** o **11888.es** pueden contener información sobre
números fijos de abonados que han optado por aparecer en directorios públicos.
Para números móviles, la cobertura es significativamente menor, dado que los
registros de móviles no son de acceso público por defecto.

Herramientas globales de directorio inverso como **Truecaller**, **Sync.me**
o **Numspy** construyen sus bases de datos a partir de la agregación de
contactos compartidos voluntariamente por millones de usuarios de sus
aplicaciones. El resultado que devuelven puede incluir un nombre asociado
al número, mencionando quién lo tiene guardado en su agenda. Su valor
operativo puede ser alto, pero sus limitaciones son también significativas:
los datos pueden ser incorrectos o desactualizados, pueden reflejar el nombre
con que alguien tiene guardado ese número en su contacto —no necesariamente
el titular real— y su cobertura varía enormemente por país y tipo de número.
El investigador debe tratar sus resultados como indicios de orientación, no
como atribuciones verificadas.

### 7.3. Herramientas de enriquecimiento del número

Las herramientas de enriquecimiento están diseñadas para obtener, a partir
de un número de teléfono, información adicional agregada de múltiples fuentes:
presencia en plataformas de redes sociales, cuentas de mensajería asociadas,
menciones en bases de datos públicas, exposición en filtraciones de datos
conocidas o vínculos con correos electrónicos.

**PhoneInfoga** es una de las herramientas de código abierto más utilizadas
en este ámbito. Acepta un número en formato E.164 y realiza búsquedas
automáticas sobre él en múltiples fuentes, incluyendo validación de rango,
búsqueda en repositorios públicos y consulta de servicios de reconocimiento
de número. Su resultado es un resumen de lo que está disponible en las fuentes
que consulta, lo que varía según la exposición pública del número. Su
limitación principal es que depende de la cobertura de las APIs y fuentes
que utiliza, que no son exhaustivas.

Las plataformas de inteligencia comercial como **Maltego**, **Skopenow** o
**Pipl** permiten enriquecer un número telefónico mediante módulos de consulta
automatizada en múltiples fuentes simultáneas, presentando los resultados
en forma de grafo relacional. Su uso requiere licencias específicas y, en
muchos casos, credenciales de acceso a APIs de terceros. Su valor es alto
en investigaciones complejas que requieren cruzar múltiples entidades
digitales, pero su coste y curva de aprendizaje los hacen más apropiados para
unidades especializadas que para uso generalizado.

Los servicios de verificación de exposición en filtraciones de datos que
incluyen números de teléfono —como algunas versiones avanzadas de **Have I
Been Pwned** o servicios similares con cobertura extendida— permiten comprobar
si un número ha aparecido en incidentes de seguridad conocidos. Cuando es
así, pueden revelar información adicional incluida en la filtración, como
correos electrónicos asociados o nombres de usuario. Su valor y sus limitaciones
son análogos a los descritos para el correo electrónico en el capítulo
anterior.

### 7.4. Herramientas de investigación en mensajería y servicios asociados

Las aplicaciones de mensajería son uno de los contextos más relevantes en
que un número de teléfono puede haber dejado rastro digital accesible. Los
principales servicios de mensajería —WhatsApp, Telegram, Signal, Viber—
utilizan el número de teléfono como identificador principal de la cuenta.
La investigación de la presencia de un número en estos servicios puede revelar
información de perfil que el titular ha hecho pública: nombre visible, foto
de perfil, descripción o estado, y en algunos casos la fecha de la última
conexión o la confirmación de que el número tiene cuenta activa.

El acceso a esa información, desde el punto de vista metodológico, debe
abordarse con especial cautela. Verificar si un número tiene cuenta en un
servicio de mensajería puede hacerse de distintas formas: la más básica es
añadir el número a la agenda de un dispositivo y comprobar si el servicio lo
reconoce y muestra perfil. Este procedimiento, aunque técnicamente simple,
implica interacción directa con la infraestructura del servicio y puede,
en algunos casos, generar notificaciones o registros que el titular del número
puede percibir. El investigador debe valorar este riesgo en función del tipo
de investigación y adoptar las cautelas de OPSEC desarrolladas en el capítulo
anterior.

En **Telegram**, la búsqueda de usuarios por número puede realizarse a través
del cliente, y los canales y grupos públicos permiten búsqueda libre de
usuarios y contenido. La visibilidad del perfil asociado a un número depende
de la configuración de privacidad que el usuario haya establecido. Los canales
y grupos públicos de Telegram son indexados por algunos motores de búsqueda,
lo que permite localizar publicaciones vinculadas a un número o a un alias
de Telegram mediante búsqueda en abierto.

Herramientas como **TelegramDB** o servicios similares de indexación de
contenido público de Telegram pueden revelar la participación de un número
o alias en grupos o canales públicos, lo que en investigaciones de fraude
organizado, venta ilícita o coordinación delictiva puede ser especialmente
relevante. Su uso está sujeto a las mismas cautelas de proporcionalidad y
pertinencia que cualquier otra herramienta de investigación.

### 7.5. Herramientas de búsqueda en anuncios, directorios y marketplaces

La búsqueda del número en plataformas de anuncios clasificados, portales de
compraventa, marketplaces generalistas y portales de servicios es una de las
líneas más productivas en investigaciones de fraude online. Plataformas como
**Wallapop**, **Milanuncios**, **Vibbo**, **InfoJobs**, **Fotocasa**,
**Idealista** o los marketplaces de las grandes plataformas de comercio
electrónico pueden contener anuncios en los que el número ha sido publicado
como dato de contacto.

La búsqueda debe realizarse con el número en sus distintas variantes de
formato, dado que las plataformas no siempre normalizan los números
almacenados. Muchas de estas plataformas permiten la búsqueda por teléfono
de forma directa o a través de su motor interno. Los resultados pueden revelar
el historial de anuncios publicados con ese número, la actividad previa del
vendedor, los artículos ofrecidos y, en muchos casos, nombres visibles,
fotografías o valoraciones de otros usuarios.

Las herramientas de búsqueda agregada de anuncios —que rastrean múltiples
plataformas simultáneamente— pueden acelerar este proceso y ampliar la
cobertura, aunque el investigador debe verificar los resultados en la
plataforma original antes de preservarlos.

### 7.6. Herramientas de búsqueda inversa de imágenes vinculadas al número

Cuando la investigación del número revela una foto de perfil —en un servicio
de mensajería, en un anuncio o en un perfil social—, esa imagen puede ser
objeto de búsqueda inversa para identificar su posible reutilización en otros
contextos. Herramientas como **Google Images**, **TinEye**, **Yandex Images**
o **Bing Visual Search** permiten subir una imagen y buscar sus apariciones
en el espacio público digital.

La búsqueda inversa de imágenes puede revelar que la foto de perfil ha sido
tomada de un tercero o de una fuente pública —lo que indica suplantación de
identidad—, o puede confirmar la coherencia del perfil al mostrar que la
misma imagen aparece en otros contextos vinculados al mismo sujeto. Ambos
resultados son informativamente relevantes para la investigación, aunque con
significados opuestos.

### 7.7. Herramientas de preservación y documentación

La preservación de los hallazgos vinculados a un número de teléfono debe
seguir los mismos principios generales descritos en capítulos anteriores.
Las herramientas de archivado web, los sellos temporales verificables y el
hash criptográfico del contenido preservado son los instrumentos básicos.
Los perfiles de mensajería, los anuncios y los contenidos en plataformas
deben ser preservados de forma inmediata, dado su potencial de eliminación
por el titular o por la plataforma.

---

## 8. Procedimiento operativo de investigación a partir de un número de teléfono

El siguiente procedimiento describe una secuencia realista de trabajo para
el investigador que recibe un número de teléfono como dato de partida. No
es un protocolo rígido: es una guía de referencia que debe adaptarse a las
circunstancias de cada investigación.

**Primera fase: análisis y normalización.** El investigador comienza por
registrar el número en el formato en que fue obtenido y producir las variantes
de formato necesarias para las búsquedas. Consulta un servicio de validación
para obtener información básica sobre el rango y el operador asignado.
Documenta el contexto de aparición del número con toda la información
disponible.

**Segunda fase: búsqueda de presencia pública.** El investigador realiza
búsquedas en motores generalistas con todas las variantes de formato del
número, entre comillas. Consulta las principales plataformas de anuncios
y marketplaces relevantes para el tipo de actividad investigada. Consulta
directorios inversos de teléfono con cobertura del país correspondiente.
Preserva de forma inmediata cualquier resultado relevante encontrado.

**Tercera fase: enriquecimiento.** El investigador utiliza herramientas de
enriquecimiento como PhoneInfoga para obtener un resumen de la presencia
conocida del número en fuentes accesibles. Consulta servicios de identificación
de caller ID que puedan tener el número en sus bases de datos. Verifica si
el número aparece en filtraciones de datos conocidas.

**Cuarta fase: investigación en mensajería.** Desde un entorno técnico
segregado y con las cautelas de OPSEC correspondientes, el investigador
verifica la presencia del número en los principales servicios de mensajería
relevantes para el caso. Documenta y preserva cualquier información de perfil
accesible: nombre visible, foto de perfil, descripción, confirmación de cuenta
activa.

**Quinta fase: investigación de pivotes.** A partir de los hallazgos obtenidos
—nombre visible, foto de perfil, alias, correo electrónico, denominación
comercial, anuncios publicados—, el investigador identifica los pivotes más
prometedores y los investiga de forma prioritaria. Cada nuevo hallazgo es
documentado y preservado antes de seguir el siguiente pivote.

**Sexta fase: síntesis y valoración.** El investigador evalúa el conjunto
de los hallazgos, valora la coherencia interna del perfil de actividad
construido, identifica las incertidumbres que permanecen abiertas y determina
qué diligencias adicionales —con cobertura judicial— serían necesarias para
confirmar o profundizar en los resultados obtenidos.

---

## 9. Interpretación de hallazgos, cautelas y errores frecuentes

### 9.1. Niveles de inferencia y prudencia interpretativa

Como en el caso del correo electrónico, el investigador debe mantener
separados tres niveles de inferencia al trabajar con un número de teléfono.
La **presencia** indica que el número ha aparecido en un contexto determinado.
La **reutilización** indica que el mismo número ha sido empleado en varios
contextos, lo que puede ser indicio de que corresponde a un mismo titular.
La **atribución personal firme** requiere corroboración independiente y, en
la mayoría de los casos, diligencias judiciales al operador o al proveedor
del servicio.

La diferencia entre un número vinculado a una persona real y un número
desechable usado por un sujeto organizado puede no ser detectable solo mediante
OSINT. El investigador que asume que todo número de teléfono con presencia
en mensajería corresponde necesariamente al usuario real del teléfono está
cometiendo un error de interpretación que puede distorsionar la investigación.

### 9.2. Errores frecuentes en la investigación de teléfonos

El primer error frecuente es la **normalización incorrecta**, que produce
búsquedas que pierden resultados relevantes porque el número se busca solo
en uno de sus formatos posibles. La variante con prefijo internacional, sin
prefijo, con espacios y sin ellos puede devolver resultados distintos.

El segundo error es la **dependencia exclusiva de una sola herramienta**:
asumir que si una herramienta de caller ID no devuelve resultados, el número
no tiene presencia relevante. Las distintas herramientas tienen coberturas
distintas, y la combinación de varias produce resultados más completos que
cualquiera de ellas por separado.

El tercero es la **sobreinterpretación de los resultados de caller ID**: asumir
que el nombre devuelto por Truecaller o servicios similares corresponde al
titular legal del número. Ese nombre es el que aparece en la agenda de los
usuarios que tienen instalada la aplicación y han sincronizado sus contactos,
y puede ser un apodo, un nombre comercial, un alias o directamente un nombre
incorrecto.

El cuarto es **no verificar la coherencia temporal**: un número puede haber
estado vinculado a un sujeto en el pasado y haber sido reasignado a otro
usuario posteriormente. Los resultados que devuelven las herramientas pueden
corresponder a distintos momentos temporales, y el investigador debe intentar
establecer, cuando sea posible, la vigencia temporal de cada hallazgo.

---

## 10. Aspectos jurídicos, deontológicos y probatorios específicos

### 10.1. Límites de la investigación en fuentes abiertas

La investigación de un número de teléfono en fuentes abiertas está sujeta
a los mismos principios de legalidad, proporcionalidad y minimización
desarrollados en el capítulo jurídico del manual. La búsqueda de la presencia
pública de un número, la consulta de anuncios en plataformas y la verificación
de perfil visible en servicios de mensajería que no requieren autenticación
son actuaciones que pueden realizarse dentro de los límites de la investigación
en fuentes abiertas.

El acceso al contenido de comunicaciones, la interceptación de mensajes o
llamadas, la obtención de los datos de registro o de la titularidad del número
mediante diligencia al operador, y cualquier actuación que implique medidas
limitativas de derechos fundamentales requieren autorización judicial. La
comunicación telefónica y los datos vinculados a ella gozan de protección
constitucional como parte del secreto de las comunicaciones y del derecho a
la intimidad.

### 10.2. Tratamiento de datos personales en la investigación

Los resultados obtenidos en la investigación de un número de teléfono son,
con frecuencia, datos de carácter personal: nombres, imágenes, actividad
comercial o de contacto vinculada a una persona identificable. Su tratamiento
en el marco de una investigación policial está sometido a los principios de
finalidad legítima, proporcionalidad y minimización. El investigador debe
documentar con precisión la finalidad de cada búsqueda y evitar la acumulación
de información personal más allá de lo estrictamente necesario para los fines
de la investigación en curso.

### 10.3. Preservación y valor probatorio de los hallazgos

La preservación adecuada de los hallazgos —con sello temporal verificable,
hash del contenido preservado, registro de la fuente y descripción del método
de obtención— es la condición que permite que un hallazgo en fuente abierta
pueda ser incorporado con valor al procedimiento. Un resultado de directorio
inverso o una foto de perfil de mensajería sin contexto, sin trazabilidad
de obtención y sin sello temporal tiene un valor procesal muy reducido frente
a cualquier impugnación.

---

## 11. Caso práctico aplicado

### Caso práctico: Identificación de un operador de fraude de inversión a través de un número de teléfono de contacto

**Supuesto de hecho**

Una unidad de policía judicial especializada en delitos económicos recibe
varias denuncias de ciudadanos que refieren haber sido captados a través de
redes sociales para invertir en una plataforma de criptomonedas fraudulenta.
Tras una captación inicial por mensajería, los denunciantes fueron derivados
a un supuesto asesor de inversiones que contactó con ellos por teléfono y
por aplicaciones de mensajería, induciéndoles a realizar transferencias que
posteriormente no pudieron recuperar. Varios denunciantes conservan el número
de teléfono desde el que recibieron las llamadas y mensajes del supuesto
asesor.

**Dato o indicio de partida**

Un número de teléfono móvil con prefijo español desde el que se realizaron
llamadas y mensajes a las víctimas en el marco de la captación fraudulenta.

**Hipótesis de trabajo**

El número puede haber sido utilizado en otros contextos digitales relacionados
con la actividad fraudulenta —anuncios, perfiles de mensajería, publicaciones
en redes— y puede estar vinculado a otros identificadores digitales del sujeto
o de la organización detrás del fraude.

**Actuaciones realizadas**

El investigador normaliza el número en sus distintas variantes de formato y
realiza una búsqueda directa en motores generalistas con cada variante entre
comillas. La búsqueda devuelve un resultado en un portal de denuncias de fraude
telefónico en que varios usuarios han reportado el mismo número como asociado
a llamadas de inversión fraudulenta, con fechas que coinciden con el periodo
denunciado.

Se consulta el número en las principales plataformas de anuncios. En una
plataforma de anuncios clasificados se localizan dos anuncios publicados en
fechas anteriores en que el número aparece como contacto para servicios de
asesoría financiera. Los anuncios incluyen un nombre comercial y una dirección
de correo electrónico. Se preservan de inmediato mediante archivado web con
sello temporal y hash.

Desde un entorno técnico segregado y con las cautelas de OPSEC descritas en
el capítulo cuarto, el investigador verifica la presencia del número en
WhatsApp y en Telegram. En WhatsApp, el perfil asociado al número muestra
una foto de perfil con la imagen de un hombre de mediana edad y un nombre
visible. La foto de perfil es preservada de inmediato. En Telegram, el número
no devuelve perfil visible.

La foto de perfil de WhatsApp es sometida a búsqueda inversa de imágenes
mediante Google Images y Yandex Images. El resultado revela que la misma
imagen aparece en el perfil de LinkedIn de una persona con nombre diferente
al que figura en el perfil de WhatsApp, lo que apunta hacia una posible
suplantación de identidad de esa persona en la construcción del perfil
fraudulento. Se documenta este hallazgo con detalle.

La dirección de correo electrónico encontrada en los anuncios se investiga
siguiendo la metodología del capítulo anterior. La búsqueda revela su
reutilización en otros anuncios de asesoría financiera publicados en plataformas
distintas bajo distintos nombres comerciales.

**Hallazgos obtenidos**

El número de teléfono ha sido utilizado como dato de contacto en anuncios
de asesoría financiera en al menos dos plataformas, en fechas compatibles con
las denuncias. Está asociado a un perfil de WhatsApp con imagen tomada de
una identidad real suplantada. El correo electrónico vinculado al número
aparece en una red de anuncios similares bajo distintas denominaciones
comerciales. El portal de denuncias de fraude telefónico confirma que el número
ha sido reportado por otros afectados.

**Análisis e interpretación**

El conjunto de hallazgos configura un patrón coherente de actividad fraudulenta
organizada: múltiples anuncios bajo distintas identidades comerciales que
comparten el mismo número y correo electrónico de contacto, suplantación de
identidad en el perfil de mensajería y multiplicidad de víctimas que reportan
el mismo número. La hipótesis de una operación organizada, posiblemente con
varios operadores bajo el mismo paraguas, es la más consistente con los datos
disponibles, aunque requiere corroboración mediante diligencias adicionales.

**Explotación policial y documental**

Los hallazgos se documentan en un informe de inteligencia que describe la
secuencia de búsquedas realizadas, las plataformas consultadas, los resultados
obtenidos y la metodología de preservación aplicada. El informe señala la
posible víctima de suplantación identificada —la persona cuya imagen fue
tomada para el perfil de WhatsApp— y plantea la posibilidad de notificarle
la circunstancia. Fundamenta la solicitud de información al operador de
telecomunicaciones sobre la titularidad y el historial de actividad del número,
así como solicitudes a las plataformas de anuncios sobre los datos de registro
del anunciante.

**Lecciones operativas**

Este caso ilustra la importancia de la búsqueda en múltiples plataformas,
incluidos portales de denuncia ciudadana de fraude telefónico, que pueden
confirmar o ampliar la información disponible. La búsqueda inversa de la
imagen de perfil fue determinante para detectar la suplantación de identidad.
La correlación entre el número y el correo electrónico de los anuncios permitió
ampliar la investigación a una red de actividad fraudulenta más amplia que
la visible desde el dato de partida inicial. Y la secuencia de preservación
desde el primer momento garantizó la trazabilidad de todos los hallazgos.

---

## 12. Conclusiones operativas

El número de teléfono es uno de los identificadores digitales con mayor
potencial de pivot investigativo en el ecosistema del cibercrimen. Su
relativamente alta estabilidad, su frecuente reutilización en múltiples
plataformas y su papel como eje de autenticación en servicios de mensajería
lo convierten en un dato de partida de gran valor cuando el investigador sabe
cómo trabajarlo.

Ese valor, sin embargo, solo se realiza cuando se trabaja con método: la
normalización correcta, la búsqueda sistemática en múltiples plataformas, el
enriquecimiento mediante herramientas especializadas, la investigación prudente
en servicios de mensajería y la explotación de los pivotes que cada hallazgo
genera son los pasos que transforman un número en conocimiento investigativo
útil. La prudencia en la atribución, la verificación cruzada de los resultados
y la documentación rigurosa del proceso son las condiciones que hacen que ese
conocimiento sea también procesalmente sostenible.

---

## 13. Checklist final de trabajo

**Análisis inicial y normalización**

- Registrar el número en el formato en que fue obtenido y el contexto
  exacto de aparición.
- Normalizar el número al formato E.164 con prefijo internacional.
- Generar todas las variantes de formato relevantes para las búsquedas.
- Consultar un servicio de validación para obtener información básica
  sobre el rango y el operador asignado.
- Identificar provisionalmente el tipo probable de número: móvil convencional,
  VoIP, virtual o desechable.

**Búsqueda de presencia pública**

- Buscar el número en motores generalistas con cada variante de formato
  entre comillas.
- Consultar las principales plataformas de anuncios y marketplaces relevantes.
- Consultar directorios inversos de teléfono con cobertura del país
  correspondiente.
- Buscar el número en portales de denuncia de fraude telefónico.
- Preservar de forma inmediata cualquier resultado relevante con sello
  temporal y hash.

**Enriquecimiento**

- Usar herramientas de enriquecimiento como PhoneInfoga u otras disponibles.
- Consultar servicios de caller ID con cobertura del país del número.
- Verificar posible exposición del número en filtraciones de datos conocidas.

**Investigación en mensajería**

- Desde entorno técnico segregado, verificar presencia en los principales
  servicios de mensajería relevantes para el caso.
- Documentar y preservar información de perfil visible: nombre, foto,
  descripción.
- Realizar búsqueda inversa de la foto de perfil si está disponible.

**Investigación de pivotes**

- Identificar todos los datos adicionales revelados por los hallazgos:
  nombre, correo, alias, foto, denominación comercial.
- Priorizar los pivotes en función de las preguntas de investigación
  definidas.
- Investigar cada pivote priorizado con la misma disciplina metodológica
  y de preservación.

**Interpretación, síntesis y explotación**

- Distinguir explícitamente entre presencia, reutilización y atribución.
- Verificar la coherencia temporal de los hallazgos.
- Contrastar cada resultado relevante con al menos una fuente independiente.
- Identificar qué diligencias adicionales con cobertura judicial son
  necesarias para completar la investigación.
- Elaborar el informe con descripción metodológica completa, archivos de
  preservación verificables y exposición honesta de los límites de las
  conclusiones.

---