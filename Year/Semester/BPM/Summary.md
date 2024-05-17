## Unidad 1
### Que es un proceso?
Un Proceso de Negocio **(Business Process)** es un conjunto de actividades que son realizadas en coordinación con el entorno organización y técnico.

### Características de un proceso
- Pueden ser medidos y están orientados al rendimiento, obligatorio
	- **Ejemplo**: Vender a un cliente y si el vende en un rango de la empresa, con bueno, regular o malo.
- Tienen resultados específicos
- Entregan resultados a clientes o “stakeholders"
- Responden a alguna acción o evento específico
- Las actividades deben agregar valor a las entradas del proceso.


### Modelo de un Proceso

![[Pasted image 20240312162936.png]]
**Ejemplo.**
![[Pasted image 20240312162949.png]]



### Identificar un proceso
Para reconocer un proceso de negocio se debe tener presente que deben generar valor para el negocio, es decir que permitan generar ingresos o transacciones comerciales por concepto de ventas, o bien mitigar el costo al negocio.

- Clasificar los procesos de negocio
- Identificar las funciones de los participantes
- Extraerlos a partir de los objetivos estratégicos.


### Clasificación de un proceso de negocios
- **Núcleo**: Considera qué valor reciben los actores del negocio primarios y más importantes: los clientes.
- **Soporte**: Contiene las actividades que no benefician al cliente directamente pero que apoyan a los principales.
- **Gerencial**: Estos procesos se encuentran buscando los procesos que tienen que ver con el manejo del negocio en su conjunto. Normalmente se relacionan con el actor propietario

### Identificación de funciones

- Descripción de cada actividad en el negocio existente por parte de los expertos en el dominio
- Luego las actividades se agrupan, surgiendo una función.
![[Pasted image 20240312163004.png]]


### Proceso estratégicos (Empresa)
Son los procesos relacionados con la estrategia de la empresa, y están a cargo de cómo establecer la misión, visión y objetivos corporativos, comunicar la estrategia y motivar a los colaboradores a cumplir sus objetivos.

**Ejemplo**: Ampliar la capacidad de clientes en una empresa.
![[Pasted image 20240312163142.png]]

### Tipos de Procesos
**Proceso clave o negocio**: Son los proceso encargados de cumplir la misión de la empresas y cumplir con las necesidades de los clientes.

**Ejemplo**: Por ejemplo, vender una mesa en una fábrica de construcción de mesas, funeraria que hayan muertos, Duoc que hayan estudiantes, clínica que hayan enfermos.

**Procesos de Apoyo o secundario**: Son los procesos internos dentro de la empresa necesarios para que el proceso de negocio cumpla su objetivo
**Ejemplo**: empresa de venta de mesas, si abastecimiento no compra barniz, no se pueden vender mesas, y abastecimiento es un proceso de apoyo o secundario


![[Pasted image 20240312163559.png]]

### Mapa de procesos
![[Pasted image 20240312170551.png]]

### Procesos estratégicos
- Aumentar participación de mercado
- Cambiar políticas de ventas
- Aumentar dotación de personal
- Definir objetivos de compras
![[Pasted image 20240312170651.png]]


### Procesos de negocios o claves
- Compra de materia Prima
- Confección o elaboración de Productos
- Logística y distribución de productos
- Servicios de ventas /atención de clientes (servicio Técnico)


### Procesos de Apoyo o secundario
- Contabilización de ventas
- Contratación de persona
- Pago remuneraciones
- Manutención de sistema informáticos

### Conceptos importantes
- **Proceso:** Un proceso es una actividad que tiene un tiempo fijo que con un conjunto de elementos da un resultado final
- **Actividad**: Es un paso dentro del proceso
- **Negocio**: Negocio nos referimos a cualquier acto de rubro que es remunerado.
- **Mejora continua**: Mejora los procesos constantemente
- **Indicadores**: Los indicadores nos pueden señalar que tan avanzado o en que estado se desarrolla un proceso.
- **Sistema informático**: Conjunto de elementos que funcionan para un fin.
- **Informatica**: capacidad de guardar la informacion y usarla.

#### Ejemplo de proceso para bizagi (Proceso / Actividades)
**Proceso**: Comprar entradas / Cine
1) Elegir película
2) Elegir horario
3) Elección asiento

### Requerimientos
Se encontrarán relacionados a identificar y describir los objetivos del proyecto junto con su relación con los objetivos del negocio de la organización donde se está realizando el proyecto.

- La aplicación de Ingeniería en Software se enfoca en la descripción de los diferentes tipos de requerimientos destacando las características y funcionalidades que debe cumplir el software.

- Cuando buscamos la explotación de la información no buscamos la construcción del sistema software, buscamos comprender el proceso que convierta los datos disponibles en conocimiento

### Fuentes de Requerimientos
Identificar las fuentes de información disponibles en la organización identificando cuáles fuentes se encuentran informatizadas (en repositorios de datos) y cuáles no.

- Análisis de los objetivos del proyecto
- Análisis de los objetivos del negocio
- Observación del negocio y sus participantes

![[Pasted image 20240314150832.png]]

### Gestión de procesos de Negocios
La gestión de procesos es una forma sistemática de identificar, comprender y aumentar el valor agregado de los procesos de la empresa para cumplir con la estrategia del negocio y elevar el nivel de satisfacción de los clientes.

La gestión de procesos de negocios se puede representar en el siguiente modelo

![[Pasted image 20240314151131.png]]

### ¿Cuándo entra en acción BPM?
En organizaciones nos encontramos con las siguientes situaciones de la vida real que inducen a un proyecto de BPM
![[Pasted image 20240314160104.png]]

### Modelando con BPMN
BPMN son las siglas de Business Process Modelling Notation.
Para modelar un BPM tenemos una notación estandarizada por la OMG, conocida como Business Process Modelling Notation o su sigla BPMN.
- Este estándar nos permite modelar los flujos de los procesos de negocios ya sean manuales o automatizados.
- Gráficamente un diagrama BPMN está compuesto solo por cinco elementos: Objetos de flujo, información , objetos de conexión, actores y roles, artefactos ![[Pasted image 20240314162254.png]]


Un modelo BPMN tiene un pequeño grupo de elementos centrales para definir el flujo de proceso (FlowObjects):

![[Pasted image 20240314162642.png]]

#### Eventos
Un evento se representa por un círculo y le indica al flujo que algo ocurrirá durante el curso de un proceso de negocio.

Los eventos afectan el flujo del proceso usualmente tienen una causa ( trigger) o un impacto (resultado)

![[Pasted image 20240314162937.png]]

#### Actividades
Una actividad se representa por un rectángulo con sus bordes redondeados y es un término genérico para el trabajo que una organización realiza.

![[Pasted image 20240314163228.png]]


#### Gateways
Un Gateway se usa para controlar divergencia o convergencia de la secuencia de un flujo.
- Determina las tradicionales decisiones, tanto de bifurcaciones, como uniones y acoplamientos de flujos. Las anotaciones al interior indicar el tipo de comportamiento de control
![[Pasted image 20240314163401.png]]

#### Conexiones entre objetos
Existe tres tipos de conectores 
- **Flujo de secuencia:** muestra el orden de la actividad dentro del proceso 
- **Flujo de mensaje:** muestra los mensajes entre dos procesos separados. 
- **Asociación:** se usa para asociar datos, textos u otros artefactos con flujos de objetos.
![[Pasted image 20240314165144.png]]

#### Swimlanes
**Pool**: es el contenedor del diagrama de flujo de trabajo proceso
**Lane**: es división dentro de un POOL. Son utilizados para organizar actividades dentro de un POOL.
![[Pasted image 20240314165323.png]]

### Gestión de procesos
Se define como un sistema completo cuyo principal objetivo es enfocarse en la mejora continua del funcionamiento de las actividades de una organización. Como resultado se obtiene una reducción de la variabilidad innecesaria en los productos finales, así como el uso óptimo de recursos y eliminación de actividades repetitivas
![[Pasted image 20240319185615.png]]

### Enfoque de procesos
Busca que la organización completa se visualice desde el punto de vista del cliente.

En el típico enfoque funcional cada área es considerada independiente, responsable únicamente de sus procesos, y no hay una adecuada interconexión y articulación con las demás áreas.

Este punto de vista genera una entropía en la organización.

Sin embargo, el enfoque por procesos rompe esas barreras entre áreas mejorando y rediseñando los procesos con el fin de lograr mejorar actividades muy arraigadas de las áreas funcionales; generar una estructura organizacional más dinámica, flexible; generar mayor valor y lograr la satisfacción del cliente
![[Pasted image 20240319185749.png]]


### Mapeo de procesos
Con la competitividad del mercado, el mapeo de procesos es un diferencial dentro de la organización. Es posible tener mayor comprensión del proceso y obtener varios puntos positivos.

- **Hacer más eficiente la toma de decisiones:** con el proceso de mapeo se puede visualizar la trayectoria del proceso dentro de la organización, ya que las actividades y sus responsables, los elementos, la mano de obra, recursos y esfuerzos necesarios.
- Además de reconocer lo que mejora, el mapeo optimiza tiempo y deja más eficiente la toma de decisión.

**¿Por qué mapear?**
Estandarizar el proceso, aumentar la productividad, mejorar la calidad de la entrega del producto y / o servicio y lograr una mayor satisfacción de los clientes

Mediante la estandarización del proceso a través de documentación, por ejemplo, se puede mantener un nivel de calidad de servicio y / o producto a entregar al cliente.

### Mapeo de Procesos AS IS/TO BE
El Mapeo de procesos AS IS / TO BE es una herramienta de gestión que ayuda en la descripción y la mejora de los procesos internos de la organización.

AS IS demuestra la situación actual y la realidad de los procesos organizacionales, con sus errores y aciertos.

El AS-IS forma parte de las etapas de modelamiento y diseño del ciclo BPM

Muestra como se ejecuta un proceso actualmente, mediante el uso de flujos, conexiones, carriles y artefactos

El mapeo de procesos AS IS es la definición de la situación actual del proceso. Los participantes de esta asignación son los usuarios que están involucrados en el proceso cotidiano (usuarios clave).

- Se dedica a la exploración del negocio de la empresa a través de metodologías y prácticas utilizadas en las actividades del día a día.

- El mapeo de procesos AS IS es la definición de la situación actual del proceso. Los participantes de esta asignación son los usuarios que están involucrados en el proceso cotidiano (usuarios clave).
![[Pasted image 20240319191617.png]]

### Sugerencias de Mapeo de Procesos

#### Defina los usuarios clave y / o el dueño del proceso
Los usuarios clave, en inglés key users, son usuarios que tienen más conocimientos acerca de las reglas de un proceso de negocio

Son ellos quienes realizan el proceso diariamente. Es necesario identificar a estos profesionales para recopilar información


#### Identifique y mapee procesos (levantamiento del proceso AS IS
También llamada de levantamiento AS IS, en esta etapa el proceso actual es modelado sin atentar a las mejoras que pueden o deben ser aplicadas.

La principal idea es levantar requerimientos, conocer los usuarios, como trabajan, etc, en resumen es conocer como funciona el trabajo en la empresa. y luego se modela

Las entrevistas o reuniones ocurren con los usuarios clave. Se debe recopilar datos sobre:
- Descripción de las reglas de negocio y usuarios involucrados, proveedores, clientes y sus interacciones
- Explicación del recorrido del proceso (secuenciación de tareas) y validaciones, los escenarios alternativos de negocio
- Descripción de las tareas, tiempo de ejecución y participantes; 
- Para entender y definir las entradas y salidas (entrada de información y de salida); 
- Buscar documentos y sistemas que faciliten el entendimiento y ayuden en lo que puede ser automatizado.

#### Rediseñe procesos (modelado del proceso TO BE
En este paso se definen soluciones a los problemas, es decir, se evalúan las posibles mejoras para poder aplicar en el proceso.

Es también aquí que definimos una nueva versión del modelado, el TO BE – nuevo gestor del proceso, alcance, objetivo, actividades, reglas y papeles.

Además de definir estos ítems, hay que resaltar actividades que agregan valor y eliminar las que no agregan, diseñando el proceso con herramientas de modelado específicas.


A acá se modela la solución del as is.

#### Consenso con el cliente
Es la etapa en que el cliente ratifica el proceso modelado, las reglas levantadas y las mejoras sugeridas.

Es necesario garantizar la ejecución de todos los caminos posibles e involucrar a los participantes de cada tarea. Con ello conseguimos el correcto progreso del proceso y la integridad de los datos.

#### Análisis de efectividad
Para evaluar la efectividad del napeo del proceso es posible aplicar encuestas de satisfacción y utilizar indicadores, siendo ellos de eficiencia
- (medición de productividad en relación a las salidas generadas), 
- eficacia (medición de la calidad en relación a las salidas totales)
- efectividad (medición del impacto).

El seguimiento de la utilización del proceso en producción también es válido para subsanar dudas de nuevas tareas que se han atribuido a los responsables de la ejecución del flujo.


### Finalizar
Sobre todo la herramienta AS IS / TO BE debe enfocarse en la madurez del proceso de modo que al final de la etapa TO BE, el proceso esté.
- Cada vez más adherente a los objetivos estratégicos de la organización y Estructurado para simplificar y traer eficacia a los procesos y sus actividades, ya sean en el ámbito estratégico o operacional.

Para lograr estos objetivos, es fundamental la participación y el compromiso de todos los participantes y el foco diario en la mejora continua, además de la adopción de una solución eficiente de Gestión de Procesos

### Procesos estratégicos
Son los procesos relacionados con la estrategia de la empresa y están a cargo  de como establecer la misión, visión  y objetivos corporativos.

### Procesos operativos
Son procesos que permiten generar el producto/servicio que se entrega al cliente, por lo que inciden directamente en la satisfacción del cliente final. Generalmente atraviesan muchas funciones.



### Procesos de apoyo
Son los procesos internos dentro de la empresa necesarios para que el proceso de negocio cumpla su objetivo.
## Unidad 2
### Plan de mejora en la organización
#### Evaluación Técnica
El análisis y modelamiento del **As Is**, en conjunto con los **KPI** y los **KRI** son esenciales para evaluar los procesos actuales del negocio, ya que nos permiten visualizar su estado y los riesgos a los cuales se enfrenta.

Uno de los problemas asociados al diseño de procesos de gran escala se centra en las actividades de inspección y evaluación del modelo durante las distintas etapas de construcción y manutención de este en el tiempo.

Las dificultades en la producción de indicadores, como los problemas en la lectura cuando los procesos son muy extensos.

Aparentemente cualquier cambio propuesto puede parecer simple, pero desencadena una gran cantidad de decisiones, estimación, esfuerzo en diseño y pruebas; junto con el impacto que uno de estos cambios pueden tener para el negocio

Por esta razón, conocer el grado de complejidad que tiene nuestro proceso de negocio, es de gran valor para la actividad de diseño y mantenimiento del negocio

Una vez centrados en el diseño y estructuración de procesos de negocio, es importante mencionar que estos procesos de negocio normalmente se encuentran desarrollados en lenguajes de alto nivel.


#### Plan de Mejora
Conjunto de acciones y tareas definidas para mejorar los procesos y reducir y/o eliminar problemas producidos por falta de controles y ejecución de malas prácticas identificadas en las áreas de análisis.

#### Beneficios para la Organización
- Incrementar la eficiencia en los procesos, subprocesos, servicio, etc. (Competen con el objetivo de la empresa)
- Corregir problemas que se presentan
- Decidir en que área o procesos se debe dar mayor atención. Establecer prioridades de solución.
- Herramienta de ayuda para la mejora de los procesos en las áreas de evaluación
- Lograr compromiso y apoyo de las áreas que están relacionadas con el o los procesos en conflicto.

### PHVA (Ciclo de mejora continua)
![[Pasted image 20240414142019.png]]

**Verificar**: ver si realmente se mejoro

#### Actores y Responsables (Stakeholder Interesados en el proyectos)
- Directores
- Gerentes y Subgerentes de áreas.
- Jefes o Supervisores (Mandos Medios)
- Analistas.
- Coordinador.

#### Tareas más importantes
- Evaluación del proceso donde se implementara el plan de mejora. Análisis de problemas que se presentan en el desarrollo del mismo.
- Capacitar e implementar el plan de mejor con la asistencia técnica en dicha implementación.
- Implementar y monitorear la implementación.
- Evaluar los resultados de los planes y realizar retroalimentación.
- Control del tiempo en el desarrollo del plan de mejora
- Entregar los instrumentos para aplicar el plan de mejora


#### Diagnostico
Es el análisis mediante el cual podemos obtener la situación actual del unidades de estudio e identificar la problemática que impiden a la organización ser más eficientes y efectivos en sus servicios y/o producción.

- Levantamiento de información
- Estado de Situación Actual
- Socialización de Resultados
- Resultado del análisis de Calidad
- Resultado de Observación
- Priorización de acciones de Mejora

#### Capacitación y Construcción del plan.
Etapa en la cual se deben capacitar a todos los actores implicados en el plan de mejor, con el fin de que utilicen las herramientas para la construcción del plan de mejora.

#### Ejecución de acciones de mejora

n esta etapa se confecciona el plan de mejora con el detalle o lista de mejoras a implementar con su respectiva priorización. 

Matriz de Trazabilidad: Identifica las acciones de mejoras, priorización, acciones a implementar, cumplimiento y observaciones.


#### Monitoreo y evaluación del plan
Es la medición de los avances para garantizar la implementación de la mejora. 
En esta etapa es fundamental contar con la completitud de la siguiente documentación:
- Matriz de trazabilidad del Plan de Mejora
- Respaldos o evidencias de las mejoras implementadas

#### Actividades de control
Control Técnico, profesional a cargo controla que se desarrollen cada una de las tareas y actividades planificadas en el plan.

Es un seguimiento continuo para verificar avances.

- **Evaluación**: En esta etapa se verifica que cada tarea planificada se implementó la o las mejoras.
- **Sistematización**: Análisis de la experiencia y los resultado obtenidos. Son los resultados y lecciones aprendidas en la implementación del plan de mejora. Esta información es de gran aporte, ya que nos ayudarán en la implementación de nuevos planes de mejoras en el futuro.

### Clasificación y técnicas de mejora

#### Análisis y estructura
Con el análisis de estructura se busca mejorar el desempeño de los procesos sobre todo con miras a reducir los tiempos de ciclo y mejorar la calidad de los servicios de los procesos. 
Para estos efectos podemos revisar:
- El orden de las actividades en un proceso
- Si existen redundancias
- Actividades, procedimientos o reglas de negocio obsoletas
- Flujos complejos que se puedan simplificar

**Las posibilidades que tenemos para reestructurar los procesos :**
- Optimizar el orden
- Acelerar
- Agregar

#### Análisis de Ciclo
El concepto de tiempo de ciclo dice relación con el tiempo que toma el proceso
en ejecutar una instancia, desde su inicio hasta el fin del proceso.

Conceptos asociados a estos son el “Cuello de Botella” que dice relación con una reducción en la capacidad de flujo del proceso, y el “Bloqueo” que se refiere a una detención de las actividades, ya que una de ellas no tiene “ donde dejar” la instancia ya procesada.

En términos generales, además de reducir el tiempo de ejecución de las actividades, las
recomendaciones a fin de reducir el tiempo de ciclo es un proceso dicen relación con:

- Reducir las interrupciones del proceso.
- Eliminar los cuellos de botella
- Eliminar las colas o almacenamientos.
- Cambiar el orden de las actividades
- Diseñar actividades en paralelo
- Juntar dos o más actividades en una.

#### Análisis de costeo de actividades
Cualquier cambio del sistema requiere un costo.

Un objetivo principal de toda empresa u organización es gestionar sus costos y
los procesos, los que durante su ejecución consumen actividades y, por su
parte, las actividades consumen recursos.

La idea central de costeo por actividades es asignar el consumo de recursos a cada actividad ( la obtención de esta información es un proceso separado al de modelamiento), por ejemplo : consumo de materiales, obra de mano, energía, tiempo de máquina, etc., obteniendo así un costo para cada actividad


##### Perspectiva de BPM.
Algunas recomendaciones para optimizar los costos de los proceso:
- Eliminar del proceso aquellas características del producto o servicio que no agregan valor para el cliente.
- Aumentar el uso de los recursos a través del aumento de la productividad de la capacidad instalada.
- Aumentar la calidad en todo el proceso


#### Análisis de responsabilidades
Estudia la relación entre las actividades del proceso y su respectiva asignación de responsabilidades.

En organizaciones grandes y antiguas, como también en la administración pública nos encontramos con estructuras jerárquicas y burocráticas que se pueden reducir, liberando de esta forma actividades que retienen el proceso y no cumplen otra función que confirmar o aprobar un documento, que elaboró un ejecutivo o usuario de negocio.



### Ventajas de Mejora continua
Los cambios no se **producen de manera traumática** y, por lo tanto, son asumidos positivamente y de forma natural por los profesionales.

Su implantación **no requiere de grandes inversiones ni de un gran sobreesfuerzo de los empleados.**
### ReIngenería
**REINGENIERÍA, REDISEÑO Y MEJORA REINGENIERÍA** Los Procesos en la empresa en el tiempo pueden mejorarse (calidad total), pero llegará un punto que será necesario realizar un cambio, innovar porque ya se agotó las mejoras.

En ese aspecto, la definición de reingeniería será hacer un nuevo diseño radicalmente distinto.

#### Ventaja
Si se toman las decisiones correctas y se implementan de forma adecuada pueden lograrse nuevos diseños radicales, notables mejoras en eficacia, eficiencia, productividad y efectividad, alcanzado un balance global muy positivo.

### Modelo To Be
El Proceso To be es la continuidad del proceso AS IS, su objetivo es mejorar el AS IS y proyectar el modelo de proceso para el futuro.

Después del análisis del proceso As Is, como es, la fase de To Be tiene el objetivo de crear o diseñar nuevos y mejores proyectos, más eficaces y eficientes.

![[Pasted image 20240416091042.png]]
![[Pasted image 20240416091054.png]]

#### Modelo To Be en 6 actividades

##### Diseño del Proceso To Be
Al diseñar el nuevo proceso (To Be), el objetivo es asegurarse de que le
ofrezca a la empresa exactamente lo que la empresa espera lograr con este
nuevo proceso, **tiene ciertos detalles a cumplir**
- Las actividades detalladas
- Las reglas de negocio
- Las interacciones con los clientes
- Los Productos

Para lograr este resultado, se utilizan diferentes metodologías, tales como
estudios de escenarios, brainstorming o intercambio de ideas, el modelado en
tiempo real, e incluso la vieja pizarra.

##### Definición de las actividades del proceso
La definición de las actividades del proceso To Be debe incluir una visión sencilla y directa de lo que se debe hacer.

La clave en esta etapa es ser tan simple como sea posible, idealizando
actividades fáciles de entender y de explicar. Buena manera de comprobar si la descripción de las actividades es eficiente y objetiva.

**Cosas a cumplir**:
- Las actividades deben estar encadenadas en orden
- Defina las actividades sin aferrarse a los agentes del proceso
- Defina objetivamente lo que se hará
- Trate de crear un paralelismo entre las actividades

##### Análisis de lagunas y comparaciones
El proceso To Be debe ser diferente y mejor que el proceso actual. Para lograr esto, es necesario hacer una comparación entre los resultados obtenidos en la actualidad, con los resultados a alcanzar.

Esto se puede hacer con herramientas de simulación:

- Esbozar lo que se debe cambiar en el proceso To Be
- Hacer tangibles las ganancias que se pretende obtener con el nuevo proceso
- Documentar los resultados esperados
- Crear una mayor colaboración y apoyo a la forma en que el proceso To Be funcionará


##### Diseño y Análisis de la Infraestructura 
Esta es una etapa crucial en el diseño de nuevos procesos, que a menudo no
se toma con la seriedad necesaria.

**Desarrollar una TI correcta hay que**:
- El flujo de datos
- Las Aplicaciones
- Los Sistemas
- Las Interfaces entre sistemas
- Quién va a usar la información
- Cuándo utilizará la información
- Por medio de qué sistema


##### Simulación, pruebas y aceptación del modelo
La simulación del proceso To Be, o cómo será el proceso en el futuro, debe aprovechar las tecnologías actuales que ayudan a predecir los resultados con seguridad, confiabilidad y también con agilidad.

Dado que se trata de una simulación, este es el momento de hacer las
pruebas para poner límites.

Certificación definitiva de las etapas del proceso, es necesario estimar los riesgos con mucho cuidado.

Siempre hay que contar con el responsable del proceso, que dará la última palabra


##### Creación del plan de implementación
Todo lo que se decidió y se diseñó, no se implementará por sí solo. El diseño del nuevo proceso es sólo un paso hacia su implementación. 

Un buen plan de implementación debe definir la gestión del cambio, qué sistemas se verán afectados por el proceso rediseñado, determinar claramente los equipos implicados y señalar las siguientes actividades del proyecto punto a punto.

### Que es un KPI
Los KPI o Índices Clave de Desempeño (Key Performance Indicators), son indicadores que ayudan a medir y cuantificar nuestro trabajo, habiendo previamente definido objetivos y actividades que nos ayuden a conseguir dichos objetivos.

Es decir, los KPI nos indican qué debemos hacer para incrementar de un modo extremadamente significativo el desempeño de la empresa. Dichos indicadores son la materia prima de los directivos de la empresa, ya que apoyaran en la toma de decisiones

#### Modo de elección
**(Specific) Específico:** Tienes que ser concreto y conciso a la hora de
seleccionar un KPI.

**(Measurable) Medible:** Son cuantificable, en cifras, categorías,
porcentajes, para luego poder compararlo con otros datos.

**(Achievable) Alcanzable:** El objetivo debe ser realista y posible de lograr.

**(Relevant) Relevante:** Son relevantes para
el objetivo y la estrategia del negocio.

**(Timely) Medible en el tiempo:** Tiene variación en el tiempo, esto para garantizar comparaciones.


#### Como definir un KPI
Cómo definimos unos KPIs para un proyecto nuevo, podemos guiarnos por las siguientes simples preguntas.

**¿Qué medimos?**
**¿Por qué medimos este dato?**
**¿Realiza el seguimiento de los resultados de uno de nuestros objetivos?**
**¿Es un factor clave para la empresa?**
**¿Quién es el responsable de supervisarlo?**
**¿Con qué periodicidad conviene supervisarlo?**

#### Partes de un KPI
**Definición:** Debemos dar una descripción de nuestro objetivo específico, de manera que
todo el equipo sepa bien a qué se refiere. **¿Por que y para que medir?**
**Formula de medición:** ¿Cómo lo vamos a medir?, Ejemplo: Ventas/Visitas a la página x 100 = %
**Unidades de medida:** Unidad de medida del KPI. Por ejemplo, Notas, veces, porcentaje, etc.
**Periodicidad:** ¿Cada cuánto vamos a medirlo? Responsable del proyecto o departamento. Actividad o proyecto al que se vincula el KPI.

#### Características
Al momento de seleccionar los KPIs con los cuales medirá sus procesos.
- Los KPIs solo resultan útiles si se definen de manera correcta.
- Se deben elegir indicadores simples que todos comprendan.
- Existen KPIs estándar, es decir, predefinidos pero lo ideal es tener KPIs que se adapten a la realidad de la organización.
- Deben ser indicadores medibles cuantitativamente.
- Deben tener una frecuencia de análisis, un constante acompañamiento nos indicará la dirección que está tomando la organización.
- Deben ser dinámicos, el indicador de ayer que fue importante, hoy puede haber perdido valor.

Otro características importante de los KPIs es que están enfocados a la
temporalidad.

**KPIs históricos:** estos indicadores mostrarán lo que ha ocurrido en el pasado
inmediato o histórico

**KPIs en tiempo real:** en este caso en particular los indicadores nos entregaran
información de procesos operacionales que entregan resultados en línea.

**KPIs predictivos:** en este caso se proyectarán resultados futuros sin cambio de
parámetros actuales

**KPIs de simulación:** permiten visualizar la proyección de posibles resultados de
futuro en función de patrones de comportamiento actual e histórico.


### ¿Indicador clave de riesgo KRI?
Los indicadores clave de riesgo, o KRI, por su sigla en inglés (Key Risk Indicators), son métricas que se utilizan para determinar el potencial de un riesgo eventual y tomar medidas oportunas.

**Definición simple:**  Los KRI proporcionan información útil sobre los riesgos potenciales que pueden impactar los objetivos estratégicos de una empresa, indicando la información que se requiere para determinar si alcanzaremos las metas del negocio


Estos indicadores son una especie de alarma que avisa cuando algo no está funcionando como debería. **Por ejemplo, una disminución en la demanda que impacta en las ventas.**

**KRI se concentran en el pronóstico de lo que podría suceder.**

![[Pasted image 20240421131610.png]]

#### Indicadores de conceptos básicos
El riesgo no siempre tiene que ser una amenaza para una empresa, también podría ser una oportunidad.

**Ejemplo**: perder a un **colaborador clave** puede ser una amenaza, por un lado, pero por otro lado, puede ser **una oportunidad de encontrar un nuevo colaborador** que le proporcione nuevas habilidades e ideas.

![[Pasted image 20240421131724.png]]

#### Auditoria continua
El proceso para determinar los riesgos y mantener una auditoria continua a nuestros procesos.
- Los procesos seleccionados determinar sus indicadores más oportunos.
- Identificar los datos que permitan obtener los indicadores seleccionados.
- Cuando no se posean datos automatizados, se pueden definir cuestionarios y fechas de recepción; estableciendo métodos de comprobación.
- Definir rangos de admisión de valores, es decir, cuando un valor es aceptable o cuando se deberían gatillar las alertas.
- Analizar los resultados y consultar las causas de las desviaciones atípicas.
- Abrir un proceso de auditoría para los casos no justificados razonablemente.
- Concluir sobre las causas reales que justifican las desviaciones.
- Proponer recomendaciones y mejoras.

Los **KRI**, al momento de analizar los datos siempre se hacen respecto de datos comparativos, es decir, comparar las situaciones observadas con las que resulten habituales, alineadas y compatibles con los objetivos del negocio.


#### Definiendo un KRI
Definir nuestro objetivo específico, de manera que todo el equipo sepa bien
que debemos mitigar y controlar.

Los mismos principios que utilizamos para los KPI los podemos llevar a la definición de KRI
- Se necesita tener un contexto empresarial adecuado
- Es necesario que sean medibles o cuantificable
- Debe ser relevante
- Tiene que haber una persona responsable del KRI
- Debería haber una participación del equipo.
- Medible en el tiempo

##### Fórmula de medición.

**¿Cómo lo vamos a medir?**
**Ejemplo**: Total Aprobados en Unidad 1/ Total alumnos del curso x 100 = %
(Ver proyección)


##### Fórmula de medición.

**¿Cómo lo vamos a medir?**
**Ejemplo**: Total Aprobados en Unidad 1/ Total alumnos del curso x 100 = %
(Ver proyección)


##### Periodicidad.
**¿Cada cuánto vamos a medir para controlar?**

Responsable del proyecto o departamento.
Actividad o proyecto al que se vincula el KRI.



![[Pasted image 20240421142551.png]]



| Nivel        | Descripción                                | Horas de Baja | % de Clientes Afectados |
|--------------|--------------------------------------------|---------------|--------------------------|
| Muy Bueno    | Bajo impacto en la operación              | Menos de 50 horas | Menos del 1% |
| Bueno        | Impacto mínimo en la operación            | 50 - 100 horas | 1% - 2.5% |
| Moderado     | Impacto perceptible en la operación       | 100 - 200 horas | 2.5% - 5% |
| Malo         | Impacto significativo en la operación     | 200 - 300 horas | 5% - 7.5% |
| Muy Malo     | Impacto grave en la operación             | Más de 300 horas | Más del 7.5% |



$$
```
\sum_{i=1}^{n} \text{Ingresos}_i
```

$$