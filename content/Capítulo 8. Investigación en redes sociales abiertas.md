# Capítulo 8. Investigación en redes sociales abiertas

---

## 1. Introducción

Las redes sociales abiertas representan, para el investigador en fuentes
abiertas, uno de los entornos más ricos y, al mismo tiempo, más complejos
de explotar con rigor. Su riqueza proviene de la densidad de información que
los usuarios publican voluntariamente: datos de identidad, imágenes, vínculos
relacionales, expresiones de opinión, hábitos de vida, patrones de actividad,
ubicaciones probables, afiliaciones comunitarias y una cronología a veces
extensa de conductas y decisiones. Su complejidad proviene de que esa
información es heterogénea, parcialmente verificable, susceptible de
manipulación y difícilmente interpretable fuera de su contexto.

En el ámbito del cibercrimen, las redes sociales desempeñan múltiples
funciones simultáneas. Son el medio a través del cual se establece contacto
inicial con las víctimas en casos de fraude sentimental, sextorsión o
ingeniería social. Son el escaparate de legitimación que utilizan muchos
operadores de fraude de inversión para construir una apariencia de
credibilidad. Son el canal de captación y coordinación de determinadas
comunidades delictivas. Y son, en muchos casos, el espacio en que los sujetos
investigados proyectan elementos de su identidad real que contradicen la
imagen que pretenden mantener en el contexto de su actividad ilícita.

Esta multiplicidad de funciones hace de las redes sociales abiertas un objeto
de investigación que el investigador OSINT no puede ignorar, pero que tampoco
puede abordar con automatismos. Una publicación aislada, una foto de perfil
o una interacción visible tienen valor solo cuando se leen dentro de un
contexto más amplio, cuando se contrastan con otros hallazgos y cuando se
interpretan con el rigor analítico que caracteriza una investigación
metodológicamente sólida.

---

## 2. Finalidad investigadora del capítulo

Este capítulo amplía la serie aplicativa del manual hacia uno de los entornos
más relevantes y habituales en la investigación de cibercrimen: las redes
sociales abiertas. Complementa los capítulos dedicados a correos electrónicos,
números de teléfono y aliases, dado que los perfiles en redes sociales
frecuentemente integran o vinculan esos mismos elementos y permiten explotarlos
de forma conjunta dentro de un ecosistema de identidad digital más complejo.

Su función dentro del manual es doble. Por un lado, proporcionar el marco
analítico necesario para entender qué puede obtenerse de un perfil, una
cuenta o una publicación en una red social abierta, qué dimensiones de análisis
son relevantes y qué factores determinan el valor investigativo de cada
hallazgo. Por otro, ofrecer una secuencia de trabajo práctica, aplicable en
el trabajo cotidiano de la policía judicial, con orientación concreta sobre
herramientas, análisis de resultados y documentación.

El capítulo resulta especialmente útil en investigaciones de fraude sentimental,
fraude de inversión, phishing con perfil social construido, sextorsión,
suplantación de identidad en redes, captación de víctimas, compraventa
fraudulenta con perfil social de respaldo, y análisis de redes de contactos
vinculadas a actividades delictivas.

---

## 3. Objeto de análisis y punto de partida

### 3.1. Los elementos investigables en una red social abierta

A efectos de este capítulo, el objeto de investigación en una red social
abierta no se reduce al perfil como unidad estática, sino que abarca un
conjunto de elementos interrelacionados que el investigador debe saber
identificar, analizar y explotar de forma coordinada.

El **perfil** es el conjunto de elementos de identidad que el titular ha
configurado de forma deliberada: nombre visible, nombre de usuario, fotografía
o avatar, biografía, información de contacto, enlace a otras cuentas y datos
de localización declarados. Estos elementos son la primera capa de análisis
y la que con mayor frecuencia aporta datos de pivote hacia otros entornos.

La **actividad pública** comprende las publicaciones, los comentarios, los
likes, las retransmisiones y cualquier otra forma de interacción que el
usuario ha realizado de forma visible para el nivel de audiencia que corresponde
a su configuración de privacidad. Incluye contenido textual, imágenes, vídeos,
enlaces compartidos, menciones a terceros y respuestas a publicaciones de
otros usuarios.

Las **relaciones visibles** son los vínculos explícitos que el usuario ha
establecido con otras cuentas: seguidores, seguidos, amigos, miembros de
grupos, listas públicas o comunidades de pertenencia. Estas relaciones pueden
revelar el entorno social del sujeto, sus afiliaciones y los actores con
quienes interactúa de forma regular.

Los **metadatos asociados** incluyen la fecha de creación de la cuenta, la
cronología de actividad, los cambios de nombre o identificador registrables
y los patrones de uso que pueden inferirse de la actividad pública.

### 3.2. Contextos de aparición y preguntas iniciales

El elemento inicial de una investigación en redes sociales puede ser muy
variado: un enlace de perfil aportado por la víctima, un nombre visible
obtenido de una pantalla capturada, un alias identificado en la investigación
de otro elemento digital, una imagen cuya búsqueda inversa ha conducido a
un perfil concreto, o la identificación autónoma de una cuenta vinculada a
la actividad investigada durante el proceso de investigación de dominios,
correos o infraestructuras.

Las preguntas que el investigador debe formular desde el inicio son las
habituales: ¿es este perfil auténtico o construido con datos falsos? ¿Existe
coherencia interna entre sus distintos elementos? ¿Ha sido activo durante un
período compatible con los hechos investigados? ¿Qué pivotes ofrece hacia
otros elementos digitales? ¿Existen relaciones visibles con otras cuentas
que puedan ser relevantes? ¿Cómo debe preservarse el contenido identificado
antes de que pueda ser eliminado?

---

## 4. La red social abierta como ecosistema de identidad digital y pivote de investigación

### 4.1. Densidad informativa y ambigüedad analítica

Una de las características distintivas de las redes sociales como objeto
de investigación OSINT es la densidad de la información que pueden contener.
Un perfil activo puede ofrecer simultáneamente datos de identidad, imágenes
del sujeto y de su entorno, indicios de localización geográfica, expresiones
de opinión e intereses, cronología de conductas, red visible de contactos
y vínculos con otras plataformas. Esa densidad es lo que hace de las redes
sociales un objeto de análisis tan valioso.

Pero esa misma densidad genera ambigüedad analítica. La información publicada
en redes sociales puede ser parcialmente falsa, construida deliberadamente
para proyectar una imagen que no corresponde a la realidad, tomada de fuentes
ajenas o simplemente desactualizada. Un perfil puede presentar una imagen de
credibilidad cuidadosamente diseñada que no resiste el contraste con otros
elementos de la investigación. El investigador que toma al pie de la letra
lo que aparece en un perfil social sin contrastarlo con fuentes independientes
está asumiendo un riesgo analítico significativo.

### 4.2. Tipología de cuentas desde la perspectiva investigativa

El investigador debe identificar desde el inicio el tipo de cuenta que tiene
ante sí, porque esa clasificación condiciona la estrategia de análisis y las
expectativas sobre lo que puede obtenerse.

La **cuenta auténtica de uso habitual** es aquella que el sujeto mantiene
como representación digital general de su identidad, con actividad regular
y coherente a lo largo del tiempo. Es el tipo de cuenta con mayor densidad
informativa y mayor potencial como fuente de datos reales sobre el sujeto.

La **cuenta instrumental o específica** es aquella creada para un propósito
concreto —una actividad delictiva determinada, un período de operación
específico— sin vinculación con otras cuentas del sujeto. Su contenido puede
ser más limitado, pero puede ser muy revelador dentro de su contexto.

La **cuenta construida con datos falsos** es aquella en que el nombre, la
fotografía y la información de perfil han sido fabricados o tomados de otras
fuentes para crear una identidad ficticia con finalidad de engaño, captación
o suplantación. La detección de este tipo de cuenta mediante contraste de
imágenes y coherencia interna es una de las tareas más importantes del
análisis inicial.

La **cuenta suplantada** es aquella que imita deliberadamente a una persona
o entidad real, reproduciendo sus elementos de identidad para inducir a error.
Su investigación tiene un foco específico: documentar la suplantación y
establecer la diferencia entre el perfil falso y la identidad legítima imitada.

La **cuenta abandonada** es aquella que existió en el pasado pero que el
titular ha dejado de usar, con contenido histórico que puede ser relevante
aunque no refleje la actividad actual. Su valor investigativo está en ese
contenido histórico y en los vínculos que puede haber mantenido con otras
cuentas activas.

### 4.3. La red social como nodo en el ecosistema de identidad digital

El valor más significativo de un perfil en red social como objeto de
investigación OSINT frecuentemente no reside en lo que contiene por sí solo,
sino en los puentes que permite establecer hacia otros elementos del ecosistema
digital del sujeto. Un perfil puede vincular un alias con un nombre real, un
correo electrónico con una red de contactos, una imagen con una localización,
o una actividad pública con una conducta que conecta con los hechos
investigados.

---

## 5. Análisis inicial del perfil y contextualización del hallazgo

### 5.1. Lectura analítica del perfil

El primer paso en la investigación de un perfil social es el análisis
sistemático de sus elementos visibles antes de iniciar ninguna búsqueda
externa. Esta lectura analítica debe ser estructurada y atenerse a criterios
explícitos.

El **nombre visible** puede contener el nombre real del sujeto, un alias,
una denominación comercial o una combinación de elementos. Su relación con
el nombre de usuario puede ser coherente o diferente, lo que en sí mismo es
informativo. Los cambios de nombre —cuando son detectables a través del
historial o de menciones anteriores— pueden ser relevantes cronológicamente.

El **nombre de usuario** sigue los criterios de análisis desarrollados en
el capítulo anterior: singularidad, estructura, variantes previsibles y
presencia transversal en otras plataformas.

La **fotografía o avatar** es uno de los elementos de mayor valor investigativo
en el perfil. Puede ser una foto real del sujeto —con potencial para búsqueda
inversa de imágenes—, una imagen tomada de una fuente pública —indicio de
construcción de perfil falso—, una imagen genérica o un elemento gráfico sin
valor identificativo directo.

La **biografía o descripción** puede contener datos de localización, referencias
de intereses o actividad, enlaces a otros perfiles o servicios, datos de
contacto y elementos de lenguaje o estilo que pueden ser analíticamente
relevantes.

Los **datos de contacto visibles** —correo electrónico, número de teléfono,
enlace a aplicación de mensajería— son pivotes directos hacia otros elementos
de la investigación que deben explotarse siguiendo los procedimientos de los
capítulos correspondientes.

La **coherencia interna** del perfil es uno de los indicadores más importantes
en el análisis inicial: ¿son consistentes entre sí el nombre, la imagen, la
bio, la fecha de creación, la actividad publicada y los seguidores? ¿Existen
inconsistencias que sugieran que el perfil ha sido construido o modificado
de forma deliberada?

### 5.2. Evaluación de la cuenta

Junto al análisis de los elementos estáticos del perfil, el investigador
debe evaluar algunos indicadores generales de la cuenta: la fecha de creación,
cuando es visible; el número de publicaciones y la frecuencia de la actividad;
la relación entre seguidores y seguidos; la presencia o ausencia de
interacciones reales de terceros —comentarios auténticos, menciones,
respuestas—; y la coherencia temporal entre la antigüedad declarada de la
cuenta y el volumen de actividad visible.

Cuentas con una antigüedad declarada larga pero con muy pocas publicaciones
o con actividad concentrada en un período breve pueden indicar una cuenta
creada con anterioridad pero usada solo circunstancialmente, una cuenta
reactivada tras un período de abandono, o una cuenta que ha eliminado la
mayor parte de su actividad.

---

## 6. Actividad pública, cronología, relaciones visibles y ampliación de la investigación

### 6.1. Análisis de la actividad pública

La actividad pública de un perfil —las publicaciones, los comentarios, los
contenidos compartidos y las interacciones visibles— es una fuente de
información analíticamente densa que va mucho más allá del contenido
declarativo de lo publicado.

El **análisis cronológico** permite identificar el período de actividad del
sujeto, los momentos de mayor o menor frecuencia de publicación, los huecos
temporales que pueden ser significativos y la evolución del tipo de contenido
a lo largo del tiempo. En investigaciones de fraude, la cronología puede
revelar cuándo comenzó la actividad investigada, cómo ha evolucionado y si
existen períodos que se corresponden con otros elementos del caso.

El **análisis de contenido** permite identificar temas recurrentes, lenguaje
y estilo característicos, referencias geográficas implícitas o explícitas,
afiliaciones ideológicas o comunitarias, intereses declarados o implícitos
y coherencia entre el contenido publicado y el perfil de conducta investigado.

El **análisis de patrones de publicación** puede revelar información sobre
los hábitos del sujeto: los horarios habituales de actividad —que pueden
orientar sobre la zona horaria—, la frecuencia y regularidad de las
publicaciones, los períodos de inactividad y los patrones de respuesta a
interacciones de terceros.

### 6.2. Relaciones visibles y comunidades de pertenencia

Las relaciones visibles en un perfil social son uno de los vectores más
ricos de información contextual. Los seguidores y seguidos, cuando son
accesibles, pueden revelar el entorno social del sujeto, sus afiliaciones
comunitarias y los actores con quienes mantiene vínculos regulares. En
investigaciones de fraude organizado o de redes delictivas, las relaciones
visibles pueden identificar a otros participantes de la estructura.

Los grupos y comunidades de pertenencia visibles —en plataformas que los
hacen públicos— pueden situar al sujeto en comunidades de interés relevantes
para la investigación: grupos de inversión, comunidades de comercio de
criptomonedas, foros de servicios técnicos o espacios de actividad que
corresponden al tipo de cibercrimen investigado.

Las menciones y los comentarios visibles en las publicaciones del sujeto,
y las publicaciones del sujeto en las que menciona a terceros, son pivotes
hacia otras cuentas que pueden ser investigadas de forma independiente.

### 6.3. Reutilización de elementos entre plataformas

La reutilización de imágenes de perfil, fragmentos de biografía, patrones
de publicación o enlaces entre distintas redes sociales es un indicador de
identidad compartida que puede fortalecer las hipótesis de atribución. Un
sujeto que usa la misma fotografía en Instagram, Twitter y LinkedIn, que
enlaza sus cuentas entre sí y que mantiene el mismo alias con variaciones
menores presenta una coherencia de identidad digital que refuerza la hipótesis
de que todas esas cuentas corresponden a la misma persona.

La detección de esa reutilización requiere búsqueda transversal de los
elementos del perfil —imagen, alias, fragmentos de bio, enlaces— en otras
plataformas, siguiendo los procedimientos de los capítulos anteriores y el
que se desarrollará en este capítulo para el bloque de herramientas.

---

## 7. Herramientas y recursos prácticos para la investigación en redes sociales abiertas

### 7.1. Herramientas de localización e identificación de perfiles

El primer bloque funcional agrupa las herramientas y los procedimientos
orientados a localizar el perfil o la cuenta relevante en el espacio digital
cuando el dato de partida es un nombre, un alias o un fragmento de identidad
y no un enlace directo al perfil.

Los **motores de búsqueda generalistas** con operadores de búsqueda avanzada
son, también en este ámbito, el punto de entrada más accesible y
frecuentemente eficaz. La búsqueda del nombre visible o del alias entre
comillas, combinada con el nombre de la plataforma en que se sospecha que
el sujeto tiene presencia, puede devolver resultados directos o referencias
a perfiles indexados. La combinación del nombre con otros datos conocidos
—localización declarada, actividad, empresa— puede refinar los resultados.

Los **buscadores nativos de cada plataforma** son en muchos casos más efectivos
que los motores generalistas para localizar perfiles específicos dentro de
esa plataforma. La búsqueda de personas en Facebook, la búsqueda avanzada
en X (antes Twitter), la búsqueda de perfiles en LinkedIn o la búsqueda por
nombre en Instagram son operaciones que el investigador debe realizar de forma
directa en cada plataforma, complementando los resultados de los motores
generalistas.

Las **herramientas de búsqueda transversal de usernames**, desarrolladas en
el capítulo anterior —Sherlock, Maigret, WhatsMyName—, son igualmente
aplicables aquí cuando el dato de partida es un alias. Su resultado incluye
con frecuencia perfiles en redes sociales, lo que las convierte en el punto
de entrada natural también para la investigación en este tipo de plataformas.

### 7.2. Herramientas de búsqueda avanzada en plataformas específicas

Varias plataformas ofrecen capacidades de búsqueda avanzada que permiten
filtrar publicaciones, usuarios o contenidos por parámetros específicos. El
investigador debe conocer estas capacidades para cada plataforma relevante
en su contexto de trabajo.

**X (Twitter)** dispone de un motor de búsqueda avanzado accesible mediante
la interfaz web o mediante operadores de búsqueda en el campo de búsqueda
estándar. Permite filtrar publicaciones por usuario, por palabras clave, por
fechas, por idioma y por tipo de contenido. Esta capacidad es especialmente
útil para localizar publicaciones antiguas de un usuario cuando el perfil
tiene una trayectoria larga, o para buscar menciones de un usuario por parte
de terceros. **Nitter** y otras herramientas de terceros han ofrecido
históricamente una interfaz alternativa con capacidades de búsqueda y
exportación adicionales, aunque su disponibilidad es variable en función de
los cambios en las políticas de la plataforma.

**Facebook** ha reducido progresivamente la capacidad de búsqueda externa
sobre sus perfiles, pero su búsqueda interna permite localizar perfiles
públicos, páginas y grupos. La exploración de grupos públicos relacionados
con la actividad investigada puede revelar participaciones de cuentas de
interés.

**Instagram** limita la búsqueda por texto a nombres de usuario y hashtags
en su interfaz pública. Las publicaciones con hashtags relacionados con la
actividad investigada pueden revelar cuentas vinculadas al contexto. La
búsqueda de imágenes de perfil mediante búsqueda inversa es especialmente
relevante en esta plataforma dado su carácter visual.

**LinkedIn** permite la búsqueda de personas por nombre, empresa, cargo y
localización. En investigaciones de fraude de inversión, suplantación de
identidades profesionales o legitimación social de esquemas fraudulentos, la
consulta de perfiles de LinkedIn puede ser especialmente relevante.

**TikTok** puede contener perfiles relevantes en investigaciones de captación
de víctimas, fraude de inversión con influencia social o campañas de
legitimación. La búsqueda por username y por hashtags es la principal vía
de localización.

### 7.3. Herramientas de análisis de publicaciones y cronologías

Una vez identificado el perfil relevante, el investigador puede apoyarse en
herramientas que facilitan el análisis sistemático de la actividad pública.

**Social Bearing** y herramientas similares permiten analizar la actividad
pública de cuentas de X, ofreciendo estadísticas de publicación, análisis
de frecuencia, distribución horaria de la actividad, palabras más frecuentes
y cronología visual de publicaciones. Su valor es alto cuando la cuenta tiene
un volumen de actividad que hace difícil el análisis manual.

**Twitonomy** ofrece funcionalidades similares de análisis de actividad en
X, incluyendo los patrones de interacción del usuario con otras cuentas, lo
que puede ser especialmente relevante para identificar relaciones recurrentes.

Para plataformas sin herramientas de análisis específicas de terceros, el
investigador puede recurrir a la búsqueda avanzada nativa de la plataforma
para filtrar publicaciones por períodos temporales y reconstruir la cronología
de actividad de forma manual o semiautomática.

**Wayback Machine** e Internet Archive son recursos esenciales para recuperar
versiones anteriores de perfiles públicos o de publicaciones que han sido
eliminadas. Su cobertura de perfiles en redes sociales es desigual —algunas
plataformas bloquean el rastreo por robots de indexación—, pero en muchos
casos permite recuperar el estado de un perfil en un momento anterior,
especialmente cuando el perfil corresponde a una página web o a una cuenta
con alta visibilidad pública.

### 7.4. Herramientas de búsqueda y análisis de imágenes

La imagen de perfil y el contenido multimedia publicado son algunos de los
elementos más ricos de un perfil social desde la perspectiva investigativa.
Las herramientas de búsqueda inversa de imágenes —**Google Images**, **Yandex
Images**, **TinEye**, **Bing Visual Search**— permiten verificar si una imagen
de perfil aparece en otros contextos, identificar la fuente original de una
imagen tomada de terceros y detectar reutilización de la misma fotografía
bajo distintos perfiles o aliases.

**PimEyes** es una herramienta de búsqueda de imágenes por similitud facial
que puede resultar útil para identificar si la misma persona aparece en
fotografías en distintos contextos en línea. Su uso debe hacerse con plena
conciencia de las implicaciones jurídicas del reconocimiento facial y de la
necesidad de que su resultado sea tratado como indicio orientativo sujeto a
contraste, no como identificación biométrica verificada.

El análisis de **metadatos de imágenes** —cuando el archivo original está
disponible, no solo la versión publicada en la plataforma— puede revelar
datos de geolocalización, fecha y hora de captura, y modelo del dispositivo
utilizado. La mayoría de las plataformas eliminan los metadatos EXIF de las
imágenes al subirlas, pero en algunos contextos —imágenes compartidas
directamente, archivos descargados de fuentes no optimizadas— los metadatos
pueden conservarse.

### 7.5. Herramientas de correlación entre plataformas

Las herramientas de inteligencia de personas y de correlación de identidades
digitales —**Maltego**, **Skopenow**, **Pipl**, **SpiderFoot**— permiten
construir grafos relacionales que vinculan los elementos de un perfil social
con otros identificadores digitales: correos electrónicos, números de teléfono,
aliases, dominios y otras cuentas. Su valor es especialmente alto cuando el
perfil contiene múltiples elementos que pueden explotarse como pivotes
simultáneos.

Para investigaciones centradas en comunidades de Telegram vinculadas a
actividades delictivas, las herramientas de indexación de contenido público
de Telegram —**TGStat**, **Telemetr**— pueden complementar la búsqueda en
redes sociales convencionales al revelar menciones del alias o de elementos
del perfil en canales o grupos de esa plataforma.

### 7.6. Herramientas de preservación y documentación

La volatilidad del contenido en redes sociales es especialmente alta: un
perfil puede ser eliminado, modificado o restringido en horas. La preservación
inmediata de cada hallazgo relevante es una exigencia que opera desde el
primer acceso. Las herramientas de archivado web —**Archive.today**,
**Wayback Machine** para guardar activamente una URL— generan una copia
verificable del estado de una página en un momento específico, con sello
temporal y URL permanente que puede ser referenciada en informes y diligencias.

La captura de pantalla, aunque insuficiente por sí sola como instrumento de
preservación probatoria, puede complementarse con el hash del archivo
generado, el sello temporal de la obtención y la descripción de la URL y el
contexto de acceso. El conjunto de esos elementos configura una preservación
mínimamente sólida para el hallazgo.

---

## 8. Procedimiento operativo de investigación a partir de un perfil o indicio en red social

El siguiente procedimiento describe una secuencia realista y ordenada para
el investigador que inicia o enriquece una investigación a partir de un
perfil, una publicación o un indicio en red social.

**Primera fase: identificación y localización del perfil.** El investigador
utiliza el dato disponible —enlace directo, nombre visible, alias, imagen—
para localizar el perfil relevante en la plataforma indicada o en otras
plataformas en que pueda tener presencia. Si el dato es un alias, aplica los
procedimientos del capítulo anterior. Si el dato es una imagen, inicia la
búsqueda inversa de esa imagen en los principales motores de búsqueda por
imágenes.

**Segunda fase: análisis del perfil visible.** Una vez localizado el perfil,
el investigador realiza una lectura analítica sistemática de todos sus
elementos visibles: nombre, username, foto, bio, datos de contacto, fecha
de creación visible, número de publicaciones y relaciones visibles. Documenta
cada elemento y formula hipótesis preliminares sobre la naturaleza de la
cuenta y su relación con la actividad investigada.

**Tercera fase: preservación inmediata.** Antes de continuar la investigación,
el investigador preserva el estado actual del perfil mediante archivado web
con sello temporal, dado el riesgo de eliminación o modificación del contenido.

**Cuarta fase: análisis de la actividad pública.** El investigador explora
la actividad pública del perfil —publicaciones, comentarios visibles,
interacciones— con atención a la cronología, los temas recurrentes, los
patrones de publicación, las menciones a terceros y cualquier elemento de
contenido relevante para la investigación. Preserva las publicaciones
individualmente relevantes.

**Quinta fase: análisis de relaciones visibles.** El investigador examina
las relaciones visibles del perfil —seguidores, seguidos, grupos, páginas
vinculadas— en busca de cuentas relacionadas que puedan ser investigadas de
forma independiente o que aporten contexto sobre el entorno del sujeto.

**Sexta fase: investigación transversal.** El investigador busca el alias,
la imagen de perfil y otros elementos del perfil en otras plataformas,
siguiendo los procedimientos de los capítulos anteriores. Verifica si los
datos de contacto visibles —correo, teléfono— han sido investigados o deben
ser incorporados como nuevas líneas de trabajo.

**Séptima fase: investigación de pivotes.** A partir de todos los elementos
obtenidos en las fases anteriores, el investigador identifica los pivotes
más prometedores y los investiga de forma prioritaria.

**Octava fase: síntesis y valoración.** El investigador evalúa el conjunto
de los hallazgos, valora la coherencia interna del perfil de actividad
construido, identifica las incertidumbres abiertas y determina qué diligencias
adicionales son necesarias para confirmar o profundizar en los resultados.

---

## 9. Interpretación de hallazgos, cautelas y errores frecuentes

### 9.1. La escala de certeza en el análisis de perfiles sociales

La interpretación de los hallazgos obtenidos en la investigación de redes
sociales debe estar presidida por la misma distinción entre niveles de
inferencia que se ha desarrollado en capítulos anteriores. La presencia de
un perfil con un nombre determinado indica la existencia de ese perfil; no
confirma la identidad del titular. La coherencia interna de los elementos
del perfil refuerza la hipótesis de autenticidad; no la prueba. La reutilización
de elementos entre plataformas fortalece la hipótesis de identidad común;
no la certifica.

La atribución personal firme —la conclusión de que ese perfil pertenece o
pertenecía a un sujeto concreto— requiere corroboración mediante fuentes
independientes y, frecuentemente, confirmación a través de diligencias
judiciales dirigidas a la plataforma.

### 9.2. Errores frecuentes en la investigación de redes sociales

El error más habitual es la **confusión entre homónimos**: asumir que un
perfil con el nombre o el alias del sujeto investigado corresponde necesariamente
a ese sujeto sin verificar la coherencia de los elementos del perfil con
otros datos conocidos. Los nombres frecuentes tienen múltiples titulares, y
las plataformas no garantizan unicidad de identidad.

El **uso acrítico de capturas de pantalla** como única forma de preservación
—sin archivado web, sin sello temporal verificable y sin registro de la
URL y las circunstancias de obtención— produce material de escaso valor
probatorio que puede ser impugnado con facilidad.

La **lectura aislada de publicaciones** —interpretar una publicación
descontextualizada de su entorno cronológico y relacional— puede producir
interpretaciones erróneas o engañosas. Una publicación siempre debe leerse
en el contexto del perfil completo y de la actividad que la rodea.

La **sobreinterpretación de interacciones visibles** es otro error frecuente:
asumir que el hecho de que dos cuentas se sigan mutuamente, se mencionen o
compartan contenido implica una relación personal real o una colaboración
en la actividad investigada. Las interacciones en redes sociales pueden ser
automáticas, recíprocas por cortesía o irrelevantes para la investigación.

### 9.3. El problema de los perfiles construidos con datos falsos

En investigaciones de fraude, suplantación y sextorsión, una proporción
significativa de los perfiles relevantes son cuentas construidas con datos
falsos: nombre ficticio, foto tomada de una fuente pública y actividad mínima
orientada a generar apariencia de legitimidad. El investigador debe incorporar
en su análisis inicial la hipótesis de que el perfil puede ser falso y buscar
activamente evidencia que la confirme o descarte: búsqueda inversa de la
imagen de perfil, coherencia entre la antigüedad declarada y el volumen de
actividad, verificación de la coherencia entre los seguidores y el contenido
publicado.

---

## 10. Aspectos jurídicos, deontológicos y probatorios específicos

### 10.1. Legitimidad de la observación en abierto

La observación y el análisis de perfiles públicos y de publicaciones visibles
para cualquier usuario sin autenticación son, con carácter general, actividades
que pueden realizarse dentro de los límites de la investigación en fuentes
abiertas. La información que el usuario ha decidido hacer pública es accesible
para cualquier observador, incluido el investigador.

La creación de cuentas falsas o de identidades de cobertura para acceder a
perfiles con configuración de privacidad restringida, la interacción con
cuentas investigadas de forma encubierta y cualquier otra actuación que vaya
más allá de la observación pasiva de contenido públicamente accesible son
actuaciones que requieren un análisis jurídico específico y, en muchos casos,
habilitación legal expresa o cobertura judicial. La distinción entre
observación y actuación encubierta es jurídicamente relevante y no puede
ser ignorada por el investigador.

### 10.2. Tratamiento de datos de terceros

La investigación de un perfil social puede revelar, inevitablemente,
información sobre personas del entorno del sujeto investigado —amigos,
familiares, compañeros— que aparecen en publicaciones, comentarios o
fotografías sin tener relación con los hechos investigados. El tratamiento
de esa información debe ajustarse al principio de minimización: el investigador
debe evitar la acumulación de datos sobre terceros no relacionados con la
investigación y debe tratar con especial cuidado cualquier dato que pueda
afectar a personas vulnerables o que pueda tener consecuencias desproporcionadas.

### 10.3. Preservación y valor probatorio de los hallazgos

El carácter altamente mutable del contenido en redes sociales hace que la
preservación sea una prioridad desde el primer acceso. El archivado web con
sello temporal verificable, el hash del contenido archivado y el registro
de la URL y las condiciones de obtención son los elementos mínimos de una
cadena de preservación sólida. Las capturas de pantalla son un complemento
útil pero insuficiente por sí solas. El informe que documenta el proceso de
obtención debe ser suficientemente detallado para que el hallazgo pueda ser
evaluado y, si es necesario, contrastado por cualquier tercero con la formación
adecuada.

---

## 11. Caso práctico aplicado

### Caso práctico: Desmontaje de una red de fraude de inversión en criptomonedas a través del perfil social del presunto asesor

**Supuesto de hecho**

Una unidad de policía judicial recibe varias denuncias de ciudadanos que
refieren haber perdido importantes sumas de dinero en una plataforma de
inversión en criptomonedas fraudulenta. El patrón es consistente: los
denunciantes fueron contactados a través de redes sociales o de aplicaciones
de mensajería por un perfil que se presentaba como asesor financiero experto
en criptomonedas, con un historial de éxitos visible en sus redes, con una
imagen profesional cuidada y con testimonios favorables visibles en sus
publicaciones. Tras ganar la confianza de las víctimas, las indujo a invertir
cantidades crecientes en una plataforma que eventualmente resultó inaccesible.
Varios denunciantes conservan el enlace al perfil de Instagram del presunto
asesor y el nombre de usuario de Telegram desde el que se coordinaron los
pagos.

**Dato o indicio de partida**

El perfil público de Instagram del presunto asesor, con más de 8.000 seguidores
y publicaciones que muestran supuestas ganancias de inversión, imágenes en
entornos de lujo y testimonios de clientes satisfechos. El nombre de usuario
de Telegram desde el que se gestionaron los pagos.

**Hipótesis de trabajo**

El perfil de Instagram puede haber sido construido artificialmente para
aparentar legitimidad, y sus elementos —foto de perfil, bio, contenido
publicado— pueden haber sido tomados de fuentes ajenas o fabricados. El
alias de Telegram puede estar vinculado a otros identificadores digitales
que amplíen la investigación.

**Actuaciones realizadas**

El investigador comienza por la lectura analítica del perfil de Instagram.
El perfil tiene dos años de antigüedad, pero la actividad publicada se
concentra casi exclusivamente en los últimos ocho meses. Los seguidores
incluyen un número elevado de cuentas con características de cuentas falsas
o inactivas. Las imágenes publicadas muestran a un hombre joven con ropa de
marca y vehículos de lujo. Las publicaciones utilizan un lenguaje característico
del entorno de las criptomonedas y de los esquemas de inversión rápida.

La foto de perfil se somete a búsqueda inversa en Google Images y Yandex.
La búsqueda revela que la imagen corresponde a un influencer de fitness de
otro país, cuya identidad real no guarda relación con la actividad investigada.
Se documenta la suplantación de imagen.

Varias de las imágenes de lujo publicadas en el perfil son sometidas también
a búsqueda inversa. Dos de ellas aparecen en bancos de imágenes de uso
comercial, confirmando que el contenido ha sido construido artificialmente.

El alias de Telegram es buscado en el buscador nativo de la plataforma y
en herramientas de indexación de canales públicos. Se localiza un canal
público con el mismo alias que ha publicado contenido de captación de víctimas
y que contiene, en publicaciones anteriores, un número de teléfono y una
dirección de correo electrónico de contacto.

El correo electrónico se investiga siguiendo el procedimiento del capítulo
dedicado a emails. La búsqueda revela su uso en el registro de un dominio
vinculado a otra plataforma de inversión fraudulenta con características
similares y su presencia en un perfil de X con actividad anterior al inicio
del perfil de Instagram investigado. El perfil de X comparte el mismo alias
y muestra publicaciones más antiguas que revelan un patrón de conducta
consistente.

**Hallazgos obtenidos**

El perfil de Instagram ha sido construido artificialmente: foto de perfil
suplantada, contenido de imágenes tomado de fuentes externas, seguidores de
perfil bajo autenticidad. El alias de Telegram está vinculado a un canal de
captación activo. El correo electrónico vinculado al canal conecta con otra
plataforma fraudulenta y con una cuenta de X con actividad anterior. El
conjunto de hallazgos revela una operación con trayectoria previa a la
investigación actual.

**Análisis e interpretación**

La coherencia entre los hallazgos —suplantación de imagen documentada,
artificialidad del contenido del perfil, alias reutilizado en Telegram y X,
correo electrónico vinculado a infraestructura adicional— configura un indicio
relacional sólido de una operación organizada y premeditada. La identificación
de la persona cuya imagen fue suplantada abre la posibilidad de contactar
con esa persona como posible víctima adicional no denunciante.

**Explotación policial y documental**

Los hallazgos se documentan en un informe de inteligencia que describe la
secuencia completa de búsquedas y análisis realizados, con los correspondientes
archivos de preservación. El informe identifica a la persona cuya imagen fue
suplantada. Fundamenta solicitudes de información a Instagram y a Telegram
sobre los datos de registro de las cuentas investigadas, con cobertura
judicial, y solicitudes de información al registrador del dominio vinculado
al correo electrónico.

**Lecciones operativas**

Este caso ilustra que el análisis de las imágenes del perfil fue el paso
determinante para desmontar la apariencia de legitimidad del fraude. La
búsqueda inversa de la foto de perfil y de las imágenes de contenido reveló
la artificialidad del perfil mucho más rápidamente que el análisis textual.
La investigación del alias de Telegram amplió la investigación hacia una
red de actividad más extensa. Y la correlación entre el correo electrónico,
el dominio y el perfil de X estableció la continuidad temporal de la operación,
que precede al perfil de Instagram investigado inicialmente.

---

## 12. Conclusiones operativas

Las redes sociales abiertas son, en el ecosistema del cibercrimen, uno de
los entornos con mayor densidad de información investigativamente relevante.
Su análisis riguroso puede revelar datos de identidad, cronología de conductas,
relaciones significativas, pivotes hacia otros elementos digitales y patrones
de actividad que, en conjunto, construyen un cuadro indiciario de notable
solidez.

Ese potencial se realiza solo cuando el investigador trabaja con método: la
lectura analítica sistemática del perfil, la preservación inmediata del
contenido identificado como relevante, el análisis cuidadoso de la actividad
y las relaciones visibles, la búsqueda transversal de los elementos del perfil
en otras plataformas y la explotación disciplinada de los pivotes que cada
hallazgo genera son los pasos que convierten una observación inicial en
conocimiento útil. La prudencia en la atribución, la verificación activa de
la autenticidad de los perfiles y la documentación rigurosa del proceso son
las condiciones que hacen que ese conocimiento sea también procesalmente
sostenible.

---

## 13. Checklist final de trabajo

**Identificación y localización del perfil**

- Localizar el perfil relevante usando el dato disponible: enlace, nombre,
  alias o imagen.
- Verificar que el perfil localizado corresponde al objeto de la
  investigación y no a un homónimo.
- Identificar posibles presencias del mismo sujeto en otras plataformas.

**Análisis inicial del perfil**

- Analizar sistemáticamente todos los elementos visibles: nombre, username,
  foto, bio, datos de contacto, fecha de creación visible, número de
  publicaciones y relaciones visibles.
- Evaluar la coherencia interna del perfil: ¿son consistentes entre sí
  todos sus elementos?
- Someter la imagen de perfil a búsqueda inversa en al menos dos motores
  de imágenes.
- Preservar el estado actual del perfil mediante archivado web con sello
  temporal antes de continuar la investigación.

**Análisis de actividad y relaciones**

- Examinar la cronología de publicaciones: fechas de actividad, períodos
  de mayor frecuencia y huecos significativos.
- Analizar el contenido de las publicaciones relevantes: temas, lenguaje,
  patrones de publicación, referencias geográficas.
- Explorar las relaciones visibles: seguidores, seguidos, menciones
  recurrentes, grupos de pertenencia.
- Preservar de forma individual las publicaciones y los perfiles relacionados
  que sean investigativamente relevantes.

**Investigación transversal y pivotes**

- Buscar el alias y la imagen de perfil en otras plataformas.
- Explotar los datos de contacto visibles como pivotes hacia otros
  elementos de la investigación.
- Investigar las cuentas relacionadas más relevantes.
- Verificar la autenticidad del contenido publicado mediante búsqueda
  inversa de imágenes cuando proceda.

**Interpretación, síntesis y explotación**

- Evaluar la coherencia interna del conjunto de hallazgos.
- Distinguir explícitamente entre cuenta auténtica, instrumental o
  construida con datos falsos.
- No formular atribuciones personales más allá de lo que los hallazgos
  permiten sostener.
- Identificar las diligencias adicionales con cobertura judicial necesarias
  para confirmar la atribución personal.
- Elaborar el informe con descripción metodológica completa, archivos de
  preservación verificables y exposición honesta de los límites de las
  conclusiones.

---