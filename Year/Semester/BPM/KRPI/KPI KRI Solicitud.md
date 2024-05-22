## Variables
**Cantidad de solicitudes recibidas de stock**
**Tiempo de demora de la solicitud de stock**
**Tiempo de demora de la alerta de Stock**


## Formulas

### Cantidad de solicitudes 
( Cantidad de solicitudes / Total de solicitudes ) X 100

### Tiempo de demora de la solicitud del stock
Fecha de envio llegada - Fecha de envió de solicitud = Dias demorado

### Tiempo de demora de la alerta del stock
Horas demoradas = ((Fecha de llegada de alerta + Hora de llegada) - (Fecha de envıio de alerta+Hora de envio))

$$
\text{Horas demoradas} = \left( (\text{Fecha de llegada de alerta} + \text{Hora de llegada}) - (\text{Fecha de envío de alerta} + \text{Hora de envío}) \right)
$$

#### Demostración

**Cantidad de solicitudes** : (200 / 500) x 100 = 40%
**Tiempo de demora de la solicitud**:  9-05 - 10-05 =  0 - 1 = -1 teniendo un día de retraso.
**Tiempo de demora de la alerta en Horas**: 24 horas + (10 horas − 23 horas) = 24 + (−13) = 1 día y 11 horas
- **Envió**: 10-05
- **Llegada**: 11-05


#### KPI

| Diagnostico | Evaluador  |
| ----------- | ---------- |
| Muy bueno   | 90% - 100% |
| Irregular   | 50% - 89%  |
| Malo        | 0% - 49%   |


| Diagnostico | Evaluador |
| ----------- | --------- |
| Muy bueno   | 1 <       |
| Normal      | 0 = 0     |
| Malo        | > 1       |


| Diagnostico | Evaluador |
| ----------- | --------- |
| Muy bueno   | < 24 hs   |
| Irregular   | > 48 hs   |
| Malo        | > 96 hs   |


#### KRI

|Clasificación|Pronóstico|Plan de acción|
|---|---|---|
|Muy bueno|Muy alto porcentaje de solicitudes atendidas (90% - 100%)|Mantener las buenas prácticas|
|Irregular|Moderado porcentaje de solicitudes atendidas (50% - 89%)|Revisar las vías de comunicación y los procesos|
|Malo|Bajo porcentaje de solicitudes atendidas (0% - 49%)|Revisar la gestión y asignación de recursos, implementar medidas correctivas|
|Muy malo|Muy bajo porcentaje de solicitudes atendidas (menos del 10%)|Identificar problemas graves en la gestión de solicitudes, realizar auditorías internas|

| Clasificación | Pronóstico                     | Plan de acción                                                                      |
| ------------- | ------------------------------ | ----------------------------------------------------------------------------------- |
| Muy bueno     | Tiempo de demora menor a 1 día | Mantener las buenas prácticas                                                       |
| Normal        | Tiempo de demora de 0 días     | Revisar y mejorar pequeños procesos                                                 |
| Malo          | Tiempo de demora mayor a 1 día | Revisar y optimizar el proceso de solicitud y envío, identificar cuellos de botella |


|Clasificación|Pronóstico|Plan de acción|
|---|---|---|
|Muy bueno|Tiempo de alerta menor a 24 horas|Mantener las buenas prácticas|
|Irregular|Tiempo de alerta entre 24 y 48 horas|Revisar y optimizar los procesos de comunicación|
|Malo|Tiempo de alerta mayor a 48 horas|Implementar mejoras significativas en los sistemas de alerta y notificación, identificar fallos críticos|
|Muy malo|Tiempo de alerta mayor a 96 horas|Revisar completamente la cadena de suministro y la gestión de inventarios, identificar problemas graves y solucionarlos|


