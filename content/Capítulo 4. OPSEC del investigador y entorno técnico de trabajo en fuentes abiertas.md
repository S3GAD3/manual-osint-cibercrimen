# Capítulo 4. OPSEC del investigador y entorno técnico de trabajo en fuentes abiertas

---

## 1. Introducción

Existe una tendencia extendida a pensar que la investigación en fuentes
abiertas es, por su propia naturaleza, una actividad inocua desde el punto
de vista de la exposición del investigador. Si la información es pública, si
no se accede a ningún sistema sin autorización y si no se realizan actuaciones
invasivas, ¿qué riesgo puede tener el simple acto de consultar? Esta
percepción, comprensible en quienes se aproximan al OSINT desde una perspectiva
principalmente metodológica o jurídica, es también una de las fuentes de error
operativo más frecuentes y de consecuencias más difíciles de reparar.

La realidad del entorno digital es que toda consulta deja huella. Toda
conexión a un servidor remoto revela, al menos, una dirección IP de origen.
Toda visita a un perfil, todo acceso a un documento, toda interacción con
un enlace puede ser registrada, analizada e interpretada por quien controla
el recurso consultado. En investigaciones de cibercrimen, donde el objetivo
puede ser un sujeto con conocimientos técnicos, un grupo organizado con
capacidad de monitorización activa o una infraestructura diseñada
deliberadamente para detectar accesos no autorizados, la exposición
inadvertida del investigador puede comprometer no solo su seguridad personal,
sino también la integridad de la investigación, la posibilidad de futuras
actuaciones y la eficacia del procedimiento en su conjunto.

La seguridad operacional —OPSEC, por sus siglas en inglés— es la disciplina
que aborda esta dimensión del trabajo investigador. No es un conjunto de
técnicas de ocultación ni una práctica orientada a la evasión de controles;
es una cultura profesional de gestión de riesgos que todo investigador que
trabaja en entornos digitales debe integrar como parte natural de su método
de trabajo. Este capítulo desarrolla sus principios, sus aplicaciones
prácticas y sus límites desde la perspectiva del investigador de fuentes
abiertas en el ámbito del cibercrimen.

---

## 2. Finalidad investigadora del capítulo

Los capítulos anteriores establecieron los fundamentos conceptuales,
jurídicos y metodológicos de la investigación OSINT. Este capítulo aborda
una dimensión que a menudo se trata como un añadido técnico, pero que en
realidad forma parte estructural del trabajo profesional: la protección del
investigador y la gestión rigurosa del entorno técnico desde el que opera.

Su función dentro del manual es dotar al lector de una comprensión clara
de los riesgos que el trabajo en fuentes abiertas puede generar para él mismo
y para la investigación, y de los criterios y las prácticas que permiten
gestionarlos con proporcionalidad y eficacia. No pretende convertir al
investigador en un especialista en ciberseguridad, sino en un profesional
consciente de su huella digital, de los riesgos de exposición y de la
importancia de trabajar en entornos controlados, segregados y documentables.

Este capítulo resulta especialmente relevante en investigaciones de
cibercrimen, donde la sofisticación técnica de algunos objetivos hace que
los riesgos de detección, alertado prematuro o contaminación de evidencias
sean genuinamente significativos. Pero sus principios son aplicables, en
mayor o menor medida, a cualquier investigación en fuentes abiertas que
pretenda conducirse con rigor profesional.

---

## 3. Objeto de análisis y punto de partida

### 3.1. Qué debe entenderse por OPSEC en el contexto del OSINT

El término OPSEC —*Operational Security*— tiene su origen en el ámbito
militar, donde designa el conjunto de procesos orientados a proteger la
información crítica de una operación frente al conocimiento o la explotación
por parte del adversario. En el contexto de la investigación en fuentes
abiertas, su significado se adapta a las circunstancias específicas del
trabajo investigador: se trata de identificar qué información sobre el
investigador, su identidad, su metodología o la propia investigación puede
ser accesible o deducible por el objetivo, y adoptar medidas razonables para
reducir esa exposición.

La OPSEC aplicada al OSINT no persigue la invisibilidad absoluta del
investigador ni la eliminación de toda huella digital, objetivos que son
técnicamente irreales en cualquier escenario práctico. Persigue una reducción
razonable y proporcionada de los riesgos identificables, mediante la adopción
de prácticas de trabajo que minimicen la probabilidad de que el investigador
sea detectado, identificado o que su actividad permita al objetivo anticiparse
a la investigación.

### 3.2. Riesgos que justifican la OPSEC en investigaciones OSINT

Los riesgos operativos y técnicos que afectan al investigador en fuentes
abiertas pueden clasificarse en tres categorías principales. La primera es
la **exposición del investigador**: la posibilidad de que el objetivo detecte
que está siendo investigado, identifique la procedencia institucional del
investigador o, en los casos más graves, localice su identidad personal o
profesional. La segunda es la **contaminación de la investigación**: la
posibilidad de que el entorno técnico desde el que opera el investigador
altere los hallazgos, introduzca variables extrañas en el proceso de obtención
o comprometa la integridad de los materiales preservados. La tercera es la
**exposición a riesgos técnicos**: la posibilidad de que el investigador,
al acceder a recursos controlados por el objetivo o a entornos potencialmente
maliciosos, descargue código dañino, exponga credenciales o permita el acceso
no autorizado a sus sistemas.

Estas tres categorías de riesgo justifican, por sí solas, que la OPSEC sea
tratada como una dimensión estructural de la metodología investigadora y no
como un complemento opcional.

---

## 4. Fundamentos de la seguridad operacional aplicada al OSINT

### 4.1. La OPSEC como actitud profesional

La OPSEC no es, fundamentalmente, una cuestión de herramientas. Es una
actitud: la disposición del investigador a pensar en términos de riesgo antes
de actuar, a identificar qué información puede revelar su actividad y a tomar
decisiones conscientes sobre cómo gestionar esa exposición. Un investigador
que trabaja con las mejores herramientas técnicas disponibles pero que no ha
interiorizado esta actitud seguirá siendo vulnerable a errores operativos
que ninguna tecnología puede compensar.

Esa actitud implica, en la práctica, hacerse sistemáticamente una serie de
preguntas antes de cada actuación significativa: ¿qué información sobre mí
o sobre esta investigación puede revelar esta acción? ¿Quién controla el
recurso al que voy a acceder y qué puede registrar ese acceso? ¿Existe alguna
razón para pensar que este recurso ha sido configurado para detectar o registrar
accesos? ¿Qué consecuencias podría tener para la investigación que el objetivo
supiera que ha sido consultado en este momento? ¿Estoy trabajando en un entorno
técnico adecuado para esta actuación?

### 4.2. OPSEC, metodología y protección del procedimiento

La relación entre OPSEC, metodología investigadora y protección del
procedimiento judicial es más estrecha de lo que a primera vista puede
parecer. Un entorno técnico mal gestionado no solo expone al investigador;
puede comprometer la cadena de preservación de los hallazgos, introducir
incertidumbre sobre la integridad del material obtenido o dificultar la
explicación del proceso de obtención ante el órgano judicial. Un investigador
que trabaja desde un dispositivo personal compartido con actividad doméstica,
con sesiones de navegación mezcladas y sin control sobre los metadatos que
genera, no puede garantizar con rigor la integridad de su proceso de trabajo.

La OPSEC bien entendida contribuye, por tanto, a la calidad probatoria del
trabajo investigador, no solo a la seguridad personal del investigador. Es
parte del mismo rigor profesional que se exige en la documentación de
hallazgos, en la verificación de fuentes o en la formulación de hipótesis.

### 4.3. Lo que la OPSEC no es

Resulta necesario delimitar con claridad lo que la OPSEC aplicada al OSINT
no es, especialmente en el contexto de un manual dirigido a profesionales
de la policía judicial. La OPSEC no es una práctica de ocultación de la
actividad del investigador frente a sus propias autoridades o frente al
órgano judicial. No es un mecanismo para eludir la supervisión institucional.
No es una autorización para usar técnicas o herramientas que no serían
admisibles en otro contexto. Y no es una garantía de impunidad técnica.

El investigador que adopta medidas de seguridad operacional actúa dentro de
su marco institucional, bajo la supervisión que corresponde a su función y
con la documentación de su actividad que exige la legalidad vigente. Lo que
la OPSEC proporciona es protección frente al objetivo de la investigación,
no opacidad frente al sistema del que el investigador forma parte.

---

## 5. Riesgos de exposición, trazabilidad y contaminación del entorno investigador

### 5.1. La huella digital del investigador

Toda consulta realizada desde un dispositivo conectado a internet genera,
como mínimo, un registro de la dirección IP de origen en el servidor del
recurso consultado. Esa dirección IP puede ser suficiente, en muchos contextos,
para identificar la red institucional desde la que opera el investigador, el
proveedor de servicios de internet asociado o el rango geográfico de la
conexión. En investigaciones contra objetivos con capacidad técnica, esta
información puede ser suficiente para deducir que el acceso fue de origen
policial o gubernamental.

Más allá de la dirección IP, los navegadores generan automáticamente un
conjunto de parámetros —versión del navegador, sistema operativo, idioma
configurado, extensiones instaladas, resolución de pantalla y otros— que
forman lo que se conoce como *fingerprint* o huella de navegación. Esa huella
puede ser suficientemente específica para identificar de forma consistente
un mismo dispositivo o configuración a través de múltiples consultas, incluso
en ausencia de cookies o de inicio de sesión. El investigador que no gestiona
su huella de navegación puede estar revelando, sin saberlo, una identidad
técnica consistente a través de todas sus consultas.

### 5.2. El riesgo de alertado prematuro

Uno de los riesgos más significativos en investigaciones de cibercrimen es
el alertado prematuro del objetivo: la posibilidad de que el sujeto o la
organización investigada detecte que está siendo objeto de atención y modifique
su comportamiento, elimine rastros, abandone infraestructuras o adopte
contramedidas que dificulten o imposibiliten la continuación de la
investigación. Este riesgo es especialmente relevante cuando se consultan
recursos directamente bajo el control del objetivo —un sitio web gestionado
por el sujeto investigado, un canal de comunicación que monitoriza sus accesos,
un perfil en una plataforma que registra las visitas recibidas— o cuando
se interactúa con servicios asociados a la infraestructura del objetivo.

El investigador debe asumir que cualquier recurso bajo control del objetivo
puede ser también un instrumento de monitorización activa. Esta asunción
no debe paralizarlo, pero sí obligarlo a planificar sus accesos de forma que
minimicen la exposición antes de disponer de información suficiente para
fundamentar diligencias judiciales que permitan actuar de forma más abierta.

### 5.3. La mezcla de entornos como fuente de riesgo

Uno de los errores operativos más frecuentes y más difíciles de gestionar
en la práctica es la mezcla de entornos: el uso del mismo dispositivo, la
misma sesión de navegación o la misma dirección IP para actividades personales,
profesionales y de investigación. Esta mezcla genera varios riesgos
simultáneos. Primero, puede revelar al objetivo información sobre la identidad
personal o profesional del investigador a través de metadatos, historiales
o asociaciones entre sesiones. Segundo, puede comprometer la integridad del
entorno de trabajo al introducir variables externas —extensiones, cookies,
credenciales, historial de búsqueda— que afectan a la neutralidad técnica
del proceso de obtención. Y tercero, puede dificultar la explicación del
proceso investigador ante el órgano judicial, que puede cuestionar la
separación entre actividad profesional y personal si ambas se han llevado
a cabo en el mismo entorno.

### 5.4. Riesgos asociados a contenidos potencialmente maliciosos

La investigación en fuentes abiertas implica, con frecuencia, el acceso a
recursos cuya fiabilidad o intención no puede garantizarse: sitios web
asociados a infraestructuras delictivas, perfiles en plataformas no
supervisadas, archivos distribuidos en redes de intercambio, documentos
publicados en repositorios sin control editorial o enlaces compartidos en
foros de acceso restringido. Cualquiera de estos recursos puede contener
código malicioso diseñado para ejecutarse en el dispositivo del visitante,
explotar vulnerabilidades del navegador, capturar credenciales o registrar
información sobre el sistema desde el que se realiza el acceso.

La descarga accidental de código malicioso no solo expone al investigador
y a su institución; puede comprometer el entorno técnico de trabajo de manera
que afecte a la integridad de todos los hallazgos obtenidos desde ese entorno.
La cautela ante enlaces desconocidos, archivos no solicitados, acortadores
de URL, redirecciones inesperadas y contenido activo no es paranoia; es
higiene técnica básica.

---

## 6. Segregación de entornos, identidades y recursos técnicos

### 6.1. El principio de segregación

El principio de segregación es el fundamento operativo de la OPSEC en el
trabajo con fuentes abiertas. Consiste en separar de forma sistemática los
entornos, identidades, dispositivos, sesiones y recursos utilizados para
distintas finalidades, de modo que una eventual exposición o compromiso en
uno de esos compartimentos no afecte a los demás.

En la práctica, la segregación implica, como mínimo, que el investigador
no utiliza los mismos dispositivos, las mismas cuentas de usuario ni las
mismas sesiones de navegación para su actividad personal, para su actividad
profesional cotidiana y para sus actividades de investigación en fuentes
abiertas. Cada uno de esos ámbitos debe tener su propio espacio técnico,
sus propias credenciales y sus propios recursos de trabajo.

### 6.2. Entornos aislados y sistemas dedicados

Para investigaciones de mayor sensibilidad —aquellas en que el riesgo de
alertado del objetivo es significativo, en que los recursos a consultar son
potencialmente hostiles o en que la integridad de los hallazgos tiene una
relevancia probatoria directa—, la segregación debe ir más allá de la simple
separación de cuentas y sesiones.

El uso de máquinas virtuales es una práctica habitual en estos contextos.
Una máquina virtual es un entorno de trabajo completamente aislado que opera
sobre el hardware del investigador pero que puede configurarse, controlarse
y restaurarse de forma independiente del sistema operativo principal. Su
principal ventaja desde el punto de vista de la OPSEC es que permite trabajar
en un entorno limpio y reproducible, que puede ser restaurado a un estado
conocido antes de cada sesión de investigación, eliminando cualquier residuo
de sesiones anteriores que pudiera comprometer la neutralidad técnica del
trabajo. Su segunda ventaja es que un eventual compromiso del entorno virtual
—por descarga de código malicioso, por ejemplo— queda contenido en ese
compartimento y no afecta al sistema principal.

Para investigaciones de nivel de riesgo elevado o para equipos con volumen
significativo de trabajo en fuentes abiertas, el uso de dispositivos físicos
dedicados exclusivamente a investigación OSINT, sin uso personal ni mezcla
con otros sistemas institucionales, es la opción que ofrece mayor garantía
de segregación. El coste de este enfoque es mayor, pero también lo es la
solidez del entorno de trabajo.

Los sistemas desechables o de uso único —dispositivos o entornos configurados
para una investigación específica y descartados o restaurados al estado inicial
al concluirla— son una opción viable en investigaciones particularmente
sensibles, aunque su implementación requiere una planificación específica que
cada unidad debe adaptar a sus recursos y procedimientos internos.

### 6.3. Gestión de sesiones, credenciales y persistencia

La persistencia de datos entre sesiones es uno de los vectores de exposición
más frecuentes y menos visibles. Las cookies, los historiales de navegación,
las credenciales almacenadas, los formularios autocumplimentados y los
archivos de caché acumulan información sobre la actividad del investigador
que puede ser accesible para recursos externos, puede revelar información
sobre sesiones anteriores o puede introducir variables que afecten al
comportamiento del navegador durante la sesión de investigación.

Una práctica básica de higiene técnica consiste en iniciar cada sesión de
investigación desde un estado limpio —sin cookies, sin historial, sin
credenciales almacenadas—, bien mediante el uso de perfiles de navegación
independientes, bien mediante el modo de navegación privada del navegador,
bien mediante la restauración del entorno virtual al estado de inicio definido.
Ninguna de estas opciones elimina toda huella de navegación, pero sí reduce
de forma significativa la persistencia de datos entre sesiones y la posibilidad
de que una sesión revele información sobre las anteriores.

La gestión de credenciales merece una atención específica. El uso de
credenciales institucionales para acceder a plataformas o servicios en el
contexto de una investigación puede revelar la identidad del investigador o
de su organización. El uso de credenciales personales mezcla el ámbito
investigador con el personal. La creación y gestión de identidades de trabajo
específicas para la actividad investigadora —correos electrónicos, cuentas
en plataformas, perfiles de acceso— es una práctica que exige, a su vez,
criterio y documentación institucional adecuada.

---

## 7. Navegación segura, acceso controlado y gestión del riesgo técnico

### 7.1. Cautelas ante recursos de riesgo desconocido

No todos los recursos que el investigador debe consultar en el curso de una
investigación tienen el mismo perfil de riesgo. Un registro oficial de
dominios o una base de datos institucional tienen un perfil de riesgo técnico
muy bajo. Un sitio web gestionado por el objetivo de la investigación, un
foro de acceso libre en la web superficial, un archivo distribuido en redes
de intercambio o un enlace compartido en una plataforma de mensajería no
verificada tienen un perfil de riesgo significativamente más alto.

Ante recursos de riesgo desconocido, el investigador debe aplicar criterios
de cautela proporcionados: consultar desde un entorno aislado, evitar la
ejecución de código no solicitado, desactivar los elementos de renderización
activa del navegador cuando sea posible, y no descargar archivos cuyo origen
o integridad no pueda verificarse sin haberlos analizado previamente en un
entorno controlado.

### 7.2. El problema de los acortadores de URL y las redirecciones

Los acortadores de URL son un recurso habitual en el entorno digital que
plantea un riesgo específico para el investigador: el destino real del enlace
no es visible antes de hacer clic, y la resolución del enlace puede implicar
una secuencia de redirecciones que pasen por servidores bajo el control de
terceros antes de llegar al destino final. Esos servidores intermedios pueden
registrar el acceso, incluidos parámetros de identificación del dispositivo.

La práctica adecuada ante acortadores de URL o ante enlaces cuyo destino
no está verificado consiste en resolverlos previamente mediante servicios
de expansión de URL que permiten ver el destino final sin acceder a él
directamente, y en valorar el riesgo del destino antes de realizar el acceso
desde el entorno de trabajo principal.

### 7.3. Metadatos en archivos y documentos

Los archivos descargados en el curso de una investigación pueden contener
metadatos relevantes para la propia investigación —información sobre el
autor, el dispositivo, la fecha de creación o la geolocalización—, pero
también pueden introducir, si se abren sin precaución, riesgos de ejecución
de código malicioso. La apertura de documentos de ofimática, archivos PDF,
imágenes o archivos comprimidos descargados de fuentes no verificadas debe
realizarse en entornos aislados del sistema principal, y los metadatos deben
ser extraídos mediante herramientas específicas antes de abrir el archivo con
su aplicación nativa.

Igualmente, el investigador debe ser consciente de que los archivos que
genera en el curso de su trabajo —capturas, informes, documentos de análisis—
contienen a su vez metadatos que pueden revelar información sobre el entorno
desde el que fueron generados. La gestión de esos metadatos, tanto para su
explotación investigadora como para evitar su exposición inadvertida, forma
parte de la disciplina técnica del trabajo en fuentes abiertas.

### 7.4. La diferencia operativa entre observar, consultar, descargar e interactuar

Desde el punto de vista de la exposición del investigador y del riesgo de
alertado, no todas las formas de acceso a un recurso tienen el mismo perfil
de riesgo. Observar —acceder a un recurso público sin ningún tipo de
interacción adicional— genera la menor huella posible. Consultar —realizar
búsquedas, acceder a perfiles, explorar registros— genera algo más de huella,
pero sigue siendo una actividad de bajo impacto en la mayoría de los
escenarios. Descargar —obtener y conservar un archivo o contenido— deja una
huella más significativa, tanto en el servidor del recurso como en el entorno
técnico del investigador. Interactuar —suscribirse, seguir, comentar, enviar
mensajes, solicitar información— es la forma de acceso con mayor riesgo de
alertado, ya que puede generar notificaciones directas al titular del recurso.

El investigador debe ser consciente de estas diferencias y de sus implicaciones
para cada actuación concreta. En términos generales, cualquier forma de
interacción directa con recursos bajo el control del objetivo debe ser
considerada con especial detenimiento y, en muchos casos, reservada para
fases de la investigación en que el alertado del objetivo ya no tiene
consecuencias operativas significativas o para las que existe cobertura
judicial suficiente.

---

## 8. Criterios de protección proporcional y límites de la OPSEC

### 8.1. No toda investigación requiere el mismo nivel de protección

La aplicación de medidas de seguridad operacional debe ser proporcional al
riesgo identificado en cada investigación. Una consulta de registros públicos
sobre un dominio en el marco de una investigación de fraude menor no requiere
el mismo despliegue técnico que el análisis de la infraestructura de una red
de cibercrimen organizada con capacidad técnica demostrada. La búsqueda de
información sobre una persona jurídica en registros mercantiles públicos no
genera los mismos riesgos que la exploración de perfiles en plataformas
controladas por un sujeto investigado por delitos graves.

El investigador debe desarrollar la capacidad de valorar el perfil de riesgo
de cada investigación y de cada actuación concreta dentro de ella, y de
calibrar las medidas de protección en función de ese perfil. La aplicación
indiscriminada del máximo nivel de seguridad operacional a todas las
actuaciones sería ineficiente y, en la práctica, insostenible. La ausencia
de criterio mínimo de seguridad en cualquier actuación es una práctica
profesionalmente deficiente.

### 8.2. Los límites reales de la OPSEC

La OPSEC reduce riesgos; no los elimina. Ninguna configuración técnica, por
sofisticada que sea, puede garantizar la invisibilidad completa del investigador
en todos los escenarios posibles. Las redes de anonimización tienen límites
técnicos y puntos de vulnerabilidad. Los entornos virtuales no son
intrínsecamente invulnerables. La segregación de identidades puede romperse
por un error humano. Y cualquier medida técnica puede ser superada por
recursos suficientemente avanzados o por errores en su implementación.

El investigador que asume que sus medidas de OPSEC le hacen invisible o
invulnerable está en una posición de riesgo más grave que el que reconoce
los límites de esas medidas y actúa en consecuencia. La OPSEC profesional
se construye sobre el realismo, no sobre la confianza ciega en la tecnología.
La actitud adecuada es la de quien gestiona el riesgo con criterio y con
consciencia de que siempre existe un margen de exposición residual que debe
ser tenido en cuenta.

### 8.3. Proporcionalidad, criterio y supervisión institucional

Las decisiones sobre el nivel de protección técnica que debe emplearse en
cada investigación no deben tomarse únicamente de forma individual. En
unidades especializadas, deben responder a protocolos institucionales que
garanticen la coherencia del enfoque, la supervisión adecuada de las
actuaciones y la compatibilidad con los requisitos jurídicos y documentales
del procedimiento. La OPSEC es una práctica profesional que se ejerce dentro
de un marco institucional, no al margen de él.

---

## 9. Documentación del entorno técnico y buenas prácticas profesionales

### 9.1. Cuándo y cómo documentar el entorno técnico

En la mayoría de las investigaciones en fuentes abiertas, la documentación
del entorno técnico de trabajo no tiene relevancia directa para el valor
de los hallazgos. La descripción de la fuente, el método de obtención, la
fecha y la hora son los elementos esenciales de la preservación. Sin embargo,
en determinados supuestos, la descripción del entorno técnico puede resultar
relevante o incluso necesaria: cuando el método de obtención ha requerido
el uso de herramientas o configuraciones específicas cuya descripción contribuye
a la comprensión del proceso; cuando la integridad del hallazgo podría ser
cuestionada en ausencia de esa descripción; o cuando el procedimiento
institucional exige un estándar de documentación que incluye las condiciones
técnicas de trabajo.

En esos supuestos, la documentación del entorno debe ser suficientemente
descriptiva para permitir la comprensión del proceso, sin necesidad de revelar
detalles técnicos que puedan comprometer futuras investigaciones o capacidades
institucionales.

### 9.2. Buenas prácticas profesionales de entorno

Las buenas prácticas de gestión del entorno técnico de trabajo en
investigaciones OSINT pueden resumirse en torno a cinco principios que el
investigador debe interiorizar como parte de su rutina profesional.

El **principio de limpieza inicial** establece que toda sesión de investigación
debe iniciarse desde un entorno técnico libre de residuos de sesiones
anteriores: sin cookies activas, sin historial de navegación relevante, sin
credenciales almacenadas que no correspondan al perfil investigador definido
para esa sesión.

El **principio de segregación** exige que los entornos de investigación, los
profesionales cotidianos y los personales no se mezclen, y que los recursos
—dispositivos, cuentas, sesiones— de cada ámbito se mantengan separados de
forma sistemática.

El **principio de contención** implica que los riesgos técnicos que puedan
surgir en el transcurso de la investigación —descarga de contenido de origen
desconocido, acceso a recursos potencialmente hostiles— se gestionen dentro
de entornos aislados que eviten su propagación al sistema principal.

El **principio de trazabilidad** establece que el entorno de trabajo debe
ser gestionado de forma que permita reconstruir el proceso de obtención de
cada hallazgo con la precisión necesaria para su explotación posterior y para
su eventual explicación en sede judicial.

El **principio de proporcionalidad** exige que el nivel de protección técnica
sea coherente con el perfil de riesgo de la investigación, sin incurrir ni
en el exceso de complejidad que genera ineficiencia ni en la negligencia que
genera exposición.

---

## 10. Caso práctico aplicado

### Caso práctico: Investigación sobre infraestructura de phishing activa con riesgo de alertado del objetivo

**Supuesto de hecho**

Una unidad especializada en cibercrimen tiene conocimiento, a través de una
denuncia de una entidad bancaria, de la existencia de una campaña de phishing
activa que utiliza un dominio fraudulento para capturar credenciales de clientes.
La entidad denunciante ha notificado el dominio a su proveedor de seguridad,
pero la infraestructura sigue activa. El investigador debe analizar en
profundidad esa infraestructura en fuentes abiertas antes de solicitar las
diligencias judiciales necesarias, sin que el operador de la infraestructura
sea alertado prematuramente.

**Dato o indicio de partida**

El dominio fraudulento identificado por la entidad bancaria y la dirección
IP del servidor en que se aloja, obtenida de la denuncia.

**Hipótesis de trabajo**

La infraestructura utilizada para la campaña de phishing puede formar parte
de una operación más amplia, y el análisis en fuentes abiertas de los registros
de dominio, la infraestructura del servidor y la actividad pública asociada
puede revelar información adicional sobre el operador o sobre otras campañas
vinculadas. El investigador asume que el servidor puede estar configurado
para registrar y analizar los accesos recibidos.

**Actuaciones realizadas**

El investigador inicia la sesión de trabajo desde un entorno virtual limpio,
configurado específicamente para esta investigación y sin conexión con los
entornos de trabajo cotidianos. La sesión comienza con la consulta de registros
de dominio y registros DNS a través de herramientas que permiten obtener esa
información sin acceder directamente al servidor fraudulento, evitando así
cualquier conexión que pueda ser registrada por el objetivo.

La consulta de los registros WHOIS revela que el dominio fue registrado cinco
días antes de la denuncia, con datos de titular anonimizados. Los registros
de resolución DNS muestran que el dominio apunta a una dirección IP que, al
ser consultada mediante herramientas de análisis de infraestructura en abierto,
muestra otros cuarenta y dos dominios alojados en el mismo servidor. Varios
de esos dominios presentan nombres similares a entidades financieras de
distintos países.

El investigador no accede directamente al sitio web fraudulento ni a ninguno
de los dominios identificados en el servidor compartido. En su lugar, utiliza
servicios de captura web que realizan la consulta de forma mediada y devuelven
una copia del contenido sin que el servidor del destino reciba la conexión
directa del investigador. El contenido del sitio es preservado mediante este
método, con sello temporal y hash criptográfico del archivo resultante.

Uno de los dominios alojados en el mismo servidor aparece, al ser consultado
en un repositorio de indicadores de compromiso de acceso público, vinculado
a una campaña de phishing previa dirigida contra otra entidad financiera
en un país diferente, con fechas de actividad que se solapan parcialmente
con las de la campaña actual.

**Hallazgos obtenidos**

El análisis permite identificar una infraestructura compartida que agrupa
múltiples campañas de phishing activas o recientes, sin haber accedido
directamente al servidor del objetivo ni generado ninguna conexión directa
que pudiera ser registrada por el operador. Los hallazgos incluyen registros
preservados con trazabilidad completa y sin exposición del investigador.

**Análisis e interpretación**

La coherencia entre los hallazgos obtenidos —el patrón de dominios, las
fechas de registro, la actividad previa vinculada a la misma infraestructura—
apunta hacia una operación organizada con cierta continuidad en el tiempo.
La utilización de un servidor compartido para múltiples campañas simultáneas
es un patrón reconocible en operaciones de phishing a escala. El investigador
registra explícitamente que no ha podido confirmar si los distintos dominios
corresponden al mismo operador o a distintos actores que utilizan los servicios
del mismo proveedor de alojamiento.

**Explotación policial y documental**

Los hallazgos se documentan en un informe técnico de inteligencia que describe
con precisión el entorno de trabajo utilizado, el método de consulta empleado
para evitar el acceso directo al servidor del objetivo, los recursos consultados
y la metodología de preservación. El informe fundamenta la solicitud judicial
de información al proveedor del servicio de alojamiento y al registrador del
dominio, y señala la existencia de posibles campañas vinculadas que podrían
ser objeto de coordinación con autoridades de otros países.

**Lecciones operativas**

Este caso ilustra de forma directa el valor de la OPSEC en investigaciones
contra objetivos con capacidad técnica. El acceso directo al servidor
fraudulento, aunque hubiera producido hallazgos equivalentes, habría generado
un registro en el servidor que podría haber alertado al operador. El uso de
métodos de consulta mediada permitió obtener la información necesaria sin
generar ese riesgo. La segregación del entorno de trabajo garantizó la
integridad del proceso y la trazabilidad de los hallazgos. Y la documentación
del entorno técnico en el informe final reforzó la solidez del material
producido para su uso judicial.

---

## 11. Conclusiones operativas

La seguridad operacional en investigaciones OSINT no es un lujo técnico
reservado a unidades especializadas de alto nivel. Es una dimensión del
trabajo profesional que todo investigador que opera en entornos digitales
debe integrar en su práctica cotidiana, con el nivel de complejidad que cada
tipo de investigación requiere y con la consciencia de que su ausencia puede
tener consecuencias reales sobre la eficacia de la investigación, sobre la
seguridad del propio investigador y sobre la solidez del procedimiento.

El principio que debe guiar esta práctica no es el de la invisibilidad, que
es inalcanzable, sino el de la reducción razonable de riesgos identificables:
saber dónde está la exposición, decidir conscientemente cómo gestionarla y
adoptar las medidas que sean proporcionadas al riesgo real de cada situación.
Un investigador que ha interiorizado esa lógica trabaja de forma más segura,
más eficiente y más sólida desde el punto de vista profesional, con
independencia de las herramientas concretas que tenga a su disposición.

La OPSEC, en definitiva, forma parte del mismo rigor que se exige en la
formulación de hipótesis, en la verificación de hallazgos o en la
documentación de la cadena de preservación. No es un añadido opcional; es
parte de la calidad del trabajo.

---

## 12. Checklist final de trabajo

**Antes de iniciar cualquier sesión de investigación**

- Verificar que se trabaja desde un entorno técnico segregado del personal
  y del profesional cotidiano.
- Confirmar que la sesión se inicia desde un estado limpio: sin cookies,
  historial ni credenciales residuales de sesiones anteriores.
- Evaluar el perfil de riesgo de la investigación y determinar el nivel
  de aislamiento técnico adecuado.
- Identificar qué recursos de la investigación pueden estar bajo el control
  del objetivo y planificar el acceso a ellos de forma que minimice el
  riesgo de alertado.

**Durante la investigación**

- Evitar el acceso directo a recursos bajo control del objetivo cuando
  exista un método alternativo de obtención de la misma información.
- Aplicar cautela ante enlaces desconocidos, acortadores de URL,
  redirecciones y archivos de origen no verificado.
- Abrir archivos descargados de fuentes no verificadas en entornos aislados,
  no en el sistema principal de trabajo.
- No interactuar directamente con perfiles, canales o servicios del objetivo
  a menos que esté planificado y sea operativamente adecuado en esa fase.
- Mantener separados los entornos de navegación de la investigación y los
  de trabajo cotidiano.

**Al preservar hallazgos**

- Preservar el contenido mediante métodos que no requieran acceso directo
  al servidor del objetivo cuando sea posible.
- Generar hash criptográfico y sello temporal de los archivos preservados
  desde el momento de su obtención.
- Documentar el método técnico de obtención cuando sea relevante para la
  trazabilidad del hallazgo.
- Verificar que los archivos generados no contienen metadatos que revelen
  información sensible sobre el entorno de trabajo.

**Al cerrar la sesión**

- Eliminar residuos de sesión del entorno de trabajo: cookies, historial,
  caché, archivos temporales.
- Si se utiliza una máquina virtual, evaluar si debe restaurarse al estado
  inicial antes de la siguiente sesión.
- Documentar cualquier incidencia técnica ocurrida durante la sesión que
  pueda tener relevancia para la integridad del proceso.
- Guardar de forma segura los materiales obtenidos en el repositorio
  designado para la investigación.

---