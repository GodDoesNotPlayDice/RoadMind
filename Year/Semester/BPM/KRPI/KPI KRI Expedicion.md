
## Identificar KPIs
- **Descarga de Productos**
- **Revision de productos**
- **Entrega de productos**


## Descarga de productos

### Variables
- Total de productos, Productos Recibidos
###  Descripción
- Este modelo permite identificar los productos faltantes al cliente.
### Formula
-  (Productos Descargados / Total  de productos de la Guia) X 100
### Formula en numeros
- (500 / 250) x 100 = 50%

### KPI

| Clasificiacion | Evaluacion |
| -------------- | ---------- |
| Muy bueno      | > 90%      |
| Bueno          | 60% - 89%  |
| Malo           | 20% - 59%  |
| Muy malo       | < 19%      |

### KRI

| Clasificiacion | Pronostico                                                                            | Plan de accion                                                                                                                                                      |
| -------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Muy bueno      | Mantener practicas de carga y gestion de los productos                                | Mantener las buenas practicas                                                                                                                                       |
| Bueno          | Re-ver la guía de despacho del total de productos                                     | Listar y anotar con cautela todos los productos de la guía de despacho y haciendo asi una checklist del los productos ya almacenados en el camion                   |
| Malo           | Ver que sucede con los encargados de la bodega, el jefe de bodega y el camionero.     | Agregar un tracker al camion y a los productos ingresados al camion.                                                                                                |
| Muy malo       | Identificar problemas graves en la cadena de suministro o en la gestión de productos. | Implementar auditorías exhaustivas, revisar todos los procesos de logística, y considerar el uso de tecnología avanzada para el seguimiento y control de productos. |


## Entrega de productos

### Variables
- Tiempo de entrega, tiempo estipulado
###  Descripción
- Este modelo permite identificar el tiempo de entrega de los productos
### Formula
$$
 
\text{Fecha de recibo Guia de despacho } + \text{Dias Habiles} - \text{Fecha de llegada}=  \text{ Dias de Retraso }
$$
### Formula en numeros
Fecha de envio : 1 de mayo de 2024 + 5 dias habiles = 8 de mayo 2024
Fecha de llegada : 10 de mayo de 2024
Fecha final : 8/05 - 10/05 = -2 dias llego antes.
### KPI

| Clasificación | Evaluación                       |
| ------------- | -------------------------------- |
| Muy bueno     | Entrega con demora ≤ 1 día       |
| Bueno         | Entrega con demora de 2 a 3 días |
| Malo          | Entrega con demora de 4 a 5 días |
| Muy malo      | Entrega con demora > 5 días      |

### KRI

| Muy bueno | Mantener prácticas eficientes de gestión y logística                       | Continuar con las buenas prácticas actuales y monitorear regularmente para asegurar la continuidad.                                                                                    |
| --------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Bueno     | Revisar y optimizar las rutas y tiempos de entrega.                        | Realizar ajustes menores en las rutas de entrega y en la gestión del tiempo, asegurar que los procesos de planificación sean precisos y actualizados.                                  |
| Malo      | Identificar los cuellos de botella y problemas en la cadena de suministro. | Realizar análisis detallados para encontrar las causas de los retrasos y mejorar la comunicación y coordinación entre los departamentos involucrados.                                  |
| Muy malo  | Graves problemas en la cadena de suministro y gestión de entregas.         | Implementar auditorías exhaustivas, revisar y reestructurar los procesos logísticos, capacitar al personal y considerar la adopción de tecnologías avanzadas de seguimiento y control. |
