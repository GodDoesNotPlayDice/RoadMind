## Que es?
Consiste en una disciplina que, a través del uso de datos y algoritmos matemáticos, permiten a los computadores aprender ayudando a predecir, clasificar, ordenar, tomar decisiones y, en general, extraer conocimientos de los datos sin necesidad de definir explícitamente las reglas para realizar esas tareas.

Matemáticas + Estadísticas + Computer Science

Ejemplos de en que se puede aplicar
1) Analizar imágenes
2) Bot regulador de normas, asistente,
3) Recomendador de productos o servicios.

### Capas de la IA

**IA**: Combinación de algoritmos planteados con el propósito de crear maquinas que presenten las mismas capacidades que el humano.

**Machine Learning**: Rama de la Inteligencia artificial que estudia como dotar a las maquinas de capacidades de aprendizaje.

**Deep Learning**: Algoritmo automático jerarquicé que emula el aprendizaje humano con el fin de obtener ciertos conocimientos.

![[Pasted image 20240307150419.png]]

### Diferencia PT y ML
#### Programación Tradicional
- Es un proceso manual
- El Programador codifica las reglas
- Se usan datos de entrada, se procesan y se obtienen datos de salida
#### Machine Learning
- Los datos de entrada y salida alimentan un programa para crear un modelo
- Los algoritmos formulan automáticamente las reglas a partir de los datos
- No sustituye la programación tradicional la complementa y potencia.





## Tabla

Conjunto de registros ordenados, dispuestos normalmente en una tabla que puede estar relacionada con otras tablas, eso define el dato.
Un conjunto de datos , con un contexto darán definición a la información.

La forma de estructurar la tabla es la siguiente.

![[Pasted image 20240307153249.png]]

### <mark style="background: #FF5582A6;">ATRIBUTO, CAMPO</mark>
Columna del contexto o de la tabla.
Espacio de representación de transacciones o de una característica de las transacciones.


### <mark style="background: #BBFABBA6;">REGISTRO</mark>
Ocurrencia o instancia de los datos que representa un registro.
Secuencia de valores para un conjunto de atributos.

### <mark style="background: #ABF7F7A6;">DATO, VALOR</mark>
Celda del contexto: Valor de un atributo para una transacción determinada.


## Tipos de datos

![[Pasted image 20240307160332.png]]


### Datos categóricos
- Los datos categóricos ordinales son tipos de datos que categorizan una entidad y van ordenados, por lo que no se hace ningún tipo de operación con ellos.

| PassengerId |
| ----------- |
| 1           |
| 2           |
| 3           |
| 4           |
| 5           |
### Datos Categóricos Nominales
- Atributos categóricos sin orden en especifico

| Gender |
| ------ |
| Female |
| Male   |
| Male   |
| Female |

### Datos numéricos discretos
Cuantifican una propiedad con un dominio contable. Es importante destacar que estos números deben ser enteros. (Edad, Cantidad de hermanos, Numero de mascotas,)

| Age  |
| ---- |
| 20.0 |
| 38.0 |
| 26.0 |
| 35.0 |

### Datos numéricos continuos
Miden una propiedad con un dominio denso. Es importante destacar que estos números deben ser reales

| Terifa |
| ------ |
| 221.23 |
| 125.23 |
| 15.34  |
| 84.23  |
| 522.73 |

### Ejemplos

**Número de teléfonos en la casa:** Numérico, discreto.
**Propiedad de un celular:** Categórico, nominal.
**Número de llamadas que hiciste durante un mes:** Numérico, discreto.
**Duración de la llamada más larga:** Numérico, continuo.
**Tamaño del pie:** Numérico, continuo.
**Precio de un libro:** Numérico, discreto (aun cuando trabajemos con dos decimales).
**Código postal:** Categórico, nominal.
**Temperatura en grados Centígrados:** Numérico, continuo.



### Naturaleza del dato

**Intervalo** : No existe un “cero”, la división no tiene sentido. Se pueden hacer operaciones de igualdad, desigualdad, de orden, sumas y restas.
![[Pasted image 20240307171624.png]]


**Radio**: El cero existe, la división tiene sentido. Podemos realizar operaciones propias de los intervalos y además multiplicación y división.

![[Pasted image 20240307171706.png]]