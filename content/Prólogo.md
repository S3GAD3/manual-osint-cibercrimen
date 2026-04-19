# Manual de Fuentes Abiertas para la Investigación de Cibercrimen
## OSINT aplicado a la Policía Judicial

---

# Prólogo

La investigación criminal ha experimentado, en las últimas dos décadas, una
transformación profunda que no siempre ha encontrado respuesta institucional
a la misma velocidad. La digitalización de las comunicaciones, las
transacciones y las relaciones sociales ha modificado de manera sustancial
no solo la forma en que se cometen los delitos, sino también la naturaleza
de los rastros que estos dejan. El delincuente que opera en el entorno
digital —ya sea con fines económicos, coactivos, de fraude, de abuso o de
cualquier otra índole— actúa casi siempre dejando huellas: fragmentos de
identidad dispersos en plataformas, registros técnicos, metadatos,
interacciones, transacciones y presencias que, en muchos casos, permanecen
accesibles en abierto para quien sabe dónde buscar y, sobre todo, para
quien sabe cómo interpretar lo que encuentra.

Es en ese espacio —el de la información accesible públicamente y su
tratamiento riguroso con fines de investigación— donde se sitúa el OSINT,
la inteligencia derivada de fuentes abiertas. No es un concepto nuevo. Su
origen se remonta a ámbitos militares e institucionales donde la explotación
sistemática de información pública fue reconocida, ya hace décadas, como una
capacidad estratégica de primer orden. Lo que ha cambiado es el contexto:
la magnitud de la información disponible, la velocidad de su generación, la
diversidad de sus fuentes y la complejidad técnica que exige su correcta
interpretación. En el ámbito policial y judicial, el OSINT ha dejado de ser
una práctica auxiliar o informal para convertirse en una disciplina con
entidad propia, capaz de orientar y enriquecer investigaciones de enorme
complejidad.

Este manual nace de esa convicción y de una necesidad concreta: proporcionar
a los investigadores, analistas criminales, policías judiciales y
profesionales de la seguridad un instrumento que no se limite a recopilar
herramientas o describir técnicas, sino que articule una metodología de
trabajo coherente, rigurosa y adaptada a las exigencias del procedimiento
penal. Porque el problema al que se enfrenta hoy el investigador
especializado en cibercrimen no es, en la mayoría de los casos, la falta de
información. Es la necesidad de obtenerla de forma técnicamente válida,
interpretarla con criterio analítico, relacionarla con el conjunto de la
investigación y documentarla de manera que sea útil en el proceso y
sostenible ante la crítica judicial.

---

El cibercrimen ha reconfigurado el mapa del delito de un modo que no admite
ya matices: no es una categoría residual ni un fenómeno marginal. El fraude
informático, los delitos de odio en red, la distribución de material de
abuso sexual infantil, el ransomware, el phishing, el acceso ilícito a
sistemas, el blanqueo de capitales a través de criptoactivos, la
suplantación de identidad o la extorsión digital representan hoy una parte
sustancial de la delincuencia con la que trabajan los cuerpos de policía
judicial. Y en todos esos ámbitos, las fuentes abiertas ofrecen
oportunidades de investigación que, bien explotadas, pueden marcar la
diferencia entre una investigación que avanza y una que se detiene ante la
primera dificultad técnica.

Un correo electrónico puede parecer, en apariencia, un dato menor. Pero un
correo electrónico puede vincular a un sospechoso con plataformas, registros
de dominios, perfiles en redes sociales, cuentas de servicios de
almacenamiento en la nube o transacciones en criptomonedas. Un alias
utilizado en un foro puede coincidir con el empleado en otra plataforma años
atrás, revelando una historia digital que el propio delincuente quizás creyó
haber borrado. Un número de teléfono puede conectar identidades fragmentadas.
Una imagen, procesada adecuadamente, puede contener metadatos que ubican a
una persona en un lugar y en un momento determinados. Un dominio puede
conducir a una infraestructura completa de servidores, pagos y registros. En
cibercrimen, el dato aparentemente menor es, con frecuencia, el punto de
entrada de una investigación mucho más amplia.

Pero ese potencial solo se realiza cuando el investigador actúa con método.
La acumulación de datos sin análisis no produce inteligencia. El hallazgo no
documentado correctamente pierde valor probatorio. La hipótesis no
contrastada puede desviar una investigación. El exceso de información —cuando
no se trabaja con criterio de selección y priorización— puede resultar tan
paralizante como la ausencia de ella. Y la obtención de información por vías
que no respeten el marco jurídico vigente puede comprometer no solo el
hallazgo en cuestión, sino la solidez del conjunto de la investigación.

---

El OSINT, concebido como disciplina y no como catálogo de herramientas,
exige del investigador una combinación de capacidades que van más allá del
manejo técnico. Requiere criterio analítico para interpretar lo que se
encuentra; conocimiento jurídico suficiente para saber qué puede hacerse,
cómo y con qué consecuencias; sentido crítico para verificar la información
antes de asumir su validez; capacidad de síntesis para convertir datos
dispersos en conocimiento estructurado; y rigor documental para preservar y
trasladar al procedimiento los hallazgos con las garantías necesarias.

Este perfil —el del investigador que se mueve con soltura entre lo técnico,
lo analítico y lo jurídico— no surge de forma espontánea. Se construye con
formación específica, experiencia acumulada y acceso a recursos que
sistematicen el conocimiento disponible. Es precisamente ese hueco el que
este manual pretende cubrir: no el de la formación tecnológica genérica,
sino el de la metodología operativa aplicada a la investigación policial en
cibercrimen.

La vocación de estas páginas es, ante todo, práctica. Se quiere enseñar
procedimientos, no solo principios. Se quiere explicar la lógica de los
pivotes de investigación —cómo se pasa de un correo a un dominio, de un
dominio a una persona, de una persona a una red de entidades—, cómo se
trabaja con la correlación de identidades digitales, cómo se aborda el
análisis de infraestructuras, cómo se documentan los hallazgos para que sean
útiles en sede judicial y no únicamente en la fase de inteligencia operativa.
Se quiere también abordar el uso de la inteligencia artificial como apoyo al
análisis, el tratamiento de los criptoactivos desde una perspectiva
investigadora, o la explotación de metadatos en imágenes, con la misma
orientación: convertir el conocimiento en procedimiento.

---

No obstante, sería un error reducir este manual a un repertorio de técnicas.
Las técnicas, por útiles que sean, envejecen. Las plataformas cambian sus
interfaces y sus políticas. Las herramientas aparecen, se actualizan o
desaparecen. Lo que permanece, y lo que este trabajo aspira a transmitir con
solidez, es la lógica analítica que subyace a toda investigación en fuentes
abiertas: la capacidad de formular hipótesis, contrastarlas, relacionar
entidades, interpretar patrones, detectar incoherencias y construir un
relato verificable a partir de datos dispersos.

Esa lógica, además, debe estar siempre encuadrada dentro de un marco de
legalidad y de respeto a los derechos fundamentales. En el contexto español,
el investigador de policía judicial opera bajo las exigencias de la Ley de
Enjuiciamiento Criminal, la normativa de protección de datos, la doctrina
constitucional sobre el secreto de las comunicaciones y la privacidad, y un
conjunto creciente de jurisprudencia que delimita con precisión qué puede
hacerse en el entorno digital sin autorización judicial y qué no. Ignorar ese
marco no es una opción. El investigador que trabaja con fuentes abiertas debe
saber exactamente dónde terminan las posibilidades legítimas de la
investigación autónoma y dónde comienza la necesidad de cobertura judicial.

Del mismo modo, la preservación de los hallazgos no es una formalidad
burocrática. Es una condición de validez. Una captura de pantalla sin
metadatos verificables, sin sello temporal, sin cadena de custodia, puede
ser irrelevante o incluso contraproducente en el procedimiento. La
documentación rigurosa de la fuente, el método, el momento y el contexto
del hallazgo no solo garantiza su admisibilidad, sino que protege al propio
investigador frente a posibles impugnaciones.

---

Este manual está pensado para quienes trabajan, o aspiran a trabajar, en la
primera línea de la investigación del cibercrimen. Para el investigador de
policía judicial que necesita un marco metodológico sólido al que recurrir
en la práctica cotidiana. Para el analista criminal que trabaja la
inteligencia operativa y necesita entender cómo estructurar y relacionar la
información obtenida en abierto. Para el criminólogo o el profesional de la
seguridad que quiere comprender la lógica de la investigación digital y sus
implicaciones técnicas y jurídicas. Para el docente o el formador que
necesita un texto de referencia que integre doctrina y práctica sin
sacrificar ninguna de las dos.

No es un texto de divulgación. No pretende explicar internet a quien no lo
conoce. Es un instrumento profesional, concebido desde el respeto a la
inteligencia y a la experiencia de sus destinatarios, y construido con la
convicción de que el conocimiento sistematizado tiene un valor real en el
trabajo de quien investiga delitos en el entorno digital.

La investigación en fuentes abiertas no es una solución universal ni un
atajo investigativo. Es una capacidad que, bien desarrollada y correctamente
integrada en el método, amplía de manera significativa las posibilidades del
investigador. Su objetivo no es otro que servir a la verdad de los hechos,
a la eficacia de la investigación y a la solidez del procedimiento. Con esa
convicción ha sido escrito este manual.

---