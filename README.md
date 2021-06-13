**Data Science aplicado a Interfaces Cerebro Computadora**

*Descripción de la técnica EEG*

La electroencefalografía (EEG) es una técnica que consiste en medir potenciales eléctricos generados por la activación de neuronas en distintas partes del Sistema Nervioso Central (SNC), y dentro de este, las señales cerebrales son el objeto de estudio más frecuente con esta técnica. Los potenciales son registrados por electrodos que se posicionan próximos a la región específica del SNC que se quiere estudiar, ya sea en sobre la superficie de la piel aledaña o en contacto directo con el tejido cerebral. En el primer caso, se habla de electrodos “superficiales”, modalidad más segura pero con mayor atenuación de la señal, y en el segundo, de electrodos “profundos” en donde el contacto directo con la corteza garantiza una mejor calidad de señal pero con el costo asociado de un riesgo de infección y daño tisular. Dependiendo del tipo de registro utilizado y la profundidad en la que son ubicados, los electrodos pueden medir potenciales generados por un conjunto muy pequeño de neuronas (electrodos profundos) o potenciales generados por un conjunto mucho mayor, de hasta cientos de miles de neuronas (electrodos superficiales). Esto último implica que, aunque mucho más segura, la electroencefalografía superficial sólo logra captar adecuadamente potenciales que involucran a grandes porciones cerebrales, que suelen ser el reflejo de procesos cognitivos generales (motricidad, procesamiento del lenguaje, visión, etc.) que se encuentran distribuidos a lo largo de regiones medianamente extensas del cerebro.

*Potenciales Evocados Visualmente de Estado* 

Los Potenciales Evocados Visualmente de Estado Estacionario (SSVEP por sus siglas en inglés), constituyen un ejemplo de respuesta de un gran conjunto de neuronas, y esta característica lo vuelve detectable por medio de electroencefalografía superficial. El fenómeno se manifiesta cuando un sujeto experimental observa una luz parpadeante a una determinada frecuencia; mientras se lleva a cabo dicha tarea la actividad de las neuronas de la región cerebral encargada de la visión replica la periodicidad con la que se enciende y apaga la luz. Ubicando electrodos en la región occipital del cerebro (corteza visual), se puede registrar el cambio y sincronización de la frecuencia de las señales eléctricas con la del estímulo luminoso aplicado, que se torna particularmente evidente al estudiar los registros en el dominio de la frecuencia.

*SSVEP en el contexto de interfaces cerebro computadora*

La posibilidad de inducir en forma controlada e inocua determinadas frecuencias de activación en el cerebro junto con la factibilidad de su registro y posterior identificación, constituye a las SSVEP (Potenciales Evocados Visualmente de Estado Estacionario) como una gran opción para generar interfaces cerebro-computadora. Al presentarle a un potencial usuario un estímulo visual al cual puede dirigir su vista, registrando su actividad cerebral y tras aplicar procesamiento de señales (ciencia de datos) a los registros conseguidos, el cambio de frecuencia de las señales de EEG puede utilizarse como una señal de control binaria. Más aún, si se disponen de diferentes estímulos visuales a diferentes frecuencias, la identificación de cada una de esas frecuencias en la señal eléctrica, permite tener un abanico más complejo de control, que luego puede luego transformarse en un comando o una decisión (la selección de una entre varias opciones, cada una asociada a una luz distinta por ejemplo).

*De la ciencia ficción a la inclusión con OTTAA Project*

OTTAA Project es una startup cordobesa que ha desarrollado una app para permitir a las personas que carecen de posibilidad comunicativa el poder comunicarse a través de la selección de frases en formato de pictogramas en un dispositivo tablet o smartphone. Sin embargo, algunos usuarios tampoco poseen habilidades motoras para poder realizar esta selección, para lo que OTTAA Project brinda un conjunto de dispositivos de accesibilidad. Uno de estos dispositivos, consta de una Interfaz Cerebro Computadora (BCI, por sus siglas en inglés) en la cual se utilizan estos potenciales para poder interpretar la intención de generar una determinada frase o comunicar una determinada idea por parte de personas con enfermedades o síndromes que no sólo impiden la comunicación verbal, sino además limitan el movimiento de cualquier parte del cuerpo, teniendo como principal ejemplo el síndrome de enclaustramiento. Utilizar una señal que demora algunos segundos en poder ser captada por el sistema puede parecer demasiado lento o fastidioso a primera vista, pero el uso de este potencial en el entorno BCI podría permitirnos comunicarnos y entendernos con personas con las que hasta el día de hoy perdíamos casi cualquier tipo de conexión.

*Descripción del eq#uipo de adquisic*

Existen muchos equipos de adquisición de señales electroencefalográficas, que varían según la cantidad de electrodos que admiten, la tasa de muestreo de datos, la fidelidad de la señal, portabilidad, entre otras características. Uno de estos equipos es OpenBCI desarrollado por la empresa homónima^3, se trata de un equipo de medición de bioseñales que, a pesar de no poseer clasificación de grado médico, ha sido avalado por muchos profesionales del área de investigación y constatado frente a otros equipos demostrando igual o mejor calidad. El sistema consiste en una pieza de hardware dada por una placa PCB que contiene todos los componentes de adquisición, filtrado analogico y digitalización, acompañada de un software que recolecta datos por medio de tecnología Bluetooth, WiFi, RF, conexión cableada o tarjeta SD, ambos con licencia OpenSource. Esto último significa que cada componente de la placa está descrito y detallado, al igual que el circuito de conexiones, y que el código fuente del software puede ser modificado para cambiar sus funcionalidades de manera legal y gratuita. OpenBCI ofrece dos principales tipos de placas de adquisición, Cyton Board y Ganglion Board, las cuales varían la tasa de adquisición de datos, el tipo de transferencia de datos hacia el ordenador y la cantidad de electrodos que pueden medir.

*Descripción específica del Dataset*

El dataset consiste en un conjunto de 7 registros, realizados en 5 individuos en 7 sesiones de adquisición utilizando para la toma de las señales la placa Ganglion Board. La elección de este hardware permite no solo la observación en tiempo real de las señales provenientes de 4 canales por medio del software de OpenBCI, sino también el guardado de los datos en formato CSV en un documento de texto (.txt) o en formato BDF.

El dataset consiste en un conjunto de series temporales que reflejan variaciones de voltaje a lo largo del tiempo tomadas a una tasa de muestreo de 200 muestras por segundo, en un contexto experimental en donde los sujetos experimentales fueron estimulados por luces en dos frecuencias específicas: 12,5 Hz y 16.5 Hz. Cada registro constituye un archivo txt que posee primero 10 líneas con las correspondientes descripciones de del hardware y software utilizados, seguidas por una tabla de 11 columnas que constan de:

Una primer columna de cuenta de muestras,
Cuatro columnas con los datos de cada canal,
Tres columnas con las mediciones de acelerómetros presentes en la placa Ganglion (no utilizados en estos estudios), 
Una columna de etiquetas (serán descritas a continuación), 
Una columna de marcas temporales, 
Una última columna de etiquetas temporales utilizadas por el Software OpenBCI para reproducir las señales posteriormente (tampoco utilizadas en este estudio). 

Etiquetado de la estimulación: El experimento consistió en indicar al sujeto que observase una u otra luz subsecuentemente, con intervalos de descanso intermedios. Al indicar cada luz se registraba en el software del equipo la etiqueta de dicha luz, lo cual colocaba en la columna de labels mencionada anteriormente un 1 para la luz parpadeante a 12,5 Hz o un 2 para la de 16,5 Hz, ambas durante 10 segundos de estimulación (aproximadamente 20000 muestras). En los intervalos de no estimulación la columna de etiquetas era ocupada por el número 99.
