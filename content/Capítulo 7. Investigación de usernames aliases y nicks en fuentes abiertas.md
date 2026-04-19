# Capítulo 7. Investigación de usernames, aliases y nicks en fuentes abiertas

---

## 1. Introducción

Entre los rastros digitales que una persona deja en su actividad en línea,
pocos tienen la persistencia y la transversalidad del alias. Un nombre de
usuario creado para acceder a un foro técnico puede reaparecer, años después,
como identificador en una plataforma de compraventa, como nick en un canal
de mensajería o como nombre de perfil en una red social. Esta tendencia a
la reutilización —que responde a razones tan simples como la comodidad de
no tener que inventar nuevas identidades o la dificultad de recordar múltiples
credenciales— convierte el alias en uno de los indicadores más valiosos de
continuidad de identidad digital disponibles para el investigador en fuentes
abiertas.

En el contexto del cibercrimen, esta realidad adquiere una dimensión
especialmente relevante. El sujeto que comete fraudes en plataformas de
compraventa, que participa en foros de venta de datos robados, que gestiona
canales de extorsión en aplicaciones de mensajería o que opera infraestructuras
de phishing puede cambiar de correo electrónico, de número de teléfono o de
tarjeta SIM con relativa facilidad. Cambiar de alias requiere un esfuerzo
cognitivo y operativo mayor, y muchos sujetos no lo hacen, o lo hacen solo
parcialmente, manteniendo variantes reconocibles de su identidad original.
Ese comportamiento es una de las fuentes de información más valiosas para
el investigador que sabe buscarlo.

Sin embargo, la investigación de aliases presenta riesgos analíticos propios
que deben conocerse con la misma claridad que sus posibilidades. Los aliases
frecuentes pueden pertenecer a miles de personas distintas. Las coincidencias
nominales no implican identidad de personas. La reutilización de un alias
puede ser coincidente en lugar de deliberada. Y la atribución personal firme
a partir de un alias requiere siempre corroboración que va más allá de la
simple constatación de que el mismo nombre de usuario aparece en varios sitios.
Este capítulo desarrolla cómo trabajar con ese potencial y cómo gestionar
esos riesgos con método y criterio profesional.

---

## 2. Finalidad investigadora del capítulo

Este capítulo es el tercero de la serie aplicativa del manual, y continúa
la línea de los capítulos dedicados a correos electrónicos y números de
teléfono, trasladando la metodología OSINT a un objeto de análisis con
características propias: el username, alias o nick como huella de identidad
digital.

Su función dentro del manual es doble. Por un lado, desarrollar el marco
analítico necesario para entender qué puede y qué no puede obtenerse en
fuentes abiertas a partir de un alias, qué factores determinan su valor
investigativo y qué riesgos analíticos son específicos de este tipo de dato.
Por otro, proporcionar una secuencia de trabajo clara, aplicable al trabajo
cotidiano de la policía judicial, con orientación concreta sobre herramientas,
interpretación de resultados y documentación de hallazgos.

El capítulo resulta especialmente relevante en investigaciones de fraude
online, suplantación de identidad, extorsión digital, sextorsión, foros de
cibercrimen, comunidades de intercambio de material ilícito, venta de datos
robados, phishing, campañas de desinformación y cualquier otro contexto en
que el sujeto investigado haya construido o mantenido una presencia digital
bajo un alias identificable.

---

## 3. Objeto de análisis y punto de partida

### 3.1. El alias como objeto de investigación OSINT

A efectos de este capítulo, el término alias engloba cualquier identificador
textual que un sujeto utiliza para representarse en entornos digitales: el
username de una plataforma, el nick de un foro, el nombre de usuario de un
servicio de mensajería, el identificador de un perfil en redes sociales, el
nombre de autor en un repositorio de código o el apodo operativo en un canal
de Telegram. Todos comparten una característica fundamental: son designaciones
elegidas por el propio sujeto, a diferencia del correo electrónico o del
número de teléfono, que implican una asignación por parte de un proveedor.

Esa condición de elección propia tiene consecuencias investigativas directas.
Por un lado, el alias puede reflejar elementos de la identidad del sujeto:
intereses, referencias culturales, fragmentos de nombre o apellido, fechas
significativas, patrones lingüísticos o estilísticos. Por otro, el sujeto
puede haber elegido el mismo alias en distintos contextos por comodidad o
por hábito, lo que convierte la reutilización en un vector de investigación
especialmente poderoso.

### 3.2. Contextos de aparición y preguntas iniciales

El alias puede llegar al investigador por vías muy distintas. Las más
frecuentes son la aportación directa de la víctima —el nombre de perfil del
extorsionador, el nick del vendedor estafador, el identificador del presunto
acosador—, la identificación autónoma durante la exploración de otros indicios
—el nombre de usuario que aparece en un dominio fraudulento, en un anuncio
vinculado a la actividad investigada o en el registro de un servicio— y la
detección en el curso de búsquedas OSINT previas —el alias que aparece
asociado a un correo electrónico o a un número de teléfono ya investigados—.

Independientemente de la vía de obtención, las preguntas que el investigador
debe formular ante un alias son sistemáticamente las mismas: ¿qué tipo de
alias es este y qué indica su estructura? ¿En qué otros contextos ha aparecido?
¿Existe evidencia de reutilización en plataformas distintas? ¿Qué elementos
vinculados —correo, teléfono, foto de perfil, biografía— aparecen asociados
al alias en los entornos identificados? ¿Qué variantes del alias deben buscarse?
¿Qué fuerza tiene la hipótesis de que todas las apariciones del alias
corresponden al mismo sujeto?

---

## 4. El alias como identificador digital y pivote de investigación

### 4.1. Estabilidad, singularidad y reutilización

La utilidad investigativa de un alias depende en gran medida de tres
características que el investigador debe evaluar desde el primer momento:
su estabilidad a lo largo del tiempo, su singularidad dentro del espacio
digital y su grado de reutilización en distintas plataformas.

Un alias **estable** es aquel que el sujeto ha utilizado de forma consistente
durante un período prolongado. Esa estabilidad puede detectarse cuando el
mismo username aparece en contextos con fechas de actividad distintas: una
publicación en un foro de 2017 y un perfil activo en una plataforma de
compraventa en 2024 bajo el mismo alias son indicios de una identidad digital
persistente. La estabilidad aumenta el valor investigativo porque amplía el
horizonte temporal de la investigación y puede revelar evolución de conductas
o vínculos con actividades pasadas.

Un alias **singular** es aquel que, por su forma, longitud, complejidad o
combinación de elementos, tiene poca probabilidad de ser compartido de forma
independiente por múltiples personas. Un alias como «admin» o «juan» no tiene
valor investigativo como identificador único; un alias como «xrk_v3n0m_93»
tiene una singularidad intrínseca que hace muy improbable la coincidencia
accidental. La evaluación de la singularidad del alias debe realizarse desde
el inicio y condiciona directamente el peso que el investigador puede atribuir
a las coincidencias que encuentre.

La **reutilización** es el factor que convierte el alias en un nodo relacional:
la posibilidad de que el sujeto haya usado el mismo identificador en entornos
digitales distintos, lo que permite establecer conexiones entre actividades
o identidades que, de otro modo, aparecerían como no relacionadas.

### 4.2. El alias como huella de estilo e identidad

Más allá de su función como identificador, el alias puede contener información
implícita sobre el sujeto que lo eligió. Los alias que incorporan nombres
o iniciales pueden sugerir vínculos con la identidad real. Los que contienen
referencias culturales —a videojuegos, géneros musicales, subculturas,
idiomas o grupos de referencia— pueden indicar intereses, procedencia o
entorno social. Los que incluyen fechas en formato numérico —frecuentemente
años de nacimiento— pueden orientar sobre la franja de edad. Los que combinan
letras y números en patrones reconocibles —leetspeak, inversiones, sustituciones
características— pueden reflejar una estética o una procedencia comunitaria
específica.

Esta dimensión del análisis no produce atribuciones firmes, pero puede generar
hipótesis orientativas que resulten útiles para priorizar líneas de búsqueda
o para contrastar la coherencia entre distintos hallazgos.

### 4.3. Tipos de alias desde la perspectiva investigativa

El investigador debe clasificar desde el inicio el tipo de alias que tiene
ante sí, porque esa clasificación condiciona la estrategia de investigación.

El **alias principal o de uso habitual** es aquel que el sujeto emplea como
representación digital general, presente en múltiples plataformas y con larga
trayectoria de uso. Es el tipo de alias con mayor potencial de reutilización
y, por tanto, de generación de pistas.

El **alias instrumental o específico de contexto** es aquel creado para un
uso determinado —un foro específico, una operación concreta, un período de
actividad delimitado— y que puede no estar reutilizado en otros entornos.
Su valor investigativo como pivote transversal es menor, pero puede ser muy
relevante para entender la actividad dentro del contexto en que aparece.

El **alias derivado o variante** es una adaptación del alias principal:
mismo núcleo con prefijos, sufijos, números o modificaciones menores.
La identificación de ese núcleo compartido puede permitir encontrar presencias
del sujeto bajo variantes que una búsqueda exacta no habría localizado.

El **alias de suplantación** es aquel creado deliberadamente para imitar
la identidad de otra persona o entidad. Su investigación tiene un foco
diferente: no se trata de identificar al sujeto real detrás del alias, sino
de documentar la suplantación y establecer la diferencia entre el alias
fraudulento y la identidad legítima que imita.

---

## 5. Análisis inicial del alias y contextualización del hallazgo

### 5.1. Análisis estructural del alias

El primer paso en la investigación de un alias es el análisis de su propio
texto antes de realizar ninguna búsqueda externa. Este análisis debe atender
a varios elementos.

La **longitud y complejidad** del alias orientan sobre su singularidad:
un alias muy corto o muy genérico tiene mucha menor singularidad que uno
largo, específico o con combinaciones poco frecuentes.

Los **componentes identificables** son fragmentos del alias que pueden tener
significado propio: palabras en distintos idiomas, nombres propios, referencias
culturales, fechas, números con estructura reconocible o combinaciones de
caracteres con patrones habituales en determinadas subculturas digitales.

Las **variantes previsibles** son las modificaciones que el sujeto podría
haber aplicado al mismo alias en distintas plataformas: adición de números
al final, sustitución de letras por números, uso de guiones bajos o puntos
como separadores, capitalización distinta o prefijos o sufijos añadidos.
La generación sistemática de variantes previsibles antes de iniciar las
búsquedas mejora significativamente la cobertura de la investigación.

El **idioma y la referencia cultural** pueden orientar sobre la procedencia
o el entorno del sujeto, aunque con la prudencia debida ante las múltiples
posibilidades de influencia cultural cruzada en el entorno digital.

### 5.2. Contextualización del hallazgo

El alias siempre aparece en un contexto, y ese contexto es inseparable del
dato. Un alias que aparece en un foro de venta de accesos a sistemas
comprometidos tiene un perfil de riesgo y una estrategia de investigación
distintos al mismo alias apareciendo como nombre de vendedor en una plataforma
de compraventa de segunda mano. El investigador debe documentar con precisión
ese contexto antes de iniciar cualquier búsqueda: la plataforma, el tipo de
actividad, los datos que acompañan al alias —correo, teléfono, foto, bio,
publicaciones—, la fecha de la actividad y su relación con los hechos
investigados.

---

## 6. Búsqueda, reutilización y ampliación de la investigación a partir del alias

### 6.1. Búsqueda de presencia pública

La búsqueda de la presencia pública de un alias debe abordarse desde varios
ángulos complementarios de forma sistemática.

La **búsqueda exacta en motores generalistas** consiste en introducir el
alias entre comillas en los principales motores de búsqueda. Esta búsqueda
puede revelar perfiles públicos, publicaciones, comentarios, registros, webs
o cualquier otro contenido en que el alias haya sido publicado de forma
accesible. La búsqueda debe repetirse para cada variante previsible del alias
identificada en el análisis inicial.

La **búsqueda en plataformas específicas** consiste en explorar directamente
las plataformas más relevantes para el tipo de actividad investigada: redes
sociales, foros técnicos o de comunidades, plataformas de código, marketplaces,
servicios de gaming, repositorios de datos, canales de mensajería pública y
cualquier otro entorno en que el alias pueda haber dejado rastro. Muchas
plataformas permiten la búsqueda de usuarios por nombre, y esa búsqueda
interna puede devolver resultados que los motores generalistas no han indexado.

La **búsqueda contextual** consiste en combinar el alias con términos
relacionados con la actividad investigada para localizar menciones que no
habrían aparecido en una búsqueda directa: el alias junto al nombre de la
plataforma donde se detectó inicialmente, el alias junto a términos asociados
al tipo de fraude investigado, o el alias junto a otros datos ya conocidos
del caso.

### 6.2. Investigación de reutilización transversal

La reutilización del alias en múltiples plataformas es el vector de mayor
valor investigativo en este tipo de análisis. Cuando el mismo alias —o una
variante reconocible— aparece en contextos distintos, el investigador tiene
ante sí potencialmente la misma persona operando en distintos entornos.

La investigación de reutilización debe abordar de forma sistemática un
espectro amplio de plataformas: no solo las más obvias para el tipo de
actividad investigada, sino también aquellas en que el sujeto podría haber
tenido actividad previa —foros de gaming, comunidades técnicas, plataformas
de entretenimiento— y que pueden revelar una historia digital más larga que
el mero contexto delictivo actual.

Es importante mantener una distinción clara durante este proceso entre el
alias exacto —búsqueda de la cadena textual completa— y las variantes
derivadas —búsqueda de modificaciones del alias con el mismo núcleo—. Los
resultados de cada tipo de búsqueda tienen una fuerza relacional distinta:
la coincidencia del alias exacto tiene más peso que la coincidencia de una
variante, aunque esta última también puede ser investigativamente relevante
si el contexto lo justifica.

### 6.3. Ampliación de la investigación mediante pivotes

Los hallazgos derivados de la investigación del alias pueden generar múltiples
pivotes: un correo electrónico asociado al alias en un registro de servicio,
una foto de perfil que puede ser sometida a búsqueda inversa de imágenes,
un número de teléfono vinculado al proceso de registro, una biografía que
contiene datos de localización o de actividad, o un dominio registrado con
el mismo identificador. Cada uno de esos elementos debe investigarse siguiendo
los procedimientos de los capítulos correspondientes, con la misma disciplina
metodológica y de preservación.

---

## 7. Herramientas y recursos prácticos para la investigación de usernames, aliases y nicks

### 7.1. Herramientas de búsqueda transversal de usernames

El primer bloque funcional agrupa las herramientas diseñadas específicamente
para buscar un username en múltiples plataformas de forma simultánea o
secuencial. Estas herramientas son el punto de entrada más eficiente para
obtener un primer mapa de la presencia del alias en el espacio digital.

**Sherlock** es una de las herramientas de código abierto más utilizadas en
este ámbito. Acepta un username como entrada y comprueba de forma automatizada
su existencia en una lista amplia de plataformas, devolviendo las URLs en
que se ha encontrado un perfil con ese identificador. Su utilidad principal
es la velocidad con que proporciona un primer panorama de presencia; su
limitación fundamental es que su cobertura depende de la lista de plataformas
incluida en su configuración, que puede no estar actualizada, y que devuelve
resultados sobre la existencia de un perfil con ese username exacto pero no
informa sobre si el perfil corresponde efectivamente al sujeto investigado
o a otra persona con el mismo alias. El investigador debe verificar manualmente
cada resultado antes de incorporarlo como hallazgo activo.

**Maigret** es una herramienta similar a Sherlock pero con funcionalidades
adicionales, incluyendo la capacidad de extraer información de perfil de las
plataformas en que encuentra el alias y de enlazar resultados entre sí.
También de código abierto, permite gestionar mejor los resultados cuando el
alias tiene presencia en muchas plataformas simultáneas.

**WhatsMyName** es un proyecto colaborativo de código abierto que mantiene
una base de datos de plataformas con sus patrones de detección de usernames.
Puede usarse a través de su interfaz web o integrarse en flujos de trabajo
automatizados. Su cobertura de plataformas es amplia y se actualiza con
regularidad por la comunidad que lo mantiene.

Estas herramientas deben usarse como punto de arranque de la investigación,
no como su conclusión. Sus resultados requieren verificación manual y no
sustituyen la búsqueda directa en plataformas específicas que la herramienta
no cubre o no detecta correctamente.

### 7.2. Herramientas de búsqueda en foros, comunidades y servicios técnicos

Muchas de las plataformas más relevantes para la investigación de cibercrimen
—foros especializados, comunidades técnicas, marketplaces de acceso abierto,
plataformas de gaming, servicios de streaming— no están incluidas en las
herramientas de búsqueda transversal generalistas. La investigación en esos
entornos requiere búsqueda directa en cada plataforma y el uso de herramientas
específicas.

Los motores de búsqueda generalistas, con el uso adecuado de operadores de
búsqueda, son en muchos casos el instrumento más eficaz para localizar
menciones del alias en plataformas que permiten indexación pública. El
operador de comillas fuerza la búsqueda de la cadena exacta. La combinación
del alias con el nombre de la plataforma en que se sospecha que puede haber
tenido actividad puede revelar contenido que una búsqueda general no habría
localizado.

Para entornos de código —repositorios de GitHub, GitLab, Bitbucket— la
búsqueda del alias puede revelar actividad de desarrollo, contribuciones a
proyectos, commits con mensajes informativos o datos de perfil que incluyen
correo electrónico u otros identificadores. La actividad en repositorios de
código es especialmente relevante en investigaciones que involucran sujetos
con perfil técnico. Las herramientas de búsqueda nativa de cada plataforma
de código son frecuentemente más efectivas que los motores generalistas para
este tipo de búsqueda.

Para entornos de gaming —plataformas como Steam, Xbox Live, PlayStation
Network, Discord—, la búsqueda del alias puede revelar perfiles con datos
de actividad, amigos, grupos o comunidades. Discord, en particular, es
relevante en investigaciones de fraude organizado, distribución de material
ilícito y comunidades de cibercrimen, y sus servidores públicos pueden ser
explorados de forma directa o a través de directorios de servidores como
Disboard.

### 7.3. Herramientas de enriquecimiento de identidades digitales

Las herramientas de enriquecimiento están diseñadas para extraer, a partir
de un alias encontrado en una o varias plataformas, información adicional
que amplíe el conocimiento disponible sobre el sujeto: correos electrónicos
vinculados, números de teléfono asociados, fotos de perfil, datos de
localización, historial de actividad o relaciones con otros perfiles.

**Maltego** es la plataforma de investigación de inteligencia más consolidada
en este ámbito. Permite crear grafos relacionales a partir de un alias de
partida, consultando múltiples fuentes mediante módulos específicos y
visualizando las conexiones entre entidades de forma interactiva. Su potencia
es máxima cuando se dispone de las licencias y los módulos adecuados para
el tipo de investigación. La curva de aprendizaje es significativa, pero la
capacidad de correlación cruzada que ofrece es difícilmente igualable con
herramientas más sencillas.

**Skopenow**, **Pipl** y herramientas similares de inteligencia de personas
permiten enriquecer una identidad digital a partir de un alias o correo
electrónico, agregando datos de múltiples fuentes accesibles. Su valor
depende de la cobertura de sus bases de datos para el país y el tipo de
plataformas relevantes en la investigación.

Los servicios de búsqueda de datos de perfil en redes sociales —ya sean
buscadores nativos de cada red o herramientas agregadoras— permiten localizar
perfiles con el alias investigado y extraer la información de perfil visible:
nombre, foto, bio, ubicación declarada, fecha de registro, número de
seguidores o conexiones, y publicaciones públicas.

### 7.4. Herramientas de correlación con imágenes de perfil

Cuando la investigación del alias revela una o varias fotos de perfil asociadas
al sujeto, esas imágenes se convierten en un pivote independiente de gran
valor. La búsqueda inversa de imágenes permite verificar si la misma foto
aparece en otros perfiles o contextos, lo que puede confirmar la reutilización
de identidad o, por el contrario, revelar que la imagen ha sido tomada de
una fuente externa —indicando suplantación—.

**Google Images**, **Yandex Images** y **TinEye** son las tres herramientas
de búsqueda inversa de imágenes más utilizadas, con coberturas parcialmente
distintas. Yandex tiene especial eficacia para imágenes de procedencia
europea del Este y rusa, mientras que Google ofrece la mayor cobertura global.
TinEye es especialmente útil para detectar versiones anteriores de una imagen
o su aparición en contextos archivados.

La comparación visual de fotos de perfil obtenidas de distintas plataformas
puede confirmar que corresponden a la misma imagen o a imágenes del mismo
sujeto, aunque esa confirmación visual debe hacerse con prudencia y no puede
sustituir a una pericial técnica cuando la identificación tiene relevancia
probatoria directa.

### 7.5. Herramientas de búsqueda en Telegram y mensajería pública

Telegram tiene una presencia creciente en investigaciones de cibercrimen
por ser el entorno en que operan numerosas comunidades relacionadas con fraude,
venta de datos robados, distribución de herramientas maliciosas y coordinación
delictiva. La búsqueda de un alias en Telegram puede realizarse a través del
buscador nativo de la aplicación, que devuelve canales, grupos y usuarios
con ese nombre o identificador.

Además del buscador nativo, existen plataformas de indexación de contenido
público de Telegram —como **TGStat**, **Telemetr** o **Lyzem**— que permiten
buscar aliases, palabras clave o números de teléfono en canales y grupos
públicos, y acceder a estadísticas e histórico de actividad de esos canales.
Su valor en investigaciones de cibercrimen organizado puede ser considerable.

La búsqueda del alias en grupos y canales públicos de Telegram puede revelar
publicaciones, interacciones o menciones que sitúan al sujeto dentro de una
comunidad específica y que pueden vincular el alias con otros identificadores
—números de teléfono de administradores, correos de contacto publicados en
el canal, otros aliases de los mismos interlocutores—.

### 7.6. Herramientas de preservación y documentación

La preservación de los hallazgos vinculados a un alias debe seguir los mismos
principios generales del manual. Las herramientas de archivado web y los
sellos temporales verificables son los instrumentos básicos. Los perfiles,
publicaciones y contenidos en plataformas deben preservarse de forma inmediata
dado su potencial de eliminación. Los resultados de herramientas como Sherlock
o Maigret deben complementarse con capturas verificadas de cada perfil
identificado, dado que la existencia del perfil en el momento de la búsqueda
de la herramienta puede no mantenerse.

---

## 8. Procedimiento operativo de investigación a partir de un alias

El siguiente procedimiento describe una secuencia realista y ordenada para
el investigador que recibe un alias como dato de partida. Es una guía
adaptable, no un protocolo rígido.

**Primera fase: análisis del alias.** El investigador analiza la estructura,
longitud, singularidad y componentes del alias. Genera una lista de variantes
previsibles. Identifica posibles referencias culturales, lingüísticas o
temporales. Documenta el contexto de aparición con toda la información
disponible.

**Segunda fase: evaluación de singularidad.** Antes de iniciar búsquedas
masivas, el investigador realiza una búsqueda rápida del alias exacto en
un motor generalista para obtener una estimación preliminar de su frecuencia
en el espacio digital. Si el alias es muy genérico o muy frecuente, ajusta
las expectativas sobre el valor de las coincidencias que va a encontrar.

**Tercera fase: búsqueda transversal con herramientas automatizadas.** El
investigador utiliza herramientas como Sherlock, Maigret o WhatsMyName para
obtener un primer mapa de presencia del alias en plataformas conocidas. Cada
resultado es anotado pero no asumido como válido hasta verificación manual.

**Cuarta fase: verificación manual de resultados.** El investigador accede
directamente a cada URL devuelta por la fase anterior y verifica: que el
perfil existe y está activo o ha sido eliminado recientemente, que el contenido
del perfil es coherente con el tipo de actividad investigada, que la información
de perfil visible —foto, bio, fecha de registro, actividad publicada—
proporciona datos adicionales de interés. Cada perfil verificado se preserva
de inmediato.

**Quinta fase: búsqueda en plataformas no cubiertas por las herramientas.** El
investigador realiza búsquedas directas en las plataformas más relevantes
para el caso que no hayan sido cubiertas por las herramientas automatizadas:
Telegram, Discord, plataformas de gaming, foros especializados, repositorios
de código, canales de mensajería pública.

**Sexta fase: búsqueda de variantes.** El investigador repite las fases
anteriores con las variantes del alias identificadas en el análisis inicial.
Un alias que no produce resultados en su forma exacta puede producirlos en
una variante con el mismo núcleo.

**Séptima fase: investigación de pivotes.** A partir de la información de
perfil recopilada —correos, teléfonos, fotos, bios, dominios—, el investigador
identifica los pivotes más prometedores y los investiga de forma prioritaria
siguiendo los procedimientos de los capítulos correspondientes.

**Octava fase: síntesis y valoración.** El investigador evalúa el conjunto
de los hallazgos, valora la coherencia interna del perfil de actividad
construido, identifica las incertidumbres abiertas y determina qué diligencias
adicionales son necesarias para confirmar o profundizar en los resultados
obtenidos.

---

## 9. Interpretación de hallazgos, cautelas y errores frecuentes

### 9.1. La escala de fuerza de las coincidencias de alias

No todas las coincidencias de alias tienen el mismo valor investigativo. El
investigador debe aplicar un criterio de ponderación que tenga en cuenta,
como mínimo, tres factores: la singularidad del alias, la coherencia contextual
entre las distintas apariciones y la existencia de elementos corroboradores
independientes.

Una coincidencia de alias altamente singular, en plataformas con actividades
coherentes y con elementos de perfil consistentes —la misma foto, datos de
localización compatibles, estilo de escritura reconocible, intereses
coherentes— tiene una fuerza relacional significativa. Una coincidencia de
alias genérico, sin elementos corroboradores y en plataformas sin relación
con la actividad investigada, tiene una fuerza relacional mínima y no justifica
atribuciones.

### 9.2. Errores frecuentes en la investigación de aliases

El error más frecuente es la **homonimia no evaluada**: asumir que dos
perfiles con el mismo alias son de la misma persona sin haber evaluado la
singularidad del alias ni buscado activamente evidencia de que corresponden
a personas distintas. Aliases frecuentes como «darkwolf», «agent47» o
«raider» pueden estar en uso simultáneo por miles de personas sin ninguna
relación entre ellas.

El segundo error es la **dependencia exclusiva de herramientas automatizadas**:
asumir que si Sherlock no devuelve un resultado en una plataforma, el sujeto
no tiene presencia en ella. Las herramientas automatizadas tienen cobertura
limitada y detectan perfiles con configuraciones estándar; un perfil con
nombre de usuario ligeramente distinto o en una plataforma no incluida en
la lista de la herramienta no será detectado.

El tercer error es la **sobreinterpretación de patrones nominales**: inferir
datos personales —nombre, fecha de nacimiento, procedencia— a partir de los
componentes del alias con más certeza de la que los datos justifican. Los
números en un alias no siempre son fechas de nacimiento, y las palabras en
un alias no siempre son referencias personales directas.

El cuarto error es la **falta de verificación cruzada**: incorporar un perfil
como hallazgo activo sin verificar directamente su contenido y sin contrastar
la hipótesis de que corresponde al mismo sujeto con elementos corroboradores
independientes.

---

## 10. Aspectos jurídicos, deontológicos y probatorios específicos

### 10.1. Límites de la investigación de aliases en fuentes abiertas

La búsqueda de un alias en plataformas de acceso público, la consulta de
perfiles con información visible y la explotación de pivotes hacia otros
datos accesibles en abierto son actuaciones que, con carácter general, pueden
realizarse dentro de los límites de la investigación en fuentes abiertas sin
necesidad de autorización judicial específica. El investigador consulta
información que ha sido publicada voluntariamente por el usuario en entornos
de acceso público.

El acceso a plataformas que requieren autenticación para visualizar perfiles,
la creación de cuentas falsas para acceder a contenido restringido y cualquier
forma de interacción que pueda suponer una medida encubierta de investigación
son actuaciones que exigen un análisis jurídico específico y, en muchos casos,
cobertura judicial o habilitación legal expresa.

### 10.2. Prudencia en el tratamiento de datos personales

Los perfiles vinculados a aliases pueden contener datos de carácter personal
de terceros —personas del entorno del sujeto que aparecen en publicaciones,
comentarios o imágenes— cuyo tratamiento debe estar sujeto al mismo criterio
de finalidad legítima y minimización que se aplica a los datos del sujeto
investigado. El investigador debe evitar la acumulación de información sobre
personas no relacionadas con los hechos investigados.

### 10.3. Preservación y valor probatorio

Un perfil de usuario vinculado a un alias tiene, como cualquier contenido
digital, el riesgo de ser eliminado en cualquier momento. La preservación
inmediata —con sello temporal verificable, hash del contenido archivado y
registro de la fuente y el método de obtención— es una exigencia que debe
aplicarse desde el primer hallazgo relevante, antes de seguir el proceso de
investigación. Un perfil que desaparece antes de ser preservado es un hallazgo
perdido que puede no recuperarse.

---

## 11. Caso práctico aplicado

### Caso práctico: Identificación transversal del operador de una red de sextorsión a partir de un alias en una plataforma de citas

**Supuesto de hecho**

Una unidad de policía judicial recibe varias denuncias de varones jóvenes
que refieren haber sido contactados en una aplicación de citas por un perfil
femenino que, tras establecer una conversación con contenido íntimo, los
indujo a compartir imágenes de contenido sexual. Posteriormente, el perfil
los amenazó con difundir esas imágenes entre sus contactos si no realizaban
un pago. El perfil desapareció de la aplicación de citas tras recibir los
primeros pagos. Varios denunciantes conservan el username del perfil en la
aplicación de citas y screenshots de la conversación.

**Dato o indicio de partida**

El alias utilizado en la aplicación de citas: «SofiaVega_oficial». Varios
denunciantes coinciden en que el perfil utilizaba ese username y una foto de
perfil de una mujer joven.

**Hipótesis de trabajo**

El alias puede haber sido reutilizado en otras plataformas digitales, lo que
podría revelar actividad previa o paralela vinculada al mismo operador. La
foto de perfil, por las características de las imágenes descritas, puede
haber sido tomada de un perfil público existente de otra persona.

**Actuaciones realizadas**

El investigador analiza el alias: «SofiaVega_oficial» combina un nombre
femenino completo con el sufijo «oficial», patrón habitual en cuentas que
simulan ser de influencers o personajes públicos. La estructura sugiere un
intento de aparentar legitimidad. Se generan variantes: «sofia_vega_oficial»,
«sofiaVega_oficial», «SofiaVegaOficial» y combinaciones similares.

Se realiza búsqueda del alias exacto en motores generalistas y en herramientas
de búsqueda transversal. Los resultados revelan un perfil con el mismo alias
en una plataforma de vídeo en streaming, ya eliminado pero aún indexado en
el caché del motor de búsqueda. Se preserva el contenido del caché con sello
temporal y hash. El perfil en la plataforma de streaming mostraba vídeos de
una mujer joven y tenía fecha de creación anterior a las denuncias.

La búsqueda del alias en Telegram a través del buscador nativo devuelve un
canal público con el mismo nombre, activo, que contiene publicaciones de
captación de víctimas bajo el mismo perfil de persona. El canal se preserva
de inmediato en su totalidad.

La foto de perfil descrita por los denunciantes —cuya imagen fue recuperada
de una captura de uno de ellos— se somete a búsqueda inversa en Google Images
y Yandex. El resultado revela que la imagen corresponde a una usuaria real
de otra red social, cuya identidad no guarda relación con la actividad
investigada. Se documenta la suplantación.

El canal de Telegram contiene, en publicaciones anteriores, un número de
teléfono de contacto para «negocios» y una dirección de correo electrónico.
Ambos datos se investigan siguiendo los procedimientos de los capítulos
previos. La investigación del número de teléfono revela varios anuncios en
plataformas de servicios publicados en fechas anteriores. La investigación
del correo revela su uso en el registro de un dominio y en un perfil en otra
plataforma social.

**Hallazgos obtenidos**

El alias ha sido utilizado en al menos tres plataformas distintas: la aplicación
de citas, la plataforma de streaming y el canal de Telegram. El canal de
Telegram revela la operación más allá de los casos denunciados. La foto de
perfil corresponde a una víctima de suplantación identificable. El canal
ha generado dos pivotes —número de teléfono y correo electrónico— que han
producido hallazgos adicionales significativos.

**Análisis e interpretación**

La coherencia entre los hallazgos —mismo alias en múltiples plataformas,
patrón de conducta consistente, foto de suplantación identificada, pivotes
que generan rastros adicionales— configura un indicio relacional sólido de
una operación organizada bajo el mismo operador o grupo de operadores. La
extensión de la actividad identificada en el canal de Telegram sugiere una
escala mayor que la reflejada en las denuncias recibidas.

**Explotación policial y documental**

Los hallazgos se documentan en un informe de inteligencia que describe la
secuencia de búsquedas, las plataformas consultadas y los resultados obtenidos.
El informe identifica a la persona cuya imagen fue suplantada —posible víctima
adicional que puede ser informada— y fundamenta solicitudes de información
a las plataformas identificadas y al operador del número de teléfono, con
cobertura judicial, para obtener datos de registro y acceso.

**Lecciones operativas**

Este caso ilustra que la búsqueda más allá de la plataforma de origen del
dato inicial —la aplicación de citas— fue determinante para revelar la escala
real de la operación. La búsqueda inversa de la imagen de perfil permitió
identificar la suplantación e identificar a una víctima no denunciante. Los
pivotes generados por el canal de Telegram ampliaron la investigación hacia
un número de teléfono y un correo electrónico que abrieron nuevas líneas de
identificación. Y la preservación inmediata del contenido del canal —antes
de ninguna actuación que pudiera alertar al operador— garantizó la
disponibilidad del material para su explotación posterior.

---

## 12. Conclusiones operativas

El alias es, en el ecosistema digital del cibercrimen, uno de los rastros
de identidad con mayor potencial de persistencia y de transversalidad. Su
tendencia a la reutilización, su valor como pivote hacia otros elementos
digitales y su capacidad de revelar continuidad de conducta a lo largo del
tiempo lo convierten en un dato de partida de alto valor cuando el investigador
sabe cómo abordarlo.

Ese valor se realiza solo cuando el análisis combina el examen estructural
del alias, la búsqueda sistemática en múltiples plataformas, la generación
y búsqueda de variantes, la verificación manual de cada resultado relevante,
la explotación de los pivotes que los hallazgos generan y la documentación
rigurosa del proceso. La ponderación honesta de la fuerza de cada coincidencia
—en función de la singularidad del alias, la coherencia contextual y la
existencia de corroboración independiente— es la condición que garantiza que
el análisis produce conclusiones que pueden sostenerse y defenderse.

---

## 13. Checklist final de trabajo

**Análisis inicial del alias**

- Registrar el alias en el formato exacto en que fue obtenido y el
  contexto de aparición.
- Analizar la estructura, longitud, singularidad y componentes del alias.
- Evaluar la frecuencia estimada del alias: ¿es un identificador singular
  o potencialmente compartido por muchos usuarios?
- Identificar posibles referencias culturales, lingüísticas o temporales
  en los componentes del alias.
- Generar la lista de variantes previsibles del alias para su uso en
  búsquedas posteriores.

**Búsqueda transversal y verificación**

- Realizar búsqueda del alias exacto en motores generalistas con comillas.
- Ejecutar búsqueda transversal con herramientas como Sherlock, Maigret
  o WhatsMyName.
- Verificar manualmente cada resultado: acceder al perfil directamente
  y evaluar su coherencia con la investigación.
- Preservar de forma inmediata cada perfil verificado como relevante:
  archivo web con sello temporal y hash.
- Repetir las búsquedas para cada variante previsible del alias.

**Búsqueda en plataformas específicas**

- Buscar el alias en las plataformas más relevantes para el tipo de
  actividad investigada no cubiertas por las herramientas automáticas.
- Explorar Telegram, Discord y otros servicios de mensajería con canales
  o grupos públicos.
- Buscar el alias en plataformas de repositorios de código si el perfil
  del sujeto lo justifica.
- Consultar directorios de servidores de Discord u otros servicios
  relevantes para el contexto.

**Enriquecimiento y pivotes**

- Extraer datos de perfil de cada aparición verificada: correo, teléfono,
  foto, bio, fecha de registro, publicaciones visibles.
- Someter las fotos de perfil a búsqueda inversa de imágenes.
- Identificar los pivotes más relevantes y priorizarlos según las
  preguntas de investigación.
- Investigar cada pivote priorizado siguiendo los procedimientos de los
  capítulos correspondientes.

**Interpretación, síntesis y explotación**

- Ponderar la fuerza de cada coincidencia en función de la singularidad
  del alias, la coherencia contextual y la existencia de corroboración.
- Distinguir explícitamente entre alias exacto y variante en la
  evaluación de cada resultado.
- Verificar activamente si los distintos perfiles identificados pueden
  corresponder a personas distintas.
- Elaborar el informe con descripción metodológica completa y exposición
  honesta de los límites de las conclusiones.
- Identificar las diligencias adicionales con cobertura judicial necesarias
  para confirmar la atribución personal.

---