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


**Comparación**:   En distribuciones simétricas de datos, la moda, la mediana y la media tienen el mismo valor. Cuando la población de datos está sesgada negativa o positivamente, la mediana suele ser la mejor medida de posición, debido a que siempre está entre la moda y la media. Pero, elegir la medida adecuada, dependerá de cada caso que se esté analizando.

![[Pasted image 20240314145151.png]]



**CUANTILES:**  Los cuantiles son aquellos valores de la variable que, ordenados de menor a mayor, dividen la distribución en partes. De tal manera, que cada una de ellas contiene el mismo número de frecuencias.

**CUARTILES:** son valores de la variable que dividen a la distribución en cuatro partes, cada una de las cuales engloba el 25% de las mismas.

**DECILES:** son los valores de la variable que dividen a la distribución en diez partes iguales, cada una de ellas engloba el 10% de los datos.

**CENTILES O PERCENTILES:** son los valores que dividen a la distribución en cien partes iguales, cada una de las cuales engloba el 1% de las observaciones.

![[Pasted image 20240314145230.png]]

**RANGO INTERCUARTIL:** 

El rango intercuartílico mide aproximadamente qué tan lejos de la mediana debemos ir en cualquiera de las dos direcciones antes de recorrer una mitad de los valores del conjunto de datos. Para calcular este rango, se calcula la diferencia entre los valores del primer y tercer cuartil

![[Pasted image 20240316215202.png]]

## Análisis de varianza
**Machine Learning** es poder seleccionar los datos adecuados (conocidos como “características”) que permitan entrenar adecuadamente un modelo, con el fin de predecir correctamente los resultados.

Sólo se requiere identificar los datos (características) que influyen en gran medida en la variable a predecir. Pero ¿qué ocurre si dicha variable es continua (números decimales) y nuestros datos (características predictoras) son categóricos?

1) Determinar una estimación de la varianza de la población a partir de la varianza entre las medias de las muestras.
2) Determinar una segunda estimación de la varianza de la población a partir de la varianza dentro de las muestras.
3) Comparar estas estimaciones. Si su valor es aproximadamente igual, se acepta la hipótesis nula.

![[Pasted image 20240409193651.png]]

### Pasos entre medidas

1) El paso 1 en el Análisis de la Varianza, indica que debemos obtener una estimación de la varianza de la población a partir de la varianza entre las medias de las muestras.
2) El paso 2 requiere una segunda estimación de la varianza de la población, basada en la varianza dentro de las muestras.
3) En el paso 3 de ANOVA se comparan estas dos estimaciones de la varianza de la población mediante el cálculo de su cociente.

### Grados de libertad
Dependiendo del tamaño de las muestras, las distribuciones son diferentes. Esto se denomina grados de libertad, que podría definirse como el número de valores que podemos escoger libremente.


### Prueba de Hipótesis

Para llevar a cabo pruebas de hipótesis F debemos utilizar una tabla F, en la cual las columnas representan el número de grados de libertad del numerador y las filas el número de grados de libertad del denominador.


### Calculo de distancias
Muchos algoritmos de Machine Learning requieren calcular distancias entre los puntos observados. Hay diferentes métricas de distancias.

Es una medida de la distancia  en línea recta entre dos puntos en el espacio euclidiano.

#### Eucliniana
Es una medida de la distancia  en línea recta entre dos puntos en el espacio euclidiano.
1) Por dos puntos pasa una sola recta.
2) Tres puntos sobre el plano forman un triángulo cuyos ángulos internos siempre suman 180º
3) En un triángulo rectángulo el cuadrado de la hipotenusa es igual a la suma de los cuadrados de sus catetos.

#### Manhatan
La única diferencia es que la anterior es mas corta porque funciona de manera oblicua para llegar y este va por cateto y adyacente.
![[Pasted image 20240410093854.png]]

#### Conseno
Esta métrica de distancia se utiliza principalmente para calcular la similitud entre dos vectores.
Se mide por el coseno del ángulo entre dos vectores y determina si dos vectores apuntan en la misma dirección. 

![[Pasted image 20240410094019.png]]

## Estadística II

### Dispersión
Son aquellas que manejan la desviación promedio respecto a alguna medida de tendencia central. Dos de estas medidas son importantes: **la varianza** y la **desviación estándar.**

1) Nos proporciona información adicional que nos permite juzgar la confiabilidad de nuestra medida de tendencia central
	1) **Ejemplo**: Si los datos se encuentran muy dispersos, como los que representa la curva C de la figura, la posición central es menos representativa de los datos en cambio A es mas representativa.
2) Existen problemas característicos para datos muy dispersos
3) Necesitamos poder reconocerla y evitar elegir distribuciones que tengan las dispersiones más grandes, Si no se desea tener una amplia dispersión

**Mientras mas alta la campana menos variabilidad tienen los datos.**
![[Pasted image 20240317133744.png]]

### Varianza
Es el promedio de los cuadrados de las distancias de las observaciones a la media
![[Pasted image 20240317134452.png]]![[Pasted image 20240317134500.png]]

### Desviacion Estandar
Estándar es la raíz cuadrada del promedio de los cuadrados de las distancias entre las observaciones y la media.

Podemos medir aún con más precisión el porcentaje de observaciones que caen dentro de un rango específico de una curva simétrica con forma de campana.


![[Pasted image 20240317134622.png]]![[Pasted image 20240317134626.png]]

## Estadística III
**El planteamiento clásico define la probabilidad de que un evento ocurra**
![[Pasted image 20240319141142.png]]

**Ejemplo**: Rifa de 1 a 50 personas la probabilidad seria de 1/50 = 0.02 (0,2%) de ganar

### Probabilidad de uno o más eventos mutuamente excluyentes
Si dos eventos son mutuamente excluyentes, podemos expresar la probabilidad que uno u otro ocurra **(la probabilidad de que ocurra al menos uno)**

**Probabilidad**

$$
P(A o B) = p(A) + P(B) 
$$

**Ejemplo**: Supongamos que cinco personas postulan a un trabajo y la empresa sólo podrá contratar a uno de ellos. ¿Cuál sería la probabilidad que uno de ellos llamado John u otro de los restantes, llamado Sally, sea elegido?
 $$
 P(Jhon \quad o \quad Sally) = P(Jhon) + P(Sally)
 $$
 $$
\frac{1}{5} + \frac{1}{5}
= \frac{2}{5} = 0.4
$$
### Probabilidad de uno o más eventos no mutuamente excluyentes
Si dos eventos no son mutuamente excluyentes, es posible que ambos se presenten al mismo tiempo **(pueden ocurrir simultáneamente.)**

 $$
 P(A \quad o \quad B) = P(A) + P(B) - P(AB)
 $$
**Ejemplo**: ¿cuál es la probabilidad de sacar un as o un corazón de un mazo de barajas? Obviamente, los eventos as y corazón pueden presentarse juntos, pues podríamos sacar una as de corazones. En consecuencia, as y corazón no son eventos mutuamente excluyentes.

La probabilidad de obtener un as o un corazón la podemos calcular como:
 $$
P(\text{as o corazón}) = P(\text{as}) + P(\text{corazón}) - P(\text{as y corazón}) \\ 
= \frac{4}{52} + \frac{13}{52} - \frac{1}{52} \\
= \frac{16}{52} \quad \frac{4}{13}
$$

### Probabilidad bajo condiciones de independencia estadística
Cuando se presentan dos eventos, el resultado del primero puede, o no, tener un efecto en el resultado del segundo. Esto es, los eventos pueden ser dependientes o independientes

![[Pasted image 20240319143629.png]]

Los eventos que son estadísticamente independientes son aquellos en donde la presentación de uno no tiene efecto sobre la probabilidad de presentación de cualquier otro.

**Probabilidad condicional para eventos estadísticamente independientes.**
$$
P(\text{B|A}) = P(\text{B})
$$
**Ejemplo**: : ¿Cuál es la probabilidad de que en el segundo lanzamiento de una moneda se obtenga cara, dado que el resultado del primero fue cara?

Simbólicamente, lo anterior se escribe como P(H1 |H2). Recordemos que para dos eventos independientes el resultado del primer lanzamiento no tiene absolutamente ningún efecto sobre el resultado del segundo. Como la probabilidad de obtener cara y la de obtener sello son exactamente iguales en cada lanzamiento, la probabilidad de obtener cara en el segundo lanzamiento es de 0.5. Por tanto, debemos decir que 

$$ P(H1|H2) = 0.5 $$
#### Tipos de Probabilidad por Independencia
1. Marginal (ya vista).
2. Conjunta (no la veremos en este curso).
3. Condicional


### Probabilidad bajo condiciones de dependencia estadística
La dependencia estadística existe cuando la probabilidad de que se presente algún evento depende o se ve afectada por la presentación de algún otro

La probabilidad condicional para eventos dependientes **estadísticamente**
$$
P(B|A) = \frac{P(BA)}{P(A)}
$$

![[Pasted image 20240319145810.png]]
#### Tipos de Probabilidad por Dependencia
1. Marginal (no la veremos en este curso).
2. Conjunta (no la veremos en este curso).
3. Condicional

**Ejemplo**:
Supongamos que tenemos una caja que contiene 10 bolas distribuidas de la siguiente manera

- Tres son de color y tienen puntos
- Una es de color y tiene franjas
- Dos son grises y tienen puntos
- Cuatro son grises y tienen franjas

La probabilidad de sacar cualquiera de las bolas es de **0.1, ya que existen 10 bolas** con igual probabilidad de ser elegidas.

Suponga que una persona saca de la caja una bola de color, ¿cuál es la probabilidad de que ésta tenga puntos? ¿Cuál es la probabilidad de que tenga franjas?

Podemos expresarla asi: **D : bola con puntos y C : Su color**
$$
P(D|C)
$$
Se nos ha dicho que la bola que se sacó es de color. Por tanto, para calcular la probabilidad de que tenga puntos, ignoraremos a todas las bolas grises y nos concentraremos exclusivamente en las de color

A partir del planteamiento del problema, sabemos que hay cuatro bolas de color  (C), tres de las cuales tienen puntos (D) y la que queda tiene franjas (S).

Ahora, nuestro problema consiste en encontrar las probabilidades sencillas de que la bola tenga puntos y de que tenga franjas. Para hacerlo dividimos el número de bolas de cada categoría entre el número total de bolas de color.
$$
P(D|C) = \frac{3}{4} = 0.75 \quad
P(S|C) = \frac{1}{4} = 0.25
=
1.00
$$
La probabilidad de sacar una bola con puntos, dado que ésta es de color, es de 0.75. De forma parecida, la probabilidad de obtener una bola con franjas, dado que ésta es de color, es de 0.25.

**Como el color afecta la probabilidad de que la bola tenga puntos o franjas, estos eventos son dependientes.**

Para calcular la probabilidad de obtener una bola con puntos dado que es de color, P(D|C), dividimos la probabilidad de que la bola sea de color y tenga puntos (tres de 10, es decir 0.3) entre la probabilidad de que la bola sea de color (cuatro de 10, es decir, 0.4):
$$
P(D|C) = \frac{P(DC)}{P(C)}
$$
### Teorema de Bayes
La fórmula básica para la probabilidad condicional en circunstancias de dependencia se conoce como Teorema de Bayes

Siempre que haya un problema de probabilidad condicional, se utiliza el Teorema de Bayes en Machine Learning

La conclusión directa de este proceso es que cuantos más datos tenga, más preciso será el resultado
$$
P(B|A) = \frac{P(BA)}{P(A)}
$$
![[Pasted image 20240319155633.png]]


## Distribución y Probabilidades 

### Tipos de distribución
Las distribuciones de probabilidad se clasifican como discretas y continuas. 

**Discreta**: En la distribución de probabilidad discreta está permitido considerar sólo un número limitado de valores. 

**Continua**: En una distribución de probabilidad continua, por otro lado, la variable que se está considerando puede tomar cualquier valor dentro de un intervalo dado.

**Variable aleatoria**: Una variable es aleatoria si toma diferentes valores como resultado de un experimento aleatorio.

Si puede tomar sólo un número limitado de valores, entonces es una variable aleatoria discreta. En el otro extremo, si puede tomar cualquier valor dentro de un intervalo dado, entonces se trata de una variable aleatoria continua. 


### Valor esperado
El valor esperado de una variable aleatoria es, sencillamente, el promedio ponderado de cada resultado posible, multiplicado por la probabilidad de que ocurra ese resultado.

Para obtener el valor esperado de una variable aleatoria discreta, multiplicamos cada valor que la variable puede tomar por la probabilidad de ocurrencia de ese valor y luego sumamos los productos.

### Distribución Binominal
Este tipo de distribución describe datos discretos, no continuos.

Una distribución de probabilidad de variable aleatoria discreta utilizada ampliamente es la distribución binomial.


**Por ejemplo**, el lanzamiento de la moneda no alterada un número fijo de veces es un **proceso** de Bernoulli, y los resultados de tales lanzamientos pueden representarse mediante la distribución binomial de probabilidad.

#### Proceso
 1. Cada intento (cada lanzamiento, en este caso) tiene solamente dos resultados posibles: cara o sello, sí o no, éxito o fracaso. 

2. La probabilidad del resultado de cualquier intento (lanzamiento) permanece fijo con respecto al tiempo. Con una moneda no alterada, la probabilidad de obtener cara siempre es 0.5 para cada lanzamiento, independientemente del número de veces que se lance la moneda.

3. Los intentos son estadísticamente independientes, es decir, el resultado de un lanzamiento no afecta el resultado de cualquier otro lanzamiento.


### Distribución de Poisson
 La distribución de Poisson se utiliza para describir ciertos tipos de procesos, **distribución de llamadas telefónicas, las solicitudes de pacientes que requieren servicio en una institución de salud,  las llegadas de camiones y automóviles**

Pueden ser descritos mediante una variable aleatoria discreta que toma valores enteros

### Distribucion Normal
Hay casos en que la variable puede tomar cualquier valor que esté en un intervalo de valores dado, y en los cuales la distribución de probabilidad es continua.

Una distribución de probabilidad continua que es muy importante es la distribución normal.

La distribución normal casi se ajusta a las distribuciones de frecuencias reales observadas en muchos fenómenos, incluyendo características humanas (peso, altura, coeficiente intelectual), resultados de procesos físicos (dimensiones y rendimientos), y muchas otras medidas de interés.



## Regresión Lineal y Correlación
La regresión es utilizada en todo tipo de industrias alrededor del mundo, es útil para predecir el valor de una propiedad inmobiliaria tal y como es útil para predecir el valor de un boleto de avión, las aplicaciones son infinitas. Casualmente también es la forma más sencilla y recomendada de entrar al mundo del Machine Learning, por este motivo es importante tener un entendimiento de la misma.
### Regresión Simple
Los análisis de regresión y de correlación se basan en la relación, o asociación, entre dos (o más) variables.

La variable (o variables) conocida(s) se llaman variable(s) independiente(s); la que tratamos de predecir es la variable dependiente.

![[Pasted image 20240323122526.png]]

### Diagramas de dispersión
El primer paso para determinar si existe una relación entre dos variables es examinar la gráfica de los datos observados (o conocidos). Esta gráfica, o dibujo, se llama diagrama de dispersión.

Un diagrama de dispersión nos puede dar dos tipos de información. Visualmente, podemos identificar patrones que indiquen que las variables están relacionadas. Si esto sucede, podemos ver qué tipo de línea, o ecuación de estimación, describe esta relación.
![[Pasted image 20240323122646.png]]La relación entre las variables X y Y también puede tomar la forma de una curva. Los especialistas en estadística la llaman relación curvilínea.

![[Pasted image 20240323122738.png]]


### Estimación

#### Recta de Regresión
Las líneas de regresión no sólo deben ajustarse visualmente. En realidad, para calcularla en forma precisa, debemos aplicar la siguiente ecuación, la cual indica con una Y la variable dependiente y con una X la variable independiente

![[Pasted image 20240323122902.png]]
La “a” se denomina la “ordenada Y” porque su valor es el punto en el cual la línea de regresión cruza el eje Y, es decir, el eje vertical.

La “b” en la ecuación es la “pendiente” de la recta. Representan qué tanto cada cambio de una unidad de la variable independiente X hace que cambie la variable dependiente Y.

Tanto “a” como “b” son constantes numéricas porque para cualquier línea recta dada, sus valores no cambian.

Supongamos que sabemos que “a” es 3 y “b” es 2. Determinemos cuál sería Y para X igual a 5.

$$
Y = a + bX \\
= 3 + 2(5) \\
= 3 + 10 \\
= 13 X
$$
La  constante “a” se puede encontrar visualmente, localizando el punto donde cruza el eje Y.

Para encontrar la pendiente de la recta, b, debemos determinar cómo cambia la variable dependiente, Y, al cambiar la variable independiente, X.
$$
b = \frac{Y_2 - Y_1}{X_2 - X_1}
$$

![[Pasted image 20240323125609.png]]


### Mínimos Cuadrados
**MÉTODO**:  Si los puntos de datos no están “sobre la línea”, ¿es posible ajustar la “mejor” recta?. Para responder esto, podemos usar el mínimo error entre los puntos estimados de la recta y los puntos reales observados que se utilizaron para trazarla.
**Linea de estimación**
$$
\hat{Y} = a + bX
$$

El símbolo Yˆ (ye gorro) se usará para simbolizar los valores individuales de los puntos estimados, esto es, aquellos puntos que están en la línea de estimación.

En los siguientes gráficos tenemos los mismos tres puntos y dos rectas diferentes. ¿Cuál será la mejor estimación.
![[Pasted image 20240323130356.png]]


De esto, podríamos deducir que el criterio adecuado para juzgar la bondad del ajuste sería sumar los valores absolutos (los valores sin los signos algebraicos) de cada error. Con esto confirmamos que la estimación “a” es la mejor (el error es menor).

![[Pasted image 20240323130505.png]]

Sin embargo, el análisis anterior es incompleto, pues la suma de los valores absolutos no hace hincapié en la magnitud del error. Mira la nueva gráfica.

![[Pasted image 20240323130556.png]]

Preferiríamos tener varios errores absolutos pequeños que uno grande, como vimos en el ejemplo anterior. En efecto, deseamos encontrar una forma de “penalizar” errores absolutos grandes, para poder evitarlos.

Podemos lograr esto podemos elevar al cuadrado los errores individuales antes de sumarlos. Los cuadrados de cada término logran dos objetivos:
1) Magnifica, o penaliza, los errores más grandes.
2) Cancela el efecto de los valores positivos y negativos (un error negativo al cuadrado sigue siendo positivo).
![[Pasted image 20240323130757.png]]


### Análisis de Correlación
El análisis de correlación es la herramienta estadística que podemos usar para describir el grado en el que una variable está linealmente relacionada con otra.

Con frecuencia, el análisis de correlación se utiliza junto con el de regresión para medir qué tan bien la línea de regresión explica los cambios de la variable dependiente, Y.

Sin embargo, la correlación también se puede usar sola para medir el grado de asociación entre dos variables.

#### Coeficiente de determinación
El coeficiente de determinación es la principal forma en que podemos medir el grado, o fuerza, de la asociación que existe entre dos variables, X e Y.

El coeficiente de determinación muestral se deriva de la relación entre dos tipos de variación, la variación de los valores Y en un conjunto de datos alrededor de:
1) La recta de regresión ajustada;
2) Su propia media.
$$
r^2 = 1 - \frac{\sum(Y - \hat{Y})^2}{\sum(Y - \bar{Y})^2}
$$
Consideremos este ejemplo, donde a partir de la tabla de datos, podemos realizar el gráfico de una correlación perfecta:
$$
\hat{Y} = 4X
$$
![[Pasted image 20240323131339.png]]
El coeficiente de determinación, se calcularía de la siguiente forma

![[Pasted image 20240323131511.png]]

#### Correlación
El coeficiente de correlación es la segunda medida que podemos usar para describir qué tan bien explica una variable a otra.

Cuando tratamos con muestras, el coeficiente de correlación de la muestra se denota por “r” y es la raíz cuadrada del coeficiente de determinación muestral.
$$
r = \sqrt{r^2}
$$









## Ecuaciones Lineales y Matrices
Una sistema de ecuaciones lineales es un conjunto finito de ecuaciones lineales, cada una con las mismas variables.

## Google Collab (Meanings)

### Librerías
- **Matplot:** Es la librería más popular en Python para visualizaciones y gráficos. Ella nos va a permitir realizar los gráficos de las distintas distribuciones de datos.
- **Seaborn**: Esta librería es un complemento ideal de matplotlib para realizar gráficos estadísticos.

### Pandas

```python
import pandas as pd

df = pd.read_csv(name, sep=",") # Separa por comas el archivo como un array. df de data frame

df.head() # se utiliza para mostrar las primeras filas del DataFrame. Por defecto, muestra las primeras 5 filas, pero también puedes especificar un número diferente de filas para mostrar. Esto es útil para tener una vista previa rápida de los datos en el DataFrame sin necesidad de mostrar todo el conjunto de datos.

describe() # La función `describe()` proporciona estadísticas descriptivas que resumen la tendencia central, dispersión y forma de la distribución de un conjunto de datos, excluyendo los valores NaN (valores perdidos).


```


## Machine Learning Introducción

### Tarea
El aprendizaje automático nos permite abordar tareas que son demasiado difíciles de resolver con programas fijos escritos y diseñados por seres humanos.

Las tareas de aprendizaje automático generalmente son descrito en términos de cómo el sistema de aprendizaje automático debe procesar un ejemplo. 

**Un ejemplo**: es una colección de características que se han medido cuantitativamente a partir de algún objeto o evento que queremos que procese el sistema de aprendizaje automático. 

Varias clases de tareas pueden ser resueltas por el aprendizaje automático. Algunas de las más comunes son: **Clasificación, Regresión, Traducción de idiomas, Detección de anomalías, entre otras.**


### Media
Para evaluar las capacidades de un algoritmo de aprendizaje automático, debemos **diseñar una medida cuantitativa de su rendimiento.** 

Para tareas como la clasificación, a menudo medimos la **precisión del modelo**.
La precisión es solo la proporción de ejemplos para los cuales el modelo produce el resultado correcto. 

También podemos obtener información equivalente midiendo la **tasa de error**, la proporción de ejemplos para los que el modelo produce una salida incorrecta.

La elección de la medida de rendimiento puede parecer sencilla y objetiva, pero a menudo es difícil elegir una medida de rendimiento que se corresponda adecuadamente con el **comportamiento deseado de el sistema.**

### Experiencia
Los algoritmos de aprendizaje automático se pueden clasificar en términos generales como **no supervisados o supervisados** según el tipo de experiencia que se les permite tener durante el proceso de aprendizaje. 

La mayoría de los algoritmos de aprendizaje se pueden entender según como experimenten sobre **un conjunto de datos.**
- Un conjunto de datos es una **colección de muchos ejemplos**.


### Tipos de aprendizaje automático
**Entrenamiento bajo o no de supervision humana.**
- Aprendizaje Supervisado
- Aprendizaje no Supervisado
- Aprendizaje Semi supervisado
- Aprendizaje por refuerzo

**Pueden aprender de forma gradual sobre la marcha**
Tenemos Aprendizaje On Line frente a Aprendizaje por Lotes.

**Si funcionan comparando datos nuevos con datos conocidos o si detectan patrones crean modelos predictivos**
Tenemos Aprendizaje basado en instancias frente a aprendizaje basado en modelos.

### Tipos
Los criterios anteriores no son exclusivos, pueden combinarse de diferentes formas. 
**Aprendizaje supervisado** y en detalle, veremos métodos de **clasificación y métodos de regresión.**
#### Aprendizaje con o sin supervisión
Los sistemas de Machine Learning pueden calificarse según la cantidad y el tipo de supervisión que tengan durante el entrenamiento.

##### Categorías
- **Aprendizaje supervisado:** En el Aprendizaje Supervisado, el conjunto de datos de entrenamiento que introducimos en el algoritmo  incluye las soluciones deseadas. A esto se le denomina etiquetas (o target).
	- Una tarea típica del aprendizaje supervisado es la clasificación. El filtro de spam es un buen ejemplo de esto.
	- Otra tarea típica es predecir un valor numérico “objetivo”
		- Como el precio de una casa, según algún conjunto de características (barrio, tipo de construcción, cercanía a colegios, etc.) denominados predictores. Este tipo de tareas se llama regresión.
- **Aprendizaje no supervisado:** En el Aprendizaje NO Supervisado, los datos de entrenamiento no están etiquetados.
	- Por ejemplo, los compradores de una tienda, para los cuales queremos generar grupos por alguna característica similar. En este caso, no indicamos al algoritmo a que grupo pertenece el comprador, pues él encuentra las conexiones sin ayuda.
	- **Algoritmos importantes de esta Area**:
		- Agrupamiento
		- Detección de anomalías y detección de novedades
		- Visualización y reducción de dimensionalidad
		- Reglas de asociación
- **Aprendizaje semi supervisado:** Puesto que etiquetar datos suele llevar mucho tiempo y supone un gasto importante, a menudo existirán un montón de instancias sin etiquetar y unas pocas etiquetadas, algunos algoritmos pueden ocuparse de datos que están etiquetados en parte.
	- Un ejemplo de esto son los servicios de alojamiento de fotos, como Google Fotos. Donde en algunas fotos se reconoce a una misma persona y en otras fotos no se reconoce. Pero si nosotros etiquetamos a esa persona en una fotografía, el algoritmo podrá hacerlo en las otras.
	- La mayoría de los algoritmos de aprendizaje semi supervisado son combinaciones de algoritmos no supervisados y supervisados.
- **Aprendizaje por refuerzo:** El Aprendizaje por refuerzo es algo totalmente diferente, el sistema de aprendizaje, que en este contexto se denomina agente, puede observar el entorno, seleccionar y realizar acciones y recibir recompensas a cambio (o castigos en forma de recompensas negativas)
	- Debe aprender por sí mismo cual es la mejor estrategia, denominada política, para obtener la mayor recompensa con el tiempo. Una política define que acción debería elegir el agente cuando se encuentra en una situación determinada.
	- Un ejemplo de aprendizaje por refuerzo, son los robots que aprenden a caminar o aquellos que juegan ajedrez o Go



## Librerías (Python)

### Pandas
Pandas se deriva del término Panel Data, un término econométrico para conjuntos de datos que incluyen observaciones en múltiples períodos de tiempo para los mismos individuos

Esta librería se desarrolló debido a la necesidad de tener una herramienta flexible de alto rendimiento para el análisis de datos.

Usando esta librería podemos lograr cinco pasos típicos en el procesamiento y análisis de datos, independientemente del origen de los datos: cargar, preparar, manipular, modelar y analizar.

#### DataFrame
El  DataFrame que es la estructura fundamental de Pandas, estos son estructuras de datos etiquetados bidimensionales con columnas de tipos potencialmente diferentes. 

Los Pandas DataFrame constan de tres componentes principales: los datos, el índice y las columnas.

Estos componentes son muy útiles cuando se requiera manipular los datos.

#### Características
- Objeto DataFrame rápido y eficiente con indexación predeterminada y personalizada.
- Herramientas para cargar datos en objetos de datos en memoria desde diferentes formatos de archivo.
- Alineación de datos y manejo integrado de datos faltantes.
- Remodelación y giro de conjuntos de fechas.
- Etiquetado, corte, indexación y subconjunto de grandes conjuntos de datos.
- Las columnas de una estructura de datos se pueden eliminar o insertar.
- Agrupa por datos para agregación y transformaciones.
- Alto rendimiento de fusión y unión de datos.
- Funcionalidad de la serie de tiempo.

#### Estructuras de datos
Los dos componentes principales de Pandas son l**a Serie y el DataFrame.**

Las Series de Pandas, estas son una **estructura de datos unidimensional** que puede almacenar valores y para cada valor también tiene un índice único.

Por su parte, los DataFrames de Pandas son **estructuras de datos de dos o más dimensiones**, básicamente una tabla con filas y columnas. Las columnas tienen nombres y las filas tienen índices.


### Numpy
es el nombre es un acrónimo de Python Numérico. Es una librería que consiste en objetos de matrices multidimensionales y una colección de rutinas para procesar esas matrices.

Es un módulo de extensión para Python, escrito en su mayor parte en C, esto asegura que las funciones y funcionalidades matemáticas y numéricas precompiladas de NumPy **garantizan una gran velocidad de ejecución**

NumPy **es un paquete de procesamiento de matrices de uso general**, proporciona un objeto de matriz multidimensional de alto rendimiento, y herramientas para trabajar con estas matrices.

**NumPy** se basa en dos módulos anteriores de Python que trataban matrices: Numeric y Numarray.
**NumPy** es una fusión de esos dos, se basa en el código de Numeric y las características de Numarray.

Los array o matrices de NumPy son un poco como las listas de Python, pero al mismo tiempo muy diferentes. 

El array de NumPy es un poderoso objeto de matriz n-dimensional que tiene forma de filas y columnas. Podemos iniciar las matrices NumPy desde listas de Python anidadas y acceder a sus elementos.

#### Características
- NumPy es una librería numérica de Python de código abierto.
- NumPy contiene una matriz multidimensional y estructuras de datos matriciales.
- Se puede utilizar para realizar una serie de operaciones matemáticas en matrices como rutinas trigonométricas, estadísticas y algebraicas. Por lo tanto, la librería contiene un gran número de funciones matemáticas, algebraicas y de transformación.
- NumPy también contiene generadores de números aleatorios.
- Los objetos de Pandas (otra librería de Python) dependen en gran medida de los objetos de NumPy. Esencialmente, Pandas extiende NumPy

### MatPlot
**Matplotlib** es una librería de trazado utilizada para gráficos 2D en lenguaje de programación Python, muy flexible y tiene muchos valores predeterminados incorporados. 

Produce figuras de calidad de publicación en una variedad de formatos impresos y entornos interactivos. .

Los datos a usar en gráficos de matplotlib deberán estar estructurados bajo la librería de NumPy.

Con NumPy podrás realizar operaciones sobre ellos, inspeccionar sus matrices y manipularlas para que estés trabajando con el subconjunto de datos adecuado.

## CRISP
Como **metodología**, incluye descripciones de las fases normales de un proyecto, las tareas necesarias en cada fase y una explicación de las relaciones entre las tareas.

Como **modelo de proceso**, CRISP-DM ofrece un resumen del ciclo vital de minería de datos.

El modelo **contiene seis fases** con flechas que indican las dependencias más importantes y frecuentes entre fases. **La secuencia de las fases no es estricta**. 
De hecho, la mayoría de los proyectos avanzan y retroceden entre fases si es necesario.

### Comprender el negocio
Esta es la etapa más importante, ya que, si no se comprende correctamente el negocio, o problema, no servirá pasar a las siguientes etapas. 

**Identificación del problema:** Aborda el entendimiento y delimitación de la problemática, así como la identificación de los requisitos, restricciones, supuestos y beneficios del proyecto.

**Determinación de objetivos:** Establece los resultados a obtener al proponer la solución.

**Evaluación de la situación actual:** Describe el estado actual antes de ser implementada la solución propuesta, con el fin de tener un objeto de comparación que permita medir el grado de éxito del proyecto.


### Comprensión de los datos
Comprende la recolección inicial de datos, con el objetivo de establecer un primer acercamiento con el problema, conociendo a los datos, identificando su calidad y estableciendo las primeras relaciones que permitan definir correlaciones entre variables.

**Recolección de datos:** Consiste en obtener los datos a utilizar en el proyecto a partir de algunas fuentes de datos, e identificando las técnicas utilizadas para su recolección.

**Exploración de datos:** Se basa en aplicar pruebas estadísticas que permitan conocer las propiedades de los datos.

### Preparación de datos
Esta es la etapa que demanda más tiempo en el proyecto, aquí se seleccionan los datos que serán transformados de acuerdo con los resultados de la etapa anterior a fin de ser utilizados en la etapa de modelado. 

**Limpieza de datos:** Para este fin se aplican diferentes técnicas, por ejemplo, normalización de datos, tratamiento de valores nulos, tratamiento de duplicados e imputación de datos.

**Transformación de datos:** Aquí se cambia la estructura o el formato de ciertos datos sin alterar su significado, a fin de poder ser utilizados en la etapa de modelado

### Modelado
En esta etapa se obtiene el modelo propuesto.

**Selección de técnica de modelado:** Se elige la técnica apropiada de acuerdo con el problema a resolver, los datos disponibles, las herramientas de minería de datos disponibles.

**Selección de datos de prueba:** En algunos modelos se necesita segmentar la muestra en datos de entrenamiento y de prueba.

**Obtención del modelo:** Aquí se genera el mejor modelo mediante un proceso iterativo con los datos de prueba y de entrenamiento.


### Evaluación de modelos
En esta etapa se determina la calidad del modelo teniendo en cuenta el análisis de determinadas métricas y criterios estadísticos del mismo, comparando los resultados con resultados previos. 

De acuerdo con los resultados de esta etapa se decide continuar con la última fase de la metodología, revisar alguna de las etapas anteriores o incluso iniciar desde cero con un nuevo proyecto. (Ciclo de mejora continua?)


### Implementación
Aquí el modelo ya ha sido construido y evaluado. Esta etapa explota, mediante acciones específicas, el conocimiento adquirido mediante el modelo en las etapas previas, pudiendo ser aplicado el modelo a diversos conjuntos de datos o también dentro de un proceso del negocio.



## Fase 4 y 5

### Regresión
#### Regresión Lineal
Predecir variables continuas, solo sirve para predecir variables continuas
**N° kills** → Game, en este caso para saber cuantos juegos va a ganar puedo medir las kills.
#### Regresión logística
Predecir variables categóricas
**1 Jugador ganara** → Feat 1, Feat 2, Feat 3.
Esperamos un resultado esperado, con distintas variables.

### Clasificación
Asignar una etiqueta de categoría

**Binaria** → Predecir si un jugador es no francotirador (Model train, modelo entrenado)
**Multi-clase** → Analiza roles ver mejor desempeño. (combinación de features)

### Clasificación (SUM)
**Estilos de juego:** (Vectorial)
- Frecuencia ganar → Ganador (Saber la frecuencia)
- Precision al disparar → Francotirador

### Arboles de decisión
Desempeño de jugadores Mapa (Ganador / Perdedor)
- feat 1
- feat 2
- feat 3

Dependiendo del mapa si alguien puede ganar o perder, tienen caminos y cada uno tiene una posibilidad, ese árbol se puede podar osea cortar ramas que no van hacia el camino deseado.


### Métricas
Necesitamos saber las métricas para saber si sirve o no sirve.


### SVM
Svm lo que hace es hacer una linea imaginaria para separar lo que es de lo que no es.


### Matriz de confusion
![[Pasted image 20240608161623.png]]