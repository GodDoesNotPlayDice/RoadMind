## Actividad Ejemplo
**Etapa de Despacho**: 
- **KPI**: 
	- Identificar actividades mas relevantes
	- Justificar variables a evaluar
	- Generar formula y comparar con "Cuadro comparacion" (Usar los datos)
- **KRI**: 
	- En caso de resultado negativo
	- Genera pronostico
	- Genera plan de accion


$$ 
(\frac{\text{T.P encontrados} - \text{T.P ensamblados}}{T.P encontrados}) * 100 =  \text{ (Porcentaje) T.P no encontrados}
$$


| Nivel     | Descripción                                         | % de productos no encontrados |
| --------- | --------------------------------------------------- | ----------------------------- |
| Muy Bueno | La gran mayoria de productos                        | 0% - 5%                       |
| Normal    | Se perdieron una distribucion normal de productos   | 6% - 15%                      |
| Malo      | Se pierden una pequeña o gran cantidad de productos | 16% - 45%                     |
| Muy Malo  | Se pierden la gran mayoría de productos o todos     | 46% - 100%                    |


| Nivel     | Acción a Tomar                                                                                                                             | Mitigar                                                                                                              |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------- |
| Muy Malo  | Se debe re-inspeccionar el stock de la bodega urgentemente y recontar los productos de la guía de despacho proveniente del jefe de bodega. | Colocar trackeadores a los productos al momento de descargar la carga, re capacitar al jefe de bodega y al bodegero. |
| Malo      | Se debe re-contar el stock de la bodega y re-inspeccionar la guia de despacho                                                              | Capacitar al bodegero y mantener el trackeador de productos                                                          |
| Normal    | Mantener ojo con el stock de la bodega y re-buscar si no quedo carga pendiente por almacenar en bodega                                     | Mantener una capacitacion al bodegero y anotar en una lista los productos que usualmente se pierden                  |
| Muy Bueno | Mantener practicas anteriores para mantener el buen porcentaje de productos encontrados.                                                   | Mantener las practicas anteriores.                                                                                   |


$$ 
(\frac{\text{T.P } - \text{T.P ensamblados}}{100}) * 100 =  \% \text{T.P no encontrados}
$$


## Resumen clase posterior
**KPI**: Rendimiento
**Variable**: Guia despacho, Tiempo
**Formula**: Guia de despacho optima = (**Tiempo Comprometido** - **Tiempo de despacho**) { **A** - **B**}
### A - B
- 10/5/24 - 10/5/24 = 0 dias -> Optimo
-  10/5/24 - 11/5/24 = -1 -> No cumple -> C. total (No cumple) / T. Solicitudes Ex 5 / 20 = 25%
- 10/5/24 - 9/5/24 = 1 (Excelente) -> Excelente

### Ejemplo 1 KPI (Despacho)
**KPI**: Rendimiento
**Variable**: Guia despacho, Tiempo
#### Formula

$$
\text{Guía de despacho óptima} = (\text{Tiempo Comprometido} - \text{Tiempo de despacho})

$$
#### Tabla de KPI

| Fecha Inicial | Fecha Final | Diferencia (días) | Evaluación |
| ------------- | ----------- | ----------------- | ---------- |
| 10/5/24       | 10/5/24     | 0                 | Óptimo     |
| 10/5/24       | 11/5/24     | -1                | No cumple  |
| 10/5/24       | 9/5/24      | 1                 | Excelente  |

### Ejemplo 2 (Despacho en base al primer KPI)
**KPI**: Si no cumple
**Variable**: C. no Cumplidas, C.totales

#### Formula

$$
\% \text{} = \frac{\text{C. total (No cumple)}}{\text{T. Solicitudes}} \times 100
$$
#### Tabla KPI

| Rango de Porcentaje | Evaluación  |
| ------------------- | ----------- |
| 1% - 10%            | Muy Grave   |
| 10% - 30%           | Grave       |
| 31% - 50%           | Mas o Menos |
| 51% - 100%          | Cumple      |


### KRI en base a lo Anterior
**KRI**
- →  0, > 0 ⇒ Muy bueno
- < 0 ⇒ Pronostico.
	- Molesta al cliente.
	- Pedidas.
	- Caida de pretigio.
	- Perdida de Clientes.
**Acciones**
- Analisis de Casos
- Alertas



### KPI Ventas
**KPI**: Recepcion de productos
**Variable**: C.Productos, T.Productos, Guia despacho, Dias Habiles, Fecha de recibo

#### Formula

$$
 
\text{Fecha de Subida Guia } + \text{Dias Habiles} - \text{Fecha de Recibo}=  \text{ Dias de Retraso }
$$

$$
 
(\frac{\text{Total de Productos } - \text{Cantidad de Productos Recibidos}}{100}) * 100 =  \text{ \%Productos}
$$

#### Tabla (KPI)

| Rango de Dias | Evaluación  |
| ------------- | ----------- |
| 30 - 20       | Muy Grave   |
| 6 - 10        | Grave       |
| 4 - 2         | Mas o Menos |
| 1 - 0         | Cumple      |

| Rango de Porcentaje | Evaluación  |
| ------------------- | ----------- |
| 1% - 5%             | Muy Grave   |
| 6% - 20%            | Grave       |
| 21% - 60%           | Mas o Menos |
| 61% - 100%          | Cumple      |

#### Tabla (KRI)

**Porcentaje** : > 0 = Pronostico
- Perdidas de Ventas
- Perdidas de Clientes
- Retraso del Stock
**Acciones**:
- Aviso a la superioridad sobre el retraso
- Alerta de retraso
- Analisis de Retrasos por empresa.




