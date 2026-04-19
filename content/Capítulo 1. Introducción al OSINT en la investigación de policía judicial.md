# Capítulo 1. Introducción al OSINT en la investigación de policía judicial

---

## 1. Introducción

La investigación criminal contemporánea opera en un entorno radicalmente
distinto al de hace apenas tres décadas. La expansión de internet, la
generalización de las comunicaciones digitales, la proliferación de
plataformas de interacción social y la progresiva digitalización de las
transacciones económicas han transformado no solo el modo en que las personas
se relacionan y actúan, sino también la forma en que delinquen y, de manera
igualmente relevante, los rastros que dejan al hacerlo. El delincuente que
opera en el entorno digital —con independencia de la naturaleza concreta de
su actividad— genera de forma casi inevitable una serie de huellas digitales
dispersas en múltiples entornos, algunas de las cuales permanecen accesibles
en abierto, sin necesidad de medidas técnicas o jurídicas extraordinarias
para su consulta.

Este fenómeno ha convertido las fuentes abiertas en un espacio de interés
creciente para la investigación policial. No porque la información pública
haya sustituido a otras fuentes o diligencias de investigación, sino porque
su correcta explotación puede aportar orientación, contexto, hipótesis de
trabajo y relaciones entre entidades que, de otro modo, serían difíciles de
detectar en fases tempranas de una investigación. La disciplina que engloba
la obtención, análisis y explotación de esa información es lo que se conoce
como OSINT —acrónimo del inglés *Open Source Intelligence*—, y su
aplicación al ámbito de la policía judicial constituye el objeto central de
este manual.

El presente capítulo tiene por finalidad sentar las bases conceptuales sobre
las que se construirá el resto de la obra. No pretende anticipar el
desarrollo metodológico ni el análisis jurídico que corresponden a otros
capítulos, pero sí establecer con claridad qué debe entenderse por OSINT
en el contexto de la investigación criminal, qué lo diferencia de una mera
búsqueda de información en internet, qué papel puede desempeñar en la
investigación del cibercrimen y qué exige del profesional que lo práctica.

---

## 2. Finalidad investigadora del capítulo

Todo manual con vocación operativa debe comenzar por un punto de anclaje
conceptual que permita al lector entender no solo qué se va a estudiar, sino
por qué merece la pena estudiarlo con rigor y con un enfoque específico. Este
capítulo cumple esa función dentro del manual.

Su propósito no es ofrecer una definición enciclopédica del OSINT ni un
repaso histórico exhaustivo de su evolución. Su propósito es más concreto y
más útil: explicar qué significa aplicar fuentes abiertas a la investigación
de cibercrimen desde la perspectiva de la policía judicial, con qué
fundamentos conceptuales debe abordarse esa tarea, qué oportunidades ofrece
y qué límites impone, y por qué el método y el criterio analítico son tan
importantes como las herramientas técnicas disponibles.

Al terminar este capítulo, el lector debe haber comprendido que el OSINT no
es sinónimo de búsqueda en Google, ni de consulta de perfiles en redes
sociales, ni de uso de herramientas automatizadas. Es una disciplina de
investigación con entidad propia, que exige formación, método, criterio
crítico y comprensión de su lugar dentro del conjunto del procedimiento. Solo
desde esa comprensión tiene sentido abordar los capítulos siguientes, que
desarrollarán en profundidad los distintos ámbitos de aplicación, las
técnicas concretas y el marco jurídico y operativo correspondiente.

---

## 3. Objeto de análisis y punto de partida

### 3.1. Las fuentes abiertas como categoría investigadora

Se entiende por fuentes abiertas, a efectos de este manual, toda aquella
información que es pública o públicamente accesible, sin que su obtención
requiera medidas técnicas de evasión de controles de acceso ni autorización
judicial específica. Esta definición abarca un espectro muy amplio: desde
la información publicada voluntariamente por los usuarios en plataformas
sociales, hasta los datos registrales asociados a dominios de internet,
pasando por foros, publicaciones en servicios de mensajería con alcance
público, registros mercantiles, bases de datos gubernamentales, archivos
históricos de páginas web, imágenes geolocalizadas o publicaciones en
mercados digitales de distinto tipo.

La amplitud de esa categoría es, al mismo tiempo, una oportunidad y un
desafío. Una oportunidad porque la cantidad de información disponible en
abierto es de una magnitud sin precedentes históricos. Un desafío porque
esa abundancia no equivale por sí sola a utilidad investigadora. La
información dispersa, no verificada, no contextualizada o mal interpretada
no solo carece de valor operativo, sino que puede inducir a error y
distorsionar el desarrollo de una investigación.

### 3.2. El rastro digital como punto de partida

En el contexto del cibercrimen, el punto de partida de una investigación
en fuentes abiertas suele ser lo que puede denominarse un rastro digital
mínimo: un dato concreto, aparentemente aislado, que el investigador obtiene
a través de una denuncia, de una diligencia de investigación previa, de la
propia actividad de monitorización o de la colaboración con otras unidades
o servicios. Ese rastro puede adoptar formas muy diversas: una dirección de
correo electrónico utilizada en una estafa, un número de teléfono asociado
a un perfil fraudulento, un nombre de usuario o alias empleado en un foro
o en una plataforma de compraventa, una imagen enviada en el marco de una
extorsión, un dominio utilizado para alojar un sitio web fraudulento, o una
dirección de cartera de criptomonedas vinculada a una transacción de origen
delictivo.

Cada uno de esos elementos constituye un potencial punto de pivote: un
dato desde el que puede iniciarse un proceso de búsqueda, correlación y
análisis que permita expandir el conocimiento disponible sobre un sujeto,
una organización o una infraestructura. La identificación correcta del punto
de partida, la comprensión de su naturaleza y la elección de la estrategia
de explotación adecuada son decisiones que corresponden al investigador, y
que condicionan en buena medida la utilidad de los hallazgos posteriores.

### 3.3. OSINT como disciplina diferenciada

El acrónimo OSINT —*Open Source Intelligence*— tiene su origen en el ámbito
de la inteligencia estratégica y militar, donde la explotación sistemática
de información pública fue reconocida como una capacidad autónoma con valor
propio. En el contexto de la investigación criminal, el término ha sido
adoptado con una extensión significativa de su significado original, para
designar el conjunto de procesos, técnicas, criterios y herramientas
orientados a obtener inteligencia aplicable a partir de información accesible
en fuentes abiertas.

La distinción entre OSINT y una simple búsqueda de información es
conceptualmente importante y tiene consecuencias prácticas directas. El
OSINT no es el acto de buscar; es el proceso estructurado de obtener,
valorar, verificar, relacionar, interpretar y documentar información
procedente de fuentes abiertas con una finalidad concreta, en un contexto
jurídicamente delimitado y con un resultado orientado a la producción de
inteligencia útil para la investigación. La herramienta —cualquiera que sea—
es un medio al servicio de ese proceso, no el proceso en sí mismo.

---

## 4. Fundamentos conceptuales del OSINT aplicado a la investigación criminal

### 4.1. La cadena dato-información-inteligencia

Para comprender qué es el OSINT y qué no es, resulta necesario distinguir
entre conceptos que en el lenguaje cotidiano se utilizan indistintamente,
pero que en el contexto de la investigación criminal tienen significados
precisos y consecuencias diferenciadas.

Un **dato** es la unidad mínima de información: un correo electrónico, un
número, una fecha, un nombre de usuario. Por sí solo, carece de significado
operativo. Su valor depende del contexto en que se inserta y de las
relaciones que puede establecer con otros datos.

La **información** surge cuando un conjunto de datos es organizado y
relacionado de modo que adquiere un significado comprensible. Saber que una
dirección de correo electrónico ha sido utilizada para registrar tres dominios
distintos en los últimos seis meses es información: tiene contexto, tiene
estructura, tiene un significado que va más allá del dato aislado.

La **inteligencia** es el producto del análisis riguroso de información
orientado a apoyar una decisión o una línea de acción. En el contexto de la
policía judicial, la inteligencia derivada de fuentes abiertas tiene valor
cuando permite orientar líneas de investigación, sustentar hipótesis de
trabajo, identificar relaciones entre sujetos o entidades, o contextualizar
hechos dentro de un patrón de conducta más amplio. La inteligencia no es
certeza; es conocimiento trabajado que reduce la incertidumbre y mejora la
capacidad de decisión.

Junto a estos tres conceptos, el investigador debe manejar con claridad las
nociones de **indicio** y **evidencia**, que tienen una dimensión
específicamente jurídico-procesal. Un indicio es un hecho conocido del que
puede inferirse, mediante un proceso lógico-deductivo, la existencia de otro
hecho desconocido relevante para la investigación. Una evidencia —o prueba,
en términos procesales— es un elemento que, obtenido y preservado conforme
a la legalidad vigente, puede ser incorporado al procedimiento y sometido a
contradicción.

Esta distinción tiene implicaciones directas para el trabajo con fuentes
abiertas: un hallazgo en OSINT puede constituir un indicio valioso, puede
orientar una línea de investigación y puede sustentar la solicitud de
diligencias más invasivas; pero su valor probatorio en sentido estricto
depende de su correcta obtención, documentación y preservación, cuestiones
que se abordarán en profundidad en capítulos posteriores.

### 4.2. Por qué el OSINT ha adquirido relevancia creciente en la investigación criminal

La relevancia actual del OSINT en la investigación policial no es el
resultado de una moda tecnológica ni de una decisión institucional aislada.
Es la consecuencia lógica de una transformación estructural del entorno en
que se produce la delincuencia. La vida social, económica y comunicativa se
ha desplazado de manera masiva hacia el entorno digital, y ese desplazamiento
ha arrastrado consigo también la actividad delictiva.

El delincuente que opera en el entorno digital —o que utiliza herramientas
digitales para la comisión de delitos de cualquier naturaleza— genera de
forma casi inevitable rastros distribuidos en múltiples plataformas y
servicios. Muchos de esos rastros son el resultado de decisiones voluntarias:
la creación de un perfil, la publicación de contenido, el registro de un
dominio, la participación en un foro. Otros son el resultado de procesos
técnicos automatizados que escapan al control consciente del delincuente:
metadatos en imágenes, registros de actividad en plataformas, huellas de
infraestructura, asociaciones entre identificadores. Unos y otros pueden ser,
en distintas circunstancias, objeto de explotación investigadora en el marco
del OSINT.

La disponibilidad de esa información no implica, sin embargo, que su
obtención y explotación sea trivial. La fragmentación de los rastros entre
múltiples plataformas, la volatilidad de determinados contenidos, la
posibilidad de manipulación o de atribución errónea, y la necesidad de operar
con garantías jurídicas suficientes hacen de la investigación en fuentes
abiertas una tarea que exige competencia profesional específica.

### 4.3. Lo que el OSINT no es

Resulta igualmente importante delimitar qué no debe entenderse por OSINT
en el contexto de este manual. No es OSINT la obtención de información
mediante el acceso no autorizado a sistemas, cuentas o comunicaciones
privadas, por más que la información resultante sea técnicamente
«accesible». Tampoco es OSINT el uso de información obtenida a través de
fugas de datos ilícitas o de mercados negros de información, aunque esos
datos se encuentren disponibles en determinados espacios de la red. No es
OSINT, en fin, cualquier forma de obtención de información que requiera
medidas de investigación limitativas de derechos fundamentales, aun cuando
no implique acceso físico.

El OSINT, tal como se concibe en este manual, se circunscribe a la
información que es genuinamente pública o públicamente accesible, obtenida
por medios legítimos, en el marco de una actividad investigadora respetuosa
con el ordenamiento jurídico vigente. Dentro de ese marco, su potencial es
muy significativo. Fuera de él, cualquier resultado obtenido, por valioso
que parezca, puede comprometer la viabilidad del procedimiento y la
responsabilidad del investigador.

---

## 5. El OSINT en el contexto del cibercrimen y de la policía judicial

### 5.1. La especificidad del cibercrimen como ámbito de investigación

El cibercrimen no es una categoría delictiva homogénea ni cerrada. Bajo esa
denominación se agrupan conductas muy diversas en cuanto a su naturaleza,
su estructura organizativa, sus motivaciones y sus consecuencias. Desde el
fraude informático clásico hasta el ransomware dirigido a infraestructuras
críticas, desde la sextorsión individual hasta la operación coordinada de
grupos de phishing a escala transnacional, el cibercrimen abarca un espectro
amplísimo que tiene, sin embargo, un denominador común: la utilización del
entorno digital como escenario, instrumento o vector de la actividad
delictiva.

Esa característica común tiene una consecuencia directa para la investigación:
en el cibercrimen, los rastros relevantes no se encuentran exclusivamente en
los sistemas afectados o en las comunicaciones interceptadas. Se encuentran
también —y a menudo de forma muy significativa— en el espacio abierto de
internet: en registros de dominios, en plataformas de publicación de
contenido, en perfiles sociales, en foros especializados, en directorios de
servicios, en historiales de infraestructura técnica o en la actividad
pública de carteras de criptomonedas. La investigación en fuentes abiertas
no es un añadido opcional a la investigación del cibercrimen; es, en muchos
casos, uno de sus vectores naturales.

### 5.2. Funciones del OSINT en la investigación de cibercrimen

La utilidad del OSINT en el marco de la investigación de cibercrimen puede
articularse en torno a cuatro funciones principales, que no son excluyentes
entre sí y que con frecuencia operan de forma simultánea.

La primera es la **función de orientación**: las fuentes abiertas pueden
proporcionar, desde fases muy tempranas de una investigación, indicios sobre
la identidad, la localización, los métodos o la infraestructura de un sujeto
o grupo investigado. Esos indicios permiten al investigador definir líneas
de trabajo, priorizar hipótesis y dirigir recursos de forma más eficiente
hacia los vectores más prometedores.

La segunda es la **función de enriquecimiento**: partiendo de un dato
inicial —un correo electrónico, un número de teléfono, un alias— la
investigación en fuentes abiertas puede añadir capas sucesivas de información
que amplían la comprensión disponible sobre el sujeto o la estructura
investigada. Cada nuevo dato que se incorpora puede abrir nuevas posibilidades
de pivote y generar conexiones que, de otro modo, no habrían sido visibles.

La tercera es la **función de contextualización**: el OSINT permite situar
los hechos investigados dentro de un marco más amplio de actividad,
vinculaciones, antecedentes y patrones. Esa contextualización es
especialmente valiosa en investigaciones que se dirigen contra estructuras
organizadas, donde la comprensión de los vínculos entre actores y la
identificación de roles dentro del grupo puede resultar determinante.

La cuarta es la **función de apoyo a la solicitud de diligencias**: los
hallazgos obtenidos en fuentes abiertas pueden fundamentar, con base
suficiente y documentación adecuada, la solicitud de diligencias de mayor
intensidad investigadora —intervenciones, registros, solicitudes de
información a proveedores— que sin ese respaldo previo podrían resultar de
difícil justificación ante la autoridad judicial.

### 5.3. El lugar del OSINT dentro de la investigación policial

Es importante subrayar que el OSINT no sustituye a ningún otro medio de
investigación ni dispensa al investigador de la obligación de practicar las
diligencias que correspondan en cada fase del procedimiento. Su valor es
complementario y funcional: opera mejor cuando se integra dentro de una
estrategia de investigación coherente, cuando sus resultados se contrastan
con otras fuentes de información disponibles y cuando su explotación se lleva
a cabo con la misma disciplina metodológica que se exige en cualquier otra
actividad investigadora de la policía judicial.

El investigador que trabaja con fuentes abiertas no actúa en un espacio
paralelo o informal respecto al procedimiento. Actúa dentro de él, con las
mismas obligaciones de rigor, documentación y respeto a la legalidad que
corresponden a cualquier otra diligencia, y con la conciencia de que los
hallazgos obtenidos pueden tener, si son correctamente tratados, consecuencias
relevantes en el desarrollo del caso.

---

## 6. Alcance, potencial y límites del OSINT

### 6.1. El potencial real de las fuentes abiertas

El potencial del OSINT en la investigación de cibercrimen es genuinamente
significativo, y sería un error subestimarlo por un exceso de cautela
institucional. En investigaciones de fraude en línea, suplantación de
identidad, extorsión digital o infraestructuras de phishing, los hallazgos
obtenidos en fuentes abiertas han resultado con frecuencia determinantes para
la identificación de autores, la comprensión de estructuras organizativas y
la localización de activos. La disponibilidad de información en registros
de dominios, plataformas sociales, foros especializados, servicios de
almacenamiento público o exploradores de bloques de criptomonedas ofrece al
investigador competente posibilidades que habrían sido impensables en el
contexto analógico.

La clave no reside, sin embargo, en la disponibilidad de esa información,
sino en la capacidad del investigador para identificar qué buscar, dónde
buscarlo, cómo verificar lo encontrado y cómo integrarlo en una narrativa
investigadora coherente. Dos investigadores con acceso a las mismas
herramientas y los mismos datos pueden obtener resultados radicalmente
distintos en función de su criterio analítico, su conocimiento del entorno
y su disciplina metodológica.

### 6.2. Los límites que deben tenerse en cuenta

El OSINT también tiene límites que el investigador debe conocer con la misma
claridad con que conoce sus posibilidades. El primero de ellos es la
**volatilidad de la información**: los contenidos publicados en plataformas
digitales pueden ser eliminados, modificados o desactivados en cualquier
momento, lo que impone una exigencia inmediata de documentación y preservación
de los hallazgos desde el primer momento de su obtención.

El segundo límite es el riesgo de **sobreinterpretación**: la coincidencia
de un alias, la similitud de un patrón de conducta o la presencia de
características comunes entre dos perfiles no son, por sí solas, prueba de
identidad ni de vinculación. El investigador debe distinguir con rigor entre
correlación y atribución, entre hipótesis y certeza, entre indicio y
evidencia. Una atribución errónea derivada de una investigación en fuentes
abiertas puede no solo inutilizar el trabajo realizado, sino generar
consecuencias graves para personas ajenas a los hechos investigados.

El tercer límite es el de la **manipulación deliberada**: un sujeto
experimentado puede construir una presencia digital falsa, sembrar pistas
erróneas o utilizar identidades de terceros para dificultar su trazabilidad.
El investigador debe aproximarse a los resultados de la investigación en
fuentes abiertas con sentido crítico y contrastar sus hallazgos con otras
fuentes disponibles antes de asumir su validez.

El cuarto límite es el de la **fiabilidad diferencial de las fuentes**: no
toda la información accesible en abierto tiene el mismo grado de fiabilidad.
El investigador debe valorar cada fuente en función de su naturaleza, su
origen, su trayectoria y la posibilidad de verificación independiente de su
contenido. La información procedente de un registro oficial de dominios no
tiene el mismo estatus que la procedente de un perfil anónimo en un foro;
la publicada por una plataforma con políticas de verificación de identidad
no equivale a la de un servicio de publicación sin restricciones.

---

## 7. Dimensión profesional del investigador en fuentes abiertas

### 7.1. Por qué la herramienta no sustituye al investigador

Existe una tendencia, especialmente entre quienes se aproximan al OSINT desde
una perspectiva puramente técnica, a identificar la calidad de la
investigación con la sofisticación de las herramientas empleadas. Esta
tendencia es comprensible —la oferta de herramientas en el ámbito del OSINT
es amplia y en constante desarrollo— pero también engañosa. La herramienta
puede facilitar la obtención, la organización o la visualización de datos;
no puede, en cambio, sustituir al investigador en las decisiones que
determinan el valor real de la investigación.

La elección del punto de partida, la definición de la hipótesis de trabajo,
la valoración de la fiabilidad de cada fuente, la interpretación de las
relaciones entre entidades, la detección de incoherencias o la identificación
de pistas falsas son operaciones que requieren criterio, experiencia y
capacidad analítica. Son, en definitiva, operaciones cognitivas que pertenecen
al investigador y que ninguna herramienta puede realizar por sí sola con
garantías suficientes.

### 7.2. Las competencias del investigador en OSINT

El perfil profesional del investigador competente en OSINT aplicado al
cibercrimen integra capacidades que proceden de ámbitos distintos y que deben
articularse de forma coherente. La competencia técnica —conocimiento de las
herramientas, de los entornos digitales, de los protocolos y de los registros
relevantes— es necesaria pero no suficiente. A ella deben añadirse la
capacidad analítica para estructurar hipótesis y contrastarlas, el
conocimiento jurídico suficiente para operar dentro del marco legal vigente,
la disciplina documental para preservar y registrar correctamente los
hallazgos y la prudencia profesional para no asumir como válidas
conclusiones que no han sido debidamente contrastadas.

Esta combinación de competencias no es innata ni se adquiere de forma
espontánea. Se construye a través de formación específica, de la práctica
reflexiva y del acceso a recursos que sistematicen el conocimiento disponible
de forma rigurosa. Es precisamente esa construcción la que este manual aspira
a apoyar.

### 7.3. La seguridad operativa del investigador

Un aspecto que no puede omitirse en este primer capítulo, aunque será
desarrollado en profundidad en un capítulo específico, es el de la seguridad
operativa del propio investigador durante el desarrollo de sus actividades
en fuentes abiertas. La investigación en entornos digitales, especialmente
cuando se dirige contra sujetos con capacidad técnica o contra estructuras
organizadas, implica riesgos que el investigador debe conocer y mitigar: la
exposición de su identidad o de la de su unidad, la contaminación de la
investigación por contacto inadvertido con el sujeto investigado, o la
exposición a contenidos dañinos o a técnicas de rastreo inverso son
situaciones que pueden comprometer tanto al investigador como al procedimiento.

La adopción de medidas básicas de OPSEC —seguridad operativa— no es una
exigencia de la paranoia profesional; es una condición de la investigación
responsable y competente.

---

## 8. Aspectos jurídicos, deontológicos y probatorios introductorios

Sin anticipar el análisis detallado que corresponde al capítulo específico
sobre el marco jurídico, resulta necesario introducir en este punto algunas
consideraciones generales que deben presidir desde el principio la comprensión
del OSINT como actividad investigadora de la policía judicial.

La investigación en fuentes abiertas no opera en un vacío normativo. Por más
que la información que se obtiene sea, por definición, públicamente accesible,
la actividad del investigador está sometida al ordenamiento jurídico en todos
sus aspectos: la forma en que obtiene la información, el uso que hace de ella,
la forma en que la documenta y preserva, y la manera en que la incorpora al
procedimiento. La accesibilidad técnica de una información no equivale a su
licitud como objeto de investigación policial en todo contexto y con cualquier
finalidad.

El investigador debe operar con plena conciencia de los límites que el
ordenamiento establece, especialmente en lo que respecta a la protección de
datos de carácter personal, al respeto al secreto de las comunicaciones y a
la privacidad como derecho fundamental. Esos límites no son obstáculos
arbitrarios; son garantías del Estado de Derecho que el investigador, en su
condición de agente de la ley, tiene la obligación específica de respetar y
hacer respetar.

La documentación correcta de los hallazgos —con indicación de la fuente, el
método, el momento y las circunstancias de obtención— no es una formalidad
accesoria; es una condición de validez procesal. Un hallazgo en fuente abierta
que no pueda acreditarse en su origen, en su integridad y en su cadena de
custodia puede ser impugnado con éxito en el procedimiento, con independencia
de su relevancia material. La preservación cuidadosa desde el primer momento
de la investigación no es, por tanto, una práctica que pueda dejarse para
una fase posterior; es una exigencia que opera desde el instante mismo en
que se produce el hallazgo.

---

## 9. Caso práctico aplicado

### Caso práctico: Identificación de un presunto autor de fraude en compraventa en línea a partir de un alias

**Supuesto de hecho**

Una unidad de policía judicial recibe una denuncia interpuesta por varios
ciudadanos que refieren haber sido víctimas de un fraude reiterado en una
plataforma de compraventa en línea. Los denunciantes habían adquirido
dispositivos electrónicos a un vendedor que, tras recibir el pago, no efectuó
ningún envío y eliminó su perfil de la plataforma. El fraude se había
producido en un periodo de aproximadamente cuatro semanas, con un importe
total estimado superior a tres mil euros.

**Dato o indicio de partida**

Los denunciantes coinciden en haber contactado con el vendedor a través del
alias «TechSales_Rapid» en la plataforma de compraventa. Algunos conservan
capturas de pantalla de la conversación, en las que figura también una
dirección de correo electrónico proporcionada por el vendedor para tramitar
el pago: `techsales.rapid@protonmail.com`.

**Hipótesis de trabajo**

El investigador formula la hipótesis de trabajo de que el alias y la
dirección de correo electrónico pueden haber sido utilizados por el mismo
sujeto en otros entornos o plataformas, y de que la correlación de esas
presencias digitales puede permitir la identificación de información adicional
sobre el presunto autor.

**Actuaciones realizadas**

En primer lugar, el investigador documenta y preserva todos los indicios
disponibles en las capturas de pantalla aportadas por los denunciantes,
procediendo a su sellado temporal mediante herramienta adecuada.

A continuación, realiza una búsqueda sistematizada del alias «TechSales_Rapid»
en otras plataformas de compraventa, foros especializados en tecnología,
plataformas de anuncios clasificados y servicios de almacenamiento público.
La búsqueda permite identificar el uso del mismo alias en una plataforma de
compraventa de segunda mano diferente, con actividad registrada varios meses
antes, que incluye datos de contacto distintos al correo electrónico conocido.

La dirección de correo electrónico `techsales.rapid@protonmail.com` es
sometida a verificación mediante servicios de búsqueda inversa de correo
electrónico en abierto. Los resultados muestran que esa dirección ha sido
utilizada para registrarse en un foro de tecnología, donde el usuario publicó
varias entradas con un nombre de usuario diferente pero vinculado al mismo
correo. En ese foro, el usuario había publicado fotografías de dispositivos
en venta con metadatos de imagen parcialmente conservados.

**Hallazgos obtenidos**

La correlación entre el alias original, la dirección de correo electrónico
y los perfiles identificados en otras plataformas permite al investigador
identificar un nombre de usuario adicional y un conjunto de imágenes
publicadas con metadatos que incluyen información sobre el dispositivo desde
el que fueron tomadas. Una de las imágenes, publicada en el foro, conserva
metadatos de geolocalización que sitúan su captura en un municipio concreto.
Adicionalmente, una de las publicaciones en el foro incluye una referencia
a un perfil de red social que el usuario presentó como propio.

**Análisis e interpretación**

El investigador analiza la coherencia entre los distintos hallazgos, verifica
que los patrones de actividad temporal son compatibles entre los distintos
perfiles identificados y contrasta las características de las imágenes para
evaluar si podrían proceder del mismo dispositivo. El análisis de los
metadatos de geolocalización permite circunscribir la zona geográfica de
actividad del presunto autor. La correlación de los distintos identificadores
—alias, correo, nombre de usuario en foro, perfil social— configura una red
de entidades digitales atribuibles, con razonable fundamento, a un mismo
sujeto.

**Explotación policial y documental**

Los hallazgos son documentados de forma exhaustiva mediante capturas con
sello temporal, descripción del método de obtención de cada uno y registro
de las fuentes consultadas. La información compilada es incorporada a un
informe de inteligencia que fundamenta la solicitud de diligencias
adicionales: en concreto, la solicitud de identificación del titular del
perfil de red social y la petición de información a la plataforma de
compraventa sobre los datos registrales del vendedor.

**Lecciones operativas**

Este caso ilustra varias cuestiones de interés general para la investigación
en fuentes abiertas. En primer lugar, que un dato aparentemente menor —un
alias y una dirección de correo de un servicio de comunicaciones cifradas—
puede constituir el punto de inicio de un proceso de correlación con
resultados significativos. En segundo lugar, que la disciplina de preservación
debe operar desde el primer momento, antes de que los contenidos sean
eliminados. En tercer lugar, que los metadatos de imágenes publicadas en
abierto constituyen una fuente de información frecuentemente infrautilizada.
Y en cuarto lugar, que el objetivo del trabajo en fuentes abiertas no es
la identificación definitiva del autor —que corresponderá a otras
diligencias—, sino la producción de información suficientemente articulada
para sustentar la investigación en sus fases siguientes.

---

## 10. Conclusiones operativas

El OSINT aplicado a la investigación de cibercrimen y de policía judicial
no es una novedad pasajera ni una moda tecnológica. Es la respuesta
metodológica a una transformación estructural del entorno en que se produce
la delincuencia, que ha llevado consigo la multiplicación de rastros digitales
disponibles en abierto con valor potencial para la investigación.

Su correcta explotación exige del investigador algo más que el dominio de
herramientas técnicas: exige criterio analítico para interpretar lo que se
encuentra, capacidad de síntesis para construir conocimiento a partir de
datos dispersos, disciplina documental para preservar los hallazgos con
las garantías necesarias, y conocimiento jurídico suficiente para operar
dentro del marco que el ordenamiento establece.

El OSINT no es una solución autónoma ni una garantía de resultado. Es una
capacidad investigadora que, integrada dentro de una estrategia de
investigación coherente y practicada con rigor profesional, puede ampliar
de forma sustancial las posibilidades del investigador y contribuir a la
eficacia del procedimiento. Su valor no reside en la cantidad de información
que puede obtenerse, sino en la calidad del análisis que se hace de ella y
en la solidez con que sus resultados se integran en el conjunto de la
investigación.

Los capítulos siguientes de este manual desarrollarán en profundidad los
distintos ámbitos de aplicación, las técnicas específicas, el marco jurídico
aplicable y los procedimientos de documentación y explotación que permiten
convertir la investigación en fuentes abiertas en una herramienta de
utilidad real para la policía judicial.

---

## 11. Checklist final de trabajo

**Conceptos y fundamentos**

- Verificar que se tiene claro qué se entiende por OSINT y qué lo diferencia
  de una búsqueda genérica de información.
- Confirmar que se distingue correctamente entre dato, información,
  inteligencia, indicio y evidencia.
- Comprobar que se conocen los límites del OSINT y los riesgos de
  sobreinterpretación.

**Antes de iniciar cualquier investigación en fuentes abiertas**

- Identificar con precisión el dato o indicio de partida disponible.
- Formular una hipótesis de trabajo que oriente la búsqueda.
- Definir el alcance de la investigación y las plataformas o entornos
  prioritarios.
- Verificar que se dispone de los medios técnicos y de documentación
  necesarios.
- Adoptar las medidas básicas de seguridad operativa antes de iniciar
  cualquier consulta.

**Durante la investigación**

- Documentar y preservar cada hallazgo desde el momento de su obtención,
  con indicación de fuente, método y fecha/hora.
- Verificar la fiabilidad de cada fuente consultada antes de integrar
  su contenido en la hipótesis de trabajo.
- Distinguir entre correlación e identidad, entre coincidencia e
  imputación.
- Contrastar los hallazgos con otras fuentes disponibles antes de asumir
  su validez.
- No asumir como definitiva ninguna atribución que no haya sido
  debidamente contrastada.

**Al cierre de la fase OSINT**

- Revisar que todos los hallazgos relevantes están debidamente documentados
  y preservados.
- Verificar que la documentación recoge la fuente, el método y el momento
  de cada obtención.
- Evaluar si los hallazgos obtenidos sustentan la solicitud de diligencias
  adicionales y en qué términos.
- Comprobar que ninguna actuación realizada ha excedido los límites de lo
  jurídicamente admisible sin cobertura judicial.
- Elaborar el informe de inteligencia o la diligencia policial
  correspondiente con precisión y rigor suficientes para su incorporación
  al procedimiento.

---