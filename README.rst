Documentación de la API de [Nombre del Proyecto]
================================================

Esta documentación detalla cómo utilizar la API de [Nombre del Proyecto] para crear y gestionar órdenes en el sistema.

Descripción
-----------

La API de [Nombre del Proyecto] proporciona funcionalidades para la creación de órdenes de forma programática, permitiendo a los usuarios integrar sus sistemas con nuestro servicio de manera eficiente.

Endpoint
--------

.. code-block:: http

   POST https://api.demo.pickuppoint.cl/api/v1/commerce/orders/

Autenticación
-------------

Para autenticarse en la API, se debe incluir el token de acceso en la cabecera de autorización de la solicitud.

.. code-block:: http

   Authorization: Token ac090ea02b68bc938f31cebed1c25483a4274050

Parámetros de la Solicitud
---------------------------

La solicitud debe ser enviada con el siguiente cuerpo en formato JSON:

.. code-block:: json

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

Descripción de Parámetros
--------------------------

- `warehouse_id` (string): Identificador de la bodega.
- `client_email` (string): Correo electrónico del cliente.
- `name_client` (string): Nombre del cliente.
- `phone_client` (string): Número de teléfono del cliente.
- `request_number` (string): Número de solicitud.
- `box_size` (integer): Tamaño de la caja.
- `box_height`, `box_width`, `box_length` (integer): Dimensiones de la caja.
- `box_weight` (integer): Peso de la caja.
- `address` (object): Objeto que contiene la dirección del cliente.
   - `street` (string): Calle.
   - `number` (string): Número.
   - `apartment` (string): Número de departamento.
   - `commune` (string): Comuna.
   - `city` (string): Ciudad.
   - `country` (string): País.
- `order_type` (string): Tipo de orden.
- `sub_status` (string): Estado secundario de la orden.

Ejemplo de Solicitud
---------------------

.. code-block:: http

   POST /api/v1/commerce/orders/ HTTP/1.1
   Host: api.demo.pickuppoint.cl
   Authorization: Token ac090ea02b68bc938f31cebed1c25483a4274050
   Content-Type: application/json

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

Respuesta
---------

La respuesta de la solicitud contendrá detalles sobre la orden creada.

Asegúrate de incluir todos los detalles relevantes sobre cómo utilizar la API, así como ejemplos claros y concisos para ayudar a los usuarios a comprender rápidamente cómo interactuar con ella.
