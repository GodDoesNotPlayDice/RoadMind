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
La gestión de procesos es una forma sistémica de identificar, comprender y aumentar el valor agregado de los procesos de la empresa para cumplir con la estrategia del negocio y elevar el nivel de satisfacción de los clientes.

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

### Gestion de procesos
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

#### Consenso con el cliente
Es la etapa en que el cliente ratifica el proceso modelado, las reglas levantadas y las mejoras sugeridas.

Es necesario garantizar la ejecución de todos los caminos posibles e involucrar a los participantes de cada tarea. Con ello conseguimos el correcto progreso del proceso y la integridad de los datos.

#### Análisis de efectividad
Para evaluar la efectividad del mapeo del proceso es posible aplicar encuestas de satisfacción y utilizar indicadores, siendo ellos de eficiencia
- (medición de productividad en relación a las salidas generadas), 
- eficacia (medición de la calidad en relación a las salidas totales)
- efectividad (medición del impacto).

El seguimiento de la utilización del proceso en producción también es válido para subsanar dudas de nuevas tareas que se han atribuido a los responsables de la ejecución del flujo.


### Finalizar
Sobre todo la herramienta AS IS / TO BE debe enfocarse en la madurez del proceso de modo que al final de la etapa TO BE, el proceso esté.
- Cada vez más adherente a los objetivos estratégicos de la organización y Estructurado para simplificar y traer eficacia a los procesos y sus actividades, ya sean en el ámbito estratégico o operacional.

Para lograr estos objetivos, es fundamental la participación y el compromiso de todos los participantes y el foco diario en la mejora continua, además de la adopción de una solución eficiente de Gestión de Procesos