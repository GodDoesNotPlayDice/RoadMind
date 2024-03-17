## Introducción
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


### Tabla

Conjunto de registros ordenados, dispuestos normalmente en una tabla que puede estar relacionada con otras tablas, eso define el dato.
Un conjunto de datos , con un contexto darán definición a la información.

La forma de estructurar la tabla es la siguiente.

![[Pasted image 20240307153249.png]]

#### <mark style="background: #FF5582A6;">ATRIBUTO, CAMPO</mark>
Columna del contexto o de la tabla.
Espacio de representación de transacciones o de una característica de las transacciones.


#### <mark style="background: #BBFABBA6;">REGISTRO</mark>
Ocurrencia o instancia de los datos que representa un registro.
Secuencia de valores para un conjunto de atributos.

#### <mark style="background: #ABF7F7A6;">DATO, VALOR</mark>
Celda del contexto: Valor de un atributo para una transacción determinada.


### Tipos de datos

![[Pasted image 20240307160332.png]]


#### Datos categóricos
- Los datos categóricos ordinales son tipos de datos que categorizan una entidad y van ordenados, por lo que no se hace ningún tipo de operación con ellos.

| PassengerId |
| ----------- |
| 1           |
| 2           |
| 3           |
| 4           |
| 5           |
#### Datos Categóricos Nominales
- Atributos categóricos sin orden en especifico

| Gender |
| ------ |
| Female |
| Male   |
| Male   |
| Female |

#### Datos numéricos discretos
Cuantifican una propiedad con un dominio contable. Es importante destacar que estos números deben ser enteros. (Edad, Cantidad de hermanos, Numero de mascotas,)

| Age  |
| ---- |
| 20.0 |
| 38.0 |
| 26.0 |
| 35.0 |

#### Datos numéricos continuos
Miden una propiedad con un dominio denso. Es importante destacar que estos números deben ser reales

| Terifa |
| ------ |
| 221.23 |
| 125.23 |
| 15.34  |
| 84.23  |
| 522.73 |

#### Ejemplos

**Número de teléfonos en la casa:** Numérico, discreto.
**Propiedad de un celular:** Categórico, nominal.
**Número de llamadas que hiciste durante un mes:** Numérico, discreto.
**Duración de la llamada más larga:** Numérico, continuo.
**Tamaño del pie:** Numérico, continuo.
**Precio de un libro:** Numérico, discreto (aun cuando trabajemos con dos decimales).
**Código postal:** Categórico, nominal.
**Temperatura en grados Centígrados:** Numérico, continuo.



#### Naturaleza del dato

**Intervalo** : No existe un “cero”, la división no tiene sentido. Se pueden hacer operaciones de igualdad, desigualdad, de orden, sumas y restas.
![[Pasted image 20240307171624.png]]


**Radio**: El cero existe, la división tiene sentido. Podemos realizar operaciones propias de los intervalos y además multiplicación y división.

![[Pasted image 20240307171706.png]]

## Estadística I

La estadística se emplea para comprender la estructura y las relaciones presentes en los datos, así como para evaluar la validez y el rendimiento de los modelos de aprendizaje automático.

### Pasos de los usos de la estadística

**Formular el problema**: Formular el problema no siempre es obvio. Se requiere una exploración de las observaciones.
Los métodos estadísticos ayudan a resumir los datos y visualizarlos en forma apropiada, con el fin de descubrir relaciones entre ellos, o identificar anomalías..

**Datos**: Entender la distribución de variables y sus relaciones. Limpiar datos corruptos, erróneos o faltantes. Seleccionarlos en forma adecuada para los modelos. Transformar los datos para un entrenamiento adecuado de los modelos. Todas estas son tareas apoyadas por estadística

**Modelar**: Las pruebas de hipótesis estadística y los estadísticos de estimación pueden ayudar en la discriminación y selección de modelos entrenados, permitiendo traducir y justificar sus habilidades y capacidades predictivas.

### Ordenar los datos 
Ordenar los datos con el objetivo de analizarlos, entenderlos y/o presentarlos
La organización puede ser ascendente o descendente. Esto ofrece varias ventajas
1) Se pueden identificar valores extremos (menor y mayor) rápidamente.
2) Es fácil dividir los datos en secciones.
3) Podemos ver si algunos valores aparecen más de una vez en el arreglo.
4) Podemos observar la distancia entre valores sucesivos de los datos.
Necesitamos, entonces, buscar una forma de comprimir la información sin que pierda su utilidad para la interpretación, ya que si llegamos a tener muchos datos estos se vuelven pesados de procesar.


### Tabla de Frecuencia 
Una manera de compactar los datos es **mediante una tabla de frecuencia o distribución de frecuencias**, donde podemos contabilizar las ocurrencias de un determinado intervalo o clase.

Podemos, también, clasificar la información de acuerdo con características cualitativas, como raza, religión y sexo, que no entran de manera natural en categorías numéricas.

### Estadísticos básicos

**Tendencia Central**: Son aquellas medidas que nos ayudan a saber DONDE están los datos, pero sin indicar como se distribuyen. También podemos decir que se refieren al punto medio de una distribución.

**Posición no central:** Estas medidas, se refieren a aquellos valores que, ordenados de menor a mayor, dividen a la distribución en partes, de tal manera que cada una de ellas contiene el mismo número de frecuencias.

**Dispersión**: Las medidas de dispersión tratan de medir el grado de dispersión (o separación) que tiene una variable estadística en torno a una medida de posición o tendencia central, indicándonos lo representativa que es la medida de posición

### Tendencia central

**MEDIA ARITMÉTICA:**  La media aritmética o simplemente media, es el número obtenido al dividir la suma de todos los valores de la variable entre el número total de observaciones.
![[Pasted image 20240312172213.png]]

**Ventajas**: 
- Intuitivamente claro.
- Cada conjunto de datos posee una y sólo una media.
- Es útil para comparar medias de varios conjuntos de datos.
**Desventaja**: 
- Puede verse afectada por valores extremos que no son representativos (outliers).
- No sirve si los datos están agrupados en intervalos y los extremos de estos están “abiertos”.


**MEDIANA:**  La mediana es el o los valores (pueden ser dos) del conjunto de datos que miden la observación central del conjunto. Esta observación es el elemento que está más al centro del conjunto de datos. La mitad de los elementos están por arriba de este punto y la otra mitad está por debajo.
![[Pasted image 20240312202824.png]]


**Ventajas**: 
- Se puede ocupar para datos cuantitativos como cualitativos.
- Incluso en datos agrupados con extremos abiertos.
- No le afectan los valores extremos.
**Desventaja**: 
- Requiere ordenar los datos.


**Moda**:  La moda es una medida de tendencia central diferente de la media, pero un tanto parecido a la mediana, pues en realidad no se calcula mediante algún proceso aritmético ordinario. La moda es el valor que más se repite en el conjunto de datos.
![[Pasted image 20240312211719.png]]


**Ventajas**: 
- Se puede ocupar para datos cuantitativos y cualitativos.
- Sirve para datos agrupados con extremos abiertos.
- No le afectan los valores extremos.
**Desventaja**: 
- Muchas veces es inútil, pues no hay valores que la representen o cada valor es la moda.
- Cuando hay varias modas, es difícil interpretarla.


**Comparación**: :  En distribuciones simétricas de datos, la moda, la mediana y la media tienen el mismo valor. Cuando la población de datos está sesgada negativa o positivamente, la mediana suele ser la mejor medida de posición, debido a que siempre está entre la moda y la media. Pero, elegir la medida adecuada, dependerá de cada caso que se esté analizando.

![[Pasted image 20240314145151.png]]



**CUANTILES:**  Los cuantiles son aquellos valores de la variable que, ordenados de menor a mayor, dividen la distribución en partes. De tal manera, que cada una de ellas contiene el mismo número de frecuencias.

**CUARTILES:** son valores de la variable que dividen a la distribución en cuatro partes, cada una de las cuales engloba el 25% de las mismas.

**DECILES:** son los valores de la variable que dividen a la distribución en diez partes iguales, cada una de ellas engloba el 10% de los datos.

**CENTILES O PERCENTILES:** son los valores que dividen a la distribución en cien partes iguales, cada una de las cuales engloba el 1% de las observaciones.

![[Pasted image 20240314145230.png]]

**RANGO INTERCUARTIL:** 

El rango intercuartílico mide aproximadamente qué tan lejos de la mediana debemos ir en cualquiera de las dos direcciones antes de recorrer una mitad de los valores del conjunto de datos. Para calcular este rango, se calcula la diferencia entre los valores del primer y tercer cuartil

![[Pasted image 20240316215202.png]]