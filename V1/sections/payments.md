Obtener colección de impuestos
------------------------------

* `GET /v1/payments.json` retornara todos los pagos realizados.

####Parametros

- *limit*, limita la cantidad de items de una respuesta JSON, si no se envia el limit es 25.
- *offset*, permite paginar los items de una respuesta JSON, si no se envia el offset es 0.
- *fields*, solo devolver atributos especificos de un recurso
- *expand*, permite expandir instancias y colecciones.
- *recorddate*, Permite filtrar por fecha del pago.
- *state*, boolean (0 o 1) indica si los pagos estan activos(0) inactivos(1).

####Ejemplos

* `GET /v1/payments.json?limit=10&offset=0`
* `GET /v1/payments.json?recorddate=2014-03-21`
* `GET /v1/payments.json?expand=[office,payment_type]`

####Respuesta
```json
{
  "href": "http://api.bsale.cl/v1/payments.json",
  "count": 1926,
  "limit": 4,
  "offset": 0,
  "items": [
    {
      "href": "http://api.bsale.cl/v1/payments/950.json",
      "id": 950,
      "recordDate": null,
      "amount": "68643.0",
      "checkDate": null,
      "checkNumber": null,
      "checkAmount": "0",
      "state": 0,
      "payment_type": {
        "href": "http://api.bsale.cl/v1/payment_types/1.json",
        "id": "1"
      },
      "office": {
        "href": "http://api.bsale.cl/v1/offices/2.json",
        "id": "2"
      }
    },
    {
      "href": "http://api.bsale.cl/v1/payments/951.json",
      "id": 951,
      "recordDate": null,
      "amount": "281494.0",
      "checkDate": null,
      "checkNumber": null,
      "checkAmount": "0",
      "state": 0,
      "payment_type": {
        "href": "http://api.bsale.cl/v1/payment_types/1.json",
        "id": "1"
      },
      "office": {
        "href": "http://api.bsale.cl/v1/offices/2.json",
        "id": "2"
      }
    },
    {
      "href": "http://api.bsale.cl/v1/payments/957.json",
      "id": 957,
      "recordDate": null,
      "amount": "52637.0",
      "checkDate": null,
      "checkNumber": null,
      "checkAmount": "0",
      "state": 0,
      "payment_type": {
        "href": "http://api.bsale.cl/v1/payment_types/1.json",
        "id": "1"
      },
      "office": {
        "href": "http://api.bsale.cl/v1/offices/2.json",
        "id": "2"
      }
    },
    {
      "href": "http://api.bsale.cl/v1/payments/958.json",
      "id": 958,
      "recordDate": null,
      "amount": "22837.0",
      "checkDate": null,
      "checkNumber": null,
      "checkAmount": "0",
      "state": 0,
      "payment_type": {
        "href": "http://api.bsale.cl/v1/payment_types/1.json",
        "id": "1"
      },
      "office": {
        "href": "http://api.bsale.cl/v1/offices/2.json",
        "id": "2"
      }
    }
  ]
}
```
Obtener un pago
---------------

* `GET /v1/payments/950.json` retornara un pago específico.

####Respuesta
```json
{
  "href": "http://api.bsale.cl/v1/payments/950.json",
  "id": 950,
  "recordDate": null,
  "amount": "68643.0",
  "checkDate": null,
  "checkNumber": null,
  "checkAmount": "0",
  "state": 0,
  "payment_type": {
    "href": "http://api.bsale.cl/v1/payment_types/1.json",
    "id": "1"
  },
  "office": {
    "href": "http://api.bsale.cl/v1/offices/2.json",
    "id": "2"
  }
}
```
Obtener cantidad de pagos.
--------------------------

* `GET /v1/payments/count.json`
```json
{
  "count": 1926
}
```