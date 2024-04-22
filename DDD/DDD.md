# Estructura de DDD simple (Tasks example)

**Dominio**: El dominio es basado en el contexto, por lo que si hacemos un dominio de `Tasks` podemos hacer `Tasks` en base al contexto.
- **Models**: Es donde se tiene el cuerpo del dominio
	- **Tasks**: Se crea el objeto que va a usar
	- **Value Objects**: los value objects son los atributos del objeto validados.
- **Repository**: Es el contrato cual tendrá los métodos del dominio, osea que hará el dominio al fin y al cabo
- **Application**: Es donde están los casos de uso del dominio y ademas como se va comunicar el dominio, ejemplo puede ser por JSON, XML, etc
	- **Mapper**: Como el dominio se expone al exterior
- **Infrastructure**: Es la  comunicación con el mundo exterior, como librerías, API, dispositivos