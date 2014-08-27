Obtener colección de devoluciones
---------------------------------

* `GET /v1/returns.json` retornara todos las devoluciones.

####Parametros

- *limit*, limita la cantidad de items de una respuesta JSON, si no se envia el limit es 25.
- *offset*, permite paginar los items de una respuesta JSON, si no se envia el offset es 0.
- *fields*, solo devolver atributos especificos de un recurso
- *expand*, permite expandir instancias y colecciones.
- *returndate*, Permite filtrar por fecha de devolución.
- *code*, filtra por codigo de la devolución.
- *type*, filtra por tipo de devolución.
- *officeid*, Permite filtrar por sucursal.
- *referencedocumentid*, filtra por documento de referencia.

####Ejemplos

* `GET /v1/returns.json?limit=10&offset=0`
* `GET /v1/returns.json?fields=[returndate,motive]`
* `GET /v1/returns.json?expand=[reference_document,credit_note,details]`

####Respuesta
```json
{
  "href": "https://api.bsale.cl/v1/returns.json",
  "count": 49,
  "limit": 2,
  "offset": 0,
  "items": [
    {
      "href": "https://api.bsale.cl/v1/returns/1.json",
      "id": 1,
      "code": "137615600351",
      "returnDate": 1376107200,
      "motive": "Cambio a Factura",
      "type": 1,
      "priceAdjustment": 0,
      "editTexts": 0,
      "amount": 27541.0,
      "office": {
        "href": "https://api.bsale.cl/v1/offices/1.json",
        "id": "1"
      },
      "reference_document": {
        "href": "https://api.bsale.cl/v1/documents/472.json",
        "id": "472"
      },
      "credit_note": {
        "href": "https://api.bsale.cl/v1/documents/477.json",
        "id": "477"
      },
      "details": {
        "href": "https://api.bsale.cl/v1/returns/1/details.json"
      }
    },
    {
      "href": "https://api.bsale.cl/v1/returns/2.json",
      "id": 2,
      "code": "137668322351",
      "returnDate": 1376625600,
      "motive": "error de ventas",
      "type": 0,
      "priceAdjustment": 0,
      "editTexts": 0,
      "amount": 21488.0,
      "office": {
        "href": "https://api.bsale.cl/v1/offices/1.json",
        "id": "1"
      },
      "reference_document": {
        "href": "https://api.bsale.cl/v1/documents/527.json",
        "id": "527"
      },
      "credit_note": {
        "href": "https://api.bsale.cl/v1/documents/529.json",
        "id": "529"
      },
      "details": {
        "href": "https://api.bsale.cl/v1/returns/2/details.json"
      }
    }
  ]
}
```
Obtener una devolución
----------------------

* `GET /v1/returns/1.json` retornara una devolución específica.

####Parametros

- *expand*, permite expandir instancias y colecciones.

####Ejemplos

* `GET /v1/returns/1.json?expand=[credit_note]`

####Respuesta
```json
{
  "href": "https://api.bsale.cl/v1/returns/1.json",
  "id": 1,
  "code": "137615600351",
  "returnDate": 1376107200,
  "motive": "Cambio a Factura",
  "type": 1,
  "priceAdjustment": 0,
  "editTexts": 0,
  "amount": 27541.0,
  "office": {
    "href": "https://api.bsale.cl/v1/offices/1.json",
    "id": "1"
  },
  "reference_document": {
    "href": "https://api.bsale.cl/v1/documents/472.json",
    "id": "472"
  },
  "credit_note": {
    "href": "https://api.bsale.cl/v1/documents/477.json",
    "id": "477"
  },
  "details": {
    "href": "https://api.bsale.cl/v1/returns/1/details.json"
  }
}
```
Obtener detalles de una devolución
----------------------------------

* `GET /v1/returns/1/details.json`
```json
{
  "href": "https://api.bsale.cl/v1/returns/1/details.json",
  "count": 2,
  "limit": 25,
  "offset": 0,
  "items": [
    {
      "href": "https://api.bsale.cl/v1/returns/1/details/1.json",
      "id": 1,
      "quantity": 2.8,
      "quantityDevStock": 2.8,
      "variantStock": 59.37,
      "variantCost": 3200.0
    },
    {
      "href": "https://api.bsale.cl/v1/returns/1/details/2.json",
      "id": 2,
      "quantity": 1.64,
      "quantityDevStock": 1.64,
      "variantStock": 45.44,
      "variantCost": 3200.0
    }
  ]
}
```
Obtener un de detalle de una devolución
---------------------------------------

* `GET /v1/returns/1/details/1.json`
```json
{
  "href": "https://api.bsale.cl/v1/returns/1/details/1.json",
  "id": 1,
  "quantity": 2.8,
  "quantityDevStock": 2.8,
  "variantStock": 59.37,
  "variantCost": 3200.0
}
```
Crear una devolución
--------------------

* `POST /v1/returns.json`

Se debe enviar un Json con la siguiente esctructura.
```json
{
  "officeId": 1,
  "referenceDocumentId": 11528,
  "motive": "prueba api",
  "declareSii": 1,
  "priceAdjustment": 0,
  "editTexts": 0,
  "amount": 6490,
  "type": 1,
  "document": {
    "expirationDate": 1407384000,
    "emissionDate": 1407384000,
    "documentTypeId": 9
  },
  "client": {
    "id": 107
  },
  "details": [
    {
      "documentDetailId": 21493,
      "quantity": 1,
      "unitValue": 0
    }
  ]
}
```
####Respuesta
```json
{
  "credit_note": {
    "href": "https://api.bsale.cl/v1/documents/11539.json",
    "id": "11539"
  },
  "reference_document": {
    "href": "https://api.bsale.cl/v1/documents/11528.json",
    "id": "11528"
  },
  "amount": 6490.0,
  "code": "140745397411",
  "type": 1,
  "editTexts": 0,
  "href": "https://api.bsale.cl/v1/returns/71.json",
  "returnDate": 1407384000,
  "details": {
    "href": "https://api.bsale.cl/v1/returns/71/details.json"
  },
  "office": {
    "href": "https://api.bsale.cl/v1/offices/1.json",
    "id": "1"
  },
  "motive": "prueba api",
  "priceAdjustment": 0,
  "id": 71
}
```