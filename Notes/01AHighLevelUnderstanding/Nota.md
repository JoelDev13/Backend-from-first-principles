## Que es el backend? -Cómo funciona y por qué lo necesitamos

Un backend es un servidor que obtiene peticiones por medio de protocolos como HTTP, WebSocket o gRPC, utilizando puertos abiertos (como el 80 o el 443, por ejemplo). Recibe solicitudes de los clientes, las gestiona y proporciona información o contenido.

## El backend puede servir:

- Archivos estáticos (HTML, CSS, JS, imágenes)
- Datos dinámicos (JSON, respuestas de API)
- También puede recibir datos de los clientes (por ejemplo, formularios o peticiones POST)

## Cómo funciona un Backend? (Flujo de una petición)

- La solicitud empieza en el navegador => el usuario entra a un dominio
- DNS Lookup => el dominio se resuelve a una dirección IP
- Firewall / Grupo de seguridad (AWS) => se verifica si el puerto (HTTP/HTTPS) está permitido
- Instancia del servidor (EC2) => la petición llega al servidor a través de su IP pública
- Reverse Proxy (Nginx) => redirige el tráfico hacia la aplicación backend (por ejemplo, localhost:3001)
- Servidor => procesa la petición y envía la respuesta

## Por qué necesitamos un Backend?

El backend se encarga de los datos obtener, guardar y procesar información osea La lógica del negocio, la persistencia de los datos y el estado centralizado son gestionados por el backend, aspectos que no pueden ser llevados a cabo con seguridad o eficacia por el frontend

## Cómo funciona un Frontend?

- El navegador solicita una página web
- El servidor responde con HTML, CSS y JavaScript
- El navegador ejecuta el JavaScript localmente
- El navegador descarga los recursos y añade los eventos para las interacciones del usuario

## Por qué no podemos escribir lógica de backend en el frontend?

# Seguridad

- El navegador se ejecuta en un ambiente separado del sistema operativo
- No tiene acceso a los datos confidenciales del usuario ni al sistema de archivos

# CORS (Cross-Origin Resource Sharing)

- El navegador bloquea llamadas a APIs externas si no tienen los encabezados correctos

# Bases de datos

- Los servidores backend pueden usar drivers nativos (SqlServer,PostgreSQL, MongoDB, etc.)
- El navegador no puede mantener estas conexiones ni manejar grandes volúmenes de datos



