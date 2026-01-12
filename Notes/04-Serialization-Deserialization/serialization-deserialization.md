# Qué es la serialización y deserialización?
Son procesos que permiten que clientes y servidores, escritos en lenguajes diferentes, puedan enviarse y entender datos entre sí

## Serialización
Seria el proceso de convertir datos internos de un programa (objetos, variables etc) a un formato estándar como JSON
para enviarlos por la red o guardarlos

- Ejemplo:
Un objeto JavaScript -> JSON -> enviado por HTTP

## Deserialización
Seria el proceso inverso toma datos en formato estándar ej JSON, y convertirlo a los tipos de datos del lenguaje receptor

- Ejemplo:
JSON recibido -> objeto Java

## Formatos de serialización
#### Basados en texto

- JSON (el más usado)
- XML
- YAML

Ventaja: Fáciles de leer por humanos
Desventajas: Más grandes y un poco más lentos

#### Binarios

- Protocol Buffers (Protobuf)
- Avro, etc

Ventaja: Más rápidos y eficientes
Desventajas: No legibles por humanos

![Deserializacion](../../Diagrams/SerializationDeserialization/deserializacion.jpg)


### JSON (el más común)

- Significa JavaScript Object Notation
- Usa { }, claves entre " " y valores simples
- Es independiente del lenguaje
- Muy usado en APIs REST, configuración y logs

Ejemplo:
```
{
  "id": 1,
  "title": "Book",
  "author": "John"
}
```