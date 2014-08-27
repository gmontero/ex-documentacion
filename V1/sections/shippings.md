Obtener colección de despachos
------------------------------

* `GET /v1/shippings.json` retornara todos los despachos.

####Parametros

- *limit*, limita la cantidad de items de una respuesta JSON, si no se envia el limit es 25.
- *offset*, permite paginar los items de una respuesta JSON, si no se envia el offset es 0.
- *fields*, solo devolver atributos especificos de un recurso
- *expand*, permite expandir instancias y colecciones.
- *shippingdate*, Permite filtrar por fecha de devolución.
- *officeid*, Permite filtrar por sucursal.
- *shippingtypeid*, filtra por documento de referencia.
- *state*, boolean (0 o 1) indica si los documentos estan activos(0) inactivos (1).


####Ejemplos

* `GET /v1/shippings.json?limit=10&offset=0`
* `GET /v1/shippings.json?fields=[shippingdate,recipient]`
* `GET /v1/shippings.json?expand=[guide,shipping_type,details]`

####Respuesta
```json
{
  "href": "https://api.bsale.cl/v1/shippings.json",
  "count": 13430,
  "limit": 3,
  "offset": 0,
  "items": [
    {
      "href": "https://api.bsale.cl/v1/shippings/22.json",
      "id": 22,
      "shippingDate": 1370318400,
      "address": null,
      "municipality": "",
      "city": "",
      "recipient": null,
      "state": 0,
      "office": {
        "href": "https://api.bsale.cl/v1/offices/1.json",
        "id": "1"
      },
      "shipping_type": {
        "href": "https://api.bsale.cl/v1/shipping_types/1.json",
        "id": "1"
      },
      "guide": {
        "href": "https://api.bsale.cl/v1/documents/23.json",
        "id": "23"
      },
      "details": {
        "href": "https://api.bsale.cl/v1/shippings/22/details.json"
      }
    },
    {
      "href": "https://api.bsale.cl/v1/shippings/23.json",
      "id": 23,
      "shippingDate": 1370318400,
      "address": null,
      "municipality": "",
      "city": "",
      "recipient": null,
      "state": 0,
      "office": {
        "href": "https://api.bsale.cl/v1/offices/1.json",
        "id": "1"
      },
      "shipping_type": {
        "href": "https://api.bsale.cl/v1/shipping_types/1.json",
        "id": "1"
      },
      "guide": {
        "href": "https://api.bsale.cl/v1/documents/24.json",
        "id": "24"
      },
      "details": {
        "href": "https://api.bsale.cl/v1/shippings/23/details.json"
      }
    },
    {
      "href": "https://api.bsale.cl/v1/shippings/24.json",
      "id": 24,
      "shippingDate": 1370318400,
      "address": null,
      "municipality": "",
      "city": "",
      "recipient": null,
      "state": 0,
      "office": {
        "href": "https://api.bsale.cl/v1/offices/1.json",
        "id": "1"
      },
      "shipping_type": {
        "href": "https://api.bsale.cl/v1/shipping_types/1.json",
        "id": "1"
      },
      "guide": {
        "href": "https://api.bsale.cl/v1/documents/25.json",
        "id": "25"
      },
      "details": {
        "href": "https://api.bsale.cl/v1/shippings/24/details.json"
      }
    }
  ]
}
```
Obtener un despacho
-------------------

* `GET /v1/shippings/22.json` retornara un despacho específico.

####Parametros

- *expand*, permite expandir instancias y colecciones.

####Ejemplos

* `GET /v1/shippings/1.json?expand=[details]`

####Respuesta
```json
{
  "href": "https://api.bsale.cl/v1/shippings/22.json",
  "id": 22,
  "shippingDate": 1370318400,
  "address": null,
  "municipality": "",
  "city": "",
  "recipient": null,
  "state": 0,
  "office": {
    "href": "https://api.bsale.cl/v1/offices/1.json",
    "id": "1"
  },
  "shipping_type": {
    "href": "https://api.bsale.cl/v1/shipping_types/1.json",
    "id": "1"
  },
  "guide": {
    "href": "https://api.bsale.cl/v1/documents/23.json",
    "id": "23"
  },
  "details": {
    "href": "https://api.bsale.cl/v1/shippings/22/details.json"
  }
}
```
Obtener detalles de un despacho
-------------------------------

* `GET /v1/shippings/22/details.json`
```json
{
  "href": "https://api.bsale.cl/v1/shippings/22/details.json",
  "count": 1,
  "limit": 25,
  "offset": 0,
  "items": [
    {
      "href": "https://api.bsale.cl/v1/shippings/22/details/31.json",
      "id": 31,
      "quantity": 1.0,
      "variantStock": 28.0,
      "variantCost": 0.0
    }
  ]
}
```
Obtener un de detalle de un despacho
------------------------------------

* `GET /v1/shippings/22/details/31.json`
```json
{
  "href": "https://api.bsale.cl/v1/shippings/22/details/31.json",
  "id": 31,
  "quantity": 1.0,
  "variantStock": 28.0,
  "variantCost": 0.0
}
```
Crear un despacho
-----------------

* `POST /v1/shippings.json`

Se debe enviar un Json con la siguiente esctructura.
```json
{
  "documentTypeId": 10,
  "officeId": 1,
  "expirationDate": 1409149934,
  "emissionDate": 1409149934,
  "shippingTypeId": 6,
  "municipality": "Puerto Varas",
  "city": "Puerto Varas",
  "address": "la quebrada 1005",
  "declareSii": 1,
  "recipient": "Andres Gallardo",
  "details": [
    {
      "taxId": "[1]",
      "quantity": 1,
      "comment": "PASAJERO: JAIME GONZALEZ",
      "netUnitValue": 12000
    }
  ],
  "client": {
    "municipality": "PUERTO MONTT",
    "code": "13121776-5",
    "activity": "SERV. TELECOMUNICACIONES",
    "company": "JAIME ALTAMIRANO SOTO",
    "city": "PUERTO MONTT",
    "address": "EMILIO RECABARREN 231"
  }
}
```
####Respuesta
```json
{
  "details": {
    "href": "https://api.bsale.cl/v1/shippings/13526/details.json"
  },
  "recipient": "Andres Gallardo",
  "municipality": "Puerto Varas",
  "guide": {
    "id": "12642",
    "href": "https://api.bsale.cl/v1/documents/12642.json"
  },
  "office": {
    "id": "1",
    "href": "https://api.bsale.cl/v1/offices/1.json"
  },
  "id": 13526,
  "shipping_type": {
    "id": "6",
    "href": "https://api.bsale.cl/v1/shipping_types/6.json"
  },
  "href": "https://api.bsale.cl/v1/shippings/13526.json",
  "city": "Puerto Varas",
  "address": "la quebrada 1005",
  "shippingDate": 1409112000,
  "state": 0
}
```