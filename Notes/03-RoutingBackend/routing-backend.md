# Routing
En las APIs HTTP, la interacción entre el cliente y el servidor se fundamenta sobre todo en dos componentes:
las rutas (routing) y los métodos HTTP

### Métodos HTTP: seria el qué 

Los métodos HTTP expresan la intención del cliente:

```
GET: obtener datos

POST: crear datos

PUT / PATCH: actualizar datos

DELETE: eliminar datos
```
Indican qué acción se quiere realizar sobre un recurso


### Routing: seria el dónde

El routing indica a qué recurso del servidor se aplica esa acción. La ruta (URL) le dice al servidor dónde debe ejecutar la lógica correspondiente.

La combinación de método HTTP + ruta se usa como una clave para que el servidor ejecute un handler específico

Ejemplo:
```
GET /api/books
```
- Acción: obtener datos
- Recurso: libros

## Tipos de rutas

### Rutas estáticas

Son rutas fijas que no cambian
```
GET /api/books
POST /api/books
```
Siempre tienen la misma estructura y devuelven el mismo tipo de información

### Rutas dinámicas (Path Parameters)

Incluyen parámetros variables dentro de la ruta
```
GET /api/users/123
```
123 es un parámetro de ruta

Se representa en el servidor como:
```
/api/users/:id
```
Se usan para identificar recursos específicos, como un usuario por su ID

### Query Parameters

Se envían después del signo ? como pares clave–valor
```
GET /api/search?query=valor
GET /api/books?page=2&limit=20
```
Se utilizan principalmente en GET requests para:

- Búsquedas

- Filtros

- Ordenamiento

- Paginación

No forman parte de la ruta principal, sino que agregan información adicional

### Rutas anidadas (Nested Routes)

Expresan relaciones entre recursos
```
GET /api/users/123/posts/456
```
Significado (ej):

- Usuario con ID 123
- Sus posts
- Post específico con ID 456

Permiten una expresión semántica clara de relaciones entre datos

### Versionado de rutas

Se usa para manejar cambios importantes en la API sin romper versiones antiguas
```
/api/v1/products
/api/v2/products
```
Beneficios:

- Mantiene compatibilidad con clientes antiguos
- Permite introducir cambios gradualmente
- Facilita la deprecación de versiones viejas

### Catch-all Route (Ruta comodín)

Captura todas las rutas que no existen
```
*
```

Se usa para devolver mensajes como:

- Ruta no encontrada
- Error 404 personalizado
- Mejora la experiencia del cliente al recibir respuestas claras