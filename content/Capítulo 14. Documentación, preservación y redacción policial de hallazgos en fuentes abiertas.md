# Capítulo 14. Documentación, preservación y redacción policial de hallazgos en fuentes abiertas

## 1. Introducción

La investigación en fuentes abiertas genera hallazgos. Genera perfiles, correos, números de teléfono, publicaciones, dominios, imágenes, cronologías, conexiones entre entidades y rastros de actividad digital que pueden resultar decisivos para el avance de una investigación de cibercrimen. Pero un hallazgo obtenido sin documentación adecuada es un hallazgo que existe solo en la memoria del investigador que lo encontró, y la memoria no es un soporte operativo.

El problema no es solo de conservación. Es de utilidad. Un investigador puede haber localizado, en una plataforma de mensajería, el perfil real detrás de un alias utilizado para ejecutar una estafa piramidal. Puede haber vinculado una dirección de correo electrónico con cuatro identidades distintas, haberlas correlacionado con una wallet de criptomonedas y haber trazado la cronología de su actividad durante seis meses. Puede haber construido una imagen analítica extraordinariamente sólida. Si ese trabajo no está documentado con método, si las capturas no están contextualizadas, si no existe registro de cuándo y cómo se obtuvieron los datos, si la trazabilidad metodológica es deficiente o si la redacción es vaga o inconsistente, gran parte de ese trabajo habrá perdido su utilidad operativa e institucional.

Documentar en OSINT no consiste en guardar capturas de pantalla. Consiste en seguir una secuencia profesional de trabajo que abarca desde la identificación del hallazgo hasta su transformación en producto explotable: nota de trabajo, ficha de hallazgo, informe analítico, soporte de diligencia, anexo documental o insumo para la línea de investigación. Esa secuencia incluye preservar el contenido, registrar la fuente, anotar el contexto, describir el método de obtención, distinguir entre observación e inferencia, organizar el material y redactar con claridad y precisión.

Este capítulo enseña esa secuencia. No desde la abstracción, sino desde el trabajo cotidiano del investigador.

## 2. Finalidad investigadora del capítulo

Dentro de un manual de OSINT aplicado a la investigación de cibercrimen, este capítulo cumple una función integradora. Los capítulos anteriores han abordado fuentes, técnicas, herramientas y tipologías de investigación. Este capítulo se ocupa de la fase que cierra el ciclo operativo: cómo se conserva lo que se ha obtenido, cómo se registra de forma que tenga sentido y utilidad para terceros, y cómo se transforma en producto documental explotable.

La relevancia de esta fase es especialmente alta en el ámbito del cibercrimen. Los entornos digitales son dinámicos: los perfiles desaparecen, las publicaciones se eliminan, los dominios cambian de titularidad, las wallets se cierran, los canales de Telegram se borran. Lo que existe hoy puede no existir mañana. El investigador que trabaja en fuentes abiertas opera, con frecuencia, en un entorno de alta volatilidad informativa en el que la ventana de preservación puede cerrarse sin previo aviso. Esa volatilidad convierte la documentación oportuna y rigurosa en un requisito operativo de primer orden.

Al mismo tiempo, el trabajo OSINT se integra en estructuras institucionales que exigen documentación formal, verificable y transmisible: equipos de investigación que comparten información, cadenas de mando que autorizan y supervisan, procedimientos judiciales en los que el origen y el método de obtención de la información pueden ser objeto de escrutinio. En todos esos contextos, la calidad documental del trabajo no es un añadido burocrático, sino una condición de su utilidad.

El lector que complete este capítulo debe saber, con criterio propio, cómo preservar un hallazgo OSINT en condiciones de trabajo reales, qué debe registrar y cómo, qué secuencia seguir, cómo redactar el resultado y cómo preparar el material para su explotación posterior.

## 3. Objeto de análisis y punto de partida

A efectos de este capítulo, se entiende por **hallazgo documentable** cualquier dato, contenido, relación, patrón o estructura obtenida mediante técnicas de consulta en fuentes de acceso público que resulta relevante para una investigación activa o para la construcción de inteligencia criminal. No todo lo que el investigador consulta es un hallazgo documentable: lo son aquellos elementos que tienen valor informativo para la hipótesis de trabajo, que refuerzan o contradicen una línea de investigación, que establecen vínculos entre entidades o que pueden servir como soporte de actuaciones posteriores.

La **preservación** es el conjunto de acciones dirigidas a fijar el contenido de un hallazgo en un soporte estable, en las condiciones más completas posibles y con el contexto suficiente para que pueda ser comprendido y utilizado posteriormente. Preservar no es simplemente almacenar: es conservar el sentido y la trazabilidad del hallazgo.

La **trazabilidad** es la capacidad de reconstruir, en cualquier momento posterior, el origen, el método de obtención, las condiciones de acceso y la secuencia de trabajo que condujeron a un hallazgo. Un hallazgo con trazabilidad completa puede ser explicado, transmitido y, en su caso, sometido a contraste o verificación independiente. Un hallazgo sin trazabilidad solo puede ser afirmado.

El **registro metodológico** es la práctica de anotar, de forma estructurada, todos los elementos que permiten reconstruir el proceso de obtención: fuente consultada, fecha y hora de la consulta, herramienta o técnica empleada, estado del contenido en el momento de la obtención, observaciones relevantes y relación del hallazgo con la línea de investigación.

El **producto documental** es el resultado elaborado a partir del hallazgo bruto: puede ser una nota interna de trabajo, una ficha de hallazgo estructurada, un informe analítico preliminar, un soporte de explotación policial o un anexo formal. Su característica esencial es que es comprensible, preciso y utilizable por alguien que no estuvo presente en el momento de la obtención.

Las preguntas prácticas que debe resolver el investigador al documentar son siempre las mismas:

- ¿Qué encontré exactamente?
- ¿Dónde estaba?
- ¿Cuándo lo encontré y cómo accedí a ello?
- ¿Cómo sé que es lo que creo que es?
- ¿Qué significa en el contexto de esta investigación?
- ¿Cómo lo preservo para que sea útil mañana?
- ¿Cómo lo redacto para que otro investigador pueda entenderlo y utilizarlo?

## 4. La documentación y la preservación como parte del método investigador

Existe una tendencia, comprensible pero perjudicial, a considerar la documentación como una fase posterior al trabajo de investigación: primero se investiga, luego se documenta. Esta secuencia es metodológicamente incorrecta en el contexto del OSINT aplicado al cibercrimen.

La razón es doble. En primer lugar, la documentación oportuna forma parte de la propia obtención del hallazgo. Un investigador que localiza un perfil vinculado a una operación de fraude y espera a documentarlo horas después puede encontrarse con que el perfil ha sido eliminado, que no recuerda con exactitud la URL, que la captura tiene un encuadre incompleto o que ya no puede reproducir la secuencia de pasos que lo llevó hasta ese contenido. El hallazgo existió, pero su utilidad ha quedado comprometida. En segundo lugar, el proceso de documentar exige un nivel de atención y precisión que, cuando se aplica desde el inicio, mejora la calidad del propio trabajo investigador: obliga al investigador a ser explícito sobre lo que sabe, lo que infiere y lo que desconoce, y a registrar el razonamiento que vincula los datos con las hipótesis.

Documentar bien es, también, una forma de pensar con rigor. El investigador que registra metódicamente sus hallazgos desarrolla una disciplina analítica que lo protege de errores frecuentes: la confusión entre observación e inferencia, la acumulación desordenada de material sin criterio de relevancia, la sobreinterpretación de indicios débiles o la pérdida de contexto que hace inservible un hallazgo aislado.

La documentación y la preservación tienen además una dimensión institucional que no puede ignorarse. Los hallazgos OSINT se integran en flujos de trabajo que involucran a otros investigadores, analistas, supervisores y, eventualmente, a órganos judiciales. En todos esos contextos, la utilidad del hallazgo depende de que pueda ser transmitido con precisión, verificado por terceros y evaluado en su contexto original. Un material bien documentado aumenta la credibilidad del trabajo y reduce significativamente los riesgos de pérdida de contexto, malinterpretación o cuestionamiento posterior.

Conviene ser explícito sobre lo que la documentación no garantiza: la mera existencia de una documentación rigurosa no confiere validez probatoria automática a los hallazgos OSINT, ni los convierte en medios de prueba por sí solos. La incorporación de los resultados de inteligencia en fuentes abiertas al procedimiento penal está sujeta a los mecanismos legales ordinarios y a las decisiones de los órganos competentes. Lo que la documentación profesional sí garantiza es que el trabajo del investigador sea comprensible, trazable y utilizable, que son condiciones necesarias para cualquier uso institucional posterior.

## 5. Análisis inicial del hallazgo y contextualización documental

Cuando el investigador obtiene un hallazgo que considera relevante, el primer impulso operativo debe ser la preservación inmediata del contexto. Antes de navegar a otras páginas, antes de abrir nuevas pestañas, antes de continuar la exploración, debe fijarse el estado actual del contenido en sus condiciones de acceso originales.

El análisis inicial de un hallazgo desde la perspectiva documental exige responder a una serie de preguntas mínimas que definen los elementos que deben registrarse. La fuente exacta debe identificarse con precisión: no basta con anotar «Twitter» o «Telegram», sino que debe registrarse la URL completa, el identificador del perfil o del canal, y cualquier otro elemento que permita localizar o referenciar el contenido con exactitud. La fecha y la hora de la consulta deben quedar registradas con la mayor precisión posible, preferiblemente en UTC, para evitar ambigüedades derivadas de diferencias horarias. El estado del contenido en el momento de la obtención debe describirse: si está accesible públicamente, si requiere estar registrado, si presenta alguna restricción de acceso, si ha sido modificado o si existen indicios de alteración reciente.

El método de acceso y las herramientas empleadas deben anotarse con la suficiente especificidad para que el proceso pueda ser explicado y, en su caso, reproducido. No es lo mismo una búsqueda directa en un motor de consulta que el uso de un operador avanzado, que el acceso a través de una herramienta de agregación, que la consulta a una caché o a un archivo histórico. Cada uno de estos métodos tiene implicaciones distintas sobre la fiabilidad y la representatividad del resultado.

El investigador debe también tomar una primera decisión de relevancia: ¿este hallazgo es directamente útil para la hipótesis de trabajo activa?, ¿es un indicador que debe ser contrastado?, ¿requiere de verificación adicional antes de ser incorporado al material de trabajo?, ¿necesita de análisis relacional para adquirir significado completo? Esta decisión inicial debe quedar reflejada en la nota de trabajo, porque condiciona el tratamiento posterior del hallazgo.

Lo que no debe registrarse en esta fase, o debe registrarse de manera claramente separada, es la interpretación analítica. El análisis inicial es descriptivo: qué existe, dónde está, cuándo se encontró y cómo se obtuvo. La interpretación y las conclusiones son una fase posterior y deben tratarse como tal.

## 6. Flujo de trabajo del investigador desde el hallazgo hasta el producto documental final

El flujo de trabajo que se describe a continuación no es un procedimiento rígido, sino una secuencia profesional de referencia que cada investigador debe adaptar a la naturaleza del caso, la tipología del hallazgo y los recursos disponibles. Lo que no es opcional es su lógica: cada fase tiene una función específica y su omisión o inversión genera problemas documentales que son difíciles de corregir retroactivamente.

### 6.1. Primera fase: identificación y valoración del hallazgo

El investigador detecta un elemento con potencial relevancia investigadora. Antes de actuar documentalmente, debe valorar si ese elemento merece ser preservado y en qué nivel de detalle. No todo lo que se consulta debe documentarse con el mismo nivel de rigor: existe material de exploración que no pasa el umbral de relevancia, y existe material que, desde el primer momento, debe ser tratado con máximo cuidado documental. Esta valoración inicial es una competencia analítica que se desarrolla con la experiencia, pero puede apoyarse en criterios básicos: vinculación con la hipótesis de trabajo, potencial para identificar entidades, contribución a la cronología o capacidad para establecer vínculos entre elementos ya conocidos.

### 6.2. Segunda fase: preservación inmediata del contenido

Una vez valorado el hallazgo como documentable, el investigador debe preservar el contenido antes de realizar cualquier otra acción. La preservación debe ser lo más completa posible: no solo el fragmento visible o el dato concreto, sino el contexto inmediato en el que aparece. Una publicación debe preservarse con el perfil que la generó visible, con la fecha y la hora legibles, con los elementos de interacción presentes si son relevantes, y con la URL completa. Un perfil debe preservarse en su estado completo en el momento de la consulta, no solo en los campos que interesan en ese momento. Un dominio debe preservarse con sus registros técnicos completos, no solo con el nombre. La preservación parcial es una forma frecuente de pobreza documental que puede comprometer la utilidad del hallazgo.

### 6.3. Tercera fase: registro estructurado de metadatos de obtención

Inmediatamente después de preservar el contenido, el investigador debe registrar los metadatos de obtención: fecha y hora exactas de la consulta, en UTC o con indicación explícita de la zona horaria; URL o identificador exacto de la fuente; plataforma o servicio consultado; método de acceso y herramientas empleadas; estado del contenido en el momento de la obtención; y cualquier observación técnica relevante, como la existencia de contenido eliminado pero accesible en caché, la presencia de metadatos EXIF en imágenes, o la detección de inconsistencias entre la información pública y la disponible en registros históricos.

### 6.4. Cuarta fase: descripción objetiva del hallazgo

El investigador redacta una descripción precisa y objetiva de lo que ha obtenido. Esta descripción debe limitarse a lo que es directamente observable: lo que muestra el contenido preservado, sin añadir inferencias ni interpretaciones. La distinción entre «el perfil indica como correo de contacto la dirección X» y «el perfil pertenece al sujeto investigado» es fundamental en esta fase. La primera afirmación es una observación; la segunda es una inferencia que requiere de análisis adicional y debe tratarse en la fase siguiente.

### 6.5. Quinta fase: análisis e interpretación

Una vez establecida la descripción objetiva, el investigador puede desarrollar el análisis: qué significa el hallazgo en el contexto de la investigación, qué vínculos establece con otros elementos ya documentados, qué hipótesis refuerza o contradice, qué líneas de trabajo sugiere. Este análisis debe estar claramente separado, textual y estructuralmente, de la descripción objetiva. En el producto documental, la distinción entre «dato observado» e «inferencia analítica» no es un formalismo académico: es una garantía de rigor que protege al investigador frente a errores de sobreinterpretación y que permite a terceros evaluar el razonamiento de forma independiente.

### 6.6. Sexta fase: verificación y contraste

Los hallazgos relevantes deben someterse a alguna forma de verificación o contraste antes de ser incorporados como certezas al material de trabajo. Verificar puede significar cosas distintas según la naturaleza del hallazgo: confirmar que una dirección de correo aparece también en otras fuentes independientes, comprobar que la información de un registro whois es consistente con los datos de un certificado SSL, contrastar una fecha de registro con una cronología ya conocida o buscar referencias cruzadas que confirmen o cuestionen la identidad de un alias. Los hallazgos que no han podido contrastarse deben incorporarse al material con la indicación explícita de que están pendientes de verificación.

### 6.7. Séptima fase: organización del material

Los elementos preservados, los metadatos de obtención y las notas de análisis deben organizarse de forma coherente dentro de la estructura de la investigación. Esto significa asignar al hallazgo un identificador único que permita referenciarlo en cualquier fase posterior, vincularlo con la línea de investigación o la hipótesis a la que contribuye, y almacenarlo en un sistema de organización documental que facilite su recuperación y su integración con otros hallazgos relacionados. La acumulación desordenada de material es tan perjudicial como la documentación insuficiente.

### 6.8. Octava fase: redacción del producto documental

El investigador redacta el producto documental adecuado al tipo de hallazgo y al uso previsto: nota de trabajo interna, ficha de hallazgo estructurada, informe preliminar o soporte de explotación policial. La redacción debe ser sobria, precisa y estructurada, con separación explícita entre descripción y análisis, y con indicación clara del nivel de confianza del hallazgo.

### 6.9. Novena fase: preparación para la explotación policial

Si el hallazgo va a ser utilizado en actuaciones policiales o en documentación formal, el investigador debe revisar que el material cumple los requisitos de trazabilidad y precisión necesarios para esos contextos. Esto puede incluir la verificación de la integridad de los archivos preservados, la comprobación de que los metadatos de obtención están completos y la revisión de que la redacción es suficientemente clara y precisa para un lector que no tiene acceso al contexto completo de la investigación.

## 7. Herramientas, recursos y plantillas prácticas para la preservación y documentación

### 7.1. Herramientas de captura y preservación básica

La captura de pantalla es el recurso más inmediato, pero también el que presenta más limitaciones documentales cuando se utiliza de forma aislada. Una captura sin contexto visible, sin URL legible, sin marca temporal o sin información sobre el entorno en el que fue tomada tiene un valor documental reducido. Para compensar estas limitaciones, el investigador debe adoptar prácticas sistemáticas: incluir siempre la barra de navegación completa con la URL en la captura, asegurarse de que la fecha y la hora del sistema sean visibles, capturar el contenido completo y no solo el fragmento de interés, y complementar la captura con el registro manual de los metadatos de obtención.

Herramientas como HTTrack o wget permiten la descarga completa de páginas o estructuras web cuando el contenido es lo suficientemente extenso o estructurado como para que una captura estática resulte insuficiente. Estas herramientas preservan no solo el contenido visible, sino también los enlaces, los recursos asociados y parte de la estructura técnica de la página. Su uso es especialmente útil cuando se investiga infraestructura web vinculada a operaciones de phishing, tiendas fraudulentas o paneles de control expuestos.

Para contenido en formato de vídeo o audio, herramientas como yt-dlp permiten la descarga de material publicado en plataformas accesibles públicamente, preservando los archivos originales con sus metadatos técnicos. Esta preservación es especialmente valiosa cuando el contenido puede ser eliminado por el operador de la plataforma o por el propio sujeto investigado.

La captura de páginas completas en formato PDF desde el navegador, utilizando la función de impresión o herramientas como la extensión SingleFile, permite preservar páginas dinámicas en un formato estable que incluye el contenido visible con el timestamp del sistema. Esta práctica es útil para preservar perfiles de redes sociales, publicaciones, anuncios o listados de foros.

### 7.2. Herramientas de archivado y conservación de contexto

El servicio Wayback Machine de Internet Archive y herramientas asociadas como archive.today permiten archivar páginas accesibles públicamente y conservar una copia fechada con sello temporal externo al investigador. Esta capa de preservación añade una referencia independiente que puede ser relevante cuando se necesita demostrar el estado de un contenido en un momento determinado. El investigador debe tener presente que estos servicios no están bajo su control, que pueden presentar limitaciones técnicas y que algunos contenidos dinámicos no se archivan correctamente, por lo que deben usarse como complemento y no como sustituto de la preservación directa.

Para la preservación de páginas con contenido dinámico o protegido frente al archivado automático, la combinación de una captura de pantalla completa, la descarga del código fuente de la página y el registro de los metadatos HTTP de la solicitud puede proporcionar una documentación más sólida que cualquier herramienta de archivado externa.

### 7.3. Integridad y verificación del material preservado

La generación de valores hash de los archivos preservados es una práctica que contribuye a la verificación de la integridad del material en fases posteriores. Herramientas estándar como `sha256sum` o `md5sum` permiten calcular el hash de un archivo en el momento de su obtención y registrar ese valor junto con el archivo. Si el archivo es posteriormente cuestionado o se sospecha de su alteración, la comparación del hash original con el hash actual permite detectar cualquier modificación. Esta práctica es especialmente relevante cuando el material pueda ser incorporado a actuaciones formales o cuando exista un riesgo de cuestionamiento posterior.

El investigador debe entender que el cálculo del hash no acredita por sí solo la autenticidad o el origen del material, sino únicamente que no ha sido modificado desde el momento de su cálculo. El hash registrado en el momento de la obtención, junto con el registro metodológico completo de cómo se obtuvo el material, proporciona una trazabilidad que refuerza la credibilidad del trabajo.

### 7.4. Herramientas de organización documental

La organización del material de trabajo requiere de un sistema que permita identificar, recuperar y relacionar los hallazgos de manera eficiente. Sistemas de gestión de casos como Maltego, en su función de almacenamiento de hallazgos y vínculos, o aplicaciones de gestión documental policial disponibles en entornos institucionales, permiten organizar el material con criterios de búsqueda y filtrado. Para investigadores que trabajan en entornos con restricciones de conectividad, aplicaciones de notas estructuradas como Obsidian o bases de datos locales sencillas pueden cumplir una función de organización útil sin requerir conexión externa.

El criterio de organización debe ser funcional: el sistema elegido debe facilitar la recuperación del material por caso, por entidad, por tipología de hallazgo o por línea de investigación. La organización cronológica tiene utilidad para el análisis de secuencias, pero resulta insuficiente como criterio único porque no refleja las relaciones entre hallazgos.

### 7.5. Herramientas para la elaboración de cronologías y análisis relacionales

La documentación de cronologías de actividad y de análisis de vínculos entre entidades requiere de herramientas que permitan visualizar y registrar relaciones complejas de forma estructurada. Maltego es la herramienta de referencia para el análisis relacional en entornos de inteligencia, con capacidad para registrar y visualizar conexiones entre entidades de distintos tipos. TimelineJS y herramientas similares permiten construir cronologías visuales que pueden servir tanto como soporte analítico interno como como anexo documental para informes. i2 Analyst's Notebook, disponible en muchos entornos policiales, cumple funciones similares con una orientación específicamente institucional.

Para el análisis y documentación de infraestructura técnica, herramientas como Shodan, Censys o VirusTotal generan informes exportables que pueden incorporarse directamente al expediente como anexos técnicos, siempre que se registren adecuadamente la fecha de consulta y las condiciones de acceso.

### 7.6. Plantillas y formatos de trabajo

El uso de plantillas homogéneas para el registro de hallazgos es una práctica que mejora de forma significativa la calidad documental del trabajo colectivo y facilita la integración de hallazgos en productos de inteligencia más amplios. Una plantilla de ficha de hallazgo debe incluir, como mínimo, los siguientes campos: identificador único del hallazgo, fecha y hora de obtención en UTC, tipología del hallazgo, fuente exacta con URL o identificador, método de obtención y herramientas empleadas, descripción objetiva del contenido, estado del contenido en el momento de la obtención, nivel de verificación, análisis e interpretación separados de la descripción, vínculos con otros hallazgos o entidades, línea de investigación o hipótesis relacionada, y decisiones de explotación o seguimiento. Este formato puede adaptarse a la tipología específica del hallazgo, pero los campos mínimos deben mantenerse como estructura fija.

## 8. Redacción profesional de hallazgos, notas, informes y soportes de explotación policial

La redacción es la fase en la que el hallazgo adquiere su forma definitiva como producto documental. Una redacción deficiente puede arruinar un trabajo analítico sólido: puede hacer ininteligible un hallazgo claro, puede mezclar observación e inferencia de forma que el lector no pueda distinguirlas, puede exagerar el valor de un indicio débil o puede infrautilizar un hallazgo relevante.

La nota de trabajo interna es el producto documental más cotidiano. Su función es registrar el hallazgo de forma rápida y estructurada para uso del propio investigador o del equipo inmediato. Debe ser concisa, precisa y completa en los campos mínimos de trazabilidad. No es un documento formal, pero su calidad determina la posibilidad de transformarla posteriormente en productos de mayor alcance. Una nota de trabajo bien elaborada incluye el hallazgo descrito objetivamente, los metadatos de obtención, una brevísima nota de análisis y la indicación de la hipótesis o línea de investigación a la que contribuye.

La ficha de hallazgo estructurada es un producto más elaborado, destinado a integrarse en el expediente de trabajo del caso. Su estructura debe ser homogénea dentro del equipo y debe incluir todos los campos del registro metodológico completo. La descripción del hallazgo debe ser precisa y sin ambigüedades; el análisis debe estar claramente separado de la descripción y debe indicar el nivel de confianza de las inferencias realizadas.

El informe OSINT preliminar es un producto analítico que integra múltiples hallazgos dentro de una narrativa coherente orientada a una hipótesis de trabajo o a la descripción de una entidad, una infraestructura o una red de actividad. Su redacción debe seguir una estructura lógica: introducción con el objeto del informe, metodología general, hallazgos principales organizados por línea analítica, análisis e interpretación, y conclusiones con indicación explícita de los elementos pendientes de verificación o de las limitaciones del análisis. El informe preliminar no es un producto jurídico: es un soporte analítico interno que puede servir de base para actuaciones posteriores.

Los soportes de explotación policial son productos orientados a facilitar actuaciones concretas: solicitudes de información a proveedores, peticiones de cooperación internacional, propuestas de diligencias o soportes para solicitudes de medidas de investigación tecnológica. En estos productos, la redacción debe ser especialmente precisa y sin ambigüedades, porque van a ser leídos por personas que no tienen acceso al contexto completo de la investigación y porque pueden ser sometidos a escrutinio formal. Deben incluir la descripción objetiva y verificada de los hallazgos relevantes, con indicación explícita de las fuentes y de los métodos de obtención, y deben diferenciar claramente entre hechos constatados e inferencias analíticas.

La redacción profesional en todos estos formatos responde a los mismos principios básicos. La precisión exige que cada afirmación sea exacta y verificable: no se afirma lo que se sospecha sin marcarlo como tal; no se describe como probado lo que está pendiente de verificación. La sobriedad exige que el texto no sea retórico ni redundante: los hallazgos no «demuestran de forma inequívoca» ni «prueban más allá de toda duda», sino que «indican», «sugieren», «son consistentes con» o «contradicen», según el grado de certeza del análisis. La estructura exige que la separación entre descripción, análisis y conclusiones sea visible y coherente. La verificabilidad exige que cualquier afirmación pueda ser rastreada hasta la fuente original con los metadatos de obtención completos.

## 9. Interpretación de hallazgos, cautelas y errores frecuentes en la documentación

La interpretación de los hallazgos OSINT es la fase analítica de mayor riesgo documental. Es en la interpretación donde con más frecuencia se producen los errores que comprometen la utilidad o la credibilidad del trabajo.

El error más frecuente es la confusión entre observación e inferencia. El investigador que documenta que «la dirección IP X aparece registrada a nombre de la empresa Y» está describiendo un hecho observable. El que añade que «por tanto, la empresa Y es la operadora de la infraestructura fraudulenta» está realizando una inferencia que puede ser razonable pero que requiere de análisis adicional y verificación. Mezclar ambas afirmaciones sin distinción en el mismo párrafo genera un producto documental que no puede evaluarse correctamente.

La sobreinterpretación de coincidencias es otro error frecuente. La existencia de una coincidencia entre dos datos, por llamativa que sea, no establece por sí sola una relación causal o una identidad. La coincidencia debe ser valorada en su contexto, contrastada con otras fuentes y presentada con el nivel de certeza que le corresponde.

La pobreza documental aparece cuando el investigador registra el dato sin el contexto necesario para darle sentido. Una dirección de correo electrónico sin la indicación de dónde fue encontrada, cuándo y en qué condiciones tiene un valor documental mínimo. Una imagen sin metadatos de obtención ni descripción del contexto en el que apareció puede ser imposible de utilizar posteriormente. La práctica de documentar lo mínimo por falta de tiempo o por subestimar la importancia del registro es una de las fuentes más comunes de pérdida de valor investigadora.

El error opuesto, la acumulación desordenada, genera un problema diferente: un expediente repleto de material sin criterio de relevancia, sin organización lógica y sin síntesis analítica es tan inútil como uno vacío. El investigador debe aplicar criterios de selección y síntesis: no todo lo que se consulta merece ser preservado, y no todo lo que se preserva merece ser analizado con el mismo nivel de profundidad.

El desajuste entre el valor real del hallazgo y su presentación documental es un error con implicaciones institucionales importantes. Presentar como certeza lo que es una hipótesis razonable puede generar actuaciones basadas en premisas incorrectas. Infrautilizar un hallazgo relevante porque su redacción es insuficiente puede llevar a que no sea incorporado al análisis colectivo. El investigador debe esforzarse por ajustar la presentación documental al valor real del hallazgo.

## 10. Aspectos jurídicos, deontológicos y probatorios específicos

La documentación y la preservación de hallazgos en fuentes abiertas tienen implicaciones jurídicas y deontológicas que el investigador debe conocer y respetar, aunque este capítulo no duplique el tratamiento jurídico específico que corresponde a otros apartados del manual.

El primer aspecto relevante es la legalidad del método de obtención. El hecho de que una información esté accesible públicamente no garantiza automáticamente que cualquier método de acceso sea lícito ni que cualquier uso de la información obtenida sea admisible. El investigador debe asegurarse de que el método de obtención empleado es compatible con el marco jurídico aplicable y con las instrucciones y procedimientos de su unidad. Documentar el método de obtención con precisión es también una forma de demostrar, en caso de cuestionamiento, que el acceso se realizó en condiciones adecuadas.

La prudencia en la atribución es un principio deontológico fundamental. Atribuir públicamente o en documentación formal una actividad delictiva a una persona, empresa o entidad basándose en hallazgos OSINT que no han sido verificados o que presentan incertidumbre analítica puede causar daños graves e injustificados. El investigador debe asegurarse de que sus conclusiones están respaldadas por el material documentado y de que el nivel de certeza expresado en la redacción es coherente con la solidez del análisis.

La conservación del contexto original tiene implicaciones probatorias importantes cuando los hallazgos van a ser incorporados a procedimientos formales. Un hallazgo descontextualizado puede ser interpretado de forma diferente a la que el investigador pretendía, con consecuencias que pueden comprometer tanto la investigación como la posición procesal. La documentación completa del contexto original es la mejor garantía frente a este riesgo.

El respeto a la privacidad y a la protección de datos es aplicable incluso en el trabajo con fuentes de acceso público. La recopilación, el tratamiento y la conservación de datos personales deben ajustarse al marco jurídico vigente y a los procedimientos internos de la unidad, con independencia de que los datos hayan sido obtenidos de fuentes abiertas.

## 11. Caso práctico aplicado

### Caso práctico: Fraude de inversión mediante perfil falso en redes sociales y canal de Telegram

**Supuesto de hecho.**

Una unidad de cibercrimen recibe varias denuncias coincidentes de personas que afirman haber sido estafadas a través de un esquema de inversión fraudulenta. Los denunciantes refieren haber sido contactados inicialmente a través de una red social profesional por un perfil que se presentaba como asesor de inversiones de una firma internacional de gestión de patrimonio. El contacto fue derivando, a través de mensajes directos, hacia un canal de Telegram en el que supuestamente se compartían señales de trading de alta rentabilidad. Los perjudicados realizaron transferencias a cuentas indicadas por los operadores del canal tras recibir supuestos comprobantes de ganancias generadas por otros miembros.

**Dato o indicio de partida.**

Uno de los denunciantes aporta el nombre de usuario de Telegram del perfil que le contactó inicialmente, la URL del canal de Telegram al que fue invitado y el nombre comercial de la firma cuya identidad fue suplantada.

**Hipótesis de trabajo.**

Los operadores del canal utilizan identidades falsas o suplantadas para captar víctimas a través de redes sociales profesionales, redirigirlas hacia un entorno de comunicación privado y ejecutar un esquema de fraude de inversión. La firma referenciada es probablemente una identidad legítima utilizada sin autorización para dar apariencia de solvencia.

**Actuaciones realizadas.**

El investigador comienza consultando el nombre comercial de la firma en fuentes abiertas: registros mercantiles accesibles, sitio web oficial, registros de la autoridad reguladora financiera competente y bases de datos de sanciones. Consulta el perfil de la red social profesional referenciado por el denunciante y preserva su estado completo con captura de página entera, URL visible y timestamp del sistema. Consulta el canal de Telegram mediante acceso con cuenta de análisis dedicada, preserva la información pública del canal, su identificador, su descripción, el número de miembros y una muestra representativa de los mensajes accesibles, con captura completa y registro de metadatos. Realiza búsquedas en fuentes abiertas con los identificadores de los perfiles de contacto para detectar reutilización de alias o de imágenes de perfil en otros servicios. Consulta registros WHOIS de los dominios referenciados en la comunicación fraudulenta.

**Hallazgos obtenidos.**

El perfil de la red social profesional presenta indicadores consistentes con un perfil fabricado: imagen de perfil que aparece en búsquedas inversas vinculada a múltiples identidades distintas, historial laboral que no puede verificarse en ninguna fuente adicional y ausencia de conexiones previas a la investigada. El canal de Telegram lleva activo, según la información accesible, un período inferior a tres meses, tiene varios miles de miembros y publica con alta frecuencia capturas que muestran supuestas ganancias de trading. Los dominios referenciados en la comunicación fueron registrados entre dos y cuatro semanas antes del inicio de los contactos con las víctimas, utilizando un servicio de privacidad de datos de registro que oculta la identidad del titular.

**Análisis e interpretación.**

Los hallazgos son consistentes con la hipótesis de trabajo. El perfil de la red social presenta características propias de una identidad fabricada para uso en operaciones de ingeniería social. El canal de Telegram tiene características estructurales propias de los esquemas de captación de víctimas mediante supuestas señales de inversión. La antigüedad de los dominios y el uso de servicios de privacidad de registro son indicadores técnicos que deben ser tenidos en cuenta en el análisis de la infraestructura. Ninguno de estos elementos, por sí solo, es concluyente, pero su concurrencia refuerza de forma significativa la hipótesis de actividad fraudulenta organizada. El análisis se registra con esta formulación explícita: los hallazgos son indicativos y consistentes con la hipótesis, no son por sí solos constitutivos de prueba.

**Explotación policial y documental.**

El investigador elabora una ficha de hallazgo estructurada para cada elemento documentado: perfil de red social, canal de Telegram y dominios. Cada ficha incluye todos los campos del registro metodológico, la descripción objetiva del hallazgo y la nota analítica con separación explícita. A partir del conjunto de fichas, redacta un informe OSINT preliminar que integra los hallazgos en una narrativa analítica coherente, con estructura diferenciada entre hechos verificados, indicadores pendientes de contraste y conclusiones provisionales. El informe incluye como anexos las capturas preservadas con sus metadatos y los hash de los archivos principales. El producto se integra en el expediente del caso como soporte analítico para las actuaciones investigadoras posteriores, incluidas eventuales solicitudes a proveedores de servicios de comunicaciones o de intermediación financiera.

**Lecciones operativas.**

La preservación inmediata del perfil y del canal resultó crítica porque ambos fueron eliminados días después del inicio de la investigación. La documentación completa del método de obtención y de las condiciones de acceso permitió responder a posteriori a preguntas sobre la fiabilidad de los datos. La separación explícita entre observación e inferencia en el informe preliminar facilitó la revisión interna del análisis y evitó que conclusiones provisionales fueran tratadas como certezas en fases posteriores. El uso de plantillas homogéneas para las fichas de hallazgo permitió integrar los resultados de varios investigadores del equipo sin pérdida de consistencia documental.

## 12. Conclusiones operativas

La documentación, la preservación y la redacción profesional de hallazgos en fuentes abiertas no son actividades secundarias que se realizan una vez concluido el trabajo investigador. Son parte integrante del trabajo mismo. Un hallazgo que no puede ser explicado con trazabilidad, que no ha sido preservado con contexto suficiente o que ha sido redactado de forma imprecisa o ambigua tiene una utilidad operativa reducida, con independencia de su valor potencial.

El trabajo OSINT en investigación de cibercrimen se desarrolla en entornos de alta volatilidad informativa, con frecuentes pérdidas de contenido y con necesidades de integración institucional en estructuras que exigen documentación formal, trazable y transmisible. En ese contexto, la calidad documental del trabajo no es un valor añadido, sino un requisito de su utilidad.

El investigador que desarrolla una disciplina sólida de documentación y preservación obtiene ventajas concretas: puede transmitir su trabajo a otros de forma eficiente, puede responder a preguntas sobre el origen y el método de los hallazgos, puede integrar sus resultados en flujos de trabajo institucionales más amplios, y puede construir sobre su trabajo anterior sin pérdida de contexto. Al mismo tiempo, una práctica documental rigurosa refuerza la calidad analítica del propio trabajo: obliga a distinguir con precisión entre lo que se sabe y lo que se infiere, a evaluar la fortaleza real de los hallazgos y a presentarlos con el nivel de certeza que les corresponde.

El paso del dato bruto al producto explotable no es automático. Requiere criterio de selección, capacidad de síntesis, rigor analítico y precisión de redacción. Esas son competencias que se desarrollan con la práctica, pero que responden a una secuencia profesional de trabajo que puede aprenderse, aplicarse y mejorarse sistemáticamente.

## 13. Checklist final de trabajo

### Preservación del hallazgo

- [ ] El contenido ha sido preservado en su estado completo, no solo el fragmento de interés.
- [ ] La URL o el identificador exacto de la fuente ha sido registrado.
- [ ] La fecha y la hora de obtención han sido registradas en UTC.
- [ ] La captura o el archivo preservado incluye el contexto visible relevante.
- [ ] Se ha generado un hash del archivo preservado cuando el hallazgo tiene importancia especial.

### Registro metodológico

- [ ] Se ha anotado la plataforma o servicio consultado.
- [ ] Se ha descrito el método de acceso y las herramientas empleadas.
- [ ] Se ha indicado el estado del contenido en el momento de la obtención.
- [ ] Se han anotado las observaciones técnicas relevantes.

### Análisis y descripción

- [ ] La descripción objetiva del hallazgo está claramente separada del análisis e interpretación.
- [ ] Las inferencias analíticas están formuladas con el nivel de certeza que corresponde a su solidez.
- [ ] Los hallazgos pendientes de verificación están indicados explícitamente.
- [ ] No se afirma como probado lo que está en fase de hipótesis.

### Organización y trazabilidad

- [ ] El hallazgo tiene asignado un identificador único dentro del expediente.
- [ ] El material está vinculado con la hipótesis o línea de investigación correspondiente.
- [ ] El material está integrado en el sistema de organización documental del caso.

### Redacción del producto documental

- [ ] El producto documental elegido es el adecuado al tipo de hallazgo y al uso previsto.
- [ ] La redacción es sobria, precisa y sin ambigüedades.
- [ ] El producto puede ser comprendido y utilizado por alguien ajeno a la obtención del hallazgo.
- [ ] La distinción entre descripción, análisis y conclusiones es visible en la estructura del documento.

### Explotación y preparación para uso posterior

- [ ] El producto está preparado para ser integrado en actuaciones investigadoras o documentación formal si procede.
- [ ] Los anexos documentales están completos y son coherentes con el texto del informe.
- [ ] El material puede ser transmitido a terceros sin pérdida de contexto ni de trazabilidad.