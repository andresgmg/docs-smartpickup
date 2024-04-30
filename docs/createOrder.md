# Crear Orden

Aquí se detalla cómo crear una orden utilizando la API de [Nombre del Proyecto].

## Endpoint

```http
POST {{host}}/commerce/orders/
content-type: application/json
Authorization: Token {{token}}
```

## Autenticación
Para autenticarse en la API, se debe incluir el token de acceso en la cabecera de autorización de la solicitud.

```http
Authorization: Token {{token}}
```

## Parámetros de la Solicitud
La solicitud debe ser enviada con el siguiente cuerpo en formato JSON:

```json
{
  "warehouse_id": "mia_wh",
  "client_email": "cliente@ejemplo.cl",
  "name_client": "Cliente de prueba",
  "phone_client": "955555555",
  "request_number": "0000000012",
  "box_size": 1,
  "box_height": 1,
  "box_width": 1,
  "box_length": 1,
  "box_weight": 1,
  "address": {
    "street": "Luis Durand",
    "number": "03057",
    "apartment": "408",
    "commune": "Temuco",
    "city": "Temuco",
    "country": "Chile"
  },
  "order_type": "lm_home",
  "sub_status": "next_day"
}
```

## Respuesta
La respuesta de la solicitud contendrá detalles sobre la orden creada.