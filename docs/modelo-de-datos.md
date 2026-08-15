# Modelo de datos

> **Este archivo lo entrega la cátedra al inicio del Bloque 3.** Es el **contrato** con el que se construye el frontend en la Entrega 3 y el backend en la Entrega 4.

Acá va el modelo de datos de tu TP: qué entidades tiene el sistema y qué campos tiene cada una.

## Por qué está en `docs/` y no dentro de una entrega

Porque **atraviesa dos entregas**. Los nombres de campo que uses en los arrays y JSON de la Entrega 3 son los mismos que van a existir como tablas en la Entrega 4, y los mismos que el backend va a devolver cuando se conecten.

## Las tres reglas

1. **Los nombres de campo salen de este documento**, no de la imaginación.
2. **Cada objeto lleva su `id`**, aunque la pantalla no lo muestre.
3. **camelCase** en el JSON (`fechaPedido`), aunque la columna de la base se llame `fecha_pedido`.

Si se respetan las tres, el día que el frontend se conecte al backend cambia **una línea**:

```js
fetch('data/platos.json')     // Entrega 3
fetch('/api/platos')          // conexión con el backend
```

Si no, hay que reescribir los arrays, las funciones que arman las tarjetas y los formularios.
