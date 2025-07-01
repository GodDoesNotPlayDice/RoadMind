# ¿Que es una API?
**API** significa **Application Programming Interface** (Interfaz de Programación de Aplicaciones).  
Es un conjunto de reglas y protocolos que define **cómo** dos programas se comunican entre sí.

- **Cliente**: la aplicación que hace la petición (por ejemplo, tu app móvil o un script Python).
- **Servidor**: la aplicación que recibe la petición y devuelve datos o realiza alguna acción.

## Estándares
1) **Puntos finales** (_endpoints_) a los que se hace la petición.
2) **Métodos** HTTP (GET, POST, PUT, DELETE, …).
3) **Formato de datos** (JSON, XML, etc.).
4) **Códigos de estado** (200 OK, 404 Not Found, 500 Internal Server Error, …).

## Rest (Representational State Transfer)
Es basado en **HTTP** ((Hypertext Transfer Protocol), 
### Operaciones CRUD mapeadas a métodos HTTP

| Operación CRUD     | SQL              | Verbo HTTP | Endpoint típico          | Código de Estado        | Idempotencia |
| ------------------ | ---------------- | ---------- | ------------------------ | ----------------------- | ------------ |
| **Create**         | `INSERT INTO …`  | `POST`     | `POST /productos`        | 201 Created             | No           |
| **Read**           | `SELECT …`       | `GET`      | `GET /productos/{id}`    | 200 OK                  | Sí           |
| **Update**         | `UPDATE … SET …` | `PUT`      | `PUT /productos/{id}`    | 200 OK / 204 No Content | Sí           |
| **Partial Update** | n/a              | `PATCH`    | `PATCH /productos/{id}`  | 200 OK                  | No (general) |
| **Delete**         | `DELETE FROM …`  | `DELETE`   | `DELETE /productos/{id}` | 204 No Content          | Sí           |
#### Prácticas avanzadas
- **Paginación en `GET` cuando hay muchos registros:** Parámetros: `page`, `limit`, `offset`, o enlaces HATEOAS (`_links.next`, `_links.prev`).
- **Filtrado y ordenamiento**: _GET /productos?categoría=ropa&sort=precio_desc_
- **Upsert** (update-or-insert): Se suele hacer con `PUT` a `/recurso/{id}` (si existe, actualiza; si no, crea).
- **Soft Delete** vs **Hard Delete**:
	- **Soft Delete**: marcar un campo `deleted=true` para poder “recuperar” registros.
	- **Hard Delete**: eliminación definitiva con `DELETE`.
- **Control de concurrencia**: **ETags** y `If-Match` para `PUT`/`PATCH`, evitando que dos clientes pisen los cambios del otro.
## SOAP (Simple Object Access Protocol)
Basado en XML y usa un contrato (WSDL) que describe la API. _Más verboso; común en entornos empresariales “legacy”._

## GraphQL
El cliente pide **exactamente** los campos que necesita en una única petición.
- Evita “over-fetching” y “under-fetching” de datos.