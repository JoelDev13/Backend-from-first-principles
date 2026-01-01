## HTTP
Es un mediador que permite la comunicación segura entre el navegador (cliente) y nuestro servidor, garantizando que los datos viajen cifrados, íntegros y autenticados

![Http](../../diagrams/UnderstandingHttp/http.jpg)

### Stateless
Básicamente significa que el servidor no tiene memoria de las interacciones pasada, pon en de por cada request debe tener toda la información necesaria para que el servidor la procese, osea tokens, cookies o credenciales deben enviarse en cada request

### Modelo Cliente-Servidor
- El cliente (browser, app, etc.) inicia la comunicación

- El servidor procesa la request y devuelve una response

- El servidor nunca inicia la comunicación

HTTP y HTTPS son iguales en principios; HTTPS es HTTP con seguridad adicional (TLS)

HTTP usa TCP como protocolo de transporte porque es confiable

### Mensajes HTTP

Un mensaje HTTP puede ser:

- Request (cliente => servidor)

- Response (servidor => cliente)

#### Request:

- Método (GET, POST, etc.)

- URL del recurso

- Versión HTTP

#### Headers

- Línea en blanco

- Body (opcional)

#### Response:

- Versión HTTP

- Status code (200, 404, etc.)

- Headers

- Línea en blanco

- Body

### Por qué necesitamos headers HTTP?
Los headers HTTP son necesarios porque hacen posible que el servidor y el cliente se comprendan más allá del mensaje. Son metadatos que explican cómo se debe manejar la solicitud o la respuesta

### Métodos HTTP
- GET: obtener datos

- POST: crear datos

- PATCH: actualización parcial

- PUT: reemplazo completo

- DELETE: eliminar recurso

#### Idempotencia
Es cuando múltiples llamadas producen el mismo resultado:

- Idempotentes: GET, PUT, DELETE

- No idempotente: POST

### Códigos de estado HTTP
```
1xx – Informativos

- 100 Continue

2xx – Éxito

- 200 OK

- 201 Created

- 204 No Content

3xx – Redirecciones

- 301 Moved Permanently

- 302 Found

- 304 Not Modified

4xx – Error del cliente

- 400 Bad Request

- 401 Unauthorized

- 403 Forbidden

- 404 Not Found

- 409 Conflict

- 429 Too Many Requests

5xx – Error del servidor

- 500 Internal Server Error

- 502 Bad Gateway

- 503 Service Unavailable
```

### OPTIONS y CORS
Política de seguridad del navegador

Controla acceso entre dominios

#### Simple request

GET / POST / HEAD

Headers simples

#### Preflight request

Usa OPTIONS

El navegador pregunta qué está permitido

#### Headers clave:

Access-Control-Allow-Origin

Access-Control-Allow-Methods

Access-Control-Allow-Headers

### Caching HTTP
Evita descargar recursos repetidos

- Cache-Control: Define cómo y por cuánto tiempo se cachea

- ETag: Identificador único del contenido

- If-None-Match: evita descargar un recurso si no ha cambiado

- Last-Modified: Fecha de última modificación