# Capítulo 10. Investigación de dominios, URLs, IP e infraestructura digital en fuentes abiertas

---

## 1. Introducción

La infraestructura digital de una operación de cibercrimen no es invisible.
Al contrario: deja rastros técnicos distribuidos en múltiples registros,
bases de datos, servicios de reputación y repositorios de información que
son accesibles en abierto para quien sabe consultarlos con el criterio
adecuado. El dominio de una página de phishing, la URL de un panel de control
fraudulento, la dirección IP de un servidor que aloja múltiples campañas de
estafa o el certificado digital de una web que suplanta a una entidad financiera
no son solo datos técnicos anónimos: son observables que, correctamente
analizados, pueden revelar relaciones entre campañas, proveedores de
infraestructura, patrones de operación y conexiones con otras actividades
o identidades digitales ya investigadas.

Esta dimensión de la investigación OSINT —el análisis de la infraestructura
técnica como objeto de investigación en fuentes abiertas— es especialmente
relevante en cibercrimen porque la actividad delictiva en internet requiere,
por definición, infraestructura: dominios para alojar páginas fraudulentas,
servidores para gestionar paneles de administración, certificados para dar
apariencia de legitimidad, registros DNS para resolver nombres a direcciones,
y todo el aparato técnico que sostiene la operación. Esa infraestructura
puede ser investigada, documentada y explotada como pivote hacia otros
elementos de la investigación sin necesidad de acceder a ningún sistema sin
autorización y sin realizar ninguna actuación ofensiva.

El investigador que sabe leer la infraestructura digital en fuentes abiertas
tiene acceso a una dimensión de la investigación que complementa de forma
sustancial el análisis de identidades digitales, correos, teléfonos y aliases
desarrollado en los capítulos anteriores. Este capítulo proporciona las
herramientas conceptuales, metodológicas y operativas para hacerlo con rigor
y con criterio profesional.

---

## 2. Finalidad investigadora del capítulo

Este capítulo cierra la serie de capítulos aplicativos centrados en objetos
de investigación específicos, abordando uno de los más técnicamente densos
pero también uno de los más ricos en posibilidades de pivot: la infraestructura
digital como conjunto de observables técnicos investigables en fuentes abiertas.

Su función dentro del manual es proporcionar al investigador un marco analítico
y una secuencia de trabajo para abordar dominios, URLs, direcciones IP y los
elementos técnicos asociados —DNS, certificados, ASN, subdominios,
infraestructura de alojamiento— con el mismo rigor metodológico aplicado en
los capítulos anteriores a otros tipos de datos.

El capítulo resulta especialmente útil en investigaciones de phishing,
suplantación de entidades, fraude de inversión con plataformas web fraudulentas,
soporte técnico falso, campañas de malware delivery, compraventa fraudulenta
con webs de apariencia legítima, y cualquier otro tipo de cibercrimen en que
la actividad delictiva se apoye en infraestructura web identificable. Su
contenido está orientado a que el lector, al concluirlo, sea capaz de iniciar
una investigación OSINT a partir de una URL, un dominio o una IP con método,
con conocimiento suficiente de las herramientas disponibles y con la prudencia
interpretativa que este tipo de análisis requiere.

---

## 3. Objeto de análisis y punto de partida

### 3.1. Tipología de observables técnicos

A efectos de este capítulo, el término observable técnico engloba los distintos
elementos de infraestructura digital que pueden constituir el punto de partida
o el objeto de análisis de una investigación OSINT en este ámbito.

El **dominio** es el nombre legible asociado a un recurso de internet, compuesto
por un nombre de segundo nivel y una extensión de primer nivel —TLD—. Los
dominios son objetos registrables con datos de titular, fecha de registro y
proveedor registrador asociados, aunque con frecuencia los datos de titular
se encuentran anonimizados a través de servicios de privacidad WHOIS.

La **URL** es la dirección completa de un recurso específico, que incluye el
protocolo, el dominio, la ruta, los parámetros y el fragmento. Una URL puede
contener información útil sobre la estructura del recurso, la tecnología
utilizada, el tipo de contenido esperado y, en ocasiones, parámetros de
rastreo o de personalización que aportan contexto sobre la campaña en que
fue utilizada.

La **dirección IP** es el identificador numérico asignado a un dispositivo
o servidor en internet. Las direcciones IP públicas están asociadas a
proveedores de servicios de internet o de alojamiento web, y pueden
contextualizarse mediante información de geolocalización aproximada, número
de sistema autónomo —ASN— y reputación registrada en servicios de inteligencia
de amenazas.

El **certificado digital** —especialmente el certificado TLS/SSL que habilita
la navegación segura bajo el protocolo HTTPS— contiene información sobre el
dominio o dominios para los que fue emitido, la autoridad de certificación
emisora y el período de validez. Su análisis puede revelar relaciones entre
dominios que comparten certificado o patrones de emisión propios de
determinadas infraestructuras de fraude.

Los **registros DNS** —A, MX, NS, CNAME, TXT y otros— son los registros de
resolución que vinculan un dominio con su infraestructura técnica: los
servidores que lo alojan, los servidores de correo asociados, los nameservers
que lo gestionan y otros elementos que pueden revelar relaciones con otras
infraestructuras o con proveedores específicos.

### 3.2. Contextos de aparición y preguntas iniciales

Los observables técnicos pueden llegar al investigador por múltiples vías:
la URL enviada por la víctima del phishing, el dominio registrado con el
mismo correo electrónico que otros dominios fraudulentos, la IP identificada
en las cabeceras de un correo malicioso, el certificado que vincula varios
dominios de una misma campaña o el enlace acortado compartido en un canal
de fraude.

Las preguntas que el investigador debe formular desde el inicio son las
siguientes: ¿qué tipo de observable es este y qué información visible contiene?
¿Cuándo fue registrado o creado y qué señales de antigüedad o de actividad
reciente existen? ¿Qué infraestructura técnica está asociada a este observable?
¿Existen relaciones con otros observables ya conocidos en la investigación?
¿Qué señales de reputación registran los servicios de inteligencia de amenazas
para este elemento? ¿Qué pivotes ofrece hacia otros elementos —correos, IP,
dominios relacionados, certificados, contenidos visibles— que puedan ampliar
la investigación?

---

## 4. El observable técnico como pivote de investigación y contexto de infraestructura

### 4.1. La infraestructura como huella operativa

Toda operación de cibercrimen que utiliza infraestructura web deja, en esa
infraestructura, una serie de huellas que pueden ser investigadas en fuentes
abiertas. La elección del proveedor de alojamiento, del registrador de dominio,
del servicio de certificación, del nameserver y de las configuraciones técnicas
específicas es una decisión operativa que refleja tanto la capacidad técnica
del operador como sus preferencias, sus recursos y, en muchos casos, sus
patrones de conducta habituales.

Un operador que registra dominios de phishing con el mismo registrador, los
aloja en el mismo proveedor de hosting y los emite bajo la misma autoridad
de certificación en campañas sucesivas está dejando una huella de
infraestructura que vincula esas campañas entre sí aunque cada dominio tenga
un nombre distinto. La detección de esos patrones es uno de los vectores más
potentes de la investigación de infraestructura en fuentes abiertas.

### 4.2. Relaciones entre observables y construcción del grafo técnico

El valor máximo de la investigación de infraestructura no reside en el análisis
de cada observable por separado, sino en la construcción de un grafo de
relaciones técnicas entre observables: el dominio A resuelve a la IP X, que
también aloja el dominio B vinculado a una campaña previa; el certificado
del dominio A fue emitido para un wildcard que incluye subdominios relacionados;
el correo del registro del dominio A es el mismo que aparece en el registro
del dominio C, vinculado a otra investigación. Cada relación añade consistencia
a la hipótesis de que distintos elementos de la investigación forman parte
del mismo ecosistema operativo.

La construcción de ese grafo requiere combinar los resultados de múltiples
herramientas y contrastarlos antes de incorporar cada relación como elemento
activo de la investigación.

---

## 5. Análisis inicial del dominio, la URL o la IP y contextualización del hallazgo

### 5.1. Lectura analítica inicial

El primer paso ante cualquier observable técnico es la lectura analítica de
su propio contenido antes de realizar ninguna consulta externa.

En el caso de una **URL**, el investigador debe descomponerla en sus partes:
protocolo —HTTP o HTTPS, con sus implicaciones sobre la presencia de
certificado—, dominio o subdominio, ruta de acceso al recurso, parámetros
de consulta y fragmento. La ruta y los parámetros pueden revelar información
sobre la estructura del recurso —si es un panel de administración, un formulario
de captura de datos, una página de descarga o una redirección—, la tecnología
utilizada y, en algunos casos, la campaña o el identificador de víctima
embebido en el enlace. El investigador debe registrar la URL completa en su
formato exacto antes de realizar cualquier análisis, porque los parámetros
pueden ser relevantes.

En el caso de un **dominio**, el análisis inicial debe atender al nombre en
sí —si contiene palabras clave que simulan legitimidad, si presenta variaciones
ortográficas respecto a dominios legítimos conocidos (*typosquatting*), si
tiene una estructura de subdominio sospechosa—, a la extensión TLD y a la
plausibilidad de la combinación nombre-extensión para el tipo de servicio
que pretende representar.

En el caso de una **IP**, el análisis inicial es más limitado en la lectura
directa, pero incluye la identificación del rango al que pertenece —que puede
indicar si es un proveedor de alojamiento conocido, un proveedor de VPN o
una red residencial— y la valoración del contexto en que fue obtenida.

### 5.2. Contextualización del hallazgo

Como en todos los capítulos anteriores, el observable técnico debe analizarse
dentro del contexto en que fue encontrado: cuándo, en qué circunstancias,
qué actividad lo rodea y cuál es su relación con los hechos investigados.
Una IP identificada en las cabeceras de un correo de phishing tiene un
contexto distinto a la misma IP encontrada como servidor de alojamiento de
una web fraudulenta. El investigador debe documentar ese contexto antes de
iniciar la investigación técnica.

---

## 6. Investigación, reutilización y ampliación de la investigación a partir de dominios, URLs, IP e infraestructura asociada

### 6.1. Investigación del dominio

La investigación de un dominio en fuentes abiertas tiene varias dimensiones
que deben abordarse de forma sistemática.

El **registro del dominio** —datos de titular, fecha de registro, registrador,
nameservers y, cuando están disponibles, datos de contacto— es la primera
fuente de información. Los servicios WHOIS públicos proporcionan esta
información, aunque con frecuencia los datos de titular están anonimizados
por servicios de privacidad. La fecha de registro y el registrador son datos
habitualmente disponibles incluso cuando el titular está anonimizado, y pueden
ser analíticamente relevantes: un dominio registrado pocos días antes de una
campaña de phishing, en un registrador conocido por sus políticas permisivas,
es un indicador de contexto que el investigador debe incorporar.

La **resolución DNS** del dominio —los registros A que vinculan el dominio
con su dirección IP, los registros MX que identifican sus servidores de correo,
los registros NS que identifican sus nameservers y otros registros relevantes—
proporciona información sobre la infraestructura técnica del dominio y puede
revelar vínculos con otros dominios que comparten los mismos servidores de
correo, los mismos nameservers o las mismas IP de alojamiento.

Los **subdominios** visibles —que pueden obtenerse a través de servicios de
enumeración pasiva de subdominios, de bases de datos de certificados y de
motores de búsqueda— pueden revelar la estructura completa de la infraestructura
del dominio: paneles de administración, sistemas de gestión, servidores de
correo, páginas de destino de campañas específicas o recursos técnicos que
no están directamente vinculados al dominio principal.

El **historial de resolución** del dominio —las IP a las que ha resuelto en
distintos momentos— puede revelar cambios de alojamiento que ayudan a
contextualizar la actividad del dominio a lo largo del tiempo.

### 6.2. Investigación de la IP

La investigación de una dirección IP en fuentes abiertas produce información
de distinta naturaleza y con distintos niveles de fiabilidad.

La **geolocalización aproximada** de una IP indica el país y, con menor
precisión, la región o ciudad asociada al bloque de IPs en que se encuentra.
Esta información es orientativa y no puede usarse como indicador de la
ubicación física del operador: los operadores de cibercrimen utilizan
habitualmente servicios de alojamiento en jurisdicciones distintas a su
ubicación real, servicios de VPN o redes de proxies.

El **ASN y el proveedor de alojamiento** asociados a la IP son más útiles
desde el punto de vista investigativo que la geolocalización: saber que una
IP pertenece a un proveedor de alojamiento cloud conocido, a un proveedor
de VPN, a una red de servidores dedicados o a un proveedor de servicios de
internet residencial aporta información sobre el tipo de infraestructura
utilizada y sobre las posibilidades de obtener datos del proveedor mediante
diligencias judiciales.

Los **dominios alojados en la misma IP** —obtenibles a través de servicios
de resolución inversa— pueden revelar si la IP aloja una infraestructura
compartida y si existen otros dominios en esa IP que puedan estar vinculados
a la misma operación o a operaciones similares.

La **reputación** de la IP en servicios de inteligencia de amenazas puede
confirmar si ha sido reportada previamente en relación con actividades
maliciosas, qué tipos de actividad se han documentado y en qué fechas.

---

## 7. Herramientas y recursos prácticos para la investigación de dominios, URLs, IP e infraestructura digital

### 7.1. Herramientas de análisis inicial y reputación de URLs

**VirusTotal** es la herramienta de análisis de reputación más ampliamente
utilizada en este ámbito. Acepta como entrada URLs, dominios, direcciones IP
o hashes de archivos, y los contrasta contra un amplio conjunto de motores
de análisis de amenazas y bases de datos de reputación. Para una URL o un
dominio, devuelve el resultado del análisis por cada motor integrado, el
historial de detecciones, los datos de resolución DNS asociados, la información
WHOIS disponible y los comentarios de la comunidad. Su valor operativo es
muy alto como primer paso de la investigación, porque permite obtener
rápidamente un panorama de la reputación del observable en múltiples fuentes
simultáneas. Su limitación principal es que los resultados de los motores
individuales no siempre son coherentes entre sí y que una ausencia de
detección no equivale a ausencia de actividad maliciosa —especialmente en
dominios recién registrados o en campañas muy recientes—.

**URLScan.io** es una herramienta de análisis de URLs que visita la URL
proporcionada desde su propia infraestructura y genera un informe detallado
del resultado: una captura de pantalla del contenido visible, el código HTML
de la página, las peticiones de red realizadas durante la carga, las
tecnologías detectadas, los dominios y IPs contactados durante la carga y
los certificados utilizados. Su valor para el investigador es doble: permite
analizar el contenido de una URL sospechosa sin acceder directamente desde
el dispositivo de investigación —reduciendo el riesgo de exposición técnica—
y genera un registro verificable del estado de la URL en el momento del
análisis, con sello temporal, que puede ser usado como documentación del
hallazgo. La búsqueda en el repositorio público de URLScan.io permite
encontrar análisis previos de dominios o IPs que otros usuarios o sistemas
han realizado, lo que puede revelar el estado de la infraestructura en
momentos anteriores.

**Google Safe Browsing** y la función equivalente de búsqueda en Google de
una URL entre comillas pueden proporcionar una indicación inicial sobre si
la URL ha sido identificada como maliciosa por los sistemas de protección del
motor de búsqueda, aunque su cobertura de campañas muy recientes o de dominios
especializados puede ser limitada.

### 7.2. Herramientas de análisis WHOIS, DNS y contexto de dominio

**SecurityTrails** es una plataforma de inteligencia de infraestructura que
proporciona acceso a datos históricos de WHOIS, historial de resolución DNS,
subdominios identificados pasivamente, registros MX y NS históricos, y
dominios que han resuelto a la misma IP. Su valor para el investigador reside
en la dimensión histórica: no solo muestra el estado actual del dominio, sino
cómo ha evolucionado su infraestructura a lo largo del tiempo, qué IP ha
utilizado en distintos momentos y qué otros dominios han compartido esa
infraestructura. La función de búsqueda inversa por correo electrónico de
registro WHOIS permite identificar todos los dominios registrados con el mismo
correo, lo que en investigaciones de phishing puede revelar campañas enteras
a partir de un único dato.

**MXToolbox** es un servicio de análisis de registros DNS con especial énfasis
en los registros de correo —MX, SPF, DKIM, DMARC—. Su valor investigativo
es alto en análisis de infraestructura de correo: permite verificar los
registros MX de un dominio, comprobar si tiene configuraciones de autenticación
de correo que dan apariencia de legitimidad y consultar el estado de reputación
del dominio y de sus IPs en listas negras de correo. En investigaciones de
phishing por correo electrónico, el análisis de los registros MX del dominio
remitente puede revelar si el dominio fue configurado específicamente para
el envío de correo malicioso o si es un dominio genérico reutilizado.

**DNSDumpster** y herramientas similares de enumeración pasiva de subdominios
permiten obtener un mapa de la infraestructura DNS visible de un dominio,
incluyendo subdominios identificados a través de diversas fuentes pasivas.
Esta visión de conjunto puede revelar la estructura operativa de una
infraestructura de fraude: un subdominio «login.», «panel.» o «admin.» en
un dominio fraudulento puede indicar la existencia de recursos técnicos
adicionales que conviene investigar.

**Whois.domaintools.com** y los servicios WHOIS de los registradores y de
ICANN ofrecen datos de registro actuales. Para dominios con datos anonimizados,
la información de registrador, fecha de registro y nameservers sigue estando
disponible y puede ser analíticamente relevante.

### 7.3. Herramientas de análisis de certificados y relaciones técnicas

**crt.sh** es un motor de búsqueda de certificados TLS/SSL basado en el
registro público de transparencia de certificados —Certificate Transparency
Log—. Permite buscar todos los certificados emitidos para un dominio o para
un patrón de dominio, con información sobre la autoridad emisora, el período
de validez y, crucialmente, todos los nombres de host —incluyendo subdominios—
para los que fue emitido cada certificado. Su valor investigativo es muy alto
porque la transparencia de certificados es un registro público inmutable: todos
los certificados emitidos por autoridades de certificación reconocidas deben
registrarse públicamente, lo que hace imposible emitir certificados «ocultos».
En la práctica, crt.sh permite identificar subdominios de un dominio investigado
que no son visibles por otras vías, y detectar relaciones entre dominios que
comparten certificados wildcard o que han sido emitidos en el mismo período
para la misma infraestructura. Una búsqueda en crt.sh del dominio de una
campaña de phishing puede revelar toda la estructura de subdominios utilizada
en esa campaña, incluyendo los que ya han sido dados de baja pero cuyo
certificado sigue registrado.

### 7.4. Herramientas de análisis de IP, ASN y contexto de alojamiento

**Shodan** es el motor de búsqueda de dispositivos y servicios expuestos en
internet más conocido en el ámbito de la ciberseguridad. Permite buscar una
dirección IP y obtener información sobre los servicios expuestos que Shodan
ha detectado en esa IP durante sus análisis periódicos: puertos abiertos,
banners de servicios, tecnologías identificadas, certificados detectados y
el historial de esa información. Su valor para el investigador de cibercrimen
en fuentes abiertas no es ofensivo —no se usa para atacar sino para observar
lo que ya está expuesto—, sino contextual: entender qué tipo de servidor es
el que aloja un dominio fraudulento, qué tecnologías utiliza y si ha presentado
históricamente otros servicios relevantes. La función de búsqueda por
organización o por ASN permite identificar toda la infraestructura visible
de un proveedor específico, lo que puede ser útil cuando la investigación
apunta hacia un proveedor de alojamiento concreto.

**Censys** ofrece funcionalidades similares a Shodan pero con un enfoque
diferente en la forma de indexar y presentar la información. Su motor de
búsqueda permite consultar IPs y certificados de forma combinada, lo que
lo hace especialmente útil para investigaciones en que la relación entre
IP y certificado es el eje del análisis. La búsqueda por hash de certificado
o por nombre de dominio en el índice de certificados de Censys puede revelar
todas las IPs que han servido ese certificado, lo que puede vincular
distintas etapas de una campaña en que la infraestructura de alojamiento
cambió pero el certificado se mantuvo.

**AbuseIPDB** es una base de datos colaborativa de reputación de IPs en la
que usuarios y sistemas automatizados reportan direcciones IP asociadas a
actividades maliciosas: spam, phishing, ataques de fuerza bruta, escaneos
maliciosos y otros tipos de abuso. Permite consultar una IP y obtener el
historial de reportes, el tipo de actividad registrada y la frecuencia de
los reportes. Su valor operativo como primer indicador de reputación es alto;
su limitación es que la calidad y la cobertura de los reportes son variables
y dependen de la actividad de sus contribuidores.

**IPinfo.io**, **ip-api.com** y servicios similares de consulta de información
de IP proporcionan datos de geolocalización aproximada, ASN, proveedor y
tipo de conexión para una dirección IP dada. Son herramientas de uso rápido
para una primera contextualización de la IP investigada.

### 7.5. Herramientas de análisis de relaciones e infraestructura asociada

**RiskIQ Community** —actualmente integrado en Microsoft Defender Threat
Intelligence— y plataformas similares de inteligencia de infraestructura
permiten explorar las relaciones entre observables técnicos: qué dominios
han resuelto a una IP, qué IPs ha utilizado un dominio, qué certificados
están asociados, qué otros dominios comparten los mismos nameservers, y otros
datos de relación que permiten construir el grafo técnico de una infraestructura.

**Maltego** con módulos de infraestructura técnica permite integrar estos
análisis en un grafo visual interactivo, combinando datos de múltiples fuentes
y visualizando las relaciones entre dominios, IPs, correos, certificados y
otros observables.

**PassiveDNS** como concepto —implementado en servicios como SecurityTrails,
DNSDB o passivedns.mnemonic.no— es el registro histórico de resoluciones DNS,
que permite ver qué IPs ha resuelto un dominio en el pasado y qué dominios
han resuelto a una IP en el pasado. Esta perspectiva histórica es fundamental
en investigaciones de infraestructura porque la actividad maliciosa frecuentemente
utiliza infraestructura que ha sido rotada: el dominio actual puede ser
diferente al que se usó en la campaña, pero la IP puede ser la misma, o los
mismos nameservers pueden haber sido utilizados en ambos.

### 7.6. Herramientas de preservación y documentación

**URLScan.io** también sirve como herramienta de preservación: el análisis
que realiza genera un informe con URL permanente, sello temporal y captura
visual del estado del recurso en el momento del análisis, que puede ser
referenciado en el informe del investigador como documentación del hallazgo.

**Archive.today** y **Wayback Machine** permiten archivar páginas web con
sello temporal verificable. Son especialmente útiles para preservar el
contenido visual de páginas fraudulentas antes de que sean dadas de baja.
La combinación de un archivo en Archive.today con el hash del archivo generado
constituye una forma sólida de documentar el estado de un recurso web en
el momento de la investigación.

Para la preservación de resultados de herramientas de análisis técnico, el
investigador debe exportar o capturar los resultados completos de cada consulta,
con registro de la fecha y hora, la herramienta utilizada, el dato de entrada
y el resultado obtenido. Las capturas de pantalla de los resultados de
VirusTotal, URLScan, SecurityTrails o crt.sh, acompañadas de sus hashes y
de la descripción del proceso de obtención, constituyen la documentación
técnica del análisis.

---

## 8. Procedimiento operativo de investigación a partir de una URL, dominio o IP

El siguiente procedimiento describe una secuencia realista para el investigador
que inicia o enriquece una investigación a partir de un observable técnico.

**Primera fase: análisis del observable.** El investigador registra el
observable exactamente tal como fue obtenido —URL completa, dominio, IP— y
analiza su estructura: tipo de observable, componentes visibles, indicadores
iniciales de interés o de alerta. Documenta el contexto de aparición del dato.

**Segunda fase: preservación inicial.** Para URLs que corresponden a páginas
web accesibles, el investigador genera un análisis en URLScan.io y un archivo
en Archive.today antes de continuar la investigación, dado el riesgo de que
el contenido sea dado de baja. Documenta los archivos generados con sus hashes
y sellos temporales.

**Tercera fase: análisis de reputación.** El investigador consulta el observable
en VirusTotal y en AbuseIPDB para obtener un primer panorama de su reputación
en servicios de inteligencia de amenazas. Documenta los resultados.

**Cuarta fase: análisis de dominio.** Si el observable es un dominio o contiene
un dominio, el investigador consulta los datos de registro WHOIS, los registros
DNS actuales —A, MX, NS, TXT— y el historial de resolución disponible en
SecurityTrails u otras fuentes de PassiveDNS. Consulta crt.sh para obtener
los certificados emitidos para ese dominio y sus subdominios. Documenta todos
los resultados.

**Quinta fase: análisis de IP.** Para la IP o IPs identificadas en la
resolución del dominio o proporcionadas directamente como dato, el investigador
consulta su información de ASN y proveedor, su reputación en AbuseIPDB y
los datos de servicios expuestos en Shodan o Censys. Identifica otros dominios
que han resuelto o resuelven actualmente a esa IP.

**Sexta fase: análisis de relaciones e infraestructura asociada.** El
investigador utiliza los datos obtenidos en las fases anteriores para construir
el grafo de relaciones técnicas: qué dominios comparten IP, qué dominios
comparten nameservers o correo de registro WHOIS, qué subdominios existen,
qué certificados vinculan varios dominios.

**Séptima fase: investigación de pivotes.** A partir de los datos de registro
—correo electrónico de WHOIS, teléfono, nombre de titular cuando están
disponibles—, el investigador los investiga siguiendo los procedimientos de
los capítulos correspondientes. Los dominios relacionados identificados se
investigan siguiendo el mismo procedimiento de forma recursiva con el nivel
de prioridad que las preguntas de investigación determinen.

**Octava fase: síntesis y valoración.** El investigador evalúa el conjunto
de hallazgos, construye el mapa de infraestructura identificado, valora la
coherencia interna de las hipótesis formuladas y determina qué diligencias
adicionales son necesarias.

---

## 9. Interpretación de hallazgos, cautelas y errores frecuentes

### 9.1. Límites de la inferencia técnica

El error más frecuente en la interpretación de observables técnicos es la
atribución directa de la infraestructura a una persona física. Una dirección
IP es la dirección de un servidor o de un dispositivo; no es la dirección
de una persona. Un servidor puede ser compartido entre múltiples clientes
sin relación entre sí. Un dominio puede haber sido registrado por un operador
que luego cedió el servidor a otro. La geolocalización de una IP indica dónde
está el servidor, no dónde está el operador.

Estas realidades no eliminan el valor investigativo de los observables técnicos,
pero imponen la exigencia de no saltar directamente del análisis técnico a
conclusiones sobre autoría personal sin corroboración adicional.

### 9.2. Errores frecuentes en la investigación de infraestructura

La **sobreinterpretación de la geolocalización IP** es el error más extendido.
Presentar la geolocalización de una IP como la localización del operador —o
incluso del dispositivo del autor— es una simplificación que puede ser
dramáticamente errónea.

La **atribución por hosting compartido** es otro error frecuente: asumir que
porque dos dominios resuelven a la misma IP están operados por la misma persona.
En servidores de alojamiento compartido, una misma IP puede albergar miles
de dominios de titulares distintos sin ninguna relación entre ellos.

La **confianza ciega en un único motor de reputación** —asumir que porque
VirusTotal no detecta actividad maliciosa el dominio es legítimo— es una
simplificación que ignora el ciclo de vida de las campañas de phishing: los
dominios recién registrados frecuentemente no han sido detectados todavía
por los motores de reputación.

La **falta de preservación oportuna** tiene consecuencias especialmente graves
en investigaciones de infraestructura, dado que los dominios de phishing y
las páginas fraudulentas tienen una vida útil frecuentemente muy corta:
pueden ser dados de baja en horas una vez que comienzan a recibir reportes.

---

## 10. Aspectos jurídicos, deontológicos y probatorios específicos

### 10.1. Legitimidad de las consultas en fuentes abiertas

El análisis de observables técnicos mediante las herramientas descritas en
este capítulo —WHOIS, DNS, análisis de reputación, consulta de bases de datos
de certificados, análisis de servicios expuestos en Shodan o Censys— constituye
observación de información públicamente disponible o de información generada
como parte del funcionamiento normal de la infraestructura de internet. Con
carácter general, estas consultas pueden realizarse dentro de los límites de
la investigación en fuentes abiertas.

El acceso directo a recursos web —visitar una URL para analizar su contenido—
tiene implicaciones distintas y debe realizarse con las cautelas de OPSEC
descritas en el capítulo cuarto, especialmente cuando el recurso puede estar
bajo el control del objetivo. El uso de herramientas como URLScan.io para
acceder al contenido de forma mediada —sin que el servidor del objetivo reciba
la conexión directa del investigador— es la práctica recomendada.

### 10.2. Preservación y valor probatorio del análisis técnico

La documentación del análisis técnico debe ser suficientemente detallada
para que cualquier tercero con la formación adecuada pueda verificar que el
proceso seguido fue razonable y reproducible. Los resultados de las
herramientas utilizadas deben ser preservados con registro de la fecha y hora
de la consulta, la herramienta y la versión utilizada, el dato de entrada y
el resultado completo obtenido. La exportación de los resultados en formato
estructurado cuando la herramienta lo permite es preferible a las capturas
de pantalla, aunque estas pueden ser un complemento útil.

---

## 11. Caso práctico aplicado

### Caso práctico: Identificación de una infraestructura de phishing bancario y su vinculación con campañas previas a partir de una URL fraudulenta

**Supuesto de hecho**

Una unidad especializada en cibercrimen recibe la comunicación de una entidad
bancaria que ha detectado una campaña de phishing activa dirigida contra sus
clientes: mensajes de correo electrónico que, bajo la apariencia de una
comunicación oficial del banco, dirigen a las víctimas a una página que imita
fielmente el portal de acceso de la entidad para capturar sus credenciales.
La entidad aporta la URL del sitio fraudulento y un ejemplo del correo de
captación.

**Dato o indicio de partida**

La URL fraudulenta aportada por la entidad bancaria, que contiene el nombre
del banco en un subdominio bajo un dominio de tercer nivel, y el correo
electrónico de remitente del mensaje de captación.

**Hipótesis de trabajo**

El dominio fraudulento puede haber sido registrado recientemente con datos
de titular que —aunque posiblemente ficticios o anonimizados— pueden vincularlo
con otros dominios de la misma operación. La IP de alojamiento puede estar
siendo utilizada para otros dominios de phishing simultáneos. El correo
electrónico del remitente puede estar vinculado a registros de otros dominios.

**Actuaciones realizadas**

El investigador comienza preservando inmediatamente el estado del sitio
fraudulento mediante un análisis en URLScan.io, que genera una captura visual
y un registro técnico completo de la página con sello temporal. El contenido
visual confirma que la página es una copia del portal legítimo del banco.
El análisis de URLScan revela la IP de alojamiento, el certificado TLS
utilizado y los recursos externos cargados durante el acceso.

Se consulta el dominio en VirusTotal, que ya muestra detecciones de varios
motores en relación con phishing bancario. El análisis WHOIS revela que el
dominio fue registrado cuatro días antes de la comunicación de la entidad,
con datos de titular anonimizados pero con nameservers específicos.

La búsqueda de esos nameservers en SecurityTrails devuelve una lista de
cuarenta y dos dominios que actualmente utilizan los mismos nameservers, varios
de los cuales presentan nombres que imitan a otras entidades financieras de
distintos países. Se documentan todos los dominios identificados.

La consulta en crt.sh del dominio fraudulento revela que el certificado fue
emitido como wildcard para ese dominio y para varios subdominios, incluyendo
tres subdominios adicionales no detectados inicialmente, con nombres que
corresponden a otros servicios del banco suplantado.

La IP de alojamiento se consulta en Shodan y AbuseIPDB. AbuseIPDB confirma
que la IP tiene reportes previos de actividad de phishing de los últimos tres
meses. La consulta en SecurityTrails de la IP revela veintiún dominios que
actualmente resuelven a esa IP, todos con características similares al dominio
investigado.

El correo electrónico de remitente del mensaje de captación se investiga
siguiendo el procedimiento del capítulo quinto. La búsqueda en SecurityTrails
por el correo como dato de registro WHOIS devuelve ocho dominios adicionales
registrados con ese correo en los últimos seis meses, todos con el mismo
patrón de imitación de entidades financieras.

**Hallazgos obtenidos**

El dominio fraudulento inicial forma parte de una infraestructura más amplia:
cuarenta y dos dominios comparten sus nameservers; veintiún dominios comparten
su IP de alojamiento; el certificado wildcard cubre subdominios adicionales;
y el correo de registro vincula ocho dominios adicionales en el mismo período.
La operación tiene características de una campaña organizada de phishing
bancario dirigida a múltiples entidades en distintos países.

**Análisis e interpretación**

La coherencia técnica entre todos los hallazgos —nameservers compartidos,
IP de alojamiento compartida con otros dominios de phishing, correo de registro
que vincula múltiples dominios, patrón de registro reciente consistente—
configura un cuadro de infraestructura que apunta hacia una operación organizada
con escala significativa y trayectoria documentable. La identificación de
entidades bancarias de otros países entre los objetivos sugiere dimensión
transnacional de la operación.

**Explotación policial y documental**

Los hallazgos se documentan en un informe técnico de inteligencia con la
secuencia completa de consultas, las herramientas utilizadas, los resultados
obtenidos y todos los archivos de preservación. El informe fundamenta
solicitudes judiciales de información al registrador del dominio y al proveedor
de alojamiento sobre los datos del cliente, y abre la posibilidad de coordinación
con autoridades de otros países afectados a través de los canales de cooperación
internacional.

**Lecciones operativas**

Este caso ilustra que la investigación de un único dominio fraudulento puede
revelar, en pocas horas de trabajo metódico con herramientas de fuentes
abiertas, el mapa técnico de una campaña organizada de escala internacional.
La combinación de nameservers, IP y correo de registro como pivotes técnicos
produjo hallazgos que habrían sido inaccesibles desde el análisis del dominio
inicial de forma aislada. La preservación inmediata mediante URLScan.io en
el primer momento de la investigación garantizó la documentación del contenido
fraudulento antes de que pudiera ser dado de baja.

---

## 12. Conclusiones operativas

Los dominios, URLs, direcciones IP y los elementos técnicos de la
infraestructura digital son, en el ecosistema del cibercrimen, uno de los
conjuntos de observables con mayor potencial de pivot investigativo. Su análisis
riguroso puede revelar la estructura técnica de operaciones de fraude, las
relaciones entre campañas aparentemente independientes, los proveedores de
servicios utilizados y los patrones operativos que caracterizan a determinados
grupos o actores.

Ese potencial se realiza solo cuando el investigador trabaja con método: el
análisis inicial estructurado del observable, la preservación inmediata del
contenido relevante, la consulta sistemática de las herramientas adecuadas
para cada tipo de dato, la construcción metódica del grafo de relaciones
técnicas y la explotación disciplinada de los pivotes que cada hallazgo genera
son los pasos que convierten un dato técnico en conocimiento investigativamente
útil. La prudencia en la atribución, el conocimiento de los límites de la
inferencia técnica y la documentación rigurosa del proceso son las condiciones
que hacen que ese conocimiento sea también procesalmente sostenible.

---

## 13. Checklist final de trabajo

**Análisis inicial del observable**

- Registrar el observable en su formato exacto: URL completa, dominio,
  IP.
- Descomponer la URL en sus partes si es el dato de partida.
- Identificar el tipo de observable y los indicadores iniciales de interés.
- Documentar el contexto de aparición del dato.

**Preservación inicial**

- Generar análisis en URLScan.io si el observable es una URL accesible.
- Archivar en Archive.today el contenido visual de páginas fraudulentas.
- Documentar los archivos de preservación con hashes y sellos temporales.

**Análisis de reputación**

- Consultar el observable en VirusTotal.
- Consultar la IP en AbuseIPDB.
- Documentar los resultados completos de cada consulta.

**Análisis de dominio**

- Consultar datos de registro WHOIS: registrador, fecha, nameservers.
- Consultar registros DNS: A, MX, NS, TXT.
- Consultar historial de resolución en SecurityTrails o fuentes equivalentes.
- Buscar subdominios mediante crt.sh y herramientas de enumeración pasiva.
- Consultar MXToolbox para registros de correo y reputación de dominio.

**Análisis de IP**

- Consultar información de ASN, proveedor y geolocalización.
- Consultar reputación en AbuseIPDB y otras fuentes.
- Identificar otros dominios que resuelven a la misma IP.
- Consultar servicios expuestos en Shodan y Censys con finalidad de
  contextualización.

**Análisis de relaciones e infraestructura**

- Identificar dominios que comparten nameservers, IP o correo de registro.
- Consultar crt.sh para certificados y relaciones técnicas entre dominios.
- Construir el grafo de relaciones técnicas con los observables identificados.

**Investigación de pivotes y síntesis**

- Investigar datos de contacto de registro disponibles según procedimientos
  de capítulos anteriores.
- Investigar dominios relacionados con el mismo procedimiento de forma
  recursiva y priorizada.
- Evaluar la coherencia interna del conjunto de hallazgos.
- Identificar las diligencias adicionales con cobertura judicial necesarias.
- Elaborar el informe con descripción metodológica completa y archivos
  de preservación verificables.

---