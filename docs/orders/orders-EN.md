![](../img/logo-spup.jpeg)

# Create Order

Here is detailed how to create an order using the [Project Name] API.

## Endpoint

```http
POST {{host}}/commerce/orders/
content-type: application/json
Authorization: Token {{token}}
```

## Authentication
To authenticate to the API, you must include the access token in the authorization header of the request.

```http
Authorization: Token {{token}}
```

## Request Parameters
The request must be sent with the following body in JSON format:

```json
{
  "warehouse_id": "mia_wh",
  "client_email": "client@example.com",
  "name_client": "Test Client",
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

## Response
The response of the request will contain details about the created order.

****

# Check Order Status

This endpoint is used to check the status of an order using a specific TrackID.

## Request Details

- **Method:** GET
- **URL:** `{{host}}/public/trackings/?search={{trackID}}`
- **Content Type:** application/json

## Request Parameters

| Parameter | Type   | Description                                  |
| --------- | ------ | -------------------------------------------- |
| trackID   | string | Unique identifier of the order to be viewed. |

## Request Headers

- `Authorization`: Token {{token}}

## Request Example

```http
GET {{host}}/public/trackings/?search={{trackID}}
Content-Type: application/json
Authorization: Token {{token}}
```

### Successful Response

The successful response will return the status of the queried order.

### Successful Response Example
```json
{
  "tracking_id": "MIALWH000000189519",
  "status": "Delivered",
  "date_delivered": "2024-04-30T10:15:00Z",
  "delivery_notes": "Delivered to the recipient's address successfully."
}
```

### Error Response
In case of error, a corresponding HTTP status code will be returned along with an explanatory error message.

### Error Response Example
```json
{
  "error": "Not Found",
  "message": "The tracking ID MIALWH000000189519 was not found."
}
```

### Status Codes - Code Description
- 200 OK - Successful request
- 404 Not Found - Order not found
- 401 Unauthorized - Invalid authentication token