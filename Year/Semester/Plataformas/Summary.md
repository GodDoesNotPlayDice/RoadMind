## Que son los procesos de negocio?

El Conjunto de actividades lógicamente relacionadas, es lo que conoceremos como un “proceso de negocio” y busca que los recursos de la organización entreguen resultados definidos, proporcionando información para la toma de decisiones de la empresa.

 **La organización**: puede identificar con claridad sus procesos de negocios, podrá mejorar el desempeño de los sistemas de trabajo, ya que, al ser identificables y perdurables en el tiempo se pueden realizar mejoras eliminando o modificando ciertos pasos.

Osea organizar un plan y una estructura de negocio para tener una mirada amplia y bien definida de lo que es la meta del cliente o de la empresa.

## Tipos de procesos
 Es conjunto de actividades que son realizadas en coordinación con el entorno organizacional y técnico.

**En las organizaciones existen diferentes tipos de procesos:**
- Procesos estratégicos
- Procesos operativos
- Procesos de apoyo
- Procesos de gestión

**Tip:** Lo ideal en una organización es tener dibujado un mapa de procesos, qué proceso se considera de apoyo, procesos estratégicos, etc.

### Procesos estratégicos
Son los procesos relacionados con la estrategia de la empresa y están a cargo  de como establecer la misión, visión  y objetivos corporativos.

### Procesos operativos
Son procesos que permiten generar el producto/servicio que se entrega al cliente, por lo que inciden directamente en la satisfacción del cliente final. Generalmente atraviesan muchas funciones.

### Procesos de apoyo
Son los procesos internos dentro de la empresa necesarios para que el proceso de negocio cumpla su objetivo.

**Ejemplo**: Finanzas, RRHH, etc., son llamados “procesos de apoyo”, ellos son servicios ayudan a que los procesos del negocio logren su objetivo.

### Procesos de gestión
Son los procesos de planificación y provisión de los recursos necesarios para llevar a cabo los Procesos Básicos y de Soporte de la empresa.

**Características**
1) Formalmente establecidos.
2) Coordinan las actividades de los procesos primarios y de apoyo.
3) Buscan la eficiencia y eficacia de los procesos.
4) Miden, monitorean y controlan.
5) No entregan valor al cliente directamente


## Modelo de Procesos
Es un conjunto de actividades que deben seguirse a fin de permitir la creación de uno o más modelos para la **representación, comunicación, análisis, diseño, síntesis, toma de decisiones y control de un negocio.**

Es un conjunto de actividades que se reflejan en un diagrama.

Existen distintos tipos de proceso, tales como procesos estratégicos, operativos, de gestión y procesos de apoyo.

**El proceso requiere**: 
1) Recursos
2) Información
3) Objetivos
**Un proceso entrega**:
1) Salidas **especificas**

![[Pasted image 20240306174203.png]]


**Recursos**: Es una entrada para el proceso, este recurso es consumido por el proceso mientras se ejecutan las actividades.

**Información**: El proceso utiliza la información para complementar sus actividades, la información no se consume, sino más bien se utiliza.

**Actividades**: Una actividad es parte de un proceso y está asociada a un cargo específico por sí sola no tiene objetivo, sino que es parte de.

**Objetivo**: Es la razón por la cual la organización realiza el conjunto de actividades.

![[Pasted image 20240306225932.png]]


## Capas de negocio

### ETL
Extract Transform Load, Extrae información y la carga eso hace un procedimiento almacenado.

## BPMN y BPM
BPM es una disciplina que implica cualquier combinación de modelado, automatización, ejecución, control, medición y optimización de flujos de actividad empresarial.
BPMN es una notación gráfica que plasma la lógica de las actividades, los mensajes entre los diferentes participantes y toda la información necesaria para que un proceso sea analizado simulado y ejecutado.


**Beneficios**:
- Mejora el servicio de atención al cliente.
- Mejora la competitividad de la empresa (reduce el tiempo en la toma de decisiones, mejora la eficiencia y la agilidad e incrementa la productividad).
- Mejora la calidad de los productos y servicios ofrecidos.
- Minimiza el tiempo de acceso a la información (documentación, aplicaciones y bases de datos).
- Aumenta el número de actividades ejecutadas simultáneamente.
- Disminuye el tiempo de comunicación entre actividades, personas y procesos.
- Implica al personal (motivación, colaboración y participación en los procesos).
- Agiliza la salida de datos (correos, SMS, y todo tipo de comunicación saliente).
- Aporta mecanismos para una mejor gestión y optimización de procesos.


Este estándar nos permite modelar los flujos de los procesos de negocios ya sean manuales o automatizados.

Gráficamente un diagrama BPMN esta compuesto solo por cinco elementos: Objetos de flujo, información , objetos de conexión, actores y roles, artefactos.

![[Pasted image 20240314170535.png]]


### BPD
Un BPD puede contener varios procesos, cada proceso puede ser de uno de los tres tipos: Interno, abstracto, colaborativo.
###  Modelado de Procesos
**Proceso de Negocios Interno:** que representa un único proceso de negocio interno donde se representa toda la secuencia del proceso.
**Proceso de Negocios abstracto:** representa un proceso de negocio externo del que desconocemos los detalles.
**Proceso de Negocios Colaborativo:** representa la interacción entre dos o más entidades del negocio. Las interacciones se representan por los mensajes intercambiados entre las entidades involucradas.

**Negocio interno**
![[Pasted image 20240314171159.png]]

**Negocio Externo**
![[Pasted image 20240314171214.png]]


**Negocio Colaborativo**
![[Pasted image 20240314171227.png]]

**Actividades**: es un paso dentro del proceso, representa el trabajo realizado dentro de una organización y consume recursos como tiempo  y costos. Se representan con rectángulos con esquinas redondeadas.

**Compuertas**: se utilizan para controlar los puntos de divergencia y convergencia del flujo (dediciones, actividades en paralelo y puntos de sincronización)- Se representan por rombos. Anotaciones al interior del rombo indican el tipo de comportamiento de la compuerta.

**Eventos**: representa algo que ocurre o puede ocurrir durante el proceso. Se representa por un Círculo.  Tiene una causa y un resultado. Puede iniciar un proceso, interrumpirlo, detenerlo o finalizarlo

![[Pasted image 20240314171355.png]]

**Ejemplo de modelo basico**
![[Pasted image 20240314171430.png]]


**Flujo de secuencia**
Representan el control de flujo y la secuencia de las actividades.

Se utiliza para representar la secuencia de los objetos de flujo, donde encontramos las actividades, las compuertas y los eventos.
![[Pasted image 20240314171458.png]]

**Pool**
- Un Proceso de Negocio Interno o Privado está contenido en un pool.
- El nombre del pool puede considerarse el nombre del proceso.
- Siempre existe al menos un pool.
- Los flujos de secuencia no pueden cruzar los límites de un pool.
- Líneas entre mensajes
![[Pasted image 20240314171528.png]]
