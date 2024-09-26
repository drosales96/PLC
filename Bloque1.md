# Autómatas programables

Un autómata programable, más conocido como PLC, (Controlador lógico programable (del inglés Programmable Logic Controller)), es un equipo electrónico de control desarrollado para ser utilizado en tareas de automatización y control industrial.

El autómata programable se conecta a la instalación que controla mediante unas entradas que le informan del estado de cada elemento que la conforma y, gracias a un programa interno de control que contiene la secuencia lógica deseada, determina cómo actuar sobre la planta a través de sus salidas, y conseguir el funcionamiento deseado de la instalación.

Actualmente los autómatas programables siguen ocupando un espacio preferente en las tareas de control industrial porque presentan diferencias importantes respecto a los ordenadores industriales que los hace especialmente aptos para el trabajo para el que están diseñados.

### Pros de los autómatas frente a un PC

1. Están preparados para manejar señales eléctricas de tensiones y corrientes elevadas, típicas del ámbito industrial.

2. Mecánicamente están preparados para ser instalados en el interior de cuadros eléctricos, maquinaria, etc. con envolventes robustas y compactas adaptadas a ese entorno y a prueba de vibraciones.

3. Pueden trabajar en un rango de temperatura y humedad mucho más amplio que un ordenador convencional.

4. Disponen de un diseño modular que permite ir ampliando funciones y prestaciones para adaptarse a instalaciones de diversos tamaños.

5. Su funcionamiento es muy estable gracias a su sistema operativo cerrado, centrado en una tarea específica y orientado a la fiabilidad frente a los sistemas operativos generalistas y abiertos de los ordenadores.

6. Disponen de buses de comunicación que facilitan la interconexión entre varias unidades para cooperar en una misma tarea.

7. La rapidez de reacción del PLC es muy superior a la de un ordenador convencional, aunque este sea más rápido al tratar grandes volúmenes de información, lo que los hace más apropiados para el control en tiempo real.

8. Los PLC están pensados para que puedan ser programados por personas con conocimientos de automatización aunque no dispongan de conocimientos informáticos.

Las señales de entrada al autómata pueden ser digitales (con dos estados solamente) o analógicas (pueden adoptar valores intermedios), y llegan al mismo a través de sensores. Por su parte, las salidas también pueden ser digitales o analógicas, y se traspasan desde el autómata a la planta a través de actuadores (dispositivos que reciben una señal eléctrica, neumática o hidráulica de un sistema de control y traslada dicha señal a una actuación física desplazamiento, calentamiento, etc.). La función primordial del autómata es controlar el estado de las salidas según el estado de las entradas siguiendo las instrucciones del programa de control, que se introduce en el PLC con una herramienta de programación y se almacena en una memoria interna.

El PLC, internamente, se compone de distintos elementos interconectados por buses. El principal es la Unidad Central de Proceso (CPU) que, con las memorias, interfaces de entrada y salida, periféricos de control (temporizadores, contadores, vigilantes de funcionamiento, etc.) posibilitan el almacenamiento y ejecución del programa de control.

### ESTRUCTURA, MANEJO E INSTALACIÓN DE LOS AUTÓMATAS PROGRAMABLES

Un autómata programable está constituido por los siguientes elementos internos (pulse sobre los iconos de la imagen para ampliar el esquema y verlo con más detalle).

1. CPU : La unidad central de proceso o CPU es el corazón del autómata, siendo la que accede al estado de las entradas, interpreta las instrucciones almacenadas en la memoria de programa, las ejecuta secuencialmente y por último traslada los valores deseados a las salidas. 

2. Memoria de programa : La memoria de programa contiene el programa de control del autómata, es decir, el conjunto de instrucciones que definen el comportamiento deseado por el autómata una vez en funcionamiento. Esta memoria es de tipo no-volátil, es decir, que no se pierde su contenido cuando se corta la alimentación al PLC, siendo necesario grabarla una única vez y pudiendo ser usada indefinidamente a partir de ese momento. 

3. Memoria de datos : La memoria de datos es una memoria, normalmente volátil, que almacena los resultados de los cálculos y operaciones intermedias requeridas por el programa de control, variables que no son traspasadas directamente a las salidas sino que se usan como cálculos intermedios. Estos valores se suelen perder en caso de pérdida de alimentación, salvo aquellas posiciones especiales que estén protegidas como verá más adelante. 

4. Memoria de imgs de entrada y salida : La memoria de imágenes de entradas y salidas es una memoria volátil utilizada por la CPU para almacenar una imagen del estado instantáneo global de todas las entradas y salidas justo al inicio de cada ciclo de procesado. De este modo, si durante el ciclo de procesado cambian los estados de alguna de las entradas, el programa de control sigue disponiendo de un estado coherente de cómo estaban todas ellas en el mismo instante. 

5. Temporizadores, contadores y otros periféricos : Los temporizadores son unos elementos gobernados por la CPU que permiten gestionar tiempos de forma muy precisa, de manera autónoma y sin consumir recursos de la unidad central de proceso. Pueden usarse para contabilizar el tiempo durante el cual una señal está activa, el tiempo transcurrido desde que se activa una señal, a modo de cronómetro, etc.

Los contadores son otros elementos internos independientes de la CPU que permiten contabilizar activaciones de entradas o de señales internas sin consumir para ello tiempo de ejecución de la unidad central de proceso.

6. Bus interno : El bus interno es un conjunto de pistas que interconectan internamente todos los elementos anteriores entre sí, permitiendo que la CPU acceda a todos ellos para leer y escribir los valores necesarios. Por economía se comparten las mismas pistas eléctricas de bus entre todos los bloques internos, por lo que la CPU debe ir accediendo secuencialmente a cada elemento, señalizando por unos hilos de control con qué bloque comunica en cada instante. 

7. Fuente de alimentación : La fuente interna de alimentación genera las tensiones internas requeridas por los distintos elementos que forman el PLC (típicamente del orden de 3.3 a 5 voltios), a partir de una tensión de alimentación externa que suele moverse típicamente en el rango de los 12 a 48 voltios de tensión continua. 

8. Interfaz de entradas : La interfaz de entradas permite la conexión de las señales de la planta al PLC, adaptando los niveles de las señales presentes en la instalación (tanto digitales como analógicas) a los niveles internos que requieren la CPU (Unidad Central de Proceso) y el resto de elementos internos para su lectura.

9. Interfaz de salidas : La interfaz de salidas adapta los niveles de las señales internas generadas por la CPU y sus periféricos a los niveles de salida al exterior del autómata que requieren los actuadores de la planta (tanto digitales como analógicos). 

ANALÓGICO: Tipo de medida que puede presentar valores continuos de dicha medida, con múltiples valores posibles dentro de su rango de trabajo.

Para implementar esta interconexión entre bloques habitualmente se distinguen en el bus interno las líneas de comunicaciones destinadas a control, direcciones y datos.

Por las líneas de control la CPU señaliza con qué dispositivo interno quiere comunicar y si desea leer o escribir en él, por las líneas de direcciones indica qué registros o direcciones de cada bloque desea leer o escribir, y por las líneas de datos se intercambian los datos leídos o escritos.

Pulse sobre la imagen para para ampliar el diagrama de bus interno.

