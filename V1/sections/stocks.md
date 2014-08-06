Obtener colección de stocks
---------------------------

* `GET /v1/stocks.json` retornara todos los stocks.

####Parametros

- *limit*, limita la cantidad de items de una respuesta JSON, si no se envia el limit es 25.
- *offset*, permite paginar los items de una respuesta JSON, si no se envia el offset es 0.
- *fields*, solo devolver atributos especificos de un recurso
- *expand*, permite expandir instancias y colecciones.
- *officeid*, Permite filtrar por sucursal.
- *variantid*, filtra por porcentaje de variante.

####Ejemplos

* `GET /v1/stocks.json?limit=10&offset=0`
* `GET /v1/stocks.json?fields=[quantity]`
* `GET /v1/stocks.json?expand=[office,variant]`

####Respuesta
```json
{
  "href": "https://api.bsale.cl/v1/stocks.json",
  "count": 1049,
  "limit": 2,
  "offset": 0,
  "items": [
    {
      "href": "https://api.bsale.cl/v1/stocks/629.json",
      "id": 629,
      "quantity": 60.36,
      "variant": {
        "href": "https://api.bsale.cl/v1/variants/351.json",
        "id": "351"
      },
      "office": {
        "href": "https://api.bsale.cl/v1/offices/2.json",
        "id": "2"
      }
    },
    {
      "href": "https://api.bsale.cl/v1/stocks/630.json",
      "id": 630,
      "quantity": 0.0,
      "variant": {
        "href": "https://api.bsale.cl/v1/variants/351.json",
        "id": "351"
      },
      "office": {
        "href": "https://api.bsale.cl/v1/offices/1.json",
        "id": "1"
      }
    }
  ]
}
```
Obtener un stock
----------------

* `GET /v1/stocks/629.json` retornara un stock específico.

####Parametros

- *expand*, permite expandir instancias y colecciones.

####Ejemplos

* `GET /v1/stocks/629.json?expand=[variant,office]`

####Respuesta
```json
{
  "href": "https://api.bsale.cl/v1/stocks/629.json",
  "id": 629,
  "quantity": 60.36,
  "variant": {
    "href": "https://api.bsale.cl/v1/variants/351.json",
    "id": "351"
  },
  "office": {
    "href": "https://api.bsale.cl/v1/offices/2.json",
    "id": "2"
  }
}
```
Obtener recepciones de stock
----------------------------

* `GET /v1/stocks/receptions.json` retornara todos las recepciones.

####Parametros

- *limit*, limita la cantidad de items de una respuesta JSON, si no se envia el limit es 25.
- *offset*, permite paginar los items de una respuesta JSON, si no se envia el offset es 0.
- *fields*, solo devolver atributos especificos de un recurso
- *expand*, permite expandir instancias y colecciones.
- *admissiondate*, Permite fecha de la recepcion.
- *documentnumber*, filtra por el numero del documento de la recepcion.
- *officeid*, Permite filtrar por sucursal.

####Ejemplos

* `GET /v1/stocks/receptions.json?limit=10&offset=0`
* `GET /v1/stocks/receptions.json?fields=[admissiondate,document,documentnumber]`
* `GET /v1/stocks/receptions.json?expand=[office,details]`

####Respuesta
```json
{
  "href": "https://api.bsale.cl/v1/stocks/receptions.json",
  "count": 819,
  "limit": 3,
  "offset": 0,
  "items": [
    {
      "href": "https://api.bsale.cl/v1/stocks/receptions/12.json",
      "id": 12,
      "admissionDate": 1371182400,
      "document": "Guía",
      "documentNumber": 14524,
      "note": "Frival",
      "imagestionCctId": 0,
      "imagestionCcDescription": "",
      "internalDispatchId": 0,
      "office": {
        "href": "https://api.bsale.cl/v1/offices/1.json",
        "id": "1"
      },
      "details": {
        "href": "https://api.bsale.cl/v1/stocks/receptions/12/details.json"
      }
    },
    {
      "href": "https://api.bsale.cl/v1/stocks/receptions/13.json",
      "id": 13,
      "admissionDate": 1371182400,
      "document": "Factura",
      "documentNumber": 3560,
      "note": "Charcuteria",
      "imagestionCctId": 0,
      "imagestionCcDescription": "",
      "internalDispatchId": 0,
      "office": {
        "href": "https://api.bsale.cl/v1/offices/1.json",
        "id": "1"
      },
      "details": {
        "href": "https://api.bsale.cl/v1/stocks/receptions/13/details.json"
      }
    },
    {
      "href": "https://api.bsale.cl/v1/stocks/receptions/14.json",
      "id": 14,
      "admissionDate": 1371182400,
      "document": "Factura",
      "documentNumber": 2558,
      "note": "Ingreso Bodega Bsale / Jessica Vargas",
      "imagestionCctId": 0,
      "imagestionCcDescription": "",
      "internalDispatchId": 0,
      "office": {
        "href": "https://api.bsale.cl/v1/offices/1.json",
        "id": "1"
      },
      "details": {
        "href": "https://api.bsale.cl/v1/stocks/receptions/14/details.json"
      }
    }
  ]
}
```
Obtener una recepcion
---------------------

* `GET /v1/stocks/receptions/12.json` retorna una recepcion específica.

####Parametros

- *expand*, permite expandir instancias y colecciones.

####Ejemplos

* `GET /v1/stocks/receptions/12.json?expand=[office,details]`

####Respuesta
```json
{
  "href": "https://api.bsale.cl/v1/stocks/receptions/12.json",
  "id": 12,
  "admissionDate": 1371182400,
  "document": "Guía",
  "documentNumber": 14524,
  "note": "Frival",
  "imagestionCctId": 0,
  "imagestionCcDescription": "",
  "internalDispatchId": 0,
  "office": {
    "href": "https://api.bsale.cl/v1/offices/1.json",
    "id": "1"
  },
  "details": {
    "href": "https://api.bsale.cl/v1/stocks/receptions/12/details.json"
  }
}
```
Obtener detalles de una recepcion
---------------------------------

* `GET /v1/stocks/receptions/12/details.json`
```json
{
  "href": "https://api.bsale.cl/v1/stocks/receptions/12/details.json",
  "count": 13,
  "limit": 25,
  "offset": 0,
  "items": [
    {
      "href": "https://api.bsale.cl/v1/stocks/receptions/12/details/65.json",
      "id": 65,
      "quantity": 32.02,
      "cost": 3200.0,
      "variantStock": 85.55,
      "serialNumber": null,
      "variant": {
        "href": "https://api.bsale.cl/v1/variant/391.json",
        "id": "391"
      }
    },
    {
      "href": "https://api.bsale.cl/v1/stocks/receptions/12/details/66.json",
      "id": 66,
      "quantity": 32.22,
      "cost": 3200.0,
      "variantStock": 185.2,
      "serialNumber": null,
      "variant": {
        "href": "https://api.bsale.cl/v1/variant/388.json",
        "id": "388"
      }
    },
    {
      "href": "https://api.bsale.cl/v1/stocks/receptions/12/details/67.json",
      "id": 67,
      "quantity": 14.46,
      "cost": 3200.0,
      "variantStock": 107.84,
      "serialNumber": null,
      "variant": {
        "href": "https://api.bsale.cl/v1/variant/393.json",
        "id": "393"
      }
    }
  ]
}
```
Obtener un de detalle de una lista de precio
--------------------------------------------

* `GET /v1/stocks/receptions/12/details/65.json`
```json
{
  "href": "https://api.bsale.cl/v1/stocks/receptions/12/details/65.json",
  "id": 65,
  "quantity": 32.02,
  "cost": 3200.0,
  "variantStock": 85.55,
  "serialNumber": null,
  "variant": {
    "href": "https://api.bsale.cl/v1/variant/391.json",
    "id": "391"
  }
}
```